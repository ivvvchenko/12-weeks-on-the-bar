# 12 weeks on the bar

A 12-week Upper/Lower training log with cardio, daily habits, XP, levels and badges.
Single-page app, no build step, no server.

## Use it on your phone
Open the GitHub Pages link, then
- iPhone (Safari): Share → *Add to Home Screen*
- Android (Chrome): menu → *Install app*

It opens full-screen and works offline.

## Sync between phone and computer
The page saves your log to `log.json` in a **private** repo (default name `training-log-data`).
Every save is a commit, so the repo's history is a full version history of your log.

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
