# 16 weeks on the bar

A 16-week Back + Delts / Chest + Legs training log (31 Oct 2026 – 19 Feb 2027) with automatic tonnage, Zone 2 walks, steps, the daily neck routine, XP, levels and badges.

## The program
Men's Physique-oriented 4-day split, each session twice a week. Weeks run Saturday to Friday.

- **Sessions:** Back + Delts A (Mon), Chest + Legs A (Tue), Back + Delts B (Thu), Chest + Legs B (Fri). Week 1 only: Back + Delts A on Sat 31 Oct, Chest + Legs A on Mon 2 Nov.
- **Two 8-week blocks:** week 1 calibration (RIR 3), weeks 2–7 and 9–15 build, weeks 8 and 16 deload (same weights, about half the sets, RIR 3+).
- **Per-exercise targets:** every exercise has its own sets, rep range, RIR and rest.
- **Grey placeholders** show your last set (deloads skipped). A green ↑ line appears when every set hit the top of the range last time.
- **Weekly targets:** steps 9,000 → 10,000 (week 3+), Zone 2 walks Sat/Sun/Wed 40 min, 2,200 kcal, 180 g protein.

To change the program, edit `EX`, `SESSIONS`, `WTYPE`, `STEPS` and `cardioPlan()` near the top of the script in `index.html`.
Single-page app, no build step, no server.

## Tonnage
Every logged set adds weight × reps (V. Goncharov, «Тренируйся!»). Shown per exercise, per session and per week, with the change against the previous week, in the 16-week overview and in the Excel export.

- Dumbbells in both hands: enter one dumbbell; it counts ×2.
- One arm at a time: enter kg and reps per arm; reps count ×2.
- Pull-ups: bodyweight (latest weekly check-in, 104 kg until you log one) + added kg, or minus assistance.
- Hanging knee raise is not counted.

## Previous log
The Push/Pull log (5–30 Oct 2026) is kept as `push-pull.html`, linked under **Sync and data**. Its data stays in `log-push-pull.json`.

## Use it on your phone
Open the GitHub Pages link, then
- iPhone (Safari): Share → *Add to Home Screen*
- Android (Chrome): menu → *Install app*

It opens full-screen and works offline.

## Sync between phone and computer
The page saves your log to `log-back-delts.json` in a **private** repo (default name `training-log-data`).
Every save is a commit, so the repo's history is a full version history of your log.
The old logs stay untouched in `log.json` (Upper/Lower) and `log-push-pull.json` (Push/Pull). Devices that were already connected stay connected.

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
- **Download history (Excel)**: weekly summary with tonnage, tonnage by session, strength progress (best estimated 1RM per exercise per week),
  every set with its volume, cardio and daily habits.
- **Export / Import backup**: a JSON copy of the whole log.

## Files
| File | Purpose |
|---|---|
| `index.html` | The whole app |
| `push-pull.html` | The previous Push/Pull log, read and edit as before |
| `manifest.webmanifest`, `icon*.png`, `icon.svg`, `apple-touch-icon.png` | Home-screen install |
| `sw.js` | Offline support. Change `CACHE` in it after editing `index.html` so phones pick up the update |
