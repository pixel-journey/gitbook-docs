# 🛠️ Developer Guides for XPR Network

> **⚠️ Important Note for Developers**  
> The XPR Network ecosystem continues to evolve with a focus on payments, identity, and efficient DeFi. Always use modern, actively maintained tools and follow current best practices. This guide focuses on safe, future-proof development.

Welcome to the Developer Guides for XPR Network. This section helps developers build safely and efficiently, with awareness of how XPR complements the broader Pixel Journey multi-chain vision.

## Introduction

XPR Network offers fast, low-cost (often feeless) experiences, making it attractive for payments, identity solutions, and DeFi experimentation. While smaller than WAX in terms of gaming/NFT activity, it provides valuable learning opportunities and efficient tooling within the Antelope family.

Pixel Journey tools are designed with cross-chain compatibility in mind, and understanding XPR development helps prepare for future PxPortals and PxPackages expansions.

## Best Practices for XPR Development

### 1. Use Modern Libraries — Wharf Kit Recommended

**Wharf Kit** remains the strongly recommended standard for interacting with XPR and other Antelope chains.

- It is actively maintained and secure.
- It provides excellent session management and multi-wallet support.
- It works well across WAX, XPR, Vaulta, and other Antelope chains.

**Deprecated / Avoid for New Projects**:
- **eosjs** — Long deprecated. Do not use for new development.
- **AnchorLink** — Deprecated in favor of modern alternatives.

**Recommendation**: Use **Wharf Kit** for all new XPR development.

### 2. Wallet Integration

- Prefer **Anchor** wallet via Wharf Kit for the best user experience.
- Support hardware wallets where possible for higher-value applications.
- Leverage session-based authentication for improved security and UX.

### 3. Smart Contract Development

- Use the latest Antelope development tools and CDT versions.
- Follow secure coding practices and test thoroughly on testnets.
- Be mindful of XPR's focus on payments and identity when designing contracts.

### 4. Security Best Practices

- Never hardcode private keys.
- Validate all inputs and contract interactions.
- Implement proper error handling.
- Keep dependencies up to date.
- Be cautious with permissions and approvals.

### 5. Pixel Journey Integration

- When building tools that may interact with Pixel Journey assets or users, follow modern standards for consistency.
- Consider how your dApp can integrate with PxWallet or future PxPortals for cross-chain experiences.
- Use efficient, low-cost mechanics that align with XPR's strengths.

### 6. General Development Recommendations

- Use TypeScript for better developer experience and type safety.
- Write clean, well-documented, and testable code.
- Follow official XPR and Antelope documentation.
- Stay active in trusted developer communities.

## Getting Started as a Developer on XPR

1. Set up your environment with the latest tools.
2. Install and explore **Wharf Kit** for wallet and chain interactions.
3. Build a simple test dApp or script focused on XPR's efficient mechanics.
4. Test thoroughly on XPR testnet.
5. Review how XPR can complement WAX-based Pixel Journey activities.

## Pixel Journey Relevance

XPR provides valuable lessons in efficient, low-cost chain design. As we expand PxPackages and PxPortals, understanding XPR development helps create better cross-chain experiences for users who want to move seamlessly between WAX (primary focus) and complementary chains like XPR.

*Educational content only. Development involves real risks and responsibilities. Always DYOR and follow security best practices. Not financial advice.*