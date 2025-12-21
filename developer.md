# Rhythm Master – Developer Notes

---

## 🎮 Core Systems
- Notes are spawned on a time-based schedule
- Visual position uses dynamic hit-line alignment
- Scoring is time-based, not position-based

---

## ⏱ Hit Detection
- HIT_WINDOW = 180ms
- HIT_BUFFER = +30ms (mobile forgiveness)
- Final check: bd <= HIT_WINDOW + HIT_BUFFER

---

## 🔁 Restart Logic
- `allowFreeRestart` controls payment bypass
- `suppressScoreSubmit` prevents leaderboard writes
- Restarts reset visuals but not payment unless exhausted

---

## 📱 Fullscreen & Orientation
- Game enters fullscreen on Start
- Orientation locked to landscape when supported
- Hit line Y-position recalculated dynamically

---

## 💳 Payments
- SSN transfers handled via WAXJS or Anchor
- Admins bypass payment logic
- Payment required per track, not per session

---

## 🗄 Leaderboards
- Stored in Supabase
- Keyed by:
  - season
  - track name
  - user account
- Only higher scores overwrite existing records

- ## NFT Drop Flow
1. Player hits green note with SUBLIME
2. Client requests `/send-nft`
3. Supabase Edge Function:
   - Verifies authorization
   - Enforces daily cap
   - Selects random Mythic NFT
   - Transfers via AtomicAssets
   - Logs transaction

## Supabase Tables
### nft_sends
- id
- to_account
- asset_id
- txid
- send_date
- reason

## Environment Variables
- WAX_RPC
- WAX_PRIVATE_KEY
- PROJECT_WALLET
- SUPABASE_URL
- SERVICE_ROLE_KEY

## Testing
- Test mode toggle supported
- Edge Functions testable via Supabase dashboard

---
