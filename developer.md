# Rhythm Master – Developer Notes

This document is intended for developers and contributors.

---

## 🧱 Architecture Overview

- Frontend: Vanilla HTML / CSS / JavaScript
- Wallets:
  - WAX Cloud Wallet (waxjs)
  - Anchor Wallet (anchor-link)
- NFTs: AtomicAssets API
- Media: IPFS with multi-gateway fallback
- Backend: Supabase (leaderboards)

---

## 🔐 Wallet Logic

- `walletType` controls transaction flow
- Anchor and WAX share the same transfer structure
- Admin accounts bypass:
  - SSN payments
  - Restart limits

---

## 💰 Payment Flow

1. User selects a track
2. Pays **100 SSN**
3. `paidForThisTrack = true`
4. Grants:
   - 1 full run
   - 3 free restarts

Payments are **per track**, not per session.

---

## 🔁 Restart Logic

Key flags:
- `restartAttempts`
- `MAX_RESTARTS`
- `allowFreeRestart`
- `suppressScoreSubmit`

Rules:
- Restarts do not submit scores
- Restart counter resets only on a new paid run
- UI payment prompts are suppressed during free restarts

---

## 🎵 Timing & Sync

- Notes are spawned using absolute timestamps
- Dynamic speed affects **visual movement only**
- Beat sync remains intact

Speed formula example:
```js
const progress = Math.min(1, now / duration);
const speed = BASE_SPEED + progress * SPEED_RAMP;
