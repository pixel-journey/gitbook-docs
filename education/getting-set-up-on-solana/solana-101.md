---
description: >-
  Sub-second finality, fees under a cent, and one of the most active NFT
  ecosystems in Web3. Here is how Solana works.
---

# Solana 101

## What Makes Solana Different

Solana is a Layer 1 blockchain, like Ethereum — but it was built from the ground up with a fundamentally different architecture. While Ethereum prioritizes decentralization and security, Solana optimizes for raw speed and throughput.

The result: Solana can process **50,000–65,000 transactions per second** under ideal conditions, with blocks finalizing in under a second and transaction fees averaging **$0.00025** — less than a fraction of a cent.

For NFT collectors and traders, this means:
- Minting an NFT costs almost nothing in fees.
- Buying and selling on marketplaces is near-instant.
- On-chain gaming and interactive experiences are practical in a way they are not on Ethereum mainnet.

---

## How Solana Works

### Proof of History (PoH)

Solana's key innovation is **Proof of History** — a cryptographic clock that creates a verifiable record of time passage between events. This allows validators to agree on the order of transactions without needing to communicate constantly, enabling much higher throughput than traditional Proof of Stake alone.

Solana also uses:
- **Proof of Stake (PoS)**: Validators stake SOL to participate in block production and earn rewards.
- **Tower BFT**: A consensus algorithm optimized to work with PoH.
- **Gulf Stream**: A mempool-less transaction forwarding protocol.
- **Sealevel**: Parallel smart contract execution (contracts run simultaneously rather than sequentially).

You do not need to understand all of this to use Solana — what matters practically is that transactions are fast and fees are negligible.

---

## SOL: The Native Token

**SOL** is the native token of the Solana blockchain. It is used for:

- **Paying transaction fees** (tiny amounts — most transactions cost 0.000005 SOL or less)
- **Rent** — Solana accounts require a small SOL deposit ("rent-exempt minimum") to exist on-chain. This is a one-time cost that is refundable if the account is closed.
- **Staking** — Delegating SOL to validators to earn staking rewards (currently around 6–8% APY).

### Addresses on Solana

Unlike EVM's `0x...` format, Solana addresses look like this:

```
7xKXtg2CW87d97TXJSDpbD5jBkheTqA83TZRuJosgAsU
```

They are **base58-encoded** strings, typically 32–44 characters long. Your Solana address is completely separate from any EVM address you have — even if you use Phantom (which supports both ecosystems), your Solana address and your EVM address are different.

---

## Accounts and Rent

Solana uses an **account model** for storing data. Every wallet, token account, and NFT you own is a separate on-chain account. Creating a new account (for example, receiving a new type of token for the first time) requires a small SOL deposit to make the account "rent-exempt" — meaning it persists indefinitely without ongoing fees.

**Practical implications:**

- When you receive a new token or NFT for the first time, your wallet may show a small SOL fee to create the **associated token account**.
- These deposits are refundable — if you close an account (e.g. by burning a token or sending it away), you get the rent deposit back.
- A small SOL buffer in your wallet (0.05–0.1 SOL) is enough to handle dozens of new account creations.

---

## Transaction Fees on Solana

Solana fees are split into two parts:

- **Base fee**: 0.000005 SOL per signature (fixed, negligible)
- **Priority fee**: An optional additional fee to increase transaction processing priority during times of network congestion

In normal conditions, the base fee alone is sufficient. During periods of high demand (a major NFT mint, a token launch), adding a small priority fee ensures your transaction lands promptly. Most Solana wallets handle this automatically with a "normal / fast / turbo" fee selector.

---

## NFTs on Solana

Solana NFTs work differently from EVM:

| | EVM (Ethereum / Base / etc.) | Solana |
|---|---|---|
| **NFT Standard** | ERC-721, ERC-1155 | Metaplex Token Metadata standard |
| **Fees to mint** | Gas (ETH or native token) | Near-zero (< $0.01) |
| **Wallet address format** | `0x...` | Base58 string |
| **Primary marketplaces** | OpenSea, Blur | Magic Eden, Tensor |
| **Collections** | Smart contract per collection | Metaplex collection groupings |

Solana NFTs are stored as **SPL tokens** (Solana Program Library tokens) with on-chain metadata managed by the Metaplex standard. Unlike EVM, each NFT is an individual on-chain account rather than a token ID inside a shared contract.

---

## Solana vs. WAX

Coming from WAX, there are some similarities worth noting:

| | WAX | Solana |
|---|---|---|
| **Speed** | Fast (~0.5 sec blocks) | Very fast (< 0.5 sec finality) |
| **Fees** | Resources (CPU/NET/RAM staking) | Near-zero SOL fees |
| **NFT ecosystems** | AtomicHub, NeftyBlocks, NFTHive | Magic Eden, Tensor |
| **DeFi** | Alcor, TacoSwap | Jupiter, Raydium, Orca |
| **Wallet** | Account name (e.g. `pixeljourney`) | Base58 address |
| **Marketcap / Ecosystem size** | Smaller, niche-focused | Much larger, broad |

The WAX resource model and Solana's rent model are both alternatives to Ethereum's gas fees — just implemented differently. The biggest adjustment is that Solana's ecosystem is much larger and more competitive.

---

## Solana Programs (Smart Contracts)

On Solana, smart contracts are called **programs**. They are:

- **Stateless** — programs do not store data themselves; data is stored in separate accounts that programs interact with.
- **Deployed once and used by many** — a single program like the Metaplex Token Metadata program is used by every NFT project on Solana.
- **Written in Rust** (primarily) or C — different from Ethereum's Solidity.

As a user, you interact with programs through your wallet — approving transactions that call program functions — just like approving transactions on EVM chains.

---

## Quick Checklist: Before You Start on Solana

- [ ] Install a wallet — Phantom is recommended for beginners (see [wallet guides](wallets/README.md))
- [ ] Write down your seed phrase and store it offline
- [ ] Get a small amount of SOL for fees and rent (0.1 SOL is more than enough to start)
- [ ] Read the [Solana Security Tips](solana-security-tips.md) before interacting with any program or link
- [ ] Check out [Magic Eden](https://magiceden.io) or [Tensor](https://tensor.trade) to browse the NFT landscape

You are ready to explore. The Pixel Journey Discord is always open if you need help!
