# Project Status

**Paula Hershko — AI & Automation showcase page**
Last updated: May 2026

## What's built

Single-file static site: `index.html` + `screenshots/` folder.

- 5 project cards: CRM × Billing, Nesah Tabo, Timeframe, Insurance E-Signature, CAD Data Extraction → BOQ
- Light gray background (`#e9e9e9`), floating rounded cards (`#f8f8f8`, `border-radius: 20px`)
- Fonts: Plus Jakarta Sans (headings) + Inter (body) via Google Fonts CDN
- "Read More" accordion per card (vanilla JS)
- Hand-drawn SVG illustrations in header, between sections, and footer
- Fully responsive (mobile + desktop)

## Screenshots

Files expected in `screenshots/`:
- `project-01.png` — CRM/n8n workflow
- `project-02.png` — Nesah Tabo UI
- `project-03.png` — Timeframe dashboard
- `project-04.png` — EasyDoc email output
- `project-05.png` — CAD extraction / BOQ pipeline

Missing files are silently hidden (no broken image shown).

## Deployment

Hosted on Vercel, connected to this GitHub repo. Every push to `main` auto-deploys.

To update content or screenshots:
```bash
git add .
git commit -m "your message"
git push
```

Then hard-refresh the live URL (`Ctrl+Shift+R`) to bypass browser cache.
