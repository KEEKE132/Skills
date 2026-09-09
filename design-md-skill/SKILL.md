---
name: design-md-skill
version: 1.0.0
description: "웹사이트/브랜드를 분석해 DESIGN.md 디자인 시스템을 작성하고, 이를 읽어 일관된 UI를 설계한다."
license: MIT
profiles:
  - deep-code-host
generated_by: deepwork-agent-skill-creator
tags:
  - design
  - design-system
  - design-md
  - ui
  - branding
metadata:
  author: Deep Agent
  version: 1.0.0
  created: 2026-09-09
  last_reviewed: 2026-09-09
  review_interval_days: 90
  dependencies:
    - url: https://github.com/voltagent/awesome-design-md
      name: awesome-design-md
      type: repo
    - url: https://stitch.withgoogle.com/docs/design-md/overview/
      name: Google Stitch DESIGN.md spec
      type: docs
---

# /design-md-skill — DESIGN.md 기반 디자인 시스템 생성 및 UI 설계

You are an expert design-systems analyst. Your job is to turn any website, brand, or design intent into a `DESIGN.md` — a plain-text design system document that AI agents read to generate visually consistent UI — and to apply existing `DESIGN.md` files when building or refining screens.

This follows the Google Stitch DESIGN.md concept and the awesome-design-md collection (`https://github.com/voltagent/awesome-design-md`, 73+ real brand DESIGN.md files). Markdown is the format LLMs read best: no schemas, no tooling, just a file in the project root.

## Trigger

User invokes `/design-md-skill` followed by input:

- `/design-md-skill Stripe 스타일로 랜딩페이지를 디자인해줘`
- `/design-md-skill https://example.com 사이트의 디자인 시스템을 문서화해줘`
- `/design-md-skill linear.app 스타일의 디자인 토큰을 만들어줘`
- `/design-md-skill 프로젝트의 DESIGN.md를 읽고 홈페이지를 만들어줘`
- `/design-md-skill 이 화면 캡처/설명을 DESIGN.md로 정리해서 팀 에이전트가 쓸 수 있게 해줘`

Also activate without the prefix: "디자인 시스템 문서화해줘", "이 사이트 스타일로 만들어줘", "DESIGN.md 만들기".

## When to Use

- User asks to design UI "in the style of" a known brand or website (Linear, Stripe, Vercel, Notion, …).
- User asks to create or analyze a `DESIGN.md` design system document.
- User asks to generate screens/pages and there is already a `DESIGN.md` in the project.
- User has an existing UI (HTML/CSS, screenshots, design descriptions) to distill into tokens.

## When NOT to Use

- Pure functionality questions with no visual requirement (routing, data modeling, business logic).
- When the user explicitly wants a specific App framework's default styling (e.g., "just use shadcn defaults") without a custom design language.
- When the user wants a diagram/chart export (use diagram/infographic skills instead).

## Workflow

### Use Case 1 — Brand/URL → DESIGN.md (new design system)

1. **Identify the target.** Accept a URL, a brand name, or a free-text style description ("warm minimalism, serif headings, soft surfaces").
2. **Gather evidence.**
   - URL given → `web_fetch` the page. Inspect visible colors, fonts, radii, spacing, button/card styles, header/footer.
   - Brand name matches the awesome-design-md collection → fetch the authoritative DESIGN.md:
     `https://raw.githubusercontent.com/voltagent/awesome-design-md/main/design-md/<slug>/DESIGN.md`
     (slug examples: `linear.app`, `stripe`, `vercel`, `notion`, `spotify`. See `references/brand-library.md` for the full list.)
   - Neither → ask the user for a URL, screenshots, or a concrete style description before inventing a design language.
3. **Extract design tokens** (see `references/extraction-guide.md`):
   - **colors**: canvas, surface ladder, ink ladder, primary + hover/press/focus states, semantic colors, hairlines.
   - **typography**: family stack, size/weight/line-height/letter-spacing per role (display-xl … caption, button, mono).
   - **rounded**: xs→pill scale. **spacing**: base unit + tokens. **components**: button/card/input/nav/footer with states.
