# 🎵 Rhythm Master – Beta

**Rhythm Master** is a blockchain-powered rhythm game built on **WAX**, combining skill-based gameplay, NFTs, and seasonal competition.  
This repository contains the live beta implementation.

---

## 🚀 Current Features

### 🎮 Core Gameplay
- 5-lane rhythm gameplay (keyboard + pointer support)
- Dynamic note spawning synced to audio or video
- Accurate hit detection with timing windows
- Score & combo-based progression
- Visual feedback:
  - SUBLIME / GREAT / OK / MISS judgements
  - Lane flashes, sparks, screen shake
  - Multiplier pickups (x2, x3)

---

### 🔥 Combo System
Combos are earned **only from GREAT and SUBLIME hits**.

| Combo | Display |
|------|--------|
| x5   | **NICE COMBO!** (green) |
| x10  | **GREAT COMBO!** (blue) |
| x20  | **AMAZING COMBO!** (larger text) |
| x30  | **SUBLIME COMBO!** (pink) |
| x50  | **RHYTHM MASTER!** (large gold text) |

- Combo celebrations appear centered for ~2 seconds
- Combo resets on MISS or OK

---

### 🎧 Media Support
- **Audio tracks via IPFS**
- **Video-only or Audio-only NFTs supported**
- Automatic IPFS gateway fallback:
  - Pinata
  - Cloudflare
  - ipfs.io
- Media auto-unmutes once gameplay starts

---

### 🧠 NFT Integration
- Tracks are loaded from the `sublimesound` AtomicAssets collection
- NFTs are deduplicated by **template ID**
- Supports:
  - `audio`
  - `video / animation_url`
  - `image`
- Track selector populated dynamically from owned NFTs

---

### 🏆 Leaderboards (Server-Side)
- Powered by **Supabase**
- Per-season & per-track leaderboards
- Stores:
  - Best score
  - Max combo
  - Autograph flag (future use)
- Only higher scores overwrite previous entries

---

### 💰 Payments & Economy
- **100 SSN per track play** (non-admin users)
- Admin accounts bypass payment
- Payment handled via:
  - WAX Cloud Wallet
  - Anchor Wallet
- Transaction links provided after payment
- Payment resets per track change

---

### Wallet Support
- ✅ WAX Cloud Wallet
- ✅ Anchor Wallet

---

### 🔐 Season Pass (Toggleable)
- Season Pass logic is present but **currently disabled**
- Controlled via:
```js
const ENABLE_SEASON_PASS = false;
