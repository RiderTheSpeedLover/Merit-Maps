# Pravesh — Mumbai Engineering Cutoffs & College Compare

Single-page web app for MH CET aspirants. Find which Mumbai-region engineering colleges your
percentile lands you, and compare colleges side by side.

## Features
- **Find my colleges** — enter your percentile; see every college × branch × seat × category with the
  lowest cutoff across CAP Rounds I–IV, coloured Safe / Match / Reach / Out. Filter by branch, seat type,
  area, category, fit; search; download the filtered list as PDF.
- **Compare** — add 2–5 colleges; compare placement, package, fees, easiest open seat, Computer/IT cutoffs,
  **all-branch lowest open cutoffs**, branches offered, and review links. Download comparison as PDF.

## Data & honesty
- **Cutoffs:** verified from the official Maharashtra State CET Cell CAP Round I–IV PDFs, A.Y. 2025-26
  (Mumbai University region, codes 03xxx). Cutoff shown = lowest merit percentile across rounds for that seat.
- **Placement % / package:** APPROXIMATE estimates for tier comparison only — not official. Editable in-app.
- **Fees:** blank by default and user-entered. Verify against the official **Fee Regulating Authority**
  list (fra.maharashtra.gov.in). The app never invents fees.
- **Reviews:** link out to a web search; no review content is stored or asserted.

Everything is self-contained in `index.html` — no build step, no backend, no external data calls
(fonts load from Google Fonts; remove that <link> if you want zero external requests).

## Deploy to Vercel (free) — pick one

### A. Drag & drop (fastest)
1. Sign in at https://vercel.com (GitHub / Google / email).
2. Open https://vercel.com/new → scroll to **"Deploy a template"**… or simply drag this whole folder
   onto the page. Vercel detects a static site (no framework).
3. Click **Deploy**. ~20s later you get a live `https://<name>.vercel.app` URL.

### B. Vercel CLI
```bash
npm i -g vercel
cd this-folder
vercel          # answer prompts; Framework = Other, build command = none, output dir = ./
vercel --prod   # promote to production
```

### C. GitHub (best for updates)
1. Create a repo, add these files, push.
2. Vercel → **Add New → Project → Import** the repo. Framework preset **Other**. Deploy.
3. Every `git push` auto-deploys. Add a custom domain under **Settings → Domains**.

No env vars or build command required.

## Updating data later (e.g., Round V or real fees)
The data lives in a single `window.DB = {...}` line inside `index.html`. Re-generate it from new
official PDFs and replace that one line. (Ask the source you built this with to regenerate it.)

## Files
- `index.html` — the entire app
- `vercel.json` — static config (optional)
- `README.md` — this file
