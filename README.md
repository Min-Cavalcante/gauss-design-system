# Gauss Energia — Design System

Visual system for **Gauss Energia**, a Brazilian solar‑energy company (residential PV, commercial PV, EV chargers). This pack modernises the legacy bar‑logo look into a sharper, more intelligent system suitable for commercial proposals, slide decks, and a future self‑service portal.

> **Brand direction:** intelligent, dynamic, growth, sharpness. Solar without clichés — no sun icons, no gradient‑sky photography, no "eco‑green" pastels. Numbers and engineering speak louder than slogans.

---

## ✅ START HERE

The identity is **three green stripes** (`#1B5D24 / #39B54A / #8FD79A`) with a diagonal AE cutout and lightly rounded edges, paired with the **Bebas Neue** wordmark and the tagline **SOLAR · BESS · EV**.

**Logo assets:**
- `assets/gauss-logo-mark.svg` — colour mark (light surfaces)
- `assets/gauss-logo-mark-white.svg` — reversed/white mark (dark or green surfaces)
- `assets/gauss-logo-lockup.svg` — full mark + wordmark + tagline

**Proposals — five products, each in three canvases (web · A4 print · iPhone):**

| Product | Web | A4 print | iPhone |
|---|---|---|---|
| Solar PV | `proposal-solar.html` | `proposal-solar-a4.html` | `proposal-solar-phone.html` |
| BESS (storage) | `proposal-bess.html` | `proposal-bess-a4.html` | `proposal-bess-phone.html` |
| EV charger + service (CPO) | `proposal-ev-service.html` | `proposal-ev-service-a4.html` | `proposal-ev-service-phone.html` |
| EV install only | `proposal-ev-install.html` | `proposal-ev-install-a4.html` | `proposal-ev-install-phone.html` |
| EV charger + solar | `proposal-ev-solar.html` | `proposal-ev-solar-a4.html` | `proposal-ev-solar-phone.html` |

All live in `ui_kits/`. **Other kits:** `ui_kits/letter.html`, `ui_kits/internal-comms.html`, `ui_kits/spreadsheet.html`. **Slides:** `slides/template.html`. **Galleries:** `explorations/proposal-samples.html`, `explorations/kits-index.html`.

---

## Index

| File | What it is |
|---|---|
| `README.md` | This document — brand context, content rules, foundations, iconography |
| `SKILL.md` | Agent‑Skill manifest (compatible with Claude Code & other agents) |
| `colors_and_type.css` | All CSS custom properties + element baseline (`h1–h6`, `p`, `a`, `code` …) |
| `fonts/` | Sora TTFs — Thin, ExtraLight, Light, SemiBold, Bold, ExtraBold |
| `assets/` | Logos (original + modernised), brand marks, photography rules |
| `preview/` | Cards shown in the Design System tab — Colors, Type, Spacing, Components, Brand |
| `ui_kits/proposal-*.html` | Commercial proposals — 5 products × 3 canvases (web / A4 / iPhone) |
| `ui_kits/letter.html`, `internal-comms.html`, `spreadsheet.html` | Document, comms & data kits |
| `slides/template.html` | 16:9 slide deck following the system |

---

## 1. Company context

Gauss Energia sells distributed generation and EV‑charging infrastructure to Brazilian customers. The primary customer‑facing artifact is the **commercial proposal PDF** — a personalised document with projected savings, system specs, ROI, financing options and contract terms. Two real examples sit in `uploads/` (`Proposta-Regis.pdf` — EV charger, `Proposta-Bento.pdf` — 12 kWp PV). The visual system here unifies those proposals with marketing surfaces and an eventual customer portal.

### Source materials

- `uploads/logo 1500.png` — current logo (1541×1370 PNG, transparent). Four horizontal bars in green → lime → yellow over an "AE" silhouette; wordmark "GAUSS" + tagline "ENERGIA SOLAR" in black geometric sans.
- **Sora** in Thin/ExtraLight/Light/SemiBold/Bold/ExtraBold. **Regular (400) and Medium (500) were not delivered** — currently substituted from Google Fonts CDN; replace `@import` in `colors_and_type.css` with self‑hosted `@font-face` rules when the files arrive.
- Two real proposals (`uploads/Proposta-Regis.pdf`, `uploads/Proposta-Bento.pdf`) — used as the structural reference for the proposal templates.

