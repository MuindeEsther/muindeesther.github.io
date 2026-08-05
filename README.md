# Esther's Portfolio Site — Deploy Guide

Two files: `index.html` (landing page) and `duka-bora-dashboard.html` (live demo dashboard). No build step, no backend — pure static HTML with Plotly charts from a CDN.

## Before you publish — 3 placeholders to replace

1. `index.html`: WhatsApp link `https://wa.me/254700000000` → your real number (format: 254XXXXXXXXX, no + or spaces).
2. `index.html`: LinkedIn link `https://www.linkedin.com/in/REPLACE-ME` → your profile URL.
3. Both files use your email. **Consider a personal address** (e.g. esther.analytics@gmail.com) — keeps side-hustle mail out of your work inbox and avoids awkwardness with your employer.

## Deploy to GitHub Pages (free, ~10 minutes)

```bash
# 1. Create a new PUBLIC repo on github.com named: <your-username>.github.io
#    (using this exact name gives you the cleanest URL)

# 2. Locally:
git clone https://github.com/<your-username>/<your-username>.github.io.git
cd <your-username>.github.io
# copy index.html and duka-bora-dashboard.html into this folder
git add .
git commit -m "Launch portfolio site"
git push

# 3. Done. Your site is live at:
#    https://<your-username>.github.io
```

If the repo has any other name (e.g. `portfolio`), enable Pages manually: repo → Settings → Pages → Source: "Deploy from a branch" → main → / (root). The site goes live at `https://<your-username>.github.io/portfolio/`.

## Custom domain later (optional)

A domain like `esthermuinde.co.ke` costs ~KES 1,000–1,500/year (KeNIC registrars, e.g. Truehost, HostPinnacle). In the repo: Settings → Pages → Custom domain, then point the domain's DNS (CNAME → `<your-username>.github.io`). Not needed to start pitching — the github.io URL is fine.

## Updating dashboards

Each dashboard page is self-contained: data lives in the `const D = {...}` block near the bottom of the HTML. To refresh a dashboard, regenerate that block (or ask Claude in the Finance project — the build scripts and process are documented there).

## Phase 2 ideas (when you have clients, not before)

- **M-Pesa statement analyzer** (dashboard #2): your own statement, anonymized — the "coming soon" card already points to it.
- **Django upload tool**: a small app on Render/PythonAnywhere free tier where a prospect uploads a statement and gets an instant mini-report + your contact. Great lead magnet, but only worth building once pitching has started.
