---
version: alpha
name: Wanon Hospital Ops UI (Light Teal)
description: Light teal visual language for the hospital internal webapp — realtime OR-register dashboard, device-usage claim form, rights-mapping settings. Tokens mirror the app's actual CSS classes; this is a hue swap from the previous dark-green/mint (Nexcent) palette and the slate-grey values in current CSS, not a redesign.
colors:
  primary: "#0f766e"
  primary-800: "#115e59"
  ink-900: "#134e4a"
  secondary-400: "#64748b"
  secondary-300: "#94a3b8"
  teal-100: "#ccfbf1"
  teal-50: "#f0fdfa"
  teal-200: "#99f6e4"
  surface: "#FFFFFF"
  neutral-100: "#e5e7eb"
  on-primary: "#FFFFFF"
typography:
  h1:
    fontFamily: Noto Sans Thai
    fontSize: 20px
    fontWeight: 800
    lineHeight: 1.3
  h2:
    fontFamily: Noto Sans Thai
    fontSize: 15px
    fontWeight: 700
    lineHeight: 1.35
  body-md:
    fontFamily: Noto Sans Thai
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.5
  label-sm:
    fontFamily: Noto Sans Thai
    fontSize: 12px
    fontWeight: 700
    lineHeight: 1.3
rounded:
  sm: 6px
  md: 10px
  lg: 14px
  pill: 999px
spacing:
  1: 4px
  2: 8px
  3: 12px
  4: 16px
  5: 20px
  6: 24px
  8: 32px
components:
  header:
    backgroundColor: "{colors.teal-50}"
    textColor: "{colors.ink-900}"
  toolbar:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink-900}"
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.md}"
    padding: 8px
  button-primary-hover:
    backgroundColor: "{colors.primary-800}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.md}"
    padding: 8px
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.primary}"
    rounded: "{rounded.md}"
    padding: 8px
  button-use:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.md}"
    padding: 8px
  loadmore:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.primary}"
    rounded: "{rounded.md}"
    padding: 8px
  nav-pill:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.primary}"
    rounded: "{rounded.sm}"
    padding: 6px
  nav-pill-current:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.sm}"
    padding: 6px
  card:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.lg}"
    padding: 20px
  table-header:
    backgroundColor: "{colors.teal-50}"
    textColor: "{colors.ink-900}"
    typography: "{typography.label-sm}"
  table-row-hover:
    backgroundColor: "{colors.teal-100}"
  badge-realtime:
    backgroundColor: "{colors.teal-100}"
    textColor: "{colors.primary}"
    rounded: "{rounded.pill}"
    padding: 4px
  input-focus:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink-900}"
    rounded: "{rounded.sm}"
    padding: 8px
  dropdown-panel:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink-900}"
    rounded: "{rounded.sm}"
    padding: 4px
  dropdown-option-active:
    backgroundColor: "{colors.teal-50}"
    textColor: "{colors.primary}"
    rounded: "{rounded.sm}"
    padding: 6px
  spinner:
    backgroundColor: "{colors.teal-200}"
    rounded: "{rounded.pill}"
    size: 22px
  divider:
    backgroundColor: "{colors.secondary-400}"
    height: 1px
  divider-strong:
    backgroundColor: "{colors.secondary-300}"
    height: 1px
  button-secondary-neutral:
    backgroundColor: "{colors.neutral-100}"
    textColor: "{colors.primary-800}"
    rounded: "{rounded.md}"
    padding: 8px
---

## Overview

Internal operations webapp for Wanon Niwat Hospital. Three pages share one visual
language: the realtime OR-register dashboard (`dashboard_rt.html`), the
device-usage claim form (`lockingscrew35_usage_form.html`), and the
rights-mapping settings page (`settings.html`).

The visual language is **light teal**: pale teal surfaces, a solid teal accent
for the one high-emphasis action, dark teal ink. Hue family stays calm and
clinical (blue-green reads as "clean" on a phone held beside an operating
theatre), while the light tint keeps the app bright in dim OR surroundings.

This file tracks what the webapp actually renders. The palette replaces the
previous dark-green/mint (Nexcent-derived) tokens and the slate-grey values
currently in the CSS — a **token swap, not a redesign**. Layout, DOM and
behaviour stay put; only colours move.

Clinical-use constraint: screens are used on phones beside an operating theatre.
Data density and colour-coded status signals outrank visual polish.

## Colors

