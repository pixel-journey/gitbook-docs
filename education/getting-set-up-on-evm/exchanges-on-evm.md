---
description: >-
  From Uniswap to Aerodrome, the EVM ecosystem has a DEX for every chain.
  Here is how to swap tokens and manage liquidity across EVM networks.
---

# DEXs & Exchanges on EVM

On WAX, the primary DEXs are Alcor Exchange and TacoSwap. On EVM chains, the landscape is broader — with Uniswap as the dominant protocol across most chains, supplemented by chain-native DEXs with deeper liquidity on their home networks.

This page covers the most relevant platforms for each chain Pixel Journey operates on.

---

## Uniswap

[Uniswap](https://app.uniswap.org) is the most widely used decentralized exchange in Web3. It operates on Ethereum, Base, Polygon, Arbitrum, Optimism, and several other EVM chains from a single interface.

**What it does:**
- Swap any ERC-20 token for another
- Provide liquidity and earn fees from trading volume
- Bridge assets between chains (via integrated third-party bridges)

{% tabs %}
{% tab title="Ethereum" %}
Uniswap originated on Ethereum and has the deepest liquidity pools here. Every major token pair is available. Gas fees apply — plan accordingly for small swaps.

- Best for: large swaps, tokens only available on mainnet
- [Uniswap on Ethereum](https://app.uniswap.org)
{% endtab %}

{% tab title="Base" %}
Uniswap on Base has grown rapidly. Fees are near-zero, making it practical for small swaps and everyday use.

- Best for: everyday token swaps, low-cost experimentation
- Gas: ETH on Base (< $0.01)
- [Uniswap on Base](https://app.uniswap.org)
{% endtab %}

{% tab title="Polygon" %}
Uniswap on Polygon offers broad token support with very low fees (paid in POL). A solid choice for Polygon-based token activity.

- Gas: POL (< $0.01)
- [Uniswap on Polygon](https://app.uniswap.org)
{% endtab %}

{% tab title="Arbitrum" %}
Uniswap on Arbitrum is popular for DeFi users seeking low-cost execution on a high-security L2.

- Gas: ETH on Arbitrum (very low)
- [Uniswap on Arbitrum](https://app.uniswap.org)
{% endtab %}

{% tab title="Optimism" %}
Uniswap is available on Optimism, though Velodrome (below) tends to be the more popular native choice here.

- Gas: ETH on Optimism (very low)
- [Uniswap on Optimism](https://app.uniswap.org)
{% endtab %}
{% endtabs %}

### How to Swap on Uniswap

1. Visit [app.uniswap.org](https://app.uniswap.org).
2. Click **"Connect"** (top right) and connect your wallet.
3. Select the correct network from the network dropdown.
4. Choose the token you are swapping **from** (top field) and the token you want to receive (bottom field).
5. Enter the amount. Uniswap shows you the estimated output and exchange rate.
6. Review the transaction details, including price impact and gas estimate.
7. Click **"Swap"** and confirm in your wallet.

> Always check the **price impact** before confirming. For tokens with lower liquidity, a large swap can significantly move the price against you. A price impact above 1–2% is worth noting; above 5% is a red flag.

---

## Chain-Native DEXs

Each chain has its own native DEX with deep liquidity in chain-specific tokens and pairs:

{% tabs %}
{% tab title="Base — Aerodrome" %}
[Aerodrome Finance](https://aerodrome.finance) is the dominant native DEX on Base, built on the ve(3,3) model pioneered by Solidly and then Velodrome. It has the deepest liquidity for Base-native tokens and offers:

- Token swaps with low slippage for major pairs
- Liquidity provision with AERO token rewards
- Vote-escrow governance (lock AERO for veAERO voting power)

If you are looking for a Base-native token that is not listed on Uniswap with good liquidity, Aerodrome is the first place to check.

- [Aerodrome Finance](https://aerodrome.finance)
{% endtab %}

{% tab title="Polygon — QuickSwap" %}
[QuickSwap](https://quickswap.exchange) is the leading native DEX on Polygon PoS. It was one of the first Uniswap forks and has maintained deep liquidity across the Polygon ecosystem.

- Broad token support for Polygon-native projects
- QUICK token rewards for liquidity providers
- NFT marketplace integration

- [QuickSwap](https://quickswap.exchange)
{% endtab %}

{% tab title="Arbitrum — Camelot" %}
[Camelot Exchange](https://camelot.exchange) is a native Arbitrum DEX focused on the Arbitrum ecosystem, with particular support for new projects launching on Arbitrum. It uses dual AMM technology (stable + volatile pools) and has a strong community launchpad presence.

- [Camelot](https://camelot.exchange)

[GMX](https://gmx.io) is also worth knowing — it is the leading perpetuals exchange on Arbitrum (and Avalanche), letting you trade with leverage. Not a spot DEX, but highly relevant for DeFi users on Arbitrum.

- [GMX](https://gmx.io)
{% endtab %}

{% tab title="Optimism — Velodrome" %}
[Velodrome Finance](https://velodrome.finance) is the dominant native DEX on Optimism, using the same ve(3,3) model that inspired Aerodrome on Base. It has the deepest native liquidity on Optimism and is the go-to for Optimism-native token pairs.

- [Velodrome Finance](https://velodrome.finance)
{% endtab %}
{% endtabs %}

---

## DEX Aggregators

DEX aggregators find the best swap route across multiple DEXs simultaneously, often getting you a better price than going directly to one platform:

| Aggregator | Chains | Notes |
|---|---|---|
| [1inch](https://app.1inch.io) | ETH, Base, Polygon, ARB, OP, + more | Most popular aggregator |
| [Paraswap](https://paraswap.io) | ETH, Polygon, ARB, OP, + more | Good institutional routes |
| [Odos](https://app.odos.xyz) | ETH, Base, ARB, OP, + more | Newer, often competitive rates |
| [KyberSwap](https://kyberswap.com) | ETH, Polygon, ARB, OP, + more | Strong on Polygon |

For any swap worth over ~$50, it is worth checking an aggregator alongside a direct DEX to compare rates.

---

## Centralized Exchanges (CEXs)

For buying crypto with fiat or acquiring major tokens at the best rates, centralized exchanges remain the most efficient option. The most relevant ones:

| Exchange | Available In | Best for |
|---|---|---|
| [Coinbase](https://coinbase.com) | US, EU, UK, + more | Beginners, Base integration, regulated |
| [Kraken](https://kraken.com) | US, EU, UK, + more | Good rates, staking, strong compliance |
| [Binance](https://binance.com) | Most of the world (not US) | Largest volume, low fees |
| [OKX](https://okx.com) | Most of the world | Strong L2 withdrawal support |

> Always withdraw from a CEX to **your own self-custody wallet** (MetaMask, Rabby, etc.) before interacting with NFT marketplaces or DeFi. Assets on a CEX are held by the exchange — not by you.

---

## Block Explorers: Checking Your Transactions

When you send a transaction on any EVM chain, you can look it up on the chain's block explorer:

| Chain | Explorer |
|---|---|
| Ethereum | [etherscan.io](https://etherscan.io) |
| Base | [basescan.org](https://basescan.org) |
| Polygon | [polygonscan.com](https://polygonscan.com) |
| Arbitrum | [arbiscan.io](https://arbiscan.io) |
| Optimism | [optimistic.etherscan.io](https://optimistic.etherscan.io) |

Paste your `0x...` wallet address or a transaction hash into any of these to see your full transaction history, token balances, and NFT holdings.

---

## Tips

- When swapping on a DEX, set a reasonable **slippage tolerance** — 0.5% is standard for liquid pairs; 1–2% for less liquid tokens. Higher slippage means you accept a worse price if the market moves while your transaction is processing.
- Gas fees on Ethereum mainnet fluctuate heavily. For non-urgent swaps, try [Ethereum Gas Tracker](https://etherscan.io/gastracker) to time lower-fee windows.
- Never use a DEX link you received in a Discord DM or tweet. Always navigate directly to the official URL.
- For token approvals on DEXs, consider setting a specific spending limit rather than "unlimited" — especially for new or less-audited protocols. See the [EVM Security Tips](evm-security-tips.md) page.
