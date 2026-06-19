# Supreme Choice Insurance Solutions — Review Reports

A collection of self-contained HTML performance review reports and client dashboards for **Supreme Choice Insurance Solutions**, built on the **GOAL Platform** brand system.

## Overview

This repository contains standalone, single-file HTML reports designed for browser viewing and PDF export. Each report features inline CSS with no external dependencies — no JavaScript frameworks, build tools, or API calls required.

Reports include KPI dashboards, campaign breakdowns, call review analyses, contact rate metrics, funnel visualizations, and actionable optimization recommendations.

## Reports

The current review package (June 19, 2026), all in the **Structured Dashboard** theme:

| File | Description |
|------|-------------|
| `index.html` | Landing page / report hub — sidebar nav linking to the three reports |
| `Supreme-Choice-Overall-Performance-Report-6-19-26.html` | Overall CA Home + CA Auto performance summary |
| `Supreme-Choice-Auto-Campaign-Deep-Dive-6-19-26.html` | CA Auto deep-dive — trend, source performance, market position |
| `Supreme-Choice-Right-Pricing-Plan-6-19-26.html` | Full bid & modifier changeset with implementation plan |

Earlier reports are archived under `past reports/` (kept in the repo, excluded from the live Vercel site via `.vercelignore`).

## Deployment

The site is a zero-build static site, ready to deploy on **Vercel**:

- `index.html` serves at the root; the three reports are linked by relative path.
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
