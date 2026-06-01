# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A single-page internal training website for the **Advanced SRX Firewall Bootcamp** (HPE APJ Systems Engineers, June 2–4 2026, Singapore). No build step, no framework, no dependencies — everything is one self-contained `index.html` file deployed to Netlify from the repo root.

## Viewing locally

```bash
open index.html
```

## Deployment

Push to `main` → Netlify auto-deploys (publish dir is `.`). No CI pipeline.

## Regenerating the PowerPoint

```bash
python3 build_pptx.py
```

Outputs `SRX_Bootcamp_Agenda.pptx` in the repo root. Requires `python-pptx`:

```bash
pip3 install python-pptx --break-system-packages
```

## Architecture of index.html

The file is entirely self-contained — all CSS, JavaScript, and content are inline. There are no external JS dependencies and no CSS framework.

**Content sections (HTML):**
- `.hero` / `.spec-card` — headline, dates, seats, format
- `#prereqs` — prerequisite cards
- `#agenda` — day-tab UI shell (`#d1-table`, `#d2-table`, `#d3-table` are empty divs populated by JS)
- `#venue` — venue and hotel cards
- `#register` — registration CTA and contact details
- `#tweaks-panel` — floating theme/accent switcher (postMessage-based, for embedding contexts)

**Agenda data (JavaScript arrays near bottom of `<body>`):**
- `AGENDA_DAY1`, `AGENDA_DAY2`, `AGENDA_DAY3` — each row is a tuple: `[time, duration, session HTML, format, optional description, optional flags]`
- `format` values: `'Lecture'`, `'Hands-on lab'`, `'Discussion'`, `''` (break/lunch)
- `flags`: `'remote'` adds a blue left-border, 📹 badge, and remote-tinted row background
- `renderDay(id, rows)` builds each table from the array at page load

**Theme system:**
- CSS custom properties on `html[data-theme]` — `light` and `dark` variants
- Accent hue is a single CSS variable `--accent-h` set from one of four named hues (teal, slate, amber, crimson)
- `TWEAK_DEFAULTS` object at the top of the first `<script>` block is the persisted default (edit here to change the shipped default)

## Key content locations

| What to change | Where |
|---|---|
| Dates, seats, format | `spec-card` aside in `.hero` |
| Glance metrics strip | `.glance` div (Duration / Lab time / Venue / Cohort) |
| Day 1–3 agenda rows | `AGENDA_DAY1` / `AGENDA_DAY2` / `AGENDA_DAY3` JS arrays |
| Day tab labels & themes | `.day-tabs` buttons and `.day-theme` paragraphs |
| Fire drill notice | `.day-notice` div inside Day 1 panel |
| Prerequisites | `#prereqs` `.prereq-card` divs |
| Venue / hotel details | `#venue` `.loc-card` articles |
| Registration contacts | `.reg-contact` div in `#register` |
| Footer date stamp | `<footer>` last `<div class="mono">` |
