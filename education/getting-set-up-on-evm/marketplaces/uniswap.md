# Uniswap

## What is Uniswap?

[Uniswap](https://app.uniswap.org) is the largest decentralised exchange (DEX) on Ethereum and EVM-compatible chains. Rather than using an order book, Uniswap uses an **Automated Market Maker (AMM)** model — liquidity is provided by users into pools, and trades happen directly against those pools via a smart contract.

If you want to swap ETH for any ERC-20 token, or convert between any two tokens, Uniswap is typically the first stop.

---

## Supported Chains

Uniswap is available on all the major EVM chains covered in this guide:

| Chain | Notes |
|---|---|
| Ethereum | The original deployment, highest liquidity |
| Base | Growing ecosystem, low fees |
| Polygon | Long-standing deployment, low fees |
| Arbitrum | High liquidity, very low fees |
| Optimism | Solid liquidity, low fees |
| BNB Chain | Available but not Uniswap's primary focus |

When you connect your wallet, Uniswap automatically detects your current network. You can also manually switch chains using the network selector in the app.

---

## Connecting Your Wallet

{% tabs %}
{% tab title="MetaMask" %}
1. Go to [app.uniswap.org](https://app.uniswap.org)
2. Click **Connect** in the top-right corner
3. Select **MetaMask**
4. Approve the connection in your MetaMask extension
5. You are now connected — your address and balance appear in the top-right
{% endtab %}

{% tab title="Rabby" %}
1. Go to [app.uniswap.org](https://app.uniswap.org)
2. Click **Connect** → **MetaMask** (Rabby injects as MetaMask-compatible)
3. Approve the connection in Rabby
4. Rabby will display a pre-approval risk summary — review and confirm
{% endtab %}

{% tab title="Phantom" %}
1. Open [app.uniswap.org](https://app.uniswap.org) in a browser where Phantom is installed
2. Click **Connect** → **Phantom** (or **MetaMask** if Phantom injects as such)
3. Select the Ethereum account you want to use in Phantom
4. Approve the connection
{% endtab %}

{% tab title="Coinbase Wallet" %}
1. Go to [app.uniswap.org](https://app.uniswap.org)
2. Click **Connect** → **Coinbase Wallet**
3. Scan the QR code with your mobile app, or approve via the browser extension
{% endtab %}
{% endtabs %}

---

## Swapping Tokens

1. On the main Uniswap page, you will see the **Swap** interface
2. In the top field, select the token you are **selling** (e.g. ETH)
3. Enter the amount you want to sell
4. In the bottom field, select the token you are **buying** (e.g. USDC)
5. Uniswap shows you the estimated output, price impact, and fee
6. Click **Review Swap**, check the details, then **Confirm Swap**
7. Approve the transaction in your wallet and wait for it to confirm on-chain

### Slippage Tolerance
If a swap fails or if you are trading a low-liquidity token, you may need to increase your **slippage tolerance**:
- Click the settings gear icon (top-right of the swap box)
- Increase slippage from the default (0.5%) to 1–3% for normal tokens, or higher for very low-liquidity tokens
- Higher slippage = more price movement tolerance, but potentially worse fills

---

## Switching Networks

To swap on a different chain (e.g. Base instead of Ethereum):

1. In your wallet, switch to the desired network (see the [chain guides](../chains/README.md) for how to add networks)
2. Uniswap will automatically detect the new network and update available liquidity pools
3. Proceed with the swap as normal — fees will reflect the new chain's gas costs

---

## Token Approvals

When swapping an ERC-20 token for the first time, Uniswap needs your permission to move that token. You will see an **Approve** transaction before the swap:

1. Click **Approve** and confirm the approval transaction in your wallet (this costs a small gas fee)
2. Once approved, proceed with the swap

> Approvals are a one-time cost per token per wallet. Rabby users will see a clear approval summary before signing.

---

## Wrapping and Unwrapping ETH

Some protocols require **WETH** (Wrapped ETH) instead of native ETH. You can wrap and unwrap directly on Uniswap:

1. In the swap interface, select **ETH** as the input token
2. Select **WETH** as the output token
3. Enter the amount — the exchange is always 1:1 with zero price impact
4. Confirm the transaction

To unwrap, simply reverse the process (WETH → ETH).

---

## Gas Fees on Uniswap

Gas costs vary significantly by chain:

| Chain | Typical Swap Fee |
|---|---|
| Ethereum | $3–$30+ depending on network congestion |
| Base | $0.01–$0.10 |
| Polygon | $0.01–$0.05 |
| Arbitrum | $0.05–$0.50 |
| Optimism | $0.05–$0.30 |

> Always check gas costs before confirming, especially on Ethereum mainnet during busy periods.

---

## Security Notes

- Always use [app.uniswap.org](https://app.uniswap.org) — bookmark it to avoid phishing sites
- Token approvals give Uniswap permission to spend your tokens — only approve on the real site
- Verify token contract addresses before swapping unknown tokens; fake tokens impersonating real ones are common
- Uniswap's smart contracts are among the most audited in DeFi, but no smart contract is entirely risk-free
- Never share your seed phrase — Uniswap (or any DEX) will never ask for it
