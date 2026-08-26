# Supreme Choice Insurance Solutions — Review Reports

A collection of self-contained HTML performance review reports and client dashboards for **Supreme Choice Insurance Solutions**, built on the **GOAL Platform** brand system.

## Overview

This repository contains standalone, single-file HTML reports designed for browser viewing and PDF export. Each report features inline CSS with no external dependencies — no JavaScript frameworks, build tools, or API calls required.

Reports include KPI dashboards, campaign breakdowns, call review analyses, contact rate metrics, funnel visualizations, and actionable optimization recommendations.

## Reports

The current review package (August 26, 2026):

| File | Description |
|------|-------------|
| `index.html` | Landing page / report hub — cards linking to the review and research reports |
| `Supreme-Choice-Home-Campaign-Performance-Last-30-Days-8-26-26.html` | CA Home campaign performance — last 30 days through Aug 26, 2026 |
| `Supreme-Choice-Auto-Campaign-Performance-Last-30-Days-8-26-26.html` | CA Auto campaign performance — last 30 days through Aug 26, 2026 |
| `Supreme-Choice-Blended-Account-Performance-YTD-8-26-26.html` | Blended account performance — 2026 year to date (Jan 1 – Aug 26) |
| `Supreme-Choice-CA-Brush-Fire-Risk-7-28-26.html` | California brush fire risk market research — Jul 28, 2026 |
| `Supreme-Choice-CA-Demographic-Research-7-28-26.html` | California demographic market research — Jul 28, 2026 |

Earlier reports are archived under `past reports/` (kept in the repo, excluded from the live Vercel site via `.vercelignore`).

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

All reports use the GOAL Platform brand palette via CSS custom properties:

| Token | Value | Usage |
|-------|-------|-------|
| `--goal-brand` | `#077BE5` | Primary blue |
| `--goal-dark-blue` | `#00172D` | Dark backgrounds |
| `--goal-accent-1` | `#3AEECA` | Accent teal |
| `--goal-accent-2` | `#97C2E8` | Accent light blue |
| `--goal-accent-3` | `#9FDACD` | Accent mint |

Semantic colors (`--success-green`, `--warning-red`, `--warning-orange`) are used for status indicators.

### Common UI Patterns

- **KPI card grids** — metric summaries with color-coded indicators
- **CSS-only bar charts** — no chart libraries; widths set via inline styles
- **Issue & recommendation cards** — left-border color coding by severity
- **Source tables** — data tables with campaign breakdowns
- **Responsive layout** — mobile-friendly with print optimization

## Tech Stack

- **HTML5** — semantic markup
- **CSS3** — custom properties, grid/flexbox layouts, media queries
- **Zero dependencies** — no JavaScript frameworks, bundlers, or external assets
