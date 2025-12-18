# 🎵 Rhythm Master – Beta

**Rhythm Master** is a blockchain-powered rhythm game built on **WAX**, featuring NFT-based tracks, skill-based scoring, and seasonal competition.

This repository contains the live beta version currently undergoing community testing.

---

## 🚀 Features

### 🎮 Core Gameplay
- 5-lane rhythm gameplay (keyboard & touch supported)
- Real-time scoring with accuracy-based judgments:
  - SUBLIME!
  - GREAT!
  - OK
  - MISS
- Combos build only on **GREAT!** and **SUBLIME!** hits
- Visual effects for hits, combos, and multipliers

### 🔁 Restart System
- Each paid track run allows **up to 3 free restarts**
- Restarts:
  - Do not submit scores
  - Do not require SSN payment
- After retries are exhausted, payment is required again

### 🎯 Combo Milestones
| Combo | Message |
|------:|---------|
| x5 | NICE COMBO! |
| x10 | GREAT COMBO! |
| x20 | AMAZING COMBO! |
| x30 | SUBLIME COMBO! |
| x50 | RHYTHM MASTER! |

---

## 💰 Economy & Access

### SSN Payments
- **100 SSN per track run**
- Payment required again after a completed run
- Admin users bypass payments

### Season Pass (Configurable)
- Season Pass requirement can be enabled/disabled via config
- When enabled, a valid NFT is required to play

---

## 🧠 NFTs & Media
- Tracks are loaded from **AtomicAssets NFTs**
- Supported media:
  - Audio (IPFS)
  - Video (IPFS)
  - Image fallback for backgrounds
- IPFS gateway fallback ensures resilience
- Duplicate templates are filtered automatically

---

## 🔐 Wallet Support
- WAX Cloud Wallet
- Anchor Wallet
- Wallet UI locks after successful login
- Wallet badge shows active wallet type

---

## 🏆 Leaderboards
- Server-side leaderboard using Supabase
- Scores are stored per:
  - Season
  - Track
  - User
- Only highest score per user is kept
- Restart attempts never submit scores

---

## 📱 Mobile Support
- Touch input optimized
- Fullscreen gameplay on track start
- Orientation hint shown for portrait mode
- Mobile timing forgiveness enabled

---

## ⚙️ Configuration Flags

```js
const ENABLE_SEASON_PASS = false;
const SSN_AMOUNT = "100.00000000";
const MAX_RESTARTS = 3;
const HIT_WINDOW = 0.18;

## ⚙️ **Beta Disclaimer**

Rhythm Master is currently in beta.
Gameplay mechanics, balance, and UI are subject to change based on testing feedback.

Blockchain transactions are irreversible — always verify wallet prompts carefully.

🧠 **Credits**

Built by Sublime Sounds
Powered by WAX, SSN, and AtomicAssets
