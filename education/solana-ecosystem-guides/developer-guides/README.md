# 🛠️ Developer Guides for Solana

> **Hands-on Companion: PxDev Examples Vault**  
> These guides provide Solana-specific theory and best practices. For runnable, production-grade code examples and patterns (many of which translate across chains — Next.js stacks, state management, i18n, PWA resilience, secure architectures, and our engineering standards), explore the **[PxDev Examples Vault](https://docs.pixeljourney.xyz/pxlabs/px-dev-examples/)** in PxLabs. It currently emphasizes WAX/Antelope production patterns from PxWallet, PxHot, PxMarket, and Px Packages, with future quests planned for multi-chain and Solana-aligned examples. Most repos are in private preview — request access on GitHub or via Discord.

> **⚠️ Important Note for Developers**  
> Solana's ecosystem moves fast. Always use modern, actively maintained libraries and follow current best practices. This guide focuses on safe, performant, and future-proof development.

Welcome to the Developer Guides for Solana. This section helps developers build safely and efficiently on Solana, with awareness of how it fits into Pixel Journey's broader multi-chain vision.

## Introduction

Solana is known for high throughput, low fees, and a rapidly growing ecosystem of dApps, NFTs, and DeFi. It offers a different development experience compared to Antelope chains, with its own set of tools, patterns, and considerations.

As Pixel Journey expands through PxPortals and PxPackages, understanding modern Solana development helps us design better cross-chain experiences and prepare for potential future integration with Solana-based assets or users.

## Best Practices for Solana Development

### 1. Use Modern Libraries and Frameworks

**Recommended Stack (2026)**:
- **Anchor** — The most popular and powerful framework for Solana smart contract development.
- **@solana/web3.js** — Core JavaScript/TypeScript library for interacting with the Solana blockchain.
- **@solana/wallet-adapter** — Standard for wallet connections (Phantom, Solflare, etc.).
- **viem** or **@solana/kit** — For more modern, type-safe interactions.

**Avoid for New Projects**:
- Outdated or unmaintained Solana libraries from early ecosystem days.
- Custom low-level implementations when established frameworks exist.

**Recommendation**: Start new Solana projects with **Anchor** (for programs) + **@solana/wallet-adapter** + **@solana/web3.js** (for frontend).

### 2. Wallet Integration

- Use **@solana/wallet-adapter** for the best user experience with popular wallets (Phantom, Solflare, Backpack, etc.).
- Support multiple wallets where possible.
- Consider hardware wallet support for higher-value applications.
- Use session-based or persistent connection patterns for better UX.

### 3. Smart Contract (Program) Development

- Use **Anchor** framework for most new programs — it provides excellent developer experience, type safety, and security features.
- Follow secure coding practices (proper account validation, signer checks, PDA derivation, etc.).
- Test thoroughly on devnet and testnet before mainnet deployment.
- Consider audits for contracts handling significant value.

### 4. Security Best Practices


- Never hardcode private keys.
- Validate all user input and account ownership rigorously.
- Be extremely careful with PDA (Program Derived Address) derivation and seeds.
- Implement proper error handling and user feedback.
- Keep dependencies up to date.
- Be cautious with permissions and approvals in your dApp.

### 5. Pixel Journey Integration

- When building tools that may interact with Pixel Journey users or assets, follow modern Solana standards for consistency.
- Consider how your dApp can integrate with PxWallet or future PxPortals for cross-chain experiences.
- Leverage Solana's speed and low cost where it makes sense in a multi-chain strategy.

### 6. General Development Recommendations

- Use TypeScript for better type safety and developer experience.
- Write clean, well-documented, and testable code.
- Follow official Solana documentation and Anchor guides.
- Stay active in trusted Solana developer communities.
- Monitor for breaking changes — the ecosystem evolves quickly.

## Solana Integration Patterns

### Installation (Frontend)

```bash
npm install @solana/web3.js @solana/wallet-adapter-base @solana/wallet-adapter-react @solana/wallet-adapter-wallets
```

For Anchor programs:
```bash
npm install -g @coral-xyz/anchor-cli
```

### 1. Basic Wallet Connection with Wallet Adapter

```tsx
import { useWallet } from '@solana/wallet-adapter-react'
import { WalletMultiButton } from '@solana/wallet-adapter-react-ui'

function SolanaDapp() {
  const { publicKey, connect, disconnect } = useWallet()

  return (
    <div>
      <WalletMultiButton />
      {publicKey && <p>Connected: {publicKey.toBase58()}</p>
    </div>
  )
}
```

### 2. Sending Transactions

```ts
import { Connection, Transaction, SystemProgram, PublicKey } from '@solana/web3.js'

const connection = new Connection('https://api.mainnet-beta.solana.com')

const transaction = new Transaction().add(
  SystemProgram.transfer({
    fromPubkey: senderPublicKey,
    toPubkey: receiverPublicKey,
    lamports: 1_000_000_000, // 1 SOL
  })
)

const signature = await sendTransaction(transaction, connection)
console.log('Transaction signature:', signature)
```

### 3. Using Anchor for Program Interaction

```ts
import { Program, AnchorProvider, web3 } from '@coral-xyz/anchor'

// Initialize provider and program
const provider = new AnchorProvider(connection, wallet, {})
const program = new Program(IDL, programId, provider)

// Call a program method
const tx = await program.methods
  .yourMethod(...args)
  .accounts({ ... })
  .rpc()

console.log('Transaction signature:', tx)
```

### 4. Multi-Chain Considerations (Solana + Antelope)

While direct bridging between Solana and Antelope chains requires careful implementation, you can design dApps that support both ecosystems:

- Use consistent UX patterns across chains.
- Abstract wallet connection logic where possible.
- Plan for future cross-chain features via PxPortals.

### 5. Error Handling

```ts
try {
  const signature = await sendTransaction(transaction, connection)
} catch (error) {
  if (error.message.includes('User rejected')) {
    console.log('User cancelled the transaction')
  } else {
    console.error('Transaction failed:', error)
  }
}
```

### Best Practices for Production dApps

- Use persistent wallet connections where appropriate.
- Handle user rejection/cancellation gracefully.
- Show clear loading states during transactions.
- Validate all data before sending transactions.
- Use TypeScript for type safety.
- Support multiple popular wallets.
- Test thoroughly on devnet before mainnet.

### Security Considerations

- Never store private keys in the frontend.
- Rigorously validate account ownership and PDAs.
- Be extremely cautious with transaction construction.
- Keep all dependencies updated.
- Consider rate limiting and abuse prevention for public dApps.

## Getting Started as a Developer on Solana

1. Set up your development environment (Node.js, Anchor CLI, etc.).
2. Explore **@solana/wallet-adapter** for wallet connections.
3. Build a simple test dApp or Anchor program.
4. Test thoroughly on Solana devnet.
5. Review how Solana can complement WAX-based Pixel Journey activities in a multi-chain strategy — and explore the **[PxDev Examples Vault](https://docs.pixeljourney.xyz/pxlabs/px-dev-examples/)** for shared patterns that apply across ecosystems.

## Pixel Journey Relevance

Solana offers high performance and a vibrant ecosystem. As we expand PxPackages and PxPortals, understanding modern Solana development helps us design better cross-chain experiences and prepare for potential future integration with Solana users or assets.

We welcome developers building on Solana who want to align with Pixel Journey's vision of safe, user-friendly, and multi-chain experiences.

*Educational content only. Development involves real risks and responsibilities. Always DYOR and follow security best practices. Not financial advice.*