# Gauss Energia Design System — project notes

## Identity
Three green stripes (`#1B5D24 / #39B54A / #8FD79A`) with a diagonal AE cutout and lightly rounded edges, paired with the **Bebas Neue** wordmark and the tagline **SOLAR · BESS · EV**. Sora is the system typeface for everything except the literal "GAUSS" wordmark (Bebas Neue). The signature green `#39B54A` (`--gauss-green`) is mandatory.

## Files
- **Logo:** `assets/gauss-logo-mark.svg` (colour), `assets/gauss-logo-mark-white.svg` (reversed/white), `assets/gauss-logo-lockup.svg` (mark + wordmark + tagline).
- **Proposals** — five products, each in three canvases (web · A4 print · iPhone), all in `ui_kits/`:
  - Solar: `proposal-solar.html` · `proposal-solar-a4.html` · `proposal-solar-phone.html`
  - BESS: `proposal-bess.html` · `proposal-bess-a4.html` · `proposal-bess-phone.html`
  - EV charger + service (CPO): `proposal-ev-service.html` · `proposal-ev-service-a4.html` · `proposal-ev-service-phone.html`
  - EV install only: `proposal-ev-install.html` · `proposal-ev-install-a4.html` · `proposal-ev-install-phone.html`
  - EV charger + solar (dual sizing + structure slot): `proposal-ev-solar.html` · `proposal-ev-solar-a4.html` · `proposal-ev-solar-phone.html`
- **Other kits:** `ui_kits/letter.html`, `ui_kits/internal-comms.html`, `ui_kits/spreadsheet.html`.
- **Slides:** `slides/template.html`. **Galleries:** `explorations/proposal-samples.html`, `explorations/kits-index.html`.
- **Tokens:** `colors_and_type.css` (every color/type/space token + element baseline).

## Conventions
- Use tokens, never raw hex (hex lives only in `colors_and_type.css`).
- Numbers are pt-BR (`R$ 1.875,00`, `12,075 kWp`, `62 %` with hard space); headlines are sentence case.
- No sun icons, no leaves, no emoji, no gradient skies — see `README.md` §4.

See `README.md` → "START HERE" for the full note and `SKILL.md` for the agent guide.