---

## 2. Content fundamentals

### Voice

- **Direct, technical, plain Portuguese.** No jargon, no startup buzzwords. We are an expert utility, not a fintech.
- **"Você"** — second‑person singular. Lowercase mid‑sentence ("sua conta de luz cai pela metade"), capitalised only when starting a sentence.
- **Numbers do the heavy lifting.** Every claim is anchored to a specific figure: `R$ 14.832 / ano`, `−62 % na conta`, `payback em 4 anos e 3 meses`. Never write "economize muito" — write the number.
- **Engineering matters.** Cite norms (`ABNT NBR 5410`, `NBR 17790`, `NR‑10`), spec inverters by manufacturer, list module wattage. Customers are buying a piece of infrastructure.
- **No emoji, ever.** This is finance + infrastructure.

### Number formatting (pt‑BR)

- Currency: `R$ 1.875,00` — `R$`, hard space, thousands `.`, decimal `,`.
- Power: `12,075 kWp`, `9 kW`, `60 kW` — number, thin space, unit. Always lowercase unit prefix except `kWp`/`kWh`.
- Percentage: `62 %` with hard space (Brazilian style).
- Time: `4 anos e 3 meses`, `45 dias`. Spell out for plain copy.
- Tabular numbers: always use `font-variant-numeric: tabular-nums` (provided on `.readout` and `.mono`).

### Capitalisation

- **Headlines** — sentence case in Portuguese ("Energia que paga sua conta"), not Title Case.
- **Eyebrows / labels** — UPPERCASE, tracked +0.14em (provided as `.eyebrow`).
- **Section numbering** — `1. Sobre nós`, `2. Introdução`, `3. Escopo de fornecimento`, mirroring the legacy proposals.

### Don't

- Don't say "sustentável", "verde", "amigo do meio ambiente", "futuro" in body copy. Show, don't tell — the customer math is the sustainability story.
- Don't put a sun icon anywhere. Ever.
- Don't use stock photos of happy families pointing at rooftops.
- Don't lead with the planet. Lead with the bill.

---

## 3. Visual foundations

### Color anchor

The **only mandatory color** is `--gauss-green: #39B54A` — sampled from the top (darkest) stripe of the current logo. Every palette decision flows from it.

- **Use `--gauss-green` for:** primary CTAs, active states, brand chrome, the logo mark, "savings"/positive‑trend data in charts.
- **Use the ink scale (`--ink-50` → `--ink-1000`) for everything else.** The system is intentionally monochromatic + one accent. Resist adding more brand colors.
- **Two functional signals** are allowed when data viz needs them: `--signal-solar` (`#F2B441`) for generation, `--signal-grid` (`#2B6CFF`) for grid/consumption. Use them only inside charts and diagrams, never as decoration.
- Hero blocks use `--ink-1000` (`#07100A`), a near‑black with a 1° green undertone — never pure `#000`.

See `preview/colors.html` for the full scale.

### Typography

One family: **Sora**. Display weights 700–800 (tight, `-0.02em` tracking) for headlines; SemiBold 600 for subheads; Regular 400 / Light 300 for body. Use `.eyebrow` (Sora SemiBold 11px UPPERCASE +0.14em) as the technical‑readout label — it appears on every section header, every spec block, every data callout.

Numbers are set with the same family but with `font-variant-numeric: tabular-nums lining-nums` (utility class `.readout`).

**Wordmark — Bebas Neue (letter‑spaced).** The literal text "GAUSS" in every lockup is set in **Bebas Neue**, +0.06–0.09em letter‑spacing, uppercase. This is a hard rule — the wordmark uses Bebas, everything else uses Sora. Use the `.gauss-wordmark` utility class (sizes `sm` / `md` / `lg` / `xl` / `xxl`) or `font-family: var(--font-wordmark)`.

