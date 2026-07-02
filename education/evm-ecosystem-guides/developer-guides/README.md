# 🛠️ Developer Guides for EVM Chains

> **Hands-on Companion: PxDev Examples Vault**  
> These guides cover EVM-specific best practices (viem + wagmi, Foundry, account abstraction, multi-chain patterns). Many core lessons from the **[PxDev Examples Vault](https://docs.pixeljourney.xyz/pxlabs/px-dev-examples/)** — especially modern frontend stacks, state management, secure wallet/key architectures, cross-chain derivation examples, i18n/PWA resilience, and our engineering/educational standards — apply directly across EVM, Solana, and Antelope. Future quests will expand with more chain-specific EVM examples. Most repos are in private preview — request access on GitHub or via Discord.

> **⚠️ Important Note for Developers**  
> The EVM ecosystem evolves quickly. Always use modern, actively maintained libraries and follow current best practices. This guide focuses on safe, performant, and future-proof development across Base, Polygon, Ethereum, BNB Chain, and other EVM networks.

Welcome to the Developer Guides for EVM Chains. This section helps developers build safely and efficiently on EVM-compatible blockchains, with awareness of how they fit into Pixel Journey's broader multi-chain vision.

## Introduction

EVM chains (Ethereum, Base, Polygon, BNB Chain, Arbitrum, Optimism, and many others) form a large and diverse ecosystem. They share a common smart contract language (Solidity) and tooling, but each chain has its own characteristics in terms of fees, speed, security models, and ecosystem focus.

As Pixel Journey expands through PxPortals and PxPackages, understanding modern EVM development is essential for building cross-chain experiences and preparing for potential future integration with EVM-based assets or users.

## Best Practices for EVM Development (2026)

### 1. Use Modern Libraries and Frameworks

**Recommended Primary Stack**:
- **viem** — Modern, lightweight, and type-safe library for interacting with EVM chains. Strongly recommended as the foundation.
- **wagmi** — Excellent React hooks built on top of viem for wallet connections and contract interactions.
- **ethers.js v6** — Still widely used and solid, but viem + wagmi is generally preferred for new projects due to better performance and type safety.
- **Foundry** or **Hardhat** — For smart contract development and testing (Foundry is often preferred for speed and Solidity-native experience).

**Recommendation**: Start new EVM projects with **viem + wagmi** (frontend) + **Foundry** (smart contracts) for the best modern developer experience.

### 2. Wallet Integration

- Use **wagmi** + **@rainbow-me/rainbowkit** or similar for the best multi-wallet UX (MetaMask, WalletConnect, Coinbase Wallet, etc.).
- Support multiple wallets and chains where possible.
- Consider hardware wallet support (Ledger, Trezor) for higher-value applications.
- Use account abstraction (ERC-4337) patterns where it improves UX.

### 3. Smart Contract Development

- Use **Foundry** for most new projects (fast compilation, excellent testing, Solidity-native).
- Follow secure coding practices (checks-effects-interactions, proper access control, reentrancy protection, etc.).
- Test thoroughly on testnets before mainnet deployment.
- Consider formal verification or audits for contracts handling significant value.
- Be mindful of gas optimization, especially on higher-fee chains like Ethereum mainnet.

### 4. Security Best Practices

- Never hardcode private keys.
- Rigorously validate all user input, signatures, and contract interactions.
- Be extremely careful with approvals and permissions (use limited approvals when possible).
- Implement proper error handling and user feedback.
- Keep all dependencies up to date.
- Pay special attention to common EVM vulnerabilities (reentrancy, integer overflow/underflow, access control issues).

### 5. Pixel Journey Integration

- When building tools that may interact with Pixel Journey users or assets, follow modern EVM standards for consistency and security.
- Consider how your dApp can integrate with PxWallet or future PxPortals for cross-chain experiences.
- Leverage EVM's mature tooling and large ecosystem where it makes sense in a multi-chain strategy.

### 6. General Development Recommendations

- Use TypeScript for better type safety and developer experience.
- Write clean, well-documented, and testable code.
- Follow official documentation for each chain (Ethereum, Base, Polygon, etc.).
- Stay active in trusted EVM developer communities.
- Be aware of chain-specific differences (gas fees, finality, security models).

## EVM Integration Patterns

### Installation (Frontend)

```bash
npm install viem wagmi @rainbow-me/rainbowkit
```

For smart contracts:
```bash
# Using Foundry
curl -L https://foundry.paradigm.xyz | bash
foundryup
```

### 1. Basic Wallet Connection with wagmi + RainbowKit

```tsx
import { useAccount, useConnect, useDisconnect } from 'wagmi'
import { RainbowKitProvider, ConnectButton } from '@rainbow-me/rainbowkit'

function EVM Dapp() {
  const { address, isConnected } = useAccount()
  const { disconnect } = useDisconnect()

  return (
    <div>
      <ConnectButton />
      {isConnected && (
        <>
          <p>Connected: {address}</p>
          <button onClick={() => disconnect()}>Disconnect</button>
        </div>
      )}
    </div>
  )
}
```

### 2. Reading and Writing to Contracts with viem

```ts
import { createPublicClient, http, parseEther } from 'viem'
import { mainnet } from 'viem/chains'

const client = createPublicClient({
  chain: mainnet,
  transport: http()
})

// Read
const balance = await client.getBalance({ address: '0x...' })

// Write (with wallet)
const hash = await walletClient.sendTransaction({
  to: '0x...',
  value: parseEther('0.01')
})
```

### 3. Using wagmi Hooks for Contract Interaction

```tsx
import { useContractRead, useContractWrite } from 'wagmi'

function MyComponent() {
  const { data } = useContractRead({
    address: contractAddress,
    abi: contractABI,
    functionName: 'balanceOf',
    args: [address],
  })

  const { write } = useContractWrite({
    address: contractAddress,
    abi: contractABI,
    functionName: 'transfer',
  })

  return <button onClick={() => write({ args: [...] })}>Transfer</button>
}
```

### 4. Multi-Chain Support (EVM + Antelope + Solana)

Modern tooling makes it easier to support multiple EVM chains and plan for cross-chain:

```ts
// viem supports many chains out of the box
import { base, polygon, mainnet, bsc } from 'viem/chains'

// Switch chains dynamically with wagmi
```

This pattern aligns well with future **PxPortals** cross-chain vision.

### 5. Error Handling

```ts
try {
  const hash = await sendTransaction(...)
} catch (error) {
  if (error.message.includes('User rejected')) {
    console.log('User cancelled the transaction')
  } else {
    console.error('Transaction failed:', error)
  }
}
```

### Best Practices for Production dApps

- Use persistent connections and account abstraction where it improves UX.
- Handle user rejection gracefully.
- Show clear loading states during transactions.
- Validate all data before sending transactions.
- Use TypeScript + strict typing for safety.
- Support multiple popular wallets and chains.
- Test thoroughly on testnets before mainnet.
- Optimize gas usage, especially on higher-fee chains.

### Security Considerations

- Never store private keys in the frontend.
- Rigorously validate all inputs, signatures, and contract calls.
- Be extremely cautious with token approvals (use limited approvals).
- Keep all dependencies updated.
- Consider audits for high-value contracts.
- Be aware of chain-specific security models.

## Getting Started as a Developer on EVM Chains

1. Set up your development environment (Node.js, Foundry or Hardhat, viem/wagmi).
2. Explore **viem + wagmi** for wallet and contract interactions.
3. Build a simple test dApp or smart contract.
4. Test thoroughly on relevant testnets (Sepolia, Base Sepolia, Polygon Amoy, etc.).
5. Review how EVM chains can complement WAX-based Pixel Journey activities in a multi-chain strategy — and explore the **[PxDev Examples Vault](https://docs.pixeljourney.xyz/pxlabs/px-dev-examples/)** for shared patterns that apply across ecosystems.

## Pixel Journey Relevance

EVM chains offer mature tooling, large user bases, and strong cross-chain infrastructure. As we expand PxPackages and PxPortals, understanding modern EVM development helps us design better cross-chain experiences and prepare for potential future integration with EVM users or assets.

We welcome developers building on EVM chains who want to align with Pixel Journey's vision of safe, user-friendly, and multi-chain experiences.

*Educational content only. Development involves real risks and responsibilities. Always DYOR and follow security best practices. Not financial advice.*