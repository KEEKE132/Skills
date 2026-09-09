# Token Extraction Guide

How to analyze a live site or existing UI and extract the values that become a DESIGN.md.
Order matters: collect raw evidence first, map to roles second, write only verified values.

## A. From a live URL

Use `web_fetch` on the marketing page(s) — home + pricing + one form/contact page gives the
widest coverage. Extraction targets:

### Colors
- Page background → `canvas` (or dark canvas for dark themes).
- Brand CTA / logo color → `primary`. Hover/press are usually darker/lighter variants.
- Large colored section fills → `surface-1`/`surface-2` ladder candidates.
- 1px line elements, table borders, dividers → `hairline`.
- Headline color → `ink`; secondary/tertiary text → `ink-muted`/`ink-subtle`.
- Green/red/amber badge colors → `semantic-*`.

### Typography
For each visible text size record: font-family stack, size, weight, line-height,
letter-spacing. Map to roles:
- Largest hero heading → `display-xl`.
- Section headings → `display-lg`/`display-md`/`headline`.
- Card titles → `card-title`; intro paragraphs → `subhead`/`body-lg`.
- Standard paragraph → `body`; small/meta → `body-sm`/`caption`.
- Buttons → `button`; small uppercase category labels → `eyebrow`; code → `mono`.

### Geometry & spacing
- Button/card/input corner radii → build the `rounded` scale (start from
  xs 4 / sm 6 / md 8 / lg 12 / xl 16 / pill 9999, adjust to what you observe).
- Consistent gaps (8/16/24/32…) → `spacing` scale. Note the base unit (usually 4px or 8px).
- Max content width; card grid counts per breakpoint.

### Components
- Buttons: count distinct kinds (primary/secondary/tertiary/inverse), record fill, text
  color, radius, padding. Note hover/press/focus states if visible.
- Cards: pricing/feature/testimonial/logo tiles — fill, radius, border, padding.
- Inputs: fill, border, focus treatment.
- Nav/footer: height, background, text color.

## B. From HTML/CSS the user provides

Ask for (or read from the repo): the compiled CSS (classes + declarations) and the main
page HTML. Map classes to components:
- `.btn`, `.button`, `.cta` → button components.
- `.card` → cards. `.input`, `.field` → inputs.
- `body { background-color }` → canvas.
Then follow the same role mapping as above. Compute nothing from memory — values must be
present in the file or you mark them "recommend".

## C. From screenshot descriptions (no computed values)

You cannot extract exact hex/sizes from prose alone. Produce a DESIGN.md skeleton with
**roles defined but values marked** `recommend:` — then generate a coherent token set
that matches the described character (e.g., "warm minimalism, serif headings, soft
surfaces" → cream canvas `#faf9f7`, serif display stack, 16px radius cards, low-contrast
borders). State clearly in the report which values are inferred, not observed.

## D. From the awesome-design-md library

If the brand already exists, do not re-extract from scratch:
fetch `https://raw.githubusercontent.com/voltagent/awesome-design-md/main/design-md/<slug>/DESIGN.md`
and use it as the token contract (slugs in `references/brand-library.md`).

## Anti-patterns

- Never invent hex values and present them as observed.
- Never drop a hover state silently — note "not observable, recommend <value>".
- Never mix two brand systems; if the user asks for "Stripe feel but our brand color",
  start from the Stripe DESIGN.md and alter ONLY the `primary` token (+ its derived states),
  documenting the deviation in the body.