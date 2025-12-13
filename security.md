# Security Policy

## Supported Versions

The following versions of **Sublime Sounds – Rhythm Master** are currently supported with security updates:

| Version | Supported |
|--------|-----------|
| `main` | ✅ Yes |
| `develop` | ⚠️ Best effort |
| Archived / older releases | ❌ No |

Only the latest version on the `main` branch is guaranteed to receive security fixes.

---

## Reporting a Vulnerability

If you discover a security vulnerability, **please do not open a public issue**.

Instead, report it responsibly using one of the methods below:

### 📧 Private Disclosure
Email: **simon@sublime-sound.com*  
*(replace with your real contact email)*

Include as much detail as possible:
- Description of the vulnerability
- Steps to reproduce
- Affected files or features
- Potential impact (if known)
- Screenshots or proof-of-concept (if available)

You can request attribution or remain anonymous.

---

## What Counts as a Security Issue

We consider the following to be **security vulnerabilities**:

- Wallet authentication or login bypass (WAX Cloud Wallet)
- Unauthorized blockchain transactions
- Manipulation of game state affecting payments or rewards
- XSS, injection, or DOM-based attacks
- Token transfer exploits (SSN or other tokens)
- NFT asset spoofing or metadata manipulation
- Sensitive data exposure via localStorage or APIs

---

## Out of Scope

The following are **not considered security issues**:

- Client-side score manipulation (local-only leaderboards)
- Cosmetic bugs or visual glitches
- Game balance issues
- Performance problems
- Feature requests

---

## Web3 / Blockchain Disclaimer

This game uses:
- **WAX Cloud Wallet**
- **Client-side JavaScript**
- **Public blockchain transactions**

Users are responsible for:
- Securing their own wallets
- Reviewing transactions before signing
- Understanding that blockchain actions are irreversible
