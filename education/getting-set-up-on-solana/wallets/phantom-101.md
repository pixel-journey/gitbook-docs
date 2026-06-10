---
description: >-
  The most widely used Solana wallet — and the best choice if you want to
  manage both Solana and EVM assets in one place.
---

# Phantom Wallet 101

[Phantom](https://phantom.app) started as the dominant Solana wallet and has since expanded to support Ethereum, Base, Polygon, and other EVM chains. For Pixel Journey users active across both ecosystems — Solana and EVM — Phantom is the single wallet that handles everything.

---

## Installing Phantom

### Browser Extension

1. Visit [phantom.app](https://phantom.app) and click **"Download"**.
2. Select your browser (Chrome, Firefox, Brave, Edge).
3. The extension installs and opens automatically.

### Mobile App

Available on [iOS](https://apps.apple.com/us/app/phantom-solana-wallet/id1598432977) and [Android](https://play.google.com/store/apps/details?id=app.phantom). The developer is **Phantom Technologies Inc.**

---

## Creating a New Wallet

1. Open Phantom and click **"Create a new wallet"**.
2. Set a password to unlock Phantom on your device.
3. Phantom generates your **Secret Recovery Phrase** — 12 words.

{% hint style="danger" %}
Write your seed phrase on paper and store it securely offline. Never type it into any website, Discord message, or app unless you are explicitly restoring your wallet on a new device. No legitimate team member will ever ask for it.
{% endhint %}

4. Confirm the phrase and your wallet is created.

Your wallet will have a **Solana address** and a separate **EVM `0x...` address**, both generated from the same seed phrase. They are independent — your Solana address is not the same as your EVM address.

---

## Understanding Your Addresses

In Phantom, you can view your address for each network separately:

- **Solana**: A base58 string (e.g. `7xKXtg2CW87d97TXJSDpbD5jBkheTqA83TZRuJosgAsU`)
- **Ethereum / Base / Polygon**: A `0x...` hex address

When receiving assets, always share the correct address for the correct chain. Sending SOL to your EVM address (or vice versa) will result in lost funds.

---

## Switching Between Networks

Click the **chain icon** at the top of the Phantom extension or app to switch between Solana, Ethereum, Base, Polygon, and other supported networks. The balances, NFTs, and transaction history shown change to match the selected chain.

---

## Connecting to Solana dApps

1. Visit any Solana dApp (Magic Eden, Tensor, Jupiter, etc.).
2. Click **"Connect Wallet"**.
3. Select **Phantom** from the list.
4. Approve the connection in the Phantom popup.
5. Make sure Phantom is set to **Solana** before connecting to a Solana-specific dApp.

---

## Viewing Your NFTs and Tokens

Phantom has a built-in portfolio view:

- **NFTs tab**: Shows all Solana NFTs and EVM NFTs in one place. Tap any NFT to view its metadata and send or list options.
- **Tokens tab**: Shows SOL balance and all SPL token balances.
- **Activity tab**: Full transaction history.

---

## Importing an Existing Wallet

To restore a Phantom wallet on a new device, or to import a wallet you created elsewhere:

1. Open Phantom and select **"I already have a wallet"**.
2. Enter your 12-word or 24-word Secret Recovery Phrase.
3. Set a new device password.

Your Solana and EVM addresses will be restored from the same phrase.

---

## Tips

- Phantom's **in-app swap** works on Solana (powered by Jupiter) and on EVM chains — useful for getting small amounts of SOL for gas without leaving the wallet.
- The mobile app's **NFT viewer** is excellent for browsing your multi-chain portfolio on the go.
- Enable **biometric unlock** (Face ID / fingerprint) on mobile for faster access without compromising security.
- For holding significant value, consider pairing Phantom with a **Ledger hardware wallet** — Phantom supports Ledger on both Solana and EVM.
