# Changelog

All notable changes to ClaudeInsights are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/); this project
uses [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Added
- **Live demo** hosted on GitHub Pages — explore the real interactive dashboard
  (synthetic data) with no install.

### Fixed
- Running a flag without an explicit subcommand (e.g. `claudeinsights --logs PATH`
  or `claudeinsights -o out.html`) no longer crashes with an argparse error; it now
  correctly defaults to the `dashboard` command. Regression-tested.

## [0.1.0] — 2026-06-13

First public release.

### Added
- **Self-contained HTML dashboard** (`claudeinsights` / `claudeinsights dashboard`):
  KPI cards, insight feed, activity heatmap, daily token/cost trend, project /
  model / tool breakdowns, hour-of-day & weekday rhythm, session leaderboards,
  and **Claude Wrapped**. Zero external dependencies, no CDN, works offline.
- **Terminal report** (`claudeinsights report`) — ANSI summary.
- **JSON export** (`claudeinsights json`) — the full analytics payload.
- **Deterministic cost model** from public Anthropic list prices, with correct
  cache read / 5-minute / 1-hour multipliers and `--pricing` overrides.
- **Unpriced-model handling** — local/synthetic models count toward usage but
  contribute $0 to spend, flagged in the UI. No fabricated costs.
- **Correctness:** streaming-duplicate deduplication by `message.id`, and
  idle-trimmed *active* session duration (resumed sessions no longer inflate).
- `claudeinsights selftest` — built-in invariant & smoke checks.
- Cross-platform support (Windows / macOS / Linux), Python 3.8–3.12.
- Synthetic demo dataset generator (`examples/generate_sample.py`).
- Docs: `METRICS.md` (auditable formulas), `ARCHITECTURE.md`, `STRATEGY.md`.

[0.1.0]: https://github.com/ingridtoulotte/claudeinsights/releases/tag/v0.1.0
