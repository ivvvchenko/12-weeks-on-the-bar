# 13 weeks on the bar

A 13-week Push/Pull training log (5 Oct 2026 – 3 Jan 2027) with Zone 2 walks, steps, the daily neck routine, XP, levels and badges.

## The program
Based on the app program «Тяни и жми без нагрузки на позвоночник», reviewed and modified (see the Program sheet in the Life OS workbook).

- **Sessions:** Pull A (Mon), Push A (Tue), Pull B (Thu), Push B (Fri). Week 13: Pull B on Wed, Push B on Sat.
- **3-week wave:** Light 12–15 reps (weeks 1, 4, 8, 11) → Medium 10–12 (2, 5, 9, 12) → Heavy 6–8 (3, 6, 10, 13). Week 7 is a deload: 2 sets, RIR 3–4, −10% load.
- **Same exercises every week:** each day uses the Light-week exercise set in all week types; only reps, effort and (deload) sets change.
- **Grey placeholders** show your last set from the same week type (deload shows last Medium −10%). A green ↑ line appears when every set hit the top of the range last time: add 2.5 kg upper / 5 kg legs.
- **Weekly targets:** steps 7,000 → 10,000 (week 6+), Zone 2 walks Wed/Sat (+Sun from week 3) 30 → 45 min, calories 2,150 → 2,100 (week 8) → maintenance in week 13.

To change the program, edit `EX`, `SESSIONS`, `WTYPE`, `STEPS`, `NECK` and `cardioPlan()` near the top of the script in `index.html`.
Single-page app, no build step, no server.

## Use it on your phone
Open the GitHub Pages link, then
- iPhone (Safari): Share → *Add to Home Screen*
- Android (Chrome): menu → *Install app*

It opens full-screen and works offline.

## Sync between phone and computer
The page saves your log to `log-push-pull.json` in a **private** repo (default name `training-log-data`).
Every save is a commit, so the repo's history is a full version history of your log.
The old Upper/Lower log stays untouched in `log.json`. Devices that were already connected stay connected.

1. Create a private repo named `training-log-data` (empty is fine).
2. Create a fine-grained token: GitHub → Settings → Developer settings → Personal access tokens →
   Fine-grained tokens → Generate new token.
   - Repository access: *Only select repositories* → `training-log-data`
   - Permissions → Repository permissions → **Contents: Read and write**
   - Expiration: up to you (you'll need a new token when it expires)
3. Open the page, scroll to **Sync and data**, enter your username, repo name and token, tap **Connect**.
4. Repeat step 3 on your other device. Keep the token in a password manager to paste it easily.

The token stays in that browser only. It's sent only to api.github.com and can only touch that one repo.
The page refuses to sync to a public repo.

## Your data
- **Download history (Excel)**: weekly summary, strength progress (best estimated 1RM per exercise per week),
  every set, cardio and daily habits.
- **Export / Import backup**: a JSON copy of the whole log.

## Files
| File | Purpose |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest`, `icon*.png`, `icon.svg`, `apple-touch-icon.png` | Home-screen install |
| `sw.js` | Offline support. Change `CACHE` in it after editing `index.html` so phones pick up the update |
