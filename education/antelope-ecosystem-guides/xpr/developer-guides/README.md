# 🛠️ Developer Guides for XPR Network

> **⚠️ Important Note for Developers**  
> The XPR Network ecosystem continues to evolve with a focus on payments, identity, and efficient DeFi. Always use modern, actively maintained tools and follow current best practices. This guide focuses on safe, future-proof development.

Welcome to the Developer Guides for XPR Network. This section helps developers build safely and efficiently, with awareness of how XPR complements the broader Pixel Journey multi-chain vision.

## Introduction

XPR Network offers fast, low-cost (often feeless) experiences, making it attractive for payments, identity solutions, and DeFi experimentation. While smaller than WAX in terms of gaming/NFT activity, it provides valuable learning opportunities and efficient tooling within the Antelope family.

Pixel Journey tools are designed with cross-chain compatibility in mind, and understanding XPR development helps prepare for future PxPortals and PxPackages expansions.

## Best Practices for XPR Development

### 1. Use Modern Libraries — Wharf Kit Recommended

**Wharf Kit** remains the strongly recommended standard for interacting with XPR and other Antelope chains.

- It is actively maintained and secure.
- It provides excellent session management and multi-wallet support.
- It works well across WAX, XPR, Vaulta, and other Antelope chains.

**Deprecated / Avoid for New Projects**:
- **eosjs** — Long deprecated. Do not use for new development.
- **AnchorLink** — Deprecated in favor of modern alternatives.

**Recommendation**: Use **Wharf Kit** for all new XPR development.

### 2. Wallet Integration

- Prefer **Anchor** wallet via Wharf Kit for the best user experience.
- Support hardware wallets where possible for higher-value applications.
- Leverage session-based authentication for improved security and UX.

### 3. Smart Contract Development

- Use the latest Antelope development tools and CDT versions.
- Follow secure coding practices and test thoroughly on testnets.
- Be mindful of XPR's focus on payments and identity when designing contracts.

### 4. Security Best Practices

- Never hardcode private keys.
- Validate all inputs and contract interactions.
- Implement proper error handling.
- Keep dependencies up to date.
- Be cautious with permissions and approvals.

### 5. Pixel Journey Integration

- When building tools that may interact with Pixel Journey assets or users, follow modern standards for consistency.
- Consider how your dApp can integrate with PxWallet or future PxPortals for cross-chain experiences.
- Use efficient, low-cost mechanics that align with XPR's strengths.

### 6. General Development Recommendations

- Use TypeScript for better developer experience and type safety.
- Write clean, well-documented, and testable code.
- Follow official XPR and Antelope documentation.
- Stay active in trusted developer communities.

## Wharf Kit Integration Patterns

**Wharf Kit** is the modern standard for building dApps on XPR and other Antelope chains. The patterns below are adapted for XPR's fast, low-cost, and payments/identity-focused environment.

### Installation

```bash
npm install @wharfkit/core @wharfkit/session @wharfkit/wallet-plugin-anchor
```

For React/Next.js projects:
```bash
npm install @wharfkit/react
```

### 1. Basic Wallet Connection Pattern

```ts
import { Session } from '@wharfkit/session'
import { WalletPluginAnchor } from '@wharfkit/wallet-plugin-anchor'

const session = new Session({
  chain: {
    id: 'XPR_CHAIN_ID_HERE', // Replace with actual XPR chain ID
    url: 'https://xpr.greymass.com'
  },
  walletPlugin: new WalletPluginAnchor()
})

const result = await session.login()
console.log('Connected account:', result.session.actor)
```

### 2. Persistent Session Management (Recommended)

```ts
import { Session } from '@wharfkit/session'

let session = Session.restore()

if (!session) {
  session = new Session({
    chain: { id: '...', url: '...' },
    walletPlugin: new WalletPluginAnchor()
  })
  await session.login()
  session.store()
}
```

### 3. Signing Efficient Transactions on XPR

XPR's low-cost nature makes it excellent for frequent small transactions:

```ts
const action = {
  account: 'yourcontract',
  name: 'transfer',
  authorization: [session.permissionLevel],
  data: {
    from: session.actor,
    to: 'receiver',
    quantity: '1.0000 XPR',
    memo: 'Pixel Journey payment'
  }
}

const result = await session.transact({ actions: [action] })
console.log('Transaction ID:', result.transaction_id)
```