- **primary (#0f766e):** Solid teal. Primary buttons, "ใช้อุปกรณ์" button,
  links, section headings, current nav pill, load-more.
- **primary-800 (#115e59):** Hover state for primary buttons — solid darker
  teal, not an opacity trick, so contrast stays constant in every state.
- **ink-900 (#134e4a):** Darkest teal ink for headings and highest-contrast body
  text.
- **secondary-400 (#64748b) / secondary-300 (#94a3b8):** Blue-grey kept for
  decorative borders/dashed rules/secondary focus outlines. **Never used for
  text at ≤14px** — fails contrast on white.
- **teal-100 (#ccfbf1) / teal-50 (#f0fdfa):** Pale teal tints for table
  headers, realtime badge, dropdown hover, row hover, header bar.
- **teal-200 (#99f6e4):** Teal border variant (dashed rules, divider).
- **neutral-100 (#e5e7eb):** Neutral fill for secondary buttons.
- **surface (#FFFFFF) / on-primary (#FFFFFF):** Base surface and text on teal.

**Intentionally NOT tokenized** (status = meaning, stays hardcoded): shift
badges (เช้า/บ่าย/ดึก), device-source badges (hosp/emerson/mdc/rockwood/other),
vendor-affinity tags, the five money-total boxes, stock-matrix signals
(`mx-*`), warning/error banners, destructive/danger buttons, toasts.

## Typography

One Thai-capable sans stack, unchanged: `"Noto Sans Thai", "Sarabun",
system-ui, sans-serif`. Runs offline on hospital machines — no new font is
loaded; only weights are raised (h1 → 800) for heading contrast.

Table and form text keeps its compact size (13px body, 11.5–12px labels) and
tight line-height (~1.2–1.3). **Do not enlarge** — density is a feature here.

## Layout

- Spacing scale `4 / 8 / 12 / 16 / 20 / 24 / 32px` applied to card padding and
  section gaps only.
- **Never apply the scale to `tbody td` / `thead th` cell padding** — current
  values are tuned for scanability at arm's length.
- Container stays full-width with the existing gutter; no new grid.

## Elevation & Depth

Flat by design — borders carry structure, not shadows. Three shadow tokens only
for elements that already float (combobox panel `dev-combo-panel`, template menu
`tpl-menu`, toast `tpl-toast`), recoloured from pure black to the ink hue:

- `shadow-sm: 0 1px 3px rgba(19,78,74,.08)` — cards (settings page).
- `shadow-md: 0 10px 25px rgba(19,78,74,.15)` — floating panels, toast.
- `shadow-lg: 0 20px 40px rgba(19,78,74,.2)` — modal overlay backdrop.

## Shapes

`6 / 10 / 14px` radii plus a `999px` pill for badges. Buttons stay rounded-rect
(not pill) so the change reads as a refinement, not a redesign.

## Components

Mapped to the real classes in the three pages:

- `header` / `.header` — pale teal bar, dark teal ink text. No gradient.
- `toolbar` / `.toolbar` — white bar with a teal bottom border; holds search,
  datebox, shift chips and the refresh (⟳) button.
- `button-primary` / `.btn`, `.btn-primary` — the single high-emphasis action
  (save, refresh, load-more, ใช้อุปกรณ์). Hover = solid darker teal.
- `button-secondary` / `.btn.secondary` — white/neutral with teal text.
- `loadmore` / `.loadmore` — outlined teal button with `lm-hint` meta text.
- `nav-pill` / `.pagenav`, `.current` — page navigation; current page is a solid
  teal chip.
- `card` / `.card` — white, bordered; settings page additionally uses
  `shadow-sm`.
- `table-header` / `.tablewrap thead` — pale teal header, faint teal row hover.
  Each page keeps its own header treatment (light vs full-colour) — only hues
  change.
- `badge-realtime` / `.rt-badge` — pale-teal pill marking the live register;
  its green dot keeps its original colour (it means "live", not "brand").
- `input-focus` — focus border/border turns solid teal.
- `dropdown-panel` / `.dev-combo-panel` — white panel; active option uses
  .dev-combo-opt with pale teal + teal text. `.dev-combo-more` keeps neutral.
- `spinner` / `.spinner` — pale teal track with a teal head.
- `.totalbar`, `.totalbar-split` — neutral bar; the money figures inside keep
  their status colours.

## Do's and Don'ts

- **Do** change values inside existing CSS rules.
- **Don't** rename or remove any selector, class or id — scripts toggle classes
  like `.loading`, `.visible`, `.item`, `.dev-combo*`, `.mx-*` and query ids by
  name; renaming breaks loading, load-more, the device combobox and the stock
  matrix silently.
- **Don't** touch anything inside `<script>`: device lists, claim codes, price
  maths, query-string prefill, polling, template menus.
- **Don't** change input padding/border-width or table cell padding —
  absolutely-positioned dropdowns, sticky offsets and arm's-length scanability
  are calibrated to the current box metrics.
- **Don't** introduce CSS variables for status/warning colours; don't tokenize
  the shift/source/matrix badges.
- **Don't** ship a page without re-running the acceptance checks (routes 200,
  script block byte-identical, ids present, device list count unchanged,
  contrast ≥ 4.5:1 for text).