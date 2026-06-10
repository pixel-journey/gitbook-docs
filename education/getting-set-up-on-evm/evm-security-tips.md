---
description: >-
  Security on EVM chains is your personal responsibility. There is no customer
  support, no chargebacks, and no way to reverse a bad transaction. Read this
  before doing anything else.
---

# EVM Security Tips

The EVM ecosystem is trustless by design — no central party can freeze your funds or reverse transactions. That freedom also means the responsibility for protecting your wallet falls entirely on you. The most common way people lose assets in Web3 is not through technical hacks of the blockchain itself, but through social engineering, phishing, and blindly approving malicious transactions.

This page covers the most important things to know.

---

## 1. Your Seed Phrase is the Master Key

Your **Secret Recovery Phrase** (also called seed phrase or mnemonic) — the 12 or 24 words generated when you create a wallet — is the most critical piece of information in your crypto life.

**Rules:**

- Write it on paper. Store it in a safe, offline location.
- Never type it into any website, Discord bot, Telegram message, or app unless you are *specifically restoring* a wallet on a new device.
- Never photograph it or store it in cloud notes, email drafts, or messaging apps.
- Never share it with anyone. Ever. Under any circumstance.
- There is no legitimate support request that requires your seed phrase. If anyone asks for it, it is a scam.

If someone gets your seed phrase, they have complete and permanent access to every wallet derived from it, including every account inside it. The damage is irreversible.

---

## 2. Token Approvals: The Most Common Attack Vector

When you use a DeFi protocol or NFT marketplace, you often sign a **token approval** — you grant a smart contract permission to spend a certain token from your wallet. This is normal and required.

The danger is:

- **Unlimited approvals**: Some contracts ask for permission to spend an unlimited amount of your tokens. A malicious contract with unlimited approval can drain your entire balance at any time.
- **Approval phishing**: Scam sites disguise malicious approval requests as harmless "sign-in" actions. You think you are logging into a site; you are actually granting permissions to a drainer contract.

**What to do:**

- Always read what a transaction is actually doing before confirming. Rabby Wallet shows a simulation of outcomes before you sign.
- When approving spending limits, set a specific amount rather than "unlimited" where possible.
- Regularly audit and revoke old approvals using [revoke.cash](https://revoke.cash) — it shows every approval you have ever granted and lets you revoke them.
- Never approve a transaction on a site you navigated to from a link in a Discord DM, a tweet, or an unsolicited message.

---

## 3. Verify Contract Addresses Before Interacting

Before sending tokens to a contract or interacting with a new protocol:

- Look up the contract address on [Etherscan](https://etherscan.io) (or the relevant chain's explorer).
- Check that it is **verified** (has a checkmark or visible source code).
- Check for a **security audit** — legitimate projects link to audits from firms like Trail of Bits, OpenZeppelin, or Certik in their docs.
- Check the contract's age and transaction history. A brand-new contract with no history is much higher risk.

When in doubt, search the project's official website or verified social accounts for the contract address. Never trust an address posted in chat.

---

## 4. Watch Out for Signature Phishing

Beyond transaction approvals, there are also **off-chain signatures** — you sign a message with your wallet without sending a transaction. These are used for things like logging into OpenSea or authorizing orders.

Some of these signatures can be malicious:

- **Permit signatures** allow a contract to transfer ERC-20 tokens without a separate approval transaction.
- **SeaPort / Blur / OpenSea signatures** can authorize selling your NFTs for a price you did not intend.
- **"Sign with Ethereum"** on a phishing site can steal your session or authorize hidden actions.

Always check:
- What site you are on (URL bar)
- What the signature message actually says
- Whether you trust the site

If anything looks unusual, reject the signature.

---

## 5. Hot Wallet vs. Cold Wallet Strategy

**Hot wallet**: A wallet connected to the internet (MetaMask, Rabby, etc.). Convenient for daily use. Higher risk exposure.

**Cold wallet**: A hardware wallet (Ledger, Trezor, GridPlus Lattice1). Private keys are stored offline on the device. Transactions must be physically confirmed on the device — a compromised computer cannot sign without it.

**Recommended setup for anyone with significant holdings:**

- Use a hot wallet for small amounts and everyday activity (minting, trading, DeFi).
- Use a hardware wallet (connected to MetaMask or Rabby) for holding valuable NFTs and larger token balances.
- Keep your most valuable assets on the cold wallet. Never interact with unknown contracts using it.

---

## 6. Scams That Target Web3 Users

**Impersonation DMs**: Scammers create fake Discord and Twitter/X accounts impersonating project admins, MetaMask support, or Pixel Journey team members. They will DM you about a "problem with your wallet" or a "limited-time opportunity". Legitimate projects do not DM you first.

**Fake minting sites**: Scammers create near-identical copies of legitimate minting pages with slightly altered URLs. Always navigate to the official site by searching for it or using a verified link — never click links from unknown sources.

**Fake airdrops**: You receive an NFT or token you did not buy. Attempting to interact with it (sell it, burn it) can trigger a drainer contract. If you receive an unknown airdrop, do not interact with it.

**Discord server hacks**: Even official project Discord servers get hacked. A "mint announcement" in an official Discord channel is not automatically trustworthy — always verify via the project's official Twitter/X and website.

**Pig butchering**: Long-term social engineering scams where the attacker builds a relationship over weeks before introducing a fake investment platform. Any "investment opportunity" from someone you met online should be treated with extreme skepticism.

---

## 7. Quick Reference Checklist

Before interacting with any new site or contract:

- [ ] Is the URL correct? Check character by character.
- [ ] Did I navigate here myself, or follow a link from a DM or chat?
- [ ] Is the contract verified on the block explorer?
- [ ] Do I understand what I am approving?
- [ ] Have I simulated the transaction (Rabby) or at minimum read the full details?
- [ ] Is the spending limit reasonable, not unlimited?
- [ ] Does this feel off in any way? (Trust your instincts — if it does, stop.)

---

## Useful Security Tools

- [revoke.cash](https://revoke.cash) — Audit and revoke ERC-20 approvals and NFT operator approvals
- [Etherscan Token Approval Checker](https://etherscan.io/tokenapprovalchecker) — Ethereum approval checker
- [Rabby Wallet](https://rabby.io) — Built-in transaction simulation and risk scanning
- [Pocket Universe](https://www.pocketuniverse.app) — Browser extension that simulates transactions before you sign (works alongside MetaMask)
- [Fire Extension](https://www.joinfire.xyz) — Similar transaction simulation extension
- [Scam Sniffer](https://www.scamsniffer.io) — Real-time phishing detection

Be safe out there. The Pixel Journey community is also here to help — if something looks suspicious, ask in Discord before acting.
