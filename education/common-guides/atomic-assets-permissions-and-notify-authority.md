# 🔐 Atomic Assets Permissions & Notify Authority on WAX

> **Important Note for Collection Owners**
> This page explains collection-level permissions on WAX's Atomic Assets standard, with special focus on **notify authority**. This is different from regular token spending approvals.

## What Are Collection-Level Permissions?

On WAX, when you create an Atomic Assets collection, you (as the collection owner) have full control. However, you can grant certain **authorities** or permissions to other accounts or smart contracts. These are powerful on-chain rights.

The most commonly discussed one is **notify authority**.

## What is Notify Authority?

Notify authority allows another account or contract to receive notifications and potentially trigger certain on-chain actions related to your collection. This is often used for advanced features such as:

- Automatic reactions to transfers or mints
- Integration with other platforms or games
- Inline actions and complex mechanics

## Potential Risks of Granting Notify Authority

While notify authority is a legitimate and useful feature, it comes with risks:

- The authorized account/contract can potentially perform actions that affect your collection (for example, in some cases blocking transfers or triggering other on-chain behavior).
- If the authorized contract is compromised or malicious, it could cause problems for your collection and its holders.
- This is **not** the same as a simple token approval — it operates at the collection level.

**Important**: This is not a commonly exploited attack vector, but it is something collection owners should understand.

## Best Practices for Collection Owners

- Only grant notify authority when you fully understand the tool or contract and trust it.
- Regularly review which accounts/contracts have notify authority on your collections.
- As the collection owner, you can **remove** any account from notify authority at any time if something feels off.
- If you're unsure whether a feature needs notify authority, start without it and only enable it when truly necessary.
- Be extra cautious with new or lesser-known tools that request this permission.

## How to Check and Remove Notify Authority

You can check current authorities on your collection using explorers like **waxblock.io** or **EOSAuthority**. If you need to remove an account from notify authority, you can do so through the collection management interface of your chosen creator tool or via direct smart contract action.

## When Is Notify Authority Actually Needed?

Many advanced creator tools and games use notify authority for smooth user experiences (e.g., automatic crafting, breeding reactions, or cross-contract mechanics). It is often legitimate — but you should always understand *why* a tool is asking for it.

## Summary

- Notify authority is a powerful collection-level permission.
- It enables advanced features but carries some risk.
- Only grant it when necessary and to trusted contracts.
- You can always revoke it later as the collection owner.
- This is different from regular token spending approvals.

*This is educational content. Always DYOR and be cautious when managing collection permissions.*