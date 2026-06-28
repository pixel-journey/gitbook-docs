# 🛠️ Developer Guides for WAX (Antelope)

> **⚠️ Important Note for Developers**  
> The WAX/Antelope ecosystem has evolved significantly. Many older libraries and tools are now deprecated. Always use modern, actively maintained tools and follow current best practices. This guide focuses on safe, future-proof development.

Welcome to the Developer Guides for WAX and the broader Antelope ecosystem. This section is designed to help developers build safely, efficiently, and in alignment with Pixel Journey's multi-chain vision.

## Introduction

WAX remains one of the most developer-friendly Antelope chains, especially for gaming, NFTs, and creator economies. However, the ecosystem has matured, and modern development practices are essential for security, performance, and maintainability.

Pixel Journey's own tools (PxWallet, PxPackages, PxPortals, etc.) are built with modern standards in mind, and we strongly encourage developers to follow similar approaches when building on WAX or integrating with our ecosystem.

## Best Practices for WAX / Antelope Development

### 1. Use Modern Libraries — Wharf Kit is Strongly Recommended

**Wharf Kit** is the current recommended standard for interacting with WAX and Antelope chains.

- It is actively maintained, secure, and designed for modern dApp development.
- It replaces older, deprecated libraries.
- It offers excellent support for session management, signing, and multi-wallet experiences.

**Deprecated / Avoid for New Projects**:
- **eosjs** — Long deprecated. Do not use for new development.
- **AnchorLink** — Deprecated in favor of modern alternatives.
- Any unmaintained or legacy EOSIO-era libraries.

**Recommendation**: Start every new WAX/Antelope project with **Wharf Kit**.

### 2. Wallet Integration

- Prefer **Anchor** wallet integration via Wharf Kit for the best user experience on WAX.
- Support hardware wallets (Ledger) where possible for higher-value applications.
- Use session-based authentication for better security and UX.

### 3. Smart Contract Development

- Use the latest versions of CDT (Contract Development Toolkit) or modern alternatives.
- Follow secure coding practices (checks-effects-interactions, proper authorization, resource management).
- Test thoroughly on testnets before mainnet deployment.
- Consider using established frameworks and audit your contracts when handling significant value.

### 4. Security Best Practices

- Never hardcode private keys.
- Validate all user input and contract interactions.
- Implement proper error handling and user feedback.
- Regularly audit dependencies and keep libraries up to date.
- Be extremely cautious with permissions and approvals in your dApp.

### 5. Pixel Journey Integration

- When building tools that interact with Pixel Journey assets (Pixals, ingredients, PxHot, etc.), use official or well-documented APIs and standards.
- Consider how your dApp can integrate with PxWallet, PxMarket, or future PxPortals for seamless cross-chain experiences.
- Follow Pixel Journey's design principles for consistency when creating user-facing interfaces.

### 6. General Development Recommendations

- Write clean, well-documented, and testable code.
- Use TypeScript for better type safety and developer experience.
- Follow the official WAX and Antelope documentation for the latest updates.
- Stay active in trusted developer communities and follow official channels for announcements.

## Wharf Kit Integration Patterns

**Wharf Kit** is the modern standard for building dApps on WAX and other Antelope chains. Below are the most common and recommended integration patterns used in production-grade applications.

### Installation

```bash
npm install @wharfkit/core @wharfkit/session @wharfkit/wallet-plugin-anchor
```

For React/Next.js projects, also consider:
```bash
npm install @wharfkit/react
```

### 1. Basic Wallet Connection Pattern

```ts
import { Session } from '@wharfkit/session'
import { WalletPluginAnchor } from '@wharfkit/wallet-plugin-anchor'

const session = new Session({
  chain: {
    id: '1064487b3cd1a897ce03ae5b6a865651747e2e152090f99c1d19d44e01aea5a4', // WAX Mainnet
    url: 'https://wax.greymass.com'
  },
  walletPlugin: new WalletPluginAnchor()
})

// Connect to Anchor wallet
const result = await session.login()
console.log('Connected account:', result.session.actor)
```

### 2. Persistent Session Management (Recommended)

Store the session so users don't have to reconnect every time:

```ts
import { Session } from '@wharfkit/session'

// Restore previous session if available
let session = Session.restore()

if (!session) {
  session = new Session({
    chain: { id: '...', url: '...' },
    walletPlugin: new WalletPluginAnchor()
  })
  await session.login()
  session.store() // Persist for future visits
}
```

### 3. Signing Transactions / Actions

```ts
const action = {
  account: 'atomicassets',
  name: 'transfer',
  authorization: [session.permissionLevel],
  data: {
    from: session.actor,
    to: 'receiver',
    asset_ids: [12345],
    memo: 'Pixel Journey transfer'
  }
}

const result = await session.transact({ actions: [action] })
console.log('Transaction ID:', result.transaction_id)
```

