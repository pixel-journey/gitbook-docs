---
description: >-
  How to buy ETH (and other EVM tokens) and get it into your wallet on the
  right chain — whether you are starting from scratch or bridging from WAX.
---

# How to Get ETH & Tokens

Before you can do anything on an EVM chain — buy an NFT, mint, swap — you need a small amount of the chain's native gas token in your wallet. For Ethereum, Base, Arbitrum, and Optimism that is **ETH**. For Polygon it is **POL** (formerly MATIC).

This guide covers the main routes.

---

## Starting From Scratch (Fiat to Crypto)

If you have no crypto at all yet, the cleanest path is through a **centralized exchange (CEX)**:

### Recommended Exchanges

| Exchange | Regions | Supports direct withdrawal to L2? |
|---|---|---|
| [Coinbase](https://coinbase.com) | US, EU, many others | Yes — Base natively |
| [Binance](https://binance.com) | Most regions (not US) | Yes — Arbitrum, Polygon |
| [Kraken](https://kraken.com) | US, EU | Yes — Arbitrum, Optimism |
| [OKX](https://okx.com) | Most regions | Yes — multiple L2s |

**Basic steps:**
1. Create an account on the exchange.
2. Complete KYC (identity verification — required on all regulated exchanges).
3. Deposit fiat (bank transfer, debit card, etc.).
4. Buy ETH (or POL for Polygon).
5. Withdraw to your self-custody wallet on the chain you want.

> Always double-check the withdrawal network. When withdrawing ETH for use on Base, select **Base** as the withdrawal network if the exchange supports it (Coinbase does). Otherwise withdraw to Ethereum mainnet and bridge from there.

---

## If You Already Have Crypto (Swapping and Bridging)

### You have WAXP and want EVM tokens

The WAX Cloud Wallet Bridge allows you to bridge tokens and NFTs from WAX to EVM chains. For WAXP specifically:

1. Visit [CoinMarketCap WAX markets](https://coinmarketcap.com/currencies/wax/markets/) to find an exchange that lists WAXP.
2. Sell WAXP for ETH or USDC on a CEX, then withdraw to your EVM wallet.
3. Alternatively, use [SimpleSwap](https://simpleswap.io) to swap WAXP for ETH without creating an account.

### You have ETH on Ethereum mainnet but want it on Base or Arbitrum

Use a bridge. The safest and most widely used options:

| Bridge | Best for |
|---|---|
| [Base Bridge](https://bridge.base.org) | ETH to/from Base (official) |
| [Arbitrum Bridge](https://bridge.arbitrum.io) | ETH to/from Arbitrum (official) |
| [Polygon Portal](https://portal.polygon.technology) | ETH to/from Polygon (official) |
| [Across Protocol](https://across.to) | Fast bridging between any major EVM chain |
| [Relay](https://relay.link) | Fast, low-fee bridging |

> Official bridges are slowest for withdrawals (7-day fraud-proof window on optimistic rollups) but have no withdrawal limits. Third-party bridges like Across are much faster (minutes) and are widely used — they solve the 7-day problem by using liquidity pools.

### You are on Polygon and need some POL for gas

If you have USDC or another token on Polygon but no POL:

- Most wallets (MetaMask, Rabby, Coinbase Wallet) have a built-in **"Get gas"** or **"Buy gas"** feature that swaps a small amount of your existing token for POL in one step.
- Alternatively, swap on [QuickSwap](https://quickswap.exchange) (USDC → POL).

---

## No-KYC Options

If you do not want to complete KYC on an exchange:

| Service | What it does |
|---|---|
| [SimpleSwap](https://simpleswap.io) | Swap almost any crypto for ETH, no account needed |
| [ChangeNOW](https://changenow.io) | No-KYC swap, wide token support |
| [Uniswap](https://app.uniswap.org) | Swap any ERC-20 token for ETH (requires existing EVM balance) |
| [LlamaSwap](https://swap.defillama.com) | DEX aggregator — best rates across Ethereum + L2s |

For complete fiat-to-crypto without KYC, options are limited in most jurisdictions. Bitcoin ATMs exist but have high fees. Peer-to-peer exchanges (LocalCoinSwap, Bisq) are an option for advanced users.

---

## Fiat On-Ramps Built Into Wallets

MetaMask, Coinbase Wallet, and Phantom all have integrated fiat on-ramps that let you buy ETH directly within the wallet using a debit or credit card:

- **MetaMask**: "Buy" button in the extension → uses MoonPay, Transak, or Stripe
- **Coinbase Wallet**: "Buy" button → uses Coinbase's own on-ramp (competitive fees)
- **Phantom**: "Buy" button → uses MoonPay or Coinbase Pay

These are convenient but typically charge higher fees (3–5%) compared to buying on an exchange and withdrawing.

---

## How Much ETH Do You Need?

A rough guide to keep in your wallet as a gas buffer:

| Chain | Suggested gas buffer |
|---|---|
| Ethereum mainnet | 0.01–0.05 ETH ($25–$125+) |
| Base | 0.001 ETH ($2–3) |
| Arbitrum | 0.001 ETH ($2–3) |
| Optimism | 0.001 ETH ($2–3) |
| Polygon | 1–5 POL (< $1) |

These buffers let you do dozens to hundreds of transactions before needing to top up. On L2s, gas costs so little that you rarely need to think about it for everyday use.

---

## Important: Send to the Right Network

When withdrawing from an exchange or receiving ETH from someone, always confirm you are sending/receiving on the correct network. ETH sent to a Base address on Ethereum mainnet, for example, will arrive on Ethereum mainnet — not Base. The tokens are not lost, but you will need to bridge them to get them onto Base.

When in doubt: check your wallet's active network before sharing your address or confirming a withdrawal.
