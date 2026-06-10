---
description: >-
  The most widely used EVM wallet in Web3. If you are new to EVM chains, start
  here.
---

# MetaMask 101

[MetaMask](https://metamask.io) is the most widely used wallet in the EVM ecosystem, with over 30 million monthly users. It works as a browser extension (Chrome, Firefox, Brave, Edge) and as a mobile app (iOS, Android). Nearly every EVM dApp supports MetaMask out of the box.

---

## Installing MetaMask

### Browser Extension (Recommended)

1. Visit [metamask.io/download](https://metamask.io/download) — **always go directly to the official site, never install from a search ad or random link**.
2. Click **"Install MetaMask for [your browser]"**.
3. The extension will open automatically once installed.

### Mobile App

Available on the [App Store](https://apps.apple.com/us/app/metamask/id1438144202) and [Google Play](https://play.google.com/store/apps/details?id=io.metamask). Search for "MetaMask" and confirm the developer is **ConsenSys**.

---

## Creating a New Wallet

1. Open the MetaMask extension or app.
2. Click **"Create a new wallet"**.
3. Set a strong **password** (this is only for unlocking the extension on your device — it is not your master backup).
4. MetaMask will show you your **Secret Recovery Phrase** — 12 random words.

### Your Seed Phrase: The Most Important Step

{% hint style="danger" %}
Your Secret Recovery Phrase is the master key to your wallet. Write it down on paper. Store it somewhere safe — offline, away from digital devices. Never type it into any website, Discord message, or app unless you are explicitly **restoring** your wallet. MetaMask staff, moderators, and anyone legitimate will **never** ask for it.
{% endhint %}

5. Confirm your seed phrase by selecting the words in order.
6. Your wallet is created. You will see your wallet address (starting with `0x`) at the top.

---

## Adding EVM Networks

MetaMask comes pre-loaded with Ethereum mainnet. To add other chains:

### Via Chainlist (Easiest)

1. Visit [chainlist.org](https://chainlist.org) with MetaMask installed.
2. Search for the chain you want (e.g., "Base", "Polygon", "Arbitrum").
3. Click **"Add to MetaMask"** and confirm in the popup.

### Manually

Go to **Settings → Networks → Add a network** and enter:

| Chain | RPC URL | Chain ID | Symbol | Explorer |
|---|---|---|---|---|
| Base | `https://mainnet.base.org` | 8453 | ETH | `https://basescan.org` |
| Polygon | `https://polygon-rpc.com` | 137 | POL | `https://polygonscan.com` |
| Arbitrum One | `https://arb1.arbitrum.io/rpc` | 42161 | ETH | `https://arbiscan.io` |
| Optimism | `https://mainnet.optimism.io` | 10 | ETH | `https://optimistic.etherscan.io` |

---

## Switching Between Networks

Click the **network dropdown** at the top of MetaMask (it will say "Ethereum Mainnet" by default) to switch to any network you have added.

> When you are on Base, your wallet shows your Base ETH balance. When you switch to Polygon, it shows your POL balance. Your address is the same — the balances are separate per chain.

---

## Connecting to a dApp

1. Visit the dApp (e.g., OpenSea, a Pixel Journey minting page).
2. Click **"Connect Wallet"** on the site.
3. Select **MetaMask** from the list of wallets.
4. Approve the connection in the MetaMask popup.
5. You are connected. The site can now see your address and request transactions — but it cannot move funds without your explicit approval each time.

---

## Importing an Existing Wallet

If you already have a MetaMask wallet and want to restore it on a new device:

1. Click **"Import an existing wallet"** during setup.
2. Enter your 12-word Secret Recovery Phrase.
3. Set a new device password.

You can also import a single account using a private key via **Accounts → Import account**.

---

## Tips for Using MetaMask Safely

- Always check the URL of a site before approving any transaction.
- Check what a transaction is actually doing before clicking **"Confirm"** — MetaMask shows a summary, but for contract interactions you should understand what action you are approving.
- Use **"Spending cap"** warnings — if a dApp asks for unlimited token approval, consider limiting the approval to the amount you actually need.
- MetaMask has a built-in **phishing detection** that warns about known scam sites. Pay attention to these warnings.
- For long-term storage of significant value, consider a hardware wallet (Ledger, Trezor) — MetaMask can connect to both.

See the [EVM Security Tips](../evm-security-tips.md) page for a full rundown.