### 4. Multi-Chain Support (WAX + XPR + Vaulta)

Wharf Kit makes it easy to support multiple Antelope chains:

```ts
const chains = {
  wax: { id: '...', url: 'https://wax.greymass.com' },
  xpr: { id: '...', url: 'https://xpr.greymass.com' },
  vaulta: { id: '...', url: 'https://vaulta.greymass.com' }
}

// Switch chain dynamically
session = new Session({
  chain: chains.wax,
  walletPlugin: new WalletPluginAnchor()
})
```

This pattern is especially powerful for future **PxPortals** cross-chain experiences.

### 5. Error Handling & User Feedback

```ts
try {
  const result = await session.transact({ actions: [...] })
} catch (error) {
  if (error.message.includes('user_cancelled')) {
    console.log('User cancelled the transaction')
  } else {
    console.error('Transaction failed:', error)
    // Show user-friendly error message
  }
}
```

### 6. React / Modern Framework Integration

Use the official `@wharfkit/react` package for clean hooks:

```tsx
import { useSession } from '@wharfkit/react'

function PixelJourneyDapp() {
  const { session, login, logout } = useSession()

  return (
    <div>
      {session ? (
        <>
          <p>Connected: {session.actor}</p>
          <button onClick={logout}>Disconnect</button>
        </>
      ) : (
        <button onClick={login}>Connect with Anchor</button>
      )}
    </div>
  )
}
```

### Best Practices for Production dApps

- Always use **persistent sessions** for better UX.
- Handle **user cancellation** gracefully.
- Show clear loading states during transactions.
- Validate all data before sending transactions.
- Use TypeScript for type safety on actions and responses.
- Support hardware wallets (Ledger) via Anchor for high-value interactions.
- Log errors properly but never expose sensitive information.
- Test thoroughly on testnet before mainnet.

### Security Considerations

- Never store private keys in your frontend.
- Always validate user input on both client and server (when applicable).
- Be extremely careful with permissions and approvals in your dApp.
- Regularly update Wharf Kit and dependencies.
- Consider rate limiting and abuse prevention for public dApps.

## Advanced Patterns for Pixel Journey Integration

These advanced patterns are especially useful when building tools that integrate deeply with Pixel Journey assets and features.

### Atomic Assets Integration (Pixals, Ingredients, Collectibles)

```ts
// Example: Transferring a Pixel Journey NFT (Atomic Asset)
const transferAction = {
  account: 'atomicassets',
  name: 'transfer',
  authorization: [session.permissionLevel],
  data: {
    from: session.actor,
    to: receiver,
    asset_ids: [pixelAssetId],
    memo: 'Pixel Journey transfer via PxMarket'
  }
}

const result = await session.transact({ actions: [transferAction] })
```

**Tips**:
- Always validate asset ownership before transfers.
- Use memo fields for tracking Pixel Journey-related activity.
- Combine with PxMarket for seamless marketplace experiences.

### Resource Management (CPU/NET/RAM)

WAX requires careful resource management for smooth UX:

```ts
// Check account resources
const accountInfo = await session.client.v1.chain.get_account(session.actor)
console.log('CPU:', accountInfo.cpu_limit)
console.log('NET:', accountInfo.net_limit)
console.log('RAM:', accountInfo.ram_quota)
```

**Best Practice**: For high-volume dApps, implement resource rental or subsidization patterns, or guide users to stake resources via Anchor.

### PxWallet & Future PxPortals Integration Patterns

When building for PxWallet or future PxPortals:
- Use persistent sessions for seamless multi-chain experiences.
- Abstract chain-specific logic behind a unified interface.
- Support hardware wallets for high-value Pixel Journey assets.
- Plan for cross-chain asset movement and unified UX.

### Batch Transactions & Efficiency

```ts
// Example: Multiple actions in one transaction
const actions = [transferAction, stakingAction, craftingAction]
const result = await session.transact({ actions })
```

Batch transactions improve UX and reduce fees where applicable.

## Getting Started as a Developer on WAX

1. Set up your development environment with the latest tools.
2. Install and explore **Wharf Kit** for wallet and chain interactions.
3. Build a simple test dApp or script to familiarize yourself with modern patterns.
4. Review Pixel Journey's own open-source patterns where available for inspiration.
5. Test thoroughly on WAX testnet before moving to mainnet.

## Pixel Journey Relevance

As we expand PxPackages, PxPortals, and our multi-chain ecosystem, having strong, modern developer tooling on WAX is foundational. By following these best practices and Wharf Kit integration patterns, you help create a safer, more consistent experience for users across the Pixel Journey ecosystem.

We especially encourage developers building tools that integrate with **PxWallet**, **PxMarket**, or future cross-chain features to follow these modern patterns.

*Educational content only. Development involves real risks and responsibilities. Always DYOR and follow security best practices. Not financial advice.*