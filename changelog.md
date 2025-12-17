# Changelog (17/12/25)

All notable changes to **Rhythm Master** will be documented in this file.

---

## [Unreleased]

### Added
- 🎵 **Free Restart System**
  - Players may restart the same track **up to 3 times** without repaying SSN.
  - Restart counter displayed in HUD.
  - Restart button disappears after all retries are exhausted.
  - Admin users have unlimited restarts.

- 🔁 **Restart Visual Counter**
  - HUD shows remaining restarts (e.g. `Restarts left: 2 / 3`).
  - Counter dims when no restarts remain.

- 🔥 **Combo Milestones**
  - x5 → NICE COMBO!
  - x10 → GREAT COMBO!
  - x20 → AMAZING COMBO!
  - x30 → SUBLIME COMBO!
  - x50 → RHYTHM MASTER!
  - Combo celebrations appear center-screen with animated glow.

- 🎯 **Combo Logic Update**
  - Combos now increment **only on GREAT and SUBLIME hits**.
  - Combo resets on OK or MISS.

- ✨ **Dynamic Multiplier UI**
  - x1 shown in neutral circle.
  - x2 activates pulsing yellow multiplier circle.
  - x3 activates glowing red multiplier circle.
  - Visuals persist only while multiplier is active.

- 🐢➡️⚡ **Dynamic Note Speed**
  - Notes fall slightly slower at the start of a track.
  - Speed gradually increases over time.
  - Beat timing remains unchanged (pure visual scaling).

- 🎥 **Video-Only Track Support**
  - Tracks with video but no audio now play correctly.
  - Beat timing derived from video duration.

- 🔊 **Audio Autoplay Fix**
  - Ensures audio and video unmute correctly on user interaction.
  - Prevents muted playback after restart or login.

- 🧠 **IPFS Gateway Fallback System**
  - Automatic fallback across multiple IPFS gateways for audio, video, and images.
  - Improves reliability and load success for NFT media.

- 🧩 **NFT De-duplication**
  - Prevents duplicate tracks by template ID.
  - Upgrades missing images if a later asset provides one.

- 🔐 **Wallet Improvements**
  - Anchor Wallet support added alongside WAX Cloud Wallet.
  - Login buttons correctly disable during gameplay.

- 🏆 **Leaderboard Improvements**
  - Scores only submitted on completed runs.
  - Restarted runs do NOT submit scores.
  - Higher score always preserved per user/track/season.

---

### Fixed
- 🐞 Restarting no longer consumes SSN.
- 🐞 Payment message no longer shows during free restarts.
- 🐞 Combo counter no longer increments on OK hits.
- 🐞 Blinking text cursor removed globally.
- 🐞 Lanes disappearing bug resolved.
- 🐞 Muted playback bug resolved.
- 🐞 Anchor blockchain ID configuration issue resolved.
- 🐞 Duplicate NFT track entries resolved.
- 🐞 Leaderboard submission triggering incorrectly on restart fixed.

---

### Changed
- Restart logic refactored to cleanly separate:
  - Paid runs
  - Free restarts
  - Exhausted retry states

# 📝 Changelog – Rhythm Master (17/12/25)

## 🚀 New Features

### 🎮 Gameplay & Scoring
- Added **combo-based celebration system** with animated on-screen text:
  - **5x Combo** → *NICE COMBO!* (green)
  - **10x Combo** → *GREAT COMBO!* (blue)
  - **20x Combo** → *AMAZING COMBO!* (larger text)
  - **30x Combo** → *SUBLIME COMBO!* (large pink)
  - **50x Combo** → *RHYTHM MASTER!* (legendary, gold)
- Combo celebrations display centrally with glow + fade animation (~2s).
- Combos now **only build from GREAT and SUBLIME hits**.
- Combo counter resets correctly on OK / MISS hits.
- Score calculation adjusted to weight:
  - SUBLIME > GREAT > OK
- Multiplier notes (x2 / x3) visually enhanced and fully integrated with scoring.

### 🎵 Media & IPFS
- Robust **IPFS gateway fallback system** for audio and video:
  - Multiple Pinata + Cloudflare + ipfs.io gateways
- Supports **audio-only**, **video-only**, and **audio+video** NFTs.
- Automatic unmute handling on game start to avoid silent playback.
- Improved video-only track startup reliability.

### 🧾 Payments & Economy
- **Per-track SSN payment system**:
  - Non-admin users must pay **100 SSN per track play**
  - Payment resets when switching tracks
- Admin accounts bypass payment logic entirely.
- Improved SSN payment UX:
  - Disabled buttons during processing
  - Success + fallback confirmation handling
- Added transaction link to WaxBlock explorer after payment.

### 👛 Wallet Support
- Dual wallet support:
  - **WAX Cloud Wallet**
  - **Anchor Wallet**
- Separate login buttons for WAX and Anchor.
- Unified gameplay flow regardless of wallet type.
- Wallet buttons disabled appropriately during gameplay to prevent conflicts.

### 🏆 Leaderboards (Server-Side)
- Migrated leaderboard from localStorage to **Supabase backend**.
- Server-side leaderboard features:
  - Per-season
  - Per-track
  - Top 10 ranking
  - Stores score, max combo, and user account
- Only higher scores overwrite existing entries.
- Leaderboard auto-refreshes on track change and game end.

### 🎨 UI / UX Improvements
- Centralized combo overlay layer (always on top).
- Improved visual feedback for:
  - SUBLIME / GREAT / OK / MISS
  - Lane hit animations
  - Screen shake on SUBLIME hits
- Disabled login buttons during active gameplay.
- Cleaner game-over flow with restart support.

---

## 🐛 Bug Fixes

- Fixed muted audio/video on game start.
- Fixed video-only tracks not starting gameplay.
- Fixed combo counter incrementing on incorrect hits.
- Fixed leaderboard not updating after game end.
- Fixed duplicate NFTs appearing in track list by:
  - De-duplicating via **template_id**
  - Merging media fields safely
- Fixed repeated note DOM buildup by clearing notes on game end.
- Fixed payment flow edge cases where WaxJS throws after successful transaction.
- Improved orientation pause/resume stability on mobile.

---

## ⚙️ Configuration & Toggles

- Added `ENABLE_SEASON_PASS` flag to quickly enable/disable season pass checks.
- Admin list centralized for easier permission control.
- Improved IPFS CID normalization across all NFT schemas.

---

## ⚠️ Known Issues / Work in Progress

- Anchor Wallet may show **“Unknown Blockchain ID”** warnings depending on chain configuration.
- Anchor chain handling requires further stabilization and testing.
- Some edge-case NFT schemas may still require manual mapping.
- Server-side leaderboard anti-cheat and validation pending.

---

## 🗺️ Coming Next
- Autographed NFT score modifiers
- Fair play / advantage disclosure
- Season-based rewards & DAO integration
- Hardened Anchor wallet flow
- Anti-cheat validation on leaderboard submissions

# 📝 Changelog / Patch Notes (16/12/25)

## [Beta] – Current Development Cycle

### ✅ Added
- GREAT + SUBLIME combo eligibility
- Combo milestone celebrations (10 / 20 / 30)
- Per-track SSN payment system
- Admin bypass for payments
- Season pass toggle flag
- Video-only NFT track support
- IPFS multi-gateway fallback
- Per-template NFT de-duplication
- Improved mobile orientation handling

---

### 🐞 Fixed
- Muted audio/video on start
- Duplicate NFT track listings
- Video-only tracks not starting
- WaxJS false-negative payment errors
- Combo counter desync
- Background image fallback issues
- Login UI lockups after gameplay

---

### ⚙️ Changed
- Combo logic simplified & more forgiving
- GREAT hits now count toward combos
- Cleaner admin vs player permission logic

---

### 🧪 Known Issues
- Some NFT images missing metadata (to be resolved)
- Certain AtomicAssets schemas incomplete

---

More updates coming soon.

# 🎵 Sublime Sounds – Rhythm Master  
## Development Log / Changelog (16/12/25)

---

## ✅ New Features

### 🎮 Gameplay Enhancements
- **Combo Celebrations Added**
  - `10x SUBLIME hits` → **GREAT COMBO!** (blue)
  - `20x SUBLIME hits` → **AMAZING COMBO!** (larger blue)
  - `30x SUBLIME hits` → **SUBLIME COMBO!** (large pink)
  - Animations display center-screen for ~2 seconds
  - Uses dedicated overlay layer to ensure visibility above all UI

- **SUBLIME-Only Combo Logic**
  - Combo counter **only increases on SUBLIME hits**
  - OK / MISS immediately resets combo
  - Combo milestone tracking prevents duplicate celebration spam

- **Improved Hit Feedback**
  - Stronger visual feedback for SUBLIME hits
  - Refined screen shake + spark effects

---

## 💳 Payment System Improvements

### Per-Track Payment Logic
- Users must pay **100 SSN per track**
- Payment resets when switching tracks
- Payment required again after each completed game (non-admins)

### Admin Bypass
- Admin wallets:
  - Bypass SSN payment
  - Payment button hidden
  - Start button always enabled

### Payment UX Improvements
- Pay button disabled while processing
- Success/failure feedback added
- Transaction link displayed on success

---

## 🔐 WAX Login & Session Handling

- Fixed incorrect wallet assignment
  - Switched to `wax.userAccount` (reliable)
- Login button disabled during gameplay
- Login restored after game end
- Improved error handling for failed login attempts

---

## 🎶 Media & Playback Fixes

- **Unmuted Audio on Game Start**
  - Explicit unmute + volume restore for audio & video
- Improved IPFS gateway fallback for audio & video
- Robust handling for:
  - Audio-only tracks
  - Video-only tracks
  - Mixed media tracks

---

## 🖼️ NFT Track Loading Improvements

### AtomicAssets Integration
- Fetches NFTs by:
  - Owner
  - Collection name
- Supports audio, video, animation, and media fields

### Duplicate Prevention
- Tracks deduplicated by **template_id**
- First valid asset per template used
- Later assets can backfill missing image data

### Metadata Handling
- Safely merges:
  - `template.immutable_data`
  - `asset.data`
- Supports:
  - `audio`
  - `video`
  - `animation_url`
  - `image / img / media`

---

## 🧠 Game State Stability

- Notes cleared correctly on:
  - Game end
  - Restart
- Prevents duplicate note spawning
- Fixed paused/resumed state when rotating mobile devices
- Ensured game loop stops cleanly on end

---

## 📱 Mobile & UX Improvements

- Orientation lock overlay added for mobile portrait mode
- Game auto-pauses on invalid orientation
- Touch gestures locked only during gameplay
- Improved button disabling to prevent accidental actions

---

## 🏆 Leaderboard

- Per-track leaderboard keys
- Scores stored locally
- Higher score replaces previous score for same user
- Sorted descending, top 10 only

---

## 🐞 Bugs Fixed

- Muted audio/video on play
- Combo counter incrementing on non-SUBLIME hits
- Duplicate NFTs appearing in track list
- Admins incorrectly required to pay
- Login button active during gameplay
- Notes persisting after game end
- Inconsistent media loading from IPFS gateways

---

## ⚠️ Known Issues (To Address Later)

- Some templates still missing background images
  - Likely inconsistent AtomicAssets metadata
  - Requires deeper per-template inspection
- Some video-only templates still inconsistent across gateways

---

## 🛠️ Next Steps (Planned)

- Alphabetical track sorting
- Improved fallback image logic
- Template-level debugging tool
- Server-side leaderboard
- Visual track previews in selector

# Changelog
All notable changes to **Rhythm Master** will be documented in this file.

This project follows **Semantic Versioning**:  
`MAJOR.MINOR.PATCH`  
and is currently in **Beta**.

---

## [0.9.0] – Beta Release Candidate  
**Status:** Feature-complete beta  
**Date:** 2025-09-15

### Added
- Mobile orientation detection with **pause-on-rotate**
- Full-screen rotate-device overlay during gameplay
- Automatic resume when returning to landscape
- Non-looping video NFT backgrounds (game ends with video)
- START_DELAY before notes spawn
- Multiplier pickup notes (x2 / x3)
- Screen flash effect on multiplier activation
- Restart button on Game Over screen
- Local leaderboard persistence per track & season
- Admin wallet bypass for Season Pass requirement
- Ad slot layout (6 slots + branded placements)
- Dynamic NFT track loading (audio / video / image priority)

### Changed
- Improved mobile touch handling (pointer events only during play)
- Refactored scroll-lock logic to avoid page freeze on mobile
- Gameplay loop now safely pauses during orientation changes
- Start button gated behind Season Pass NFT ownership
- Video NFTs take priority over static images when both exist
- Audio/video playback synced to gameplay loop

### Fixed
- iOS Safari scrolling freeze during gameplay start
- Lost lane hit effects (pulse, sparks, shake)
- Muted background video playback
- Notes persisting after game end
- WAX login failures caused by reinitialisation
- Restart logic resetting multipliers and timers correctly

---

## [0.8.0] – Mobile Stability & UX Update  
**Date:** 2025-08-XX

### Added
- Mobile-only rotate-for-best-experience hint
- Tablet viewport scaling safeguards
- Visual hit judgements (SUBLIME / OK / MISS)
- Lane pulse animations and camera shake
- Background image support per NFT track

### Changed
- Improved viewport meta configuration
- Refined touch-action rules for lanes vs page
- Reduced accidental gesture blocking on mobile

### Fixed
- Lane interaction not registering on some Android devices
- Judge text not appearing on perfect hits
- Game loop desync on slower devices

---

## [0.7.0] – NFT & WAX Integration  
**Date:** 2025-07-XX

### Added
- WAX Cloud Wallet login
- NFT ownership detection via AtomicAssets API
- Track selection from owned NFTs
- Season Pass NFT gating (template-based)
- Admin wallet override
- Local leaderboard storage

### Changed
- Start button disabled until wallet login
- Track selector locked until NFTs are loaded

### Fixed
- WAX login state resetting on UI changes
- Track selector breaking login flow

---

## [0.6.0] – Core Gameplay  
**Date:** 2025-06-XX

### Added
- Rhythm gameplay engine
- Falling note system
- Accuracy-based scoring
- Combo tracking
- Multiplier HUD
- Game Over overlay

### Changed
- Timing window tuned for mobile input latency

---

## [0.5.0] – Visual Foundation  
**Date:** 2025-05-XX

### Added
- Lane system (5 lanes)
- Hit line
- Background container
- Spark hit effects
- Sublime Sounds branding

---

## [0.4.0] – Initial Prototype  
**Date:** 2025-04-XX

### Added
- Basic UI layout
- Static lanes
- Placeholder scoring
- Early concept visuals

---

## Planned
- Cloud-backed leaderboards
- Player profiles & progression
- Achievements & mintable rewards
- Multiplayer modes
- PWA support
- Anti-cheat & analytics
- Seasonal events

---

**Maintained by:** Sublime Sounds  
**Project:** Rhythm Master  
**Status:** Beta (Pre-Launch)
