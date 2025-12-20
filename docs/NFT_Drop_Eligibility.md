# 🎟️ NFT Eligibility & Drop Rules  
**Rhythm Master – Sublime Sounds**

This document defines how rare in-game NFT drops work, who is eligible, and how abuse is prevented.  
NFT drops are designed as **surprise rewards**, not guaranteed payouts.

---

## 🎮 Overview

During gameplay, a **rare special note** labeled **“NFT”** may appear.

- The note is visually distinct (green bar with “NFT” label)
- It behaves similarly to multiplier notes
- Hitting it correctly may grant a **Sublime Sounds NFT**

NFT drops are:
- **Extremely rare**
- **Skill-gated**
- **Capped per season**
- **Protected against bots and abuse**

---

## ✅ Eligibility Requirements

A player is eligible for an NFT drop only if **all** of the following are true:

### 1. Wallet Requirements
- Logged in via **WAX** or **Anchor**
- Wallet address is valid and active
- Wallet is **not flagged** for abuse

### 2. Gameplay Requirements
- NFT note must be hit with:
  - **GREAT** or **SUBLIME** timing
- Misses or OK hits do **not** trigger eligibility
- Game must be played normally (no restart exploit)

### 3. Session Rules
- NFT drops are **disabled during free restarts**
- Score must be eligible for leaderboard submission
- Only one NFT can be earned per session

---

## 🎲 Drop Probability

NFT notes are spawned with **very low probability**:

| Parameter | Value |
|---------|------|
Spawn chance per note | ~0.1–0.2%
Max NFT drops per player per day | 1
Max NFT drops per wallet per season | 3
Global season cap | Configurable (e.g. 50–100 NFTs)

> NFT drops are **not guaranteed**, even if the note appears.

---

## 🧠 Anti-Abuse Safeguards

To protect the ecosystem, the following safeguards apply:

### Rate Limiting
- One NFT award attempt per wallet per session
- Cooldown enforced between successful drops

### Skill Gating
- Requires GREAT or SUBLIME timing
- Combo-based play strongly favored

### Restart Protection
- NFT drops disabled during:
  - Free restarts
  - Retry abuse scenarios

### Bot Detection (Server-Side)
- Unrealistic hit accuracy flags
- Impossible reaction time detection
- Repeated failed NFT-note hits tracked

Flagged wallets may be:
- Temporarily blocked from NFT drops
- Permanently excluded from future rewards

---

## 🧾 Recording & Transparency

Each NFT drop attempt is logged server-side with:

- Wallet address
- Timestamp
- Track name
- Judgement (GREAT / SUBLIME)
- Result (success / fail)
- NFT ID (if awarded)

This ensures:
- Full auditability
- Fair distribution
- DAO-level transparency

---

## 🧱 NFT Source & Distribution

- NFTs are transferred from the **project wallet**  
  `a1hd.wam`
- NFTs belong to the **Sublime Sounds collection**
- Transfer occurs **server-side only**
- No private keys are exposed client-side

---

## ⚠️ Important Disclaimers

- NFT drops are **not guaranteed**
- NFTs have **no promised financial value**
- Drops may be paused, adjusted, or disabled per season
- Abuse or exploits result in permanent disqualification

---

## 🛠️ Future Extensions (Planned)

- Autographed NFT variants
- Artist-specific NFT drops
- Seasonal NFT themes
- DAO-voted NFT rarity adjustments

---

**Rhythm Master is built to reward skill, not automation.**  
Play fair, play hard, and let the rhythm decide 🎶
