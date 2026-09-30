---
name: gauss-design-system
description: Visual design system for Gauss Energia (solar PV, battery storage & EV charging, Brazil). Modern, technical, monochromatic with one mandatory green accent. Use this skill any time you are producing a customer-facing artifact for Gauss — commercial proposals, slide decks, web pages, internal dashboards, or marketing.
---

# Gauss Energia — Design System Skill

## The identity
Three green stripes (`#1B5D24 / #39B54A / #8FD79A`) with a diagonal AE cutout and lightly rounded edges, paired with the **Bebas Neue** wordmark and the tagline **SOLAR · BESS · EV**. Marks: `assets/gauss-logo-mark.svg` (colour, light surfaces), `assets/gauss-logo-mark-white.svg` (reversed, dark/green), `assets/gauss-logo-lockup.svg` (mark + wordmark + tagline). See `README.md` for the full brief.

## When to use
Producing **any** customer- or partner-facing artifact for Gauss Energia: proposals (web / A4 / mobile), slide decks (16:9), web pages, dashboards, social posts, contracts, technical reports.

## Quick start
1. **Read `README.md` first.** Brand brief, voice rules, number-formatting conventions, iconography, logo usage. Treat it as binding.
2. **Link `colors_and_type.css`** from the `<head>` of any HTML artifact. It defines every token (`--gauss-green`, `--ink-*`, `--space-*`, `--fs-*`, `--font-wordmark`) and a working baseline for `h1–h6`, `p`, `a`, `code`, etc.
3. **Use tokens, never hex.** The only place a hex value appears is inside `colors_and_type.css`.
4. **Open `preview/components.html`** for ready-made buttons, inputs, badges, cards, and the seven primary icons. Copy them, don't reinvent them.
5. **For proposals → start from the closest product, in the canvas you need** (web / A4 / iPhone — see file map). All mirror the structure of the real PDFs in `uploads/` (cover, "Quem é a Gauss?", introdução & escopo, equipamentos, premissas técnicas & cronograma, investimento).
6. **For slides → start from `slides/template.html`.** 1920×1080, sectioned with `<section data-screen-label="…">`.

## Non-negotiables
- The signature green `#39B54A` (token `--gauss-green`) is mandatory and untouchable.
- Two typefaces only: **Sora** for everything, **Bebas Neue** for the literal "GAUSS" wordmark (token `--font-wordmark`). Don't add a third.
- No sun icons. No leaves. No emoji. No gradient skies. See `README.md` §4 for the strict ban list.
- Numbers always pt-BR formatted (`R$ 1.875,00`, `12,075 kWp`, `62 %` with hard space).
- Headlines are sentence case in Portuguese, never Title Case.

## File map
| Path | Purpose |
|---|---|
| `README.md` | Brand brief, content rules, iconography, caveats |
| `colors_and_type.css` | All design tokens + element baseline |
| `fonts/Sora-*.ttf` | Self-hosted Sora weights |
| `assets/gauss-logo-mark.svg` | Mark — colour, for light surfaces |
| `assets/gauss-logo-mark-white.svg` | Mark — reversed white, for dark/green |
| `assets/gauss-logo-lockup.svg` | Mark + Bebas wordmark + SOLAR · BESS · EV |
| `assets/mapa-instalacoes.png` | Installation footprint map (used in "Quem é a Gauss") |
| `preview/*.html` | Reference cards: colors, type, spacing, components, brand |
| `ui_kits/proposal-solar.{html,-a4,-phone}` | Solar PV proposal — web / A4 / iPhone |
| `ui_kits/proposal-bess.{html,-a4,-phone}` | BESS / battery-storage proposal — web / A4 / iPhone |
| `ui_kits/proposal-ev-service.{html,-a4,-phone}` | EV — charger + operation (CPO) — web / A4 / iPhone |
| `ui_kits/proposal-ev-install.{html,-a4,-phone}` | EV — installation only — web / A4 / iPhone |
| `ui_kits/proposal-ev-solar.{html,-a4,-phone}` | EV charger + solar (dual sizing) — web / A4 / iPhone |
| `ui_kits/letter.html` | Formal letter + notification letter (A4) |
| `ui_kits/internal-comms.html` | Transactional email, internal memo, chat announcement |
| `ui_kits/spreadsheet.html` | Excel-style dimensioning + financial workbooks |
| `slides/template.html` | 16:9 slide deck template |
| `explorations/proposal-samples.html`, `kits-index.html` | Gallery / index pages |
| `uploads/Proposta-*.pdf` | Two real reference proposals (structural source) |

## Common tasks

### Build a new proposal
Pick the product (solar / bess / ev-service / ev-install / ev-solar) and the canvas (web `.html`, print `-a4.html`, mobile `-phone.html`). Duplicate it and replace the customer block (name, specs, address, date, proposal #) and the investment table. Section order must match: cover → "Quem é a Gauss?" (intro + footprint map) → introdução & escopo → equipamentos → premissas técnicas & cronograma (or operação for ev-service; dual-sizing + structure for ev-solar) → investimento → contato. Don't add sections that aren't in the source without asking.

### Build a deck
Start from `slides/template.html`. Use `deck_stage.js` (already wired). Label each slide with `[data-screen-label="NN Title"]` so reviewers can comment by slide. Hero slides go full-bleed on `--ink-1000` with one `--gauss-green` accent — not the other way around.

### Add a chart
Two colors max: `--gauss-green` for the Gauss/savings series, `--ink-400` for the comparison/grid series. Three colors only inside multi-series energy charts: add `--signal-solar` for generation and `--signal-grid` for grid pull. Never use red unless the chart shows a loss, and prefer `--signal-warn` over inventing a red.

### Pick an icon
See `preview/components.html` for the seven primary icons (module, inverter, battery, charger, grid, savings, generation). Need one outside that set? Draw it in the same style — 24 px frame, 1.75 px stroke, rounded caps, no fills, line-drawing schematic feel — and never a sun, leaf, or recycle symbol.

## Caveats
- Sora **Regular (400)** and **Medium (500)** fall back to the Google Fonts CDN at the top of `colors_and_type.css` until self-hosted files are supplied.
- Proposal image areas (`data-img-slot`) are placeholder cards until real photography is commissioned — the installation footprint map is real (`assets/mapa-instalacoes.png`).
