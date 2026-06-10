---
description: >-
  Security on Solana is your personal responsibility. Transactions are
  irreversible, and the ecosystem has its own unique attack vectors. Read
  this before interacting with anything.
---

# Solana Security Tips

Solana's speed and open nature also make it a target for scammers. The most common ways people lose assets on Solana are not technical exploits of the blockchain itself — they are social engineering, phishing, and blindly approving malicious transactions. The principles are similar to EVM security, but Solana has some unique attack patterns worth knowing.

---

## 1. Your Seed Phrase is Everything

Your **Secret Recovery Phrase** (12 or 24 words) is the master key to your wallet and every account inside it. The same rules that apply everywhere in Web3 apply here:

- Write it on paper. Store it somewhere safe, offline.
- Never photograph it or store it in cloud notes, email, messaging apps, or anywhere digital.
- Never type it into any website, bot, or app unless you are *explicitly restoring* your wallet on a new device.
- No legitimate team member, moderator, or support agent will ever ask for your seed phrase. Anyone who does is running a scam.

If someone obtains your seed phrase, they have complete and permanent access to all of your SOL, tokens, and NFTs. The damage is instant and irreversible.

---

## 2. Transaction Approvals and Simulations

Every time you interact with a Solana program, you sign a transaction. This is normal. The danger is in approving transactions you do not understand.

**What to do:**

- Always read what a transaction is doing before confirming. Your wallet will show a summary of what is being transferred.
- **Phantom** shows a transaction simulation (what assets leave and arrive) for many interactions — pay attention to it.
- If a transaction claims to be a simple "confirm" or "verify" but the wallet shows assets leaving, reject it immediately.
- Never confirm a transaction on a site you arrived at via an unsolicited link.

---

## 3. Spam NFTs: Do Not Interact With Them

Solana makes it very cheap to airdrop NFTs to any wallet address. Scammers exploit this to flood wallets with spam NFTs — often with names like "You won 500 SOL" or "Claim your reward" with a link in the description.

**Rules for spam NFTs:**

- Never click links embedded in unknown NFT metadata.
- Never attempt to list, sell, burn, or transfer an NFT you received without requesting if you are not sure it is safe. Some have malicious logic that triggers when you interact with them.
- To safely remove spam NFTs, use the **burn** feature in Solflare or [sol-incinerator.com](https://sol-incinerator.com) — this reclaims the rent deposit and removes the NFT without interacting with any external contract.

---

## 4. Fake Minting and Phishing Sites

Scammers create near-perfect copies of legitimate Solana minting pages, NFT marketplaces, and DeFi protocols, with slightly altered URLs. A single character difference in the domain can be invisible at a glance.

**Checklist before connecting your wallet to any site:**

- Check the full URL character by character. Look for substitutions like `rn` for `m`, extra hyphens, or `.xyz` in place of `.io`.
- Did you navigate here yourself from a trusted bookmark or the official social account, or did you follow a link from a DM, tweet, or Discord chat? If the latter — stop and verify.
- Look up the project's official website from their verified Twitter/X or Discord before connecting.

---

## 5. Discord and Social Impersonation

Solana projects are frequently targeted by impersonators on Discord and Twitter/X:

- Fake accounts copy the name, profile picture, and posting style of project founders or admins.
- They DM users about "limited mints", "wallet verification", or "support issues" — all designed to get you to a phishing site or reveal your seed phrase.
- Even official Discord servers get compromised. A message in an #announcements channel is not automatically trustworthy — always cross-reference with the project's official Twitter/X.

Legitimate Pixel Journey team members will never DM you first about a wallet issue or ask you to sign anything unprompted.

---

## 6. Hot vs. Cold Wallet Strategy

The same hot/cold principle from EVM applies on Solana:

- **Hot wallet** (Phantom, Solflare, etc.): Use for daily activity — minting, trading, DeFi. Keep only what you need for active use.
- **Cold wallet** (Ledger with Phantom or Solflare): For long-term storage of valuable SOL and NFTs. Requires physical button confirmation for every transaction — a compromised computer or browser extension cannot sign without it.

Phantom and Solflare both support Ledger for Solana. The setup takes 10 minutes and is one of the highest-impact security upgrades you can make.

---

## 7. Common Solana Scam Patterns

**Fake Jupiter / DEX sites**: Scammers clone aggregator sites. Always use [jup.ag](https://jup.ag) directly — bookmark it.

**"Free SOL" bot claims**: Any bot or DM promising free SOL for connecting your wallet is a drainer. Your wallet's "Connect" permission does not give access to your funds — but a subsequent "Approve" transaction can.

**Compromised project Discord mint links**: Even verified Discord servers have been hacked to post malicious mint links during real launches. Verify mint links on the project's Twitter/X before using them.

**Rug pulls**: New Solana tokens and NFT projects carry significant risk of being abandoned or fraudulent. Research teams and contracts before investing. Use [RugCheck](https://rugcheck.xyz) to scan token contracts for red flags.

---

## 8. Quick Reference Checklist

Before interacting with any new site, token, or NFT:

- [ ] Is the URL exactly correct, character by character?
- [ ] Did I navigate here myself, or follow an unsolicited link?
- [ ] Does the transaction preview show what I expect — nothing unexpectedly leaving my wallet?
- [ ] Is this a known and established project, or something brand new with no track record?
- [ ] Have I checked the project's official social accounts to verify this is a real event?

---

## Useful Security Tools

- [Sol Incinerator](https://sol-incinerator.com) — Burn spam NFTs and reclaim rent
- [RugCheck](https://rugcheck.xyz) — Token contract risk scanner for Solana
- [Blowfish](https://blowfish.xyz) — Transaction simulation and phishing protection
- [Solana Explorer](https://explorer.solana.com) — Verify any transaction or program address
- [Step Finance](https://step.finance) — Portfolio tracker with spam token filtering

Stay safe out there — and when in doubt, ask in the Pixel Journey Discord before taking any action.
