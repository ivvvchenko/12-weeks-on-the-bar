# 8 weeks on the bar

An 8-week Chest / Back / Legs training log (5 Nov – 30 Dec 2026), six sessions a week, with automatic tonnage, a Sunday Zone 2 walk, steps, the daily neck routine, XP, levels and badges.

## The program
Each muscle group twice a week. Weeks run Thursday to Wednesday, Sunday off.

- **Sessions:** Thu Chest A, Fri Back A, Sat Legs A, Mon Chest B, Tue Back B, Wed Legs B.
- **Pyramids:** the first lift of each day goes 15, 12, then 3–4 work sets of 6 (bent-over row: 8). Set 6 is the optional 4th work set.
- **Weeks 1–7 build, week 8 deload** (same weights, about half the sets, RIR 3+).
- **Neck-friendly:** leg press instead of back squats, seated leg curl instead of Romanian deadlifts, one-arm cable lateral raise instead of the Smith upright row.
- **Grey placeholders** show your last set (or the target reps before you log one). A green ↑ line appears when every set (pyramids: all 4 work sets) hit the target last time.
- **Weekly targets:** steps 10,000, Zone 2 walk on Sunday 40 min, 2,200 kcal, 180 g protein.

To change the program, edit `EX`, `SESSIONS`, `WTYPE`, `STEPS` and `cardioPlan()` near the top of the script in `index.html`.
Single-page app, no build step, no server.

## Tonnage
Every logged set adds weight × reps (V. Goncharov, «Тренируйся!»). Shown per exercise, per session and per week, with the change against the previous week, in the 8-week overview and in the Excel export.

- Dumbbells in both hands: enter one dumbbell; it counts ×2.
- One arm at a time: enter kg and reps per arm; reps count ×2.
- Pull-ups and dips: bodyweight (latest weekly check-in, 104 kg until you log one) + added kg, or minus assistance.
- Back extension: only the plate you hold counts.

## Previous logs
Linked under **Sync and data**, each with its own data file:
- `back-delts.html`: Back + Delts / Chest + Legs (31 Oct – 4 Nov 2026), data in `log-back-delts.json`.
- `push-pull.html`: Push/Pull (5–30 Oct 2026), data in `log-push-pull.json`.

## Use it on your phone
Open the GitHub Pages link, then
- iPhone (Safari): Share → *Add to Home Screen*
- Android (Chrome): menu → *Install app*

It opens full-screen and works offline.

## Sync between phone and computer
The page saves your log to `log-chest-back-legs.json` in a **private** repo (default name `training-log-data`).
Every save is a commit, so the repo's history is a full version history of your log.
The old logs stay untouched in `log.json` (Upper/Lower), `log-push-pull.json` (Push/Pull) and `log-back-delts.json` (Back + Delts). Devices that were already connected stay connected.

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
| `back-delts.html` | The previous Back + Delts / Chest + Legs log |
| `push-pull.html` | The previous Push/Pull log, read and edit as before |
| `manifest.webmanifest`, `icon*.png`, `icon.svg`, `apple-touch-icon.png` | Home-screen install |
| `sw.js` | Offline support. Change `CACHE` in it after editing `index.html` so phones pick up the update |