### Spacing & radii

4 px base scale (`--space-1` 4 → `--space-10` 128). Radii are deliberately restrained — `--radius-md` 8 px for cards, `--radius-lg` 14 px for hero panels, `--radius-pill` only for chips/badges. No "bubble" UI.

### Elevation

Shadows are crisp and low — `--shadow-sm` for resting cards, `--shadow-md` for hovered/active, `--shadow-lg` for floating overlays. The hero "glow‑green" (`--shadow-glow-green`) is reserved for the primary CTA at rest. Never blur shadows past 48 px.

---

## 4. Iconography

**Style — line, 1.75 px stroke, 24 px frame, rounded line caps & joins, no fills (except solid‑state dots and the brand mark).** The vocabulary borrows from electrical schematics and engineering documents: simple, technical, drawn as if from a calliper.

| Concept | How we draw it |
|---|---|
| Solar module | A 3×2 grid of cells, slightly trapezoidal in perspective; never a sun. |
| Inverter | A small rectangle with one input and one output line; corner LED dot. |
| Battery | Two stacked horizontal capsules with terminal bumps. |
| EV charger | A pedestal with a coiled cable looping to the right; never a car. |
| Grid | A pylon abstraction — vertical line with two horizontal arms. |
| Savings | Down‑and‑right arrow trace under a horizontal baseline. |
| Generation | Up‑and‑right arrow trace over a horizontal baseline. |
| Contract | Document with a single underlined signature stroke. |
| Engineer / technician | Hard‑hat silhouette as a thin arc + vertical line, never a person figure. |

**Strict bans:**
- Sun, sunrays, sunburst, sunshine‑in‑hands.
- Leaves, sprouts, recycle arrows, green planets.
- Money bags, dollar signs, growth arrows next to coins.
- Robots, AI sparkles, magic wands.

Until a real icon set is commissioned, use simple SVG strokes inline; see the Components preview for the seven primary icons (`module`, `inverter`, `battery`, `charger`, `grid`, `savings`, `generation`).

---

## 5. Logo

**The logo** is three green stripes (`#1B5D24 / #39B54A / #8FD79A`), the diagonal AE cutout retained, lightly rounded edges, plus the Bebas Neue "GAUSS" wordmark and the **SOLAR · BESS · EV** tagline. Colour mark on light surfaces, reversed white on dark/green.

Files: `assets/gauss-logo-mark.svg`, `assets/gauss-logo-mark-white.svg`, `assets/gauss-logo-lockup.svg`. The original uploaded reference (four-bar logo with yellow) remains in `uploads/logo 1500.png` only as historical source material — it is not part of the system.

**Construction rules:**
- The mark sits on a square of `--gauss-green` or `--ink-1000`.
- Minimum clear space around the lockup = the height of the "G" in the wordmark.
- Minimum mark size on screen: 24 px. Below that, use the wordmark alone.
- Never tilt, distort, recolor, gradient‑fill, or place over photography without a solid backing.

---

## 6. Photography & illustration (when commissioned)

Until photography exists, every imagery slot in templates is a placeholder card with a single‑word label (`MODULES`, `INVERTER`, `ROOFTOP`, `TEAM`). When commissioning real imagery:

- **Architectural over editorial.** Show the installation as engineered infrastructure — flat lighting, no golden‑hour drama.
- **People do work, never pose.** Technician installing a clamp on a rail — not smiling at the camera in a polo.
- **Roofs are clean.** No ferns, no neighbourhood clutter. Aerial / drone preferred.
- **No stock.** If a real photo isn't available, use a placeholder card. Never reach for shutterstock.

---

## 7. Caveats

- **Sora Regular (400) and Medium (500)** are not in the project — they fall back to the Google Fonts CDN at the top of `colors_and_type.css`. Replace with self‑hosted files when supplied.
- The icon set described in §4 is illustrated in `preview/components.html` but is not an exhaustive icon library — only the seven primary concepts are drawn.
