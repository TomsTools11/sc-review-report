# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Standalone HTML performance review reports for **Supreme Choice Insurance Solutions**, a GOAL Platform client. These are self-contained, single-file reports (inline CSS, no JS frameworks or build tools) designed for browser viewing and PDF export via print.

## Files

- `index.html` — Internal-facing campaign review report with detailed issue analysis, data visualizations, and optimization recommendations
- `sc-client-review.html` — Client-facing account review report with KPI summaries, campaign breakdowns, funnel visualization, source-level tables, and actionable recommendations

## Design System

All reports use the GOAL Platform brand palette defined as CSS custom properties:
- `--goal-brand: #077BE5` (primary blue)
- `--goal-dark-blue: #00172D`
- `--goal-accent-1: #3AEECA`, `--goal-accent-2: #97C2E8`, `--goal-accent-3: #9FDACD`
- Semantic colors: `--success-green`, `--warning-red`, `--warning-orange`

Reports share common CSS patterns: KPI card grids, bar charts (CSS-only, no chart libraries), issue/recommendation cards with left-border color coding, comparison boxes, stat grids, and source tables. Print and mobile responsive styles are included.

## Working with Reports

- No build step — open HTML files directly in a browser
- Reports are print-optimized (`@media print` rules with `break-inside: avoid`)
- All data is hardcoded in the HTML — no API calls or dynamic data loading
- Bar chart widths use inline `style="width: X%"` on `.bar` elements
