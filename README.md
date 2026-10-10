# Supreme Choice Insurance Solutions — Review Reports

A collection of self-contained HTML performance review reports and client dashboards for **Supreme Choice Insurance Solutions**, built on the **GOAL Platform** brand system.

## Overview

This repository contains standalone, single-file HTML reports designed for browser viewing and PDF export. Each report features inline CSS and at most a few lines of inline JS — no frameworks, build tools, or API calls required.

Reports include KPI dashboards, campaign breakdowns, call review analyses, contact rate metrics, funnel visualizations, website SEO audits, and actionable optimization recommendations.

## Reports

The current review package (October 9, 2026 account review):

| File | Description |
|------|-------------|
| `index.html` | Landing page / report hub — sidebar layout with cards linking to the campaign and research reports |
| `Supreme-Choice-Campaign-Overview-Last-3-Months-10-9-26.html` | All-campaigns overview (Home + Auto) — last 3 months through Oct 9, 2026 |
| `Supreme-Choice-Home-Campaign-Performance-Last-3-Months-10-9-26.html` | CA Home campaign performance — last 3 months through Oct 9, 2026 |
| `Supreme-Choice-Auto-Campaign-Performance-Last-3-Months-10-9-26.html` | CA Auto campaign performance — last 3 months through Oct 9, 2026 |
| `Supreme-Choice-SEO-Audit-9-9-26.html` | supreme-choice.com SEO audit — measured Sep 9, 2026 |
| `Supreme-Choice-CA-Brush-Fire-Risk-7-28-26.html` | California brush fire risk market research — Jul 28, 2026 |
| `Supreme-Choice-CA-Demographic-Research-7-28-26.html` | California demographic market research — Jul 28, 2026 |

Earlier reports (including the superseded Oct 9 last-60-days set) are archived under `past reports/` (kept in the repo, excluded from the live Vercel site via `.vercelignore`).

## Deployment

The site is a zero-build static site, ready to deploy on **Vercel**:

- `index.html` serves at the root; the reports are linked by relative path.
- `vercel.json` keeps `.html` URLs intact (no `cleanUrls` rewrites).
- `.vercelignore` excludes the `past reports/` archive from deployment.

To deploy, connect this GitHub repo to a Vercel project (Framework Preset: **Other**, no build command, output directory: root). Pushes to `main` then publish automatically.

## Getting Started

1. **Clone the repository**
```bash
git clone https://github.com/TomsTools11/sc-review-report.git
```
2. **Open any HTML file** directly in your browser — no build step or server needed.
3. **Export to PDF** via print (`Cmd+P` / `Ctrl+P`). Reports include `@media print` styles for clean page breaks.

## Design System

As of the October 9, 2026 package, the hub and campaign reports use the **new GOAL site style**. All new reporting sites should use it.

- **Fonts** — Sora (headings, numbers) and Outfit (body), loaded from Google Fonts
- **Theming** — tokens are scoped to a `.g` wrapper; `data-theme="system"` follows the viewer's light/dark preference (`light` / `dark` force a theme). Print always renders light.
- **Core tokens** — `--brand: #057be5`, `--ink`, `--ink-soft`, `--ink-muted`, `--ground`, `--surface`, `--surface-raised`, `--amber`, `--success`, and series colors `--s1`…`--s5`
- **Logos** — light and dark GOAL logos embedded as base64 PNGs, toggled via `--logo-light` / `--logo-dark`

### Common UI Patterns

- **Hub layout** — sidebar (logo, client, review date, section nav) plus a main column with a period strip and numbered report cards showing headline stats
- **Report pages** — period strip, KPI panels, animated bars (`data-w` widths) and SVG donut segments (`.seg`), with a back link to `index.html`
- **Minimal JS** — a small IntersectionObserver animates bars/donuts on scroll, and a `beforeprint` handler draws them fully for PDF export
- **Light/dark toggle** — a button at the top right of every page. It follows the viewer's system theme by default, and a manual choice is remembered across all reports on the site. Print always renders light.
- **Responsive layout** — mobile-friendly with print optimization

The older research and SEO reports still use the previous GOAL palette (`--goal-brand: #077BE5`, `--goal-dark-blue`, `--goal-accent-*`). They have a dark-mode color map added so the toggle works on them too.

## Tech Stack

- **HTML5** — semantic markup
- **CSS3** — custom properties, grid/flexbox layouts, media queries
- **Zero build dependencies** — no frameworks or bundlers; Google Fonts is the only external asset
