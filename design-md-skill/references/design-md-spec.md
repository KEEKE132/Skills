# DESIGN.md Field Specification

Reference for the Google Stitch DESIGN.md format, extended with the sections used by
the awesome-design-md collection. A DESIGN.md = YAML frontmatter (machine-readable token
contract) + Markdown body (readable narrative an agent follows when generating UI).

## 1. Frontmatter (YAML)

All free-form string values MUST be double-quoted. Numeric and hex values are unquoted.
Tokens are referenced from `components` and the body via `{section.token}` syntax
(e.g. `{colors.primary}`, `{typography.body}`, `{rounded.md}`, `{spacing.lg}`).

### Required top-level fields

| Field | Type | Purpose |
|-------|------|---------|
| `version` | string | Format version tag, e.g. `alpha` or `1.0.0` |
| `name` | string | Analysis name, e.g. `Linear-design-analysis` |
| `description` | string | Single-line double-quoted summary: canvas color, ink, primary/accent, surface behavior, typography character, depth philosophy. 60–120 chars of dense signal. |
| `colors` | map | All color tokens (see below) |
| `typography` | map | Role → {fontFamily, fontSize, fontWeight, lineHeight, letterSpacing, optional fontFeature} |
| `rounded` | map | Corner scale: `xs` 4px · `sm` 6px · `md` 8px · `lg` 12px · `xl` 16px · `xxl` 24px · `pill` 9999px (adjust to brand) |
| `spacing` | map | Spacing scale, e.g. `xs` 4px · `sm` 8px · `md` 16px · `lg` 24px · `xl` 32px · `section` 96px |
| `components` | map | Component name → {backgroundColor, textColor, typography, rounded, padding, optional height} using only token references |

### `colors` key contract (use these role names; extend only for real brand tokens)

| Group | Keys |
|-------|------|
| Brand & accent | `primary`, `primary-hover`, `primary-focus`, `primary-press`, `primary-deep`, `brand-secure` |
| Surface | `canvas`, `surface-1` … `surface-4`, `hairline`, `hairline-strong`, `inverse-canvas`, `inverse-surface-1` |
| Text | `ink`, `ink-muted`, `ink-subtle`, `ink-tertiary`, `on-primary`, `inverse-ink` |
| Semantic | `semantic-success`, `semantic-warning`, `semantic-error`, `semantic-overlay` |

### `typography` key contract

| Role | Size | Use |
|------|------|-----|
| `display-xl/display-lg/display-md` | 80/56/40px class | Hero headlines |
| `headline` / `card-title` / `subhead` | 28/22/20px class | Section titles, card titles, leads |
| `body-lg` / `body` / `body-sm` / `caption` | 18/16/14/12px class | Body ladder |
| `button` / `eyebrow` / `mono` | 14/13/13px class | Labels, taxonomy eyebrows, code |

`fontFamily` strings are quoted; fallback stacks look like
`"sohne-var, 'SF Pro Display', system-ui, sans-serif"`. `fontFeature` (ss01, tnum) is optional.

### `components` key contract

Each component uses ONLY token references — never raw hex values in components:

```yaml
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
    padding: 8px 14px
```

State variants are separate keys (`button-primary`, `button-primary-hover`,
`button-primary-pressed`). Standard components: `button-primary(-hover/-pressed)`,
`button-secondary`, `button-tertiary`, `button-inverse`, `pricing-card(-featured)`,
`feature-card`, `product-screenshot-card`, `testimonial-card`, `customer-logo-tile`,
`text-input(-focused)`, `cta-banner`, `top-nav`, `footer`, `status-badge`.

## 2. Body (Markdown)

Sections in order:

1. **Overview** — Design language in 2–3 short paragraphs: canvas, accent discipline, type
   character, layout rhythm. End with 5–8 bullet "Key Characteristics".
2. **Colors** — Grouped by Brand & Accent / Surface / Text / Semantic. Every frontmatter
   color must be documented with its semantic role and usage. Reference tokens as
   `{colors.primary}` with the hex value inline for readability.
3. **Typography** — Font families + fallback substitutes (note when a proprietary font has
   no free equivalent, e.g. "Inter is the closest free substitute"), a hierarchy table
   (Token | Size | Weight | Line Height | Letter Spacing | Use), and principles.
4. **Layout** — Spacing system (base unit), grid & container (max width, column counts per
   breakpoint), whitespace philosophy.
5. **Elevation & Depth** — Level table (Level | Treatment | Use). State explicitly whether
   depth uses shadows, surface ladders, or borders.
6. **Shapes** — Border radius scale table. Photography/illustration geometry rules.
7. **Components** — Per-component spec: background, text, type, padding, radius, border,
   states.
8. **Do's and Don'ts** — Guardrails; at least 3, phrased as hard rules
   ("Never use gradients", "Only one chromatic accent", "Mono only in code contexts").
9. **Responsive Behavior** — Breakpoints, grid collapse strategy, touch target minimums,
   what happens to hero/pricing/nav at each breakpoint.
10. **Agent Prompt Guide** — Short ready-to-paste prompts; quick color reference block.

## 3. Quality bar

- No placeholder values, no "TBD", no unverified hex codes.
- Source pages listed in Colors section (`> Source pages: ...`).
- Every color, type role, radius, and component used in the body exists in frontmatter
  (and vice versa, except where body explicitly documents a "recommended" addition).