# 🛠️ Developer Guides for Vaulta (previously EOS)

> **⚠️ Important Note for Developers**  
> Vaulta is evolving toward regulated Web3 banking and institutional use cases with the $A token focus. Development practices must emphasize security, compliance, and modern tooling. This guide focuses on safe, future-proof development.

Welcome to the Developer Guides for Vaulta (evolving from EOS). This section helps developers build responsibly within a more institutional and regulated Antelope environment.

## Introduction

Vaulta represents the evolution of the original EOS blockchain toward secure, compliant, and institutional-grade Web3 infrastructure. With its focus on regulated finance, custody, and the new $A token, development on Vaulta requires attention to security, compliance considerations, and modern Antelope tooling.

Understanding Vaulta development is valuable for grasping the broader evolution of the Antelope ecosystem and preparing for future cross-chain features in PxPortals and PxPackages.

## Best Practices for Vaulta Development

### 1. Use Modern Libraries — Wharf Kit Strongly Recommended

**Wharf Kit** is the current recommended standard for interacting with Vaulta and other Antelope chains.

- It is actively maintained, secure, and designed for modern dApp development.
- It provides excellent session management and multi-wallet support.
- It works consistently across WAX, XPR, Vaulta, and emerging Antelope chains.

**Deprecated / Avoid for New Projects**:
- **eosjs** — Long deprecated. Do not use for new development.
- **AnchorLink** — Deprecated in favor of modern alternatives.

**Recommendation**: Always start new Vaulta projects with **Wharf Kit**.

### 2. Wallet Integration

- Prefer **Anchor** wallet integration via Wharf Kit.
- Strongly consider hardware wallet support (Ledger) for applications handling significant value or institutional use cases.
- Use session-based authentication for better security and user experience.

### 3. Smart Contract Development

- Use the latest Antelope development tools and CDT versions.
- Emphasize security, proper authorization, and compliance-friendly design patterns.
- Test thoroughly on testnets before mainnet deployment.
- Consider audits for contracts handling significant value or institutional features.

### 4. Security Best Practices

- Never hardcode private keys.
- Validate all inputs and contract interactions rigorously.
- Implement proper error handling and user feedback.
- Keep all dependencies up to date.
- Be extremely cautious with permissions, approvals, and resource management.
- Pay special attention to compliance and regulatory considerations in design.

### 5. Pixel Journey Integration

- When building tools that may interact with Pixel Journey users or assets, follow modern standards for consistency and security.
- Consider how your dApp can integrate with PxWallet or future PxPortals for cross-chain experiences involving Vaulta.
- Align with Vaulta's focus on security and compliance where relevant.

### 6. General Development Recommendations

- Use TypeScript for better type safety and developer experience.
- Write clean, well-documented, and testable code.
- Follow official Vaulta and Antelope documentation for the latest updates.
- Stay active in trusted developer communities.
- Be mindful of the evolving regulatory landscape around Vaulta.

## Wharf Kit Integration Patterns

**Wharf Kit** is the modern standard for building dApps on Vaulta. The patterns below emphasize security, compliance-friendly design, and institutional-grade reliability.

### Installation

```bash
npm install @wharfkit/core @wharfkit/session @wharfkit/wallet-plugin-anchor
```

For React/Next.js:
```bash
npm install @wharfkit/react
```

### 1. Basic Wallet Connection Pattern

```ts
import { Session } from '@wharfkit/session'
import { WalletPluginAnchor } from '@wharfkit/wallet-plugin-anchor'

const session = new Session({
  chain: {
    id: 'VAULTA_CHAIN_ID_HERE',
    url: 'https://vaulta.greymass.com'
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

### 3. Signing Transactions with Security Focus

```ts
const action = {
  account: 'yourcontract',
  name: 'transfer',
  authorization: [session.permissionLevel],
  data: {
    from: session.actor,
    to: 'receiver',
    quantity: '1.0000 A',
    memo: 'Pixel Journey transfer'
  }
}

const result = await session.transact({ actions: [action] })
console.log('Transaction ID:', result.transaction_id)
```

### 4. Multi-Chain Support (Vaulta + WAX + XPR)

```ts
const chains = {
  vaulta: { id: '...', url: 'https://vaulta.greymass.com' },
  wax: { id: '...', url: 'https://wax.greymass.com' },
  xpr: { id: '...', url: 'https://xpr.greymass.com' }
}

session = new Session({
  chain: chains.vaulta,
  walletPlugin: new WalletPluginAnchor()
})
```

Ideal for future **PxPortals** cross-chain experiences involving regulated environments.

### 5. Error Handling & User Feedback

```ts
try {
  const result = await session.transact({ actions: [...] })
} catch (error) {
  if (error.message.includes('user_cancelled')) {
    console.log('User cancelled the transaction')
  } else {
    console.error('Transaction failed:', error)
  }
}
```

### 6. React Integration

```tsx
import { useSession } from '@wharfkit/react'

function VaultaDapp() {
  const { session, login, logout } = useSession()

  return (
    <div>
      {session ? (
        <p>Connected on Vaulta: {session.actor}</p>
      ) : (
        <button onClick={login}>Connect with Anchor</button>
      )}
    </div>
  )
}
```

### Best Practices for Vaulta dApps

- Emphasize security and compliance in all transaction flows.
- Use persistent sessions for reliable UX.
- Strongly support hardware wallets (Ledger) for higher-value or institutional interactions.
- Design with regulatory considerations in mind.
- Handle errors gracefully and provide clear user feedback.
- Use TypeScript for type safety and maintainability.

### Security Considerations

- Never store private keys in the frontend.
- Rigorously validate all inputs and contract interactions.
- Be extremely cautious with permissions and approvals.
- Keep Wharf Kit and all dependencies updated.
- Consider additional auditing for contracts handling significant value.

## Getting Started as a Developer on Vaulta

1. Set up your development environment with the latest tools.
2. Install and explore **Wharf Kit** for wallet and chain interactions.
3. Build a simple test dApp or script focused on Vaulta's strengths (security, compliance).
4. Test thoroughly on Vaulta testnet.
5. Review how Vaulta fits into the broader Antelope ecosystem and Pixel Journey's multi-chain vision.

## Pixel Journey Relevance

Vaulta provides important lessons in secure, institutional-grade blockchain development. As we expand PxPackages and PxPortals, understanding Vaulta helps us design safer, more robust cross-chain experiences that may one day include regulated environments.

*Educational content only. Development involves real risks and responsibilities. Always DYOR and follow security best practices. Not financial advice.*