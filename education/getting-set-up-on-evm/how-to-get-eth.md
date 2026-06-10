---
description: >-
  ETH is the gas that powers most EVM chains. Here is how to get it onto
  whichever chain you need — whether you are starting from fiat or from another
  crypto.
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

## Chain-by-Chain: How to Get Gas

{% tabs %}
{% tab title="Ethereum" %}
### Getting ETH on Ethereum Mainnet

**Option 1: Centralized exchange (most cost-effective)**
Buy ETH on Coinbase, Binance, Kraken, or Gemini and withdraw to your Ethereum mainnet address. This is almost always the cheapest way to acquire ETH when starting from fiat.

**Option 2: In-wallet fiat on-ramp**
MetaMask, Rabby, and Coinbase Wallet all have built-in "Buy" buttons that connect to on-ramp providers (MoonPay, Transak, Ramp, Stripe). Convenient but typically 2–4% higher fees than a CEX.

**Option 3: Receive from another person**
If you have a friend or colleague who already holds ETH, they can simply send it to your `0x...` address. Make sure they are sending on the correct network (Ethereum mainnet = Chain ID 1).

**Useful links:**
- [Coinbase](https://coinbase.com) — Beginner-friendly, US and international
- [Kraken](https://kraken.com) — Strong in Europe and US, good rates
- [Binance](https://binance.com) — Largest global volume
{% endtab %}

{% tab title="Base" %}
### Getting ETH on Base

Base uses ETH as its gas token, but Base ETH is separate from Ethereum mainnet ETH — you need to either bridge it or acquire it directly on Base.

**Option 1: Withdraw directly from Coinbase exchange**
If you have a Coinbase account, tap "Send" → select your wallet address → choose **"Base network"** as the destination. ETH will arrive in your wallet already on Base, with no bridging needed.

**Option 2: Bridge from Ethereum mainnet**
Use the [Base Bridge](https://bridge.base.org) to move ETH from Ethereum to Base. The official bridge has a 7-day withdrawal window back to mainnet. For faster withdrawals in either direction, use:
- [Across Protocol](https://across.to) — Fast, low fees
- [Relay](https://relay.link) — Instant bridging between EVM chains

**Option 3: In-app on-ramp via Coinbase Wallet**
Open Coinbase Wallet, select the Base network, tap "Buy". This deposits ETH directly onto Base via a fiat on-ramp.

**Useful links:**
- [Base Bridge](https://bridge.base.org) — Official Ethereum ↔ Base bridge
- [Across Protocol](https://across.to) — Fast cross-chain bridging
{% endtab %}

{% tab title="Polygon" %}
### Getting POL on Polygon

Polygon uses **POL** (formerly MATIC) as its gas token.

**Option 1: Buy POL directly on a centralized exchange**
POL is listed on most major exchanges — Coinbase, Binance, Kraken, OKX. Buy POL and withdraw it to your Polygon PoS address (Chain ID 137). Most exchanges support direct Polygon withdrawal.

**Option 2: Bridge from Ethereum**
Use the [Polygon Portal](https://portal.polygon.technology) to bridge ETH or USDC from Ethereum mainnet to Polygon, then swap for POL on QuickSwap or Uniswap.

**Option 3: Gas swap if you have other tokens on Polygon**
If you already have USDC or another token on Polygon but no POL for gas, use the "Get gas" feature inside MetaMask or Rabby — it swaps a tiny amount of your token into POL so you can pay fees.

**About MATIC → POL migration:**
If you hold old MATIC tokens, they can be migrated 1:1 to POL via the [Polygon Portal](https://portal.polygon.technology). Most exchanges now issue POL directly.

**Useful links:**
- [Polygon Portal (Bridge)](https://portal.polygon.technology)
- [QuickSwap](https://quickswap.exchange) — Native Polygon DEX
{% endtab %}

{% tab title="Arbitrum" %}
### Getting ETH on Arbitrum

Arbitrum One uses ETH as its gas token.

**Option 1: Withdraw directly from a CEX to Arbitrum**
Binance, OKX, and several other exchanges support direct withdrawal to Arbitrum One. This avoids bridging entirely — ETH lands straight in your wallet on Arbitrum.

**Option 2: Bridge from Ethereum mainnet**
Use the [Arbitrum Bridge](https://bridge.arbitrum.io) to move ETH from Ethereum to Arbitrum One. Withdrawal back to Ethereum takes 7 days (the fraud-proof window). For fast exits, use [Across Protocol](https://across.to) or [Orbiter Finance](https://orbiter.finance).

**Option 3: On-ramp directly to Arbitrum**
MetaMask, Coinbase Wallet, and Rabby all offer fiat on-ramp options that can deposit ETH directly onto Arbitrum.

**Useful links:**
- [Arbitrum Bridge](https://bridge.arbitrum.io) — Official Ethereum ↔ Arbitrum bridge
- [Across Protocol](https://across.to) — Fast cross-chain bridging
{% endtab %}

{% tab title="Optimism" %}
### Getting ETH on Optimism

Optimism uses ETH as its gas token.

**Option 1: Withdraw directly from a CEX to Optimism**
Coinbase, Binance, and Kraken all support direct ETH withdrawal to Optimism. No bridging needed.

**Option 2: Bridge from Ethereum mainnet**
Use the [Optimism Bridge](https://app.optimism.io/bridge). As with all optimistic rollups, withdrawal back to mainnet takes 7 days without a fast bridge. Use [Across Protocol](https://across.to) for fast exits.

**Option 3: Bridge from Base**
Since Base and Optimism both use the OP Stack, bridging between them is fast and cheap via [Across](https://across.to) or [Relay](https://relay.link).

**Useful links:**
- [Optimism Bridge](https://app.optimism.io/bridge) — Official bridge
- [Across Protocol](https://across.to) — Fast bridging
{% endtab %}
{% endtabs %}

---

## Cross-Chain Bridges: Moving Between EVM Chains

Once you have ETH on one chain, you can move it to another using a bridge:

| Bridge | Best for | Speed |
|---|---|---|
| [Across Protocol](https://across.to) | Fast bridging between all major L2s | Minutes |
| [Relay](https://relay.link) | Instant bridging, good UX | Seconds–minutes |
| [Orbiter Finance](https://orbiter.finance) | Low fees across many chains | Minutes |
| [Base Bridge](https://bridge.base.org) | ETH ↔ Base (official) | Minutes (7-day withdrawal) |
| [Arbitrum Bridge](https://bridge.arbitrum.io) | ETH ↔ Arbitrum (official) | Minutes (7-day withdrawal) |
| [Polygon Portal](https://portal.polygon.technology) | ETH ↔ Polygon (official) | Minutes |
| [Optimism Bridge](https://app.optimism.io/bridge) | ETH ↔ Optimism (official) | Minutes (7-day withdrawal) |

> Official bridges are the most trustless option but have a 7-day withdrawal delay for optimistic rollups (Arbitrum, Optimism, Base). Third-party bridges like Across solve this using liquidity pools that front the funds immediately.

---

## No-KYC Options

If you do not want to complete KYC on an exchange:

| Service | What it does |
|---|---|
| [SimpleSwap](https://simpleswap.io) | Swap almost any crypto for ETH, no account needed |
| [ChangeNOW](https://changenow.io) | No-KYC swap, wide token support |
| [Uniswap](https://app.uniswap.org) | Swap any ERC-20 token for ETH (requires existing EVM balance) |
| [LlamaSwap](https://swap.defillama.com) | DEX aggregator — best rates across Ethereum + L2s |

---

## Fiat On-Ramps Built Into Wallets

MetaMask, Coinbase Wallet, and Phantom all have integrated fiat on-ramps:

- **MetaMask**: "Buy" button in the extension → uses MoonPay, Transak, or Stripe
- **Coinbase Wallet**: "Buy" button → uses Coinbase's own on-ramp (competitive fees)
- **Phantom**: "Buy" button → uses MoonPay or Coinbase Pay

Convenient but typically charge higher fees (3–5%) compared to buying on an exchange and withdrawing.

---

## Getting from WAX to EVM

If you hold WAXP and want to fund an EVM wallet:

1. Find an exchange that lists WAXP via [CoinMarketCap WAX markets](https://coinmarketcap.com/currencies/wax/markets/).
2. Sell WAXP for ETH or USDC on a CEX, then withdraw to your EVM wallet.
3. Alternatively, use [SimpleSwap](https://simpleswap.io) to swap WAXP for ETH without creating an account.
4. For NFT bridging specifically, use the [Cloud Wallet Bridge](../../introduction/wax-ecosystem-guides/cloud-wallet-bridge/) to move assets directly from WAX to an EVM chain.

---

## How Much ETH Do You Need?

A rough guide to keep in your wallet as a gas buffer:

| Chain | Suggested gas buffer |
|---|---|
| Ethereum mainnet | 0.01–0.05 ETH |
| Base | 0.001 ETH |
| Arbitrum | 0.001 ETH |
| Optimism | 0.001 ETH |
| Polygon | 1–5 POL |

On L2s, gas costs so little that you rarely need to think about it for everyday use.

---

## Important: Send to the Right Network

Always confirm you are sending/receiving on the correct network. ETH sent to a Base address on Ethereum mainnet will arrive on Ethereum mainnet — not Base. The tokens are not lost, but you will need to bridge them to get them onto Base.

When in doubt: check your wallet's active network before sharing your address or confirming a withdrawal.
