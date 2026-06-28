---
description: >-
  Jupiter, Raydium, Orca, and the key DeFi tools on Solana. Swapping tokens
  on Solana is fast, cheap, and accessible from day one. Advanced features
  like DCA, limit orders, and perps add powerful trading options.
---

# DEXs & Exchanges on Solana

Solana's DeFi ecosystem is one of the most active in Web3 outside of Ethereum. Transaction fees are near-zero, execution is near-instant, and the tooling — especially Jupiter — is among the best in the industry for token swaps.

For advanced trading strategies, see the dedicated **[Jupiter Advanced Features](jupiter-advanced-features.md)** guide.

---

## Jupiter

[Jupiter](https://jup.ag) is the dominant DEX aggregator on Solana and the first place most users go to swap tokens. It routes your swap across all of Solana's liquidity sources simultaneously — Raydium, Orca, Meteora, and others — to find the best price.

### How to Swap on Jupiter

1. Visit [jup.ag](https://jup.ag).
2. Click **"Connect Wallet"** and select Phantom, Solflare, or Backpack.
3. Select the token you want to swap **from** (e.g. SOL) and the token you want to receive.
4. Enter the amount. Jupiter shows the expected output, price impact, and the route it will use.
5. Adjust slippage if needed (default 0.5% is fine for liquid pairs).
6. Click **"Swap"** and confirm in your wallet.

Jupiter also offers:
- **Limit orders**: Set a target price and let Jupiter execute automatically when the market reaches it.
- **DCA (Dollar Cost Averaging)**: Automate recurring purchases of a token over time.
- **Perpetuals**: Jupiter Perps for leveraged trading.

Jupiter is widely considered the best swap interface in all of Web3 for ease of use and routing efficiency.

---

## Raydium

[Raydium](https://raydium.io) is Solana's most established native DEX and liquidity protocol. It powers a large portion of the liquidity that Jupiter routes through.

### What Raydium Offers

- **Token swaps**: Swap any Solana token pair with Raydium liquidity.
- **Liquidity pools**: Provide liquidity to earn trading fees.
- **Concentrated liquidity (CLMM)**: Advanced liquidity provision where you specify a price range to maximize capital efficiency.
- **Launchpad (AcceleRaytor)**: IDO launchpad for new Solana tokens.

For most swaps, using Jupiter (which includes Raydium liquidity automatically) is simpler. Raydium is more relevant if you want to provide liquidity or participate in token launches directly.

- [Raydium](https://raydium.io)

---

## Orca

[Orca](https://orca.so) is another leading Solana DEX focused on a clean user experience and concentrated liquidity (Whirlpools). It is particularly popular with liquidity providers.

- **Whirlpools**: Concentrated liquidity pools with tight spreads and high capital efficiency.
- **Clean UI**: One of the most intuitive swap and LP interfaces on Solana.

Again, Jupiter routes through Orca automatically — go there directly only if you are providing liquidity.

- [Orca](https://orca.so)

---

## Meteora

[Meteora](https://meteora.ag) is a newer but rapidly growing Solana protocol specializing in dynamic liquidity pools (DLMM — Dynamic Liquidity Market Maker). It has become particularly popular for new token launches and deep liquidity on volatile pairs.

- [Meteora](https://meteora.ag)

---

## Quick Comparison

| Platform | Best for | Notes |
|---|---|---|
| [Jupiter](https://jup.ag) | Token swaps (all users) | Aggregates all DEX liquidity |
| [Raydium](https://raydium.io) | Liquidity provision, launchpad | Longest-running Solana DEX |
| [Orca](https://orca.so) | Concentrated liquidity (LP) | Clean UI, Whirlpools |
| [Meteora](https://meteora.ag) | New token launches, dynamic LPs | Best for volatile pairs |

For the vast majority of users who just want to swap tokens, **Jupiter is the only tool you need**. The others become relevant when you move into liquidity provision or advanced DeFi strategies.

---

## Centralized Exchanges

For buying SOL with fiat or trading major tokens at the best rates, centralized exchanges remain efficient. See the [How to Get SOL](how-to-get-sol.md) guide for a full list of recommended exchanges.

---

## Block Explorer

To verify transactions, look up wallet addresses, or inspect token contracts on Solana, use:

- [Solana Explorer](https://explorer.solana.com) — Official Solana Foundation explorer
- [Solscan](https://solscan.io) — Popular third-party explorer with richer UI
- [SolanaFM](https://solana.fm) — Explorer with focus on program and instruction data

Paste any wallet address, transaction signature, or token address into any of these to inspect it.

---

## Tips

- Always use [jup.ag](https://jup.ag) by navigating there directly — bookmark it. Fake Jupiter sites are common and will drain your wallet.
- Check the **price impact** before confirming large swaps. If price impact is above 1–2% for a major token pair, you are likely using a low-liquidity pool — consider splitting the swap or waiting.
- Priority fees on Solana are optional but worth enabling ("Fast" or "Turbo" in your wallet settings) during congested periods — for example during a major token launch — to ensure your transaction lands quickly.
- For tokens you are not familiar with, use [RugCheck](https://rugcheck.xyz) to scan the token contract for red flags before swapping.