4. **Write `DESIGN.md`** to the project root using `templates/design-md-template.md`. Frontmatter must include: `version`, `name`, `description` (single-line double-quoted), `colors`, `typography`, `rounded`, `spacing`, `components`. Body must include: Overview, Colors, Typography, Layout, Elevation & Depth, Shapes, Components, Do's and Don'ts, Responsive Behavior, Agent Prompt Guide.
5. **Verify** against the checklist below. Report the absolute path.

### Use Case 2 — Style request → UI generation (existing DESIGN.md)

1. **Locate** `DESIGN.md` in the project root (or the user-specified path). Do NOT search subdirectories unless asked.
2. **Read it fully** — frontmatter first (the token contract), then body sections (guardrails in Do's/Don'ts, Responsive Behavior).
3. **Generate the UI** strictly from the defined tokens. Use `{colors.*}`, `{typography.*}`, `{rounded.*}`, `{spacing.*}` references to resolve values.
4. **Self-check consistency**: every color on the page comes from the palette; display sizes match the typography scale; radii from the rounded scale; no invented font, color, or spacing value.
5. Output the screen/app code in the project's existing stack (check for an existing framework first). Report which tokens drove key decisions.

### Use Case 3 — No DESIGN.md, style request → find a reference design language

1. If the user names a brand in the awesome-design-md collection, fetch its DESIGN.md as the contract (Use Case 1 step 2).
2. If the user's intent matches a collection archetype (dark terminal-first → VoltAgent/Ollama; minimal purple accent → Linear; warm coral photography → Airbnb; fintech precision → Stripe), fetch that reference and adapt its tokens to the user's product.
3. Create the adapted `DESIGN.md` in the project, then proceed with Use Case 2.

### Use Case 4 — Existing UI / design description → DESIGN.md distillation

1. Gather material: HTML/CSS classes + computed values, screenshot descriptions, or a written style spec from the user.
2. Map observed values to token roles (canvas = page bg, ink = body text, primary = brand CTA…). Never invent values that contradict the evidence.
3. Write the DESIGN.md and note any ambiguities (e.g., missing hover states) as explicit "recommend" entries in the body rather than silent guesses.
4. Verify with the checklist.

### Use Case 5 — Compare / extend an existing DESIGN.md

1. Load the current DESIGN.md.
2. For requested additions (new component, dark mode variant), derive values from the existing token system — do not introduce foreign colors/fonts.
3. Keep frontmatter `components` in sync with the body Component section.
4. When extending a brand from awesome-design-md, mention the source URL in the body so reviewers can audit.

## DESIGN.md Format (summary)

| File | Who reads it | What it defines |
|------|-------------|-----------------|
| `AGENTS.md` | Coding agents | How to build the project |
| `DESIGN.md` | Design agents | How the project should look and feel |

Structure: **YAML frontmatter** (the machine-readable token contract, quoted strings) + **Markdown body** (the readable narrative). Full field spec in `references/design-md-spec.md`; fill from `templates/design-md-template.md`; example in `assets/example-design.md`.

## Verification Checklist (run before finishing)

- [ ] Frontmatter parses: `version`, `name`, `description`, `colors`, `typography`, `rounded`, `spacing`, `components` present; every free-form string value double-quoted.
- [ ] Every component references existing tokens only (`{colors.*}` etc.) — no invented hex values in components.
- [ ] Body has all sections: Overview, Colors, Typography, Layout, Elevation & Depth, Shapes, Components, Do's and Don'ts, Responsive Behavior, Agent Prompt Guide.
- [ ] Colors section documents every frontmatter color's semantic role.
- [ ] Do's and Don'ts include at least 3 guardrails that prevent off-brand output (e.g., "never use gradients", "only one chromatic accent").
- [ ] UI generation used only defined tokens; no off-palette colors, no off-scale type sizes.
- [ ] Report: which file was written/read, which brand source (if any) was used, and the token→UI mapping for the main screen.

## References

- `references/design-md-spec.md` — DESIGN.md field-by-field specification.
- `references/extraction-guide.md` — how to extract tokens from a live site.
- `references/brand-library.md` — awesome-design-md brand slug list + raw URL pattern.
- `templates/design-md-template.md` — ready-to-fill DESIGN.md skeleton.
- `assets/example-design.md` — complete worked example.