### 4. Multi-Chain Support (XPR + WAX + Vaulta)

```ts
const chains = {
  xpr: { id: '...', url: 'https://xpr.greymass.com' },
  wax: { id: '...', url: 'https://wax.greymass.com' },
  vaulta: { id: '...', url: 'https://vaulta.greymass.com' }
}

session = new Session({
  chain: chains.xpr,
  walletPlugin: new WalletPluginAnchor()
})
```

This pattern is ideal for future **PxPortals** cross-chain experiences.

### 5. Error Handling & User Feedback

```ts
try {
  const result = await session.transact({ actions: [...] })
} catch (error) {
  if (error.message.includes('user_cancelled')) {
    console.log('User cancelled')
  } else {
    console.error('Transaction failed:', error)
  }
}
```

### 6. React Integration

```tsx
import { useSession } from '@wharfkit/react'

function XPRDapp() {
  const { session, login, logout } = useSession()

  return (
    <div>
      {session ? (
        <p>Connected on XPR: {session.actor}</p>
      ) : (
        <button onClick={login}>Connect with Anchor</button>
      )}
    </div>
  )
}
```

### Best Practices for XPR dApps

- Take advantage of XPR's low-cost / feeless nature for frequent small actions.
- Use persistent sessions for smooth UX.
- Design for payments and identity use cases.
- Handle user cancellation gracefully.
- Use TypeScript for type safety.
- Support hardware wallets via Anchor for higher-value interactions.

### Security Considerations

- Never store private keys in the frontend.
- Validate all inputs and contract interactions.
- Be cautious with permissions and approvals.
- Keep Wharf Kit and dependencies updated.

## Advanced Patterns for Pixel Journey Integration

These advanced patterns are especially useful when building tools that integrate with Pixel Journey assets and features, leveraging XPR's efficient, low-cost nature.

### Efficient Payments & Identity Integration

XPR excels at fast, low-cost (often feeless) payments and identity use cases:

```ts
// Example: Efficient XPR payment
const paymentAction = {
  account: 'yourcontract',
  name: 'transfer',
  authorization: [session.permissionLevel],
  data: {
    from: session.actor,
    to: receiver,
    quantity: '1.0000 XPR',
    memo: 'Pixel Journey payment via PxWallet'
  }
}

const result = await session.transact({ actions: [paymentAction] })
```

**Tips**:
- Leverage XPR's low-cost nature for frequent small transactions and micro-payments.
- Use memo fields for tracking Pixel Journey-related activity.
- Combine with identity features for user verification flows.

### Multi-Chain Resource & Efficiency Patterns

```ts
// Check account resources on XPR
const accountInfo = await session.client.v1.chain.get_account(session.actor)
console.log('Resources available for efficient operations')
```

**Best Practice**: Use XPR for high-frequency, low-value operations and testing, while keeping primary holdings and focus on WAX.

### PxWallet & Future PxPortals Integration Patterns

When building for PxWallet or future PxPortals:
- Use persistent sessions for seamless multi-chain experiences.
- Abstract chain-specific logic behind a unified interface.
- Leverage XPR's efficiency for quick operations and testing.
- Plan for cross-chain asset movement and unified UX across WAX (primary) and XPR.

### Batch Transactions & Efficiency

```ts
// Example: Multiple actions in one transaction
const actions = [paymentAction, identityAction, defiAction]
const result = await session.transact({ actions })
```

Batch transactions improve UX and take advantage of XPR's efficiency.

## Getting Started as a Developer on XPR

1. Set up your environment with the latest tools.
2. Install and explore **Wharf Kit** for wallet and chain interactions.
3. Build a simple test dApp or script focused on XPR's efficient mechanics.
4. Test thoroughly on XPR testnet.
5. Review how XPR can complement WAX-based Pixel Journey activities.

## Pixel Journey Relevance

XPR provides valuable lessons in efficient, low-cost chain design. As we expand PxPackages and PxPortals, understanding XPR development helps create better cross-chain experiences for users who want to move seamlessly between WAX (primary focus) and complementary chains like XPR.

*Educational content only. Development involves real risks and responsibilities. Always DYOR and follow security best practices. Not financial advice.*