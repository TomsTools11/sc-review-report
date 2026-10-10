# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Standalone HTML performance review reports for **Supreme Choice Insurance Solutions**, a GOAL Platform client. These are self-contained, single-file reports (inline CSS, no JS frameworks or build tools) designed for browser viewing and PDF export via print.

## Files

- `index.html` — Report hub (landing page) linking to every current report
- `Supreme-Choice-*-10-9-26.html` — Current campaign reports (Campaign Overview, Home, Auto; last 3 months through Oct 9, 2026)
- `Supreme-Choice-SEO-Audit-*.html`, `Supreme-Choice-CA-*.html` — Website and market research reports
- `past reports/` — Archived reports, excluded from Vercel deploys via `.vercelignore`

## Design System

**All new reporting sites use the new GOAL site style** (introduced with the Oct 9, 2026 package — `index.html` and the three campaign reports are the reference):

- Fonts: Sora (headings/numbers) + Outfit (body) from Google Fonts
- Tokens scoped to a `.g` wrapper with `data-theme="system"` (follows viewer light/dark); print always renders light
- Core tokens: `--brand: #057be5`, `--ink`/`--ink-soft`/`--ink-muted`, `--ground`/`--surface`/`--surface-raised`, `--amber`, `--success`, series `--s1`..`--s5`
- Hub: sidebar + main column with period strip and numbered report cards (`.rc`) carrying headline stats
- Report pages link back to `index.html`; bars use `data-w` (percent) and donut segments use `.seg` with `data-dash`/`data-offset`, animated by a small inline script with a `beforeprint` fallback

Older research/SEO reports still use the legacy palette (`--goal-brand: #077BE5`, `--goal-dark-blue: #00172D`, `--goal-accent-1/2/3`).

## Working with Reports

- No build step — open HTML files directly in a browser
- Reports are print-optimized (`@media print` rules with `break-inside: avoid`)
- All data is hardcoded in the HTML — no API calls or dynamic data loading
- Use hyphenated filenames (`Supreme-Choice-<Report>-<Period>-<M-D-YY>.html`) and move superseded reports to `past reports/`
