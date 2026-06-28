# 🛠️ Developer Guides for WAX (Antelope)

> **⚠️ Important Note for Developers**  
> The WAX/Antelope ecosystem has evolved significantly. Many older libraries and tools are now deprecated. Always use modern, actively maintained tools and follow current best practices. This guide focuses on safe, future-proof development.

Welcome to the Developer Guides for WAX and the broader Antelope ecosystem. This section is designed to help developers build safely, efficiently, and in alignment with Pixel Journey's multi-chain vision.

## Introduction

WAX remains one of the most developer-friendly Antelope chains, especially for gaming, NFTs, and creator economies. However, the ecosystem has matured, and modern development practices are essential for security, performance, and maintainability.

Pixel Journey's own tools (PxWallet, PxPackages, PxPortals, etc.) are built with modern standards in mind, and we strongly encourage developers to follow similar approaches when building on WAX or integrating with our ecosystem.

## Best Practices for WAX / Antelope Development

### 1. Use Modern Libraries — Wharf Kit is Strongly Recommended

**Wharf Kit** is the current recommended standard for interacting with WAX and Antelope chains.

- It is actively maintained, secure, and designed for modern dApp development.
- It replaces older, deprecated libraries.
- It offers excellent support for session management, signing, and multi-wallet experiences.

**Deprecated / Avoid for New Projects**:
- **eosjs** — Long deprecated. Do not use for new development.
- **AnchorLink** — Deprecated in favor of modern alternatives.
- Any unmaintained or legacy EOSIO-era libraries.

**Recommendation**: Start every new WAX/Antelope project with **Wharf Kit**.

### 2. Wallet Integration

- Prefer **Anchor** wallet integration via Wharf Kit for the best user experience on WAX.
- Support hardware wallets (Ledger) where possible for higher-value applications.
- Use session-based authentication for better security and UX.

### 3. Smart Contract Development

- Use the latest versions of CDT (Contract Development Toolkit) or modern alternatives.
- Follow secure coding practices (checks-effects-interactions, proper authorization, resource management).
- Test thoroughly on testnets before mainnet deployment.
- Consider using established frameworks and audit your contracts when handling significant value.

### 4. Security Best Practices

- Never hardcode private keys.
- Validate all user input and contract interactions.
- Implement proper error handling and user feedback.
- Regularly audit dependencies and keep libraries up to date.
- Be extremely cautious with permissions and approvals in your dApp.

### 5. Pixel Journey Integration

- When building tools that interact with Pixel Journey assets (Pixals, ingredients, PxHot, etc.), use official or well-documented APIs and standards.
- Consider how your dApp can integrate with PxWallet, PxMarket, or future PxPortals for seamless cross-chain experiences.
- Follow Pixel Journey's design principles for consistency when creating user-facing interfaces.

### 6. General Development Recommendations

- Write clean, well-documented, and testable code.
- Use TypeScript for better type safety and developer experience.
- Follow the official WAX and Antelope documentation for the latest updates.
- Stay active in trusted developer communities and follow official channels for announcements.

## Getting Started as a Developer on WAX

1. Set up your development environment with the latest tools.
2. Install and explore **Wharf Kit** for wallet and chain interactions.
3. Build a simple test dApp or script to familiarize yourself with modern patterns.
4. Review Pixel Journey's own open-source patterns where available for inspiration.
5. Test thoroughly on WAX testnet before moving to mainnet.

## Pixel Journey Relevance

As we expand PxPackages, PxPortals, and our multi-chain ecosystem, having strong, modern developer tooling on WAX is foundational. By following these best practices, you help create a safer, more consistent experience for users across the Pixel Journey ecosystem.

We welcome developers who want to build on WAX while aligning with Pixel Journey's vision of safe, user-friendly, and cross-chain experiences.

*Educational content only. Development involves real risks and responsibilities. Always DYOR and follow security best practices. Not financial advice.*