---
version: alpha
name: linear-design-analysis
description: "A near-black product-focused marketing canvas built around #010102, light gray text (#f7f8f8), and the signature Linear lavender-blue (#5e6ad2) used as the single chromatic accent. Display type set in Linear custom sans at weight 600 with strong negative tracking; cards live as charcoal panels with hairline borders. Depth comes from a four-step surface ladder, never shadows."
colors:
  primary: "#5e6ad2"
  on-primary: "#ffffff"
  primary-hover: "#828fff"
  primary-focus: "#5e69d1"
  ink: "#f7f8f8"
  ink-muted: "#d0d6e0"
  ink-subtle: "#8a8f98"
  ink-tertiary: "#62666d"
  canvas: "#010102"
  surface-1: "#0f1011"
  surface-2: "#141516"
  surface-3: "#18191a"
  surface-4: "#191a1b"
  hairline: "#23252a"
  hairline-strong: "#34343a"
  hairline-tertiary: "#3e3e44"
  inverse-canvas: "#ffffff"
  inverse-surface-1: "#f5f6f6"
  inverse-ink: "#000000"
  brand-secure: "#7a7fad"
  semantic-success: "#27a644"
  semantic-overlay: "#000000"
typography:
  display-xl:
    fontFamily: "Linear Display, SF Pro Display, system-ui, sans-serif"
    fontSize: 80px
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: -3.0px
  display-lg:
    fontFamily: "Linear Display, SF Pro Display, system-ui, sans-serif"
    fontSize: 56px
    fontWeight: 600
    lineHeight: 1.10
    letterSpacing: -1.8px
  display-md:
    fontFamily: "Linear Display, SF Pro Display, system-ui, sans-serif"
    fontSize: 40px
    fontWeight: 600
    lineHeight: 1.15
    letterSpacing: -1.0px
  headline:
    fontFamily: "Linear Display, SF Pro Display, system-ui, sans-serif"
    fontSize: 28px
    fontWeight: 600
    lineHeight: 1.20
    letterSpacing: -0.6px
  card-title:
    fontFamily: "Linear Display, SF Pro Display, system-ui, sans-serif"
    fontSize: 22px
    fontWeight: 500
    lineHeight: 1.25
    letterSpacing: -0.4px
  subhead:
    fontFamily: "Linear Display, SF Pro Display, system-ui, sans-serif"
    fontSize: 20px
    fontWeight: 400
    lineHeight: 1.40
    letterSpacing: -0.2px
  body-lg:
    fontFamily: "Linear Text, system-ui, sans-serif"
    fontSize: 18px
    fontWeight: 400
    lineHeight: 1.50
    letterSpacing: -0.1px
  body:
    fontFamily: "Linear Text, system-ui, sans-serif"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.50
    letterSpacing: -0.05px
  body-sm:
    fontFamily: "Linear Text, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.50
    letterSpacing: 0
  caption:
    fontFamily: "Linear Text, system-ui, sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.40
    letterSpacing: 0
  button:
    fontFamily: "Linear Text, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 500
    lineHeight: 1.20
    letterSpacing: 0
  eyebrow:
    fontFamily: "Linear Text, system-ui, sans-serif"
    fontSize: 13px
    fontWeight: 500
    lineHeight: 1.30
    letterSpacing: 0.4px
  mono:
    fontFamily: "Linear Mono, ui-monospace, SF Mono, Menlo, monospace"
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.50
    letterSpacing: 0
rounded:
  xs: 4px
  sm: 6px
  md: 8px
  lg: 12px
  xl: 16px
  xxl: 24px
  pill: 9999px
  full: 9999px
spacing:
  xxs: 4px
  xs: 8px
  sm: 12px
  md: 16px
  lg: 24px
  xl: 32px
  xxl: 48px
  section: 96px
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
    padding: 8px 14px
  button-primary-pressed:
    backgroundColor: "{colors.primary-focus}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
  button-secondary:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
    padding: 8px 14px
  button-inverse:
    backgroundColor: "{colors.inverse-canvas}"
    textColor: "{colors.inverse-ink}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
    padding: 8px 14px
  pricing-card:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: 24px
  pricing-card-featured:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: 24px
  feature-card:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: 24px
  product-screenshot-card:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.xl}"
    padding: 24px
  testimonial-card:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.body-lg}"
    rounded: "{rounded.lg}"
    padding: 32px
  customer-logo-tile:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink-subtle}"
    typography: "{typography.caption}"
    rounded: "{rounded.xs}"
    padding: 16px
  text-input:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: 8px 12px
  text-input-focused:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: 8px 12px
  pricing-tab-default:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink-subtle}"
    typography: "{typography.button}"
    rounded: "{rounded.pill}"
    padding: 6px 14px
  pricing-tab-selected:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.ink}"
    typography: "{typography.button}"
    rounded: "{rounded.pill}"
    padding: 6px 14px
  cta-banner:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.headline}"
    rounded: "{rounded.lg}"
    padding: 48px
  status-badge:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.ink-muted}"
    typography: "{typography.caption}"
    rounded: "{rounded.pill}"
    padding: 2px 8px
  top-nav:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.xs}"
    height: 56px
  footer:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink-subtle}"
    typography: "{typography.caption}"
    rounded: "{rounded.xs}"
    padding: 64px 32px
---

## Overview

Linear's marketing canvas is the deepest dark surface in this collection — `{colors.canvas}` is #010102, essentially pure black with a faint blue tint. On top sits a four-step surface ladder (`{colors.surface-1}` through `{colors.surface-4}`) for cards, panels, and lifted tiles, with hairline borders running from `{colors.hairline}` (#23252a) up through `{colors.hairline-strong}` and `{colors.hairline-tertiary}`. Light gray text (`{colors.ink}` #f7f8f8) carries the body and headlines.

The single chromatic accent is **Linear lavender-blue** `{colors.primary}` (#5e6ad2) — used on the brand mark, focus rings, and the primary CTA button. Lighter hover (`{colors.primary-hover}` #828fff) and focus-tinted (`{colors.primary-focus}` #5e69d1) variants extend the same hue. Linear avoids saturated greens, oranges, reds on the marketing canvas; the only semantic color is `{colors.semantic-success}` (#27a644) for status pills.

Display type runs Linear's custom sans at weight 500–600 with negative letter-spacing scaling from -3.0px at 80px down to 0 at body. The page rhythm is dense product screenshots framed in `{colors.surface-1}` panels with `{rounded.xl}` 16px corners — the minimal chrome lets the app screenshots do the heavy lifting.

**Key Characteristics:**
- **Dark-canvas marketing system** — `{colors.canvas}` #010102 is the deepest dark surface.
- **Lavender-blue brand accent** (`{colors.primary}` #5e6ad2) — used scarcely on brand mark, focus, and the primary CTA.
- Four-step surface ladder (canvas → surface-1 → … → surface-4) carries hierarchy without shadow.
- Display tracking pulls aggressively negative (-3.0px at 80px); body holds at -0.05px.
- Cards use `{rounded.lg}` 12px corners with 1px hairline borders — never pill, rarely 16px+.
- **Product UI screenshots** dominate the page; the marketing chrome is a dark frame for the app.
- No second chromatic color. No atmospheric gradients. No spotlight cards.

## Colors

> Source pages: linear.app (home), /intake, /pricing, /contact/sales, /build.

### Brand & Accent
- **Lavender-Blue** ({colors.primary}): The signature Linear accent — primary CTA, brand mark, link emphasis.
- **Lavender Hover** ({colors.primary-hover}): Lighter lavender (#828fff) — hovered state of the primary CTA.
- **Lavender Focus** ({colors.primary-focus}): Focus-ring tint (#5e69d1) — focused inputs, focused buttons.
- **Brand Secure** ({colors.brand-secure}): Muted lavender-gray (#7a7fad) — used in "Linear Security" surfaces.

### Surface
- **Canvas** ({colors.canvas}): Default page background — #010102, near-pure black with a faint blue tint.
- **Surface 1** ({colors.surface-1}): One step above canvas — feature cards, pricing cards, product screenshot panels.
- **Surface 2** ({colors.surface-2}): Two steps above — featured pricing card, hovered cards.
- **Surface 3** ({colors.surface-3}): Three steps above — tier-three backgrounds, sub-nav.
- **Surface 4** ({colors.surface-4}): Four steps above — deepest lifted surface.
- **Hairline** ({colors.hairline}): 1px borders on cards and dividers.
- **Hairline Strong** ({colors.hairline-strong}): Stronger 1px borders — input focus rings.
- **Hairline Tertiary** ({colors.hairline-tertiary}): Tertiary borders for nested surfaces.
- **Inverse Canvas** ({colors.inverse-canvas}): Pure white — surface of the inverse pill CTA on select section openers.
- **Inverse Surface 1** ({colors.inverse-surface-1}): One step above inverse canvas.

### Text
- **Ink** ({colors.ink}): Headlines and emphasized body — light gray #f7f8f8.
- **Ink Muted** ({colors.ink-muted}): Secondary type #d0d6e0 — meta info on hero panels.
- **Ink Subtle** ({colors.ink-subtle}): Tertiary type #8a8f98 — deselected pricing tabs, footer columns.
- **Ink Tertiary** ({colors.ink-tertiary}): Quaternary #62666d — disabled, footnotes.

### Semantic
- **Success Green** ({colors.semantic-success}): Status pills, success indicators. The only semantic color on marketing.
- **Overlay** ({colors.semantic-overlay}): Pure black overlay scrim for modals.

## Typography

### Font Family

- **Linear Display** — custom display sans; fallback `SF Pro Display, system-ui, Segoe UI, Roboto`. Carries display-xl through subhead.
- **Linear Text** — custom text cut tuned for body; same fallback stack. Carries body, buttons, captions.
- **Linear Mono** — custom mono; fallback `ui-monospace, SF Mono, Menlo`. Code snippets in product screenshots.

**Free substitute**: Inter at weight 500/600/700 is the closest cross-platform replacement; Geist Sans also viable. Mono: JetBrains Mono or Geist Mono.

### Hierarchy

| Token | Size | Weight | Line Height | Letter Spacing | Use |
|---|---|---|---|---|---|
| `{typography.display-xl}` | 80px | 600 | 1.05 | -3.0px | Largest hero headline |
| `{typography.display-lg}` | 56px | 600 | 1.10 | -1.8px | Section opener headlines |
| `{typography.display-md}` | 40px | 600 | 1.15 | -1.0px | Sub-section headlines |
| `{typography.headline}` | 28px | 600 | 1.20 | -0.6px | Pricing tier titles, CTA banner heading |
| `{typography.card-title}` | 22px | 500 | 1.25 | -0.4px | Feature card title |
| `{typography.subhead}` | 20px | 400 | 1.40 | -0.2px | Lead body, intro paragraphs |
| `{typography.body-lg}` | 18px | 400 | 1.50 | -0.1px | Hero subhead, lead paragraphs |
| `{typography.body}` | 16px | 400 | 1.50 | -0.05px | Default body |
| `{typography.body-sm}` | 14px | 400 | 1.50 | 0 | Card body, footer columns |
| `{typography.caption}` | 12px | 400 | 1.40 | 0 | Captions, meta, status |
| `{typography.button}` | 14px | 500 | 1.20 | 0 | All button labels |
| `{typography.eyebrow}` | 13px | 500 | 1.30 | 0.4px | Section eyebrow (positive tracking) |
| `{typography.mono}` | 13px | 400 | 1.50 | 0 | Code in product screenshots |

### Principles

- **Aggressive negative tracking on display** (-3.0px at 80px ≈ 4% of size).
- **Single voice from display to body** — display-xl 600 → body 400, same family.
- **Eyebrow uses positive tracking** (+0.4px) — marks the eyebrow as taxonomy.
- **Mono only in code contexts.**

## Layout

### Spacing System

- **Base unit**: 4px.
- **Tokens**: `{spacing.xxs}` 4px · `{spacing.xs}` 8px · `{spacing.sm}` 12px · `{spacing.md}` 16px · `{spacing.lg}` 24px · `{spacing.xl}` 32px · `{spacing.xxl}` 48px · `{spacing.section}` 96px.
- Card interior: `{spacing.lg}` 24px feature/pricing, `{spacing.xl}` 32px testimonial, `{spacing.xxl}` 48px CTA banner.
- Pill button padding: 8px vertical · 14px horizontal. Input padding: 8px vertical · 12px horizontal.

### Grid & Container

- Max content width ~1280px.
- Card grids: 3-up desktop, 2-up tablet, 1-up mobile; pricing 3-up.
- Product screenshot panels span full content width — the protagonist.

### Whitespace Philosophy

The dark canvas IS the whitespace. Sections separate by lift onto surface-1 panels, not gaps in white. `{spacing.lg}` 24px gaps within panels; `{spacing.section}` 96px between sections.

## Elevation & Depth

| Level | Treatment | Use |
|---|---|---|
| 0 (flat) | No shadow, no border | Default body type, hero text, footer |
| 1 (charcoal lift) | `{colors.surface-1}` on canvas, 1px `{colors.hairline}` | Default cards, product panels |
| 2 (surface-2 lift) | `{colors.surface-2}`, 1px `{colors.hairline-strong}` | Featured pricing card, hovered cards |
| 3 (surface-3 lift) | `{colors.surface-3}` | Sub-nav, dropdown menus |
| 4 (focus ring) | 2px `{colors.primary-focus}` outline at 50% opacity | Focused input, focused button |

Depth is carried by surface ladder + hairline borders. The brand resists drop shadows on dark almost entirely.

### Decorative Depth

- Product UI screenshots dominate as decorative depth.
- No atmospheric gradients, no spotlight cards.
- Subtle white edge highlight on top edge of lifted panels — faint "pixel rendered" feel.

## Shapes

### Border Radius Scale

| Token | Value | Use |
|---|---|---|
| `{rounded.xs}` | 4px | Small chips, status badges |
| `{rounded.sm}` | 6px | Inline tags |
| `{rounded.md}` | 8px | All buttons, form inputs |
| `{rounded.lg}` | 12px | Pricing/feature/testimonial cards |
| `{rounded.xl}` | 16px | Product screenshot panels |
| `{rounded.xxl}` | 24px | Oversized CTA banners (rare) |
| `{rounded.pill}` | 9999px | Pricing tab toggles, status pills |
| `{rounded.full}` | 9999px | Avatar circles |

### Photography & Illustration Geometry

- Product screenshots sit in `{rounded.xl}` 16px tiles with `{spacing.lg}` 24px outer padding.
- Customer logo tiles ~24px logo height on `{colors.canvas}`, no border.
- Avatar circles `{rounded.full}` at 32–40px.

## Components

### Buttons

**`button-primary`** — Lavender CTA. The default primary CTA across all pages.
- Background `{colors.primary}`, text `{colors.on-primary}`, type `{typography.button}`, padding 8px 14px, rounded `{rounded.md}`.
- Pressed (`button-primary-pressed`): background shifts to `{colors.primary-focus}`.
- Hover (`button-primary-hover`): background shifts to `{colors.primary-hover}`.

**`button-secondary`** — Charcoal button ("Sign in", "Read changelog").
- Background `{colors.surface-1}`, text `{colors.ink}`, type `{typography.button}`, padding 8px 14px, rounded `{rounded.md}`, 1px `{colors.hairline}` border.

**`button-inverse`** — White-on-dark inverse CTA.
- Background `{colors.inverse-canvas}`, text `{colors.inverse-ink}`, type `{typography.button}`, rounded `{rounded.md}`, padding 8px 14px.

### Pricing Tabs

**`pricing-tab-default`** + **`pricing-tab-selected`**.
- Default: `{colors.canvas}` bg, `{colors.ink-subtle}` text, `{rounded.pill}`, padding 6px 14px.
- Selected: `{colors.surface-2}` bg, `{colors.ink}` text — selected = surface lift.

### Cards & Containers

**`pricing-card`** — Each tier on /pricing. `{colors.surface-1}`, `{typography.body}`, `{rounded.lg}`, padding 24px, 1px `{colors.hairline}`.

**`pricing-card-featured`** — Recommended tier — surface lift to surface-2.

**`feature-card`** — Generic feature highlight tile. `{colors.surface-1}`, `{rounded.lg}`, padding 24px.

**`product-screenshot-card`** — Dominant card type; frames product UI. `{colors.surface-1}`, `{rounded.xl}`, padding 24px.

**`testimonial-card`** — Quote with avatar + name + role. `{colors.surface-1}`, `{typography.body-lg}`, `{rounded.lg}`, padding 32px.

**`customer-logo-tile`** — Marquee logo tile. `{colors.canvas}`, `{colors.ink-subtle}`, `{rounded.xs}`, padding 16px.

**`cta-banner`** — Closing CTA panel. `{colors.surface-1}`, `{typography.headline}`, `{rounded.lg}`, padding 48px.

### Inputs & Forms

**`text-input`** + **`text-input-focused`**.
- Background `{colors.surface-1}`, text `{colors.ink}`, type `{typography.body}`, rounded `{rounded.md}`, padding 8px 12px.
- Focus ring: 2px `{colors.primary-focus}` at 50% opacity.

## Do's and Don'ts

**Do**
- Use the surface ladder to lift: canvas → surface-1 → surface-4. Elevation = surface, not shadow.
- Keep the lavender (`{colors.primary}`) for focus, primary CTA, and the brand mark. Sparingly.
- Set display headings in weights 500–600 with the negative tracking scale.
- Lead pages with product screenshots framed in dark panels.
- Use hairline borders (1px) on all cards; the border is the light source.

**Don't**
- Never use drop shadows or atmospheric gradients on the dark canvas.
- Never introduce a second chromatic accent (no greens, oranges, reds except `{colors.semantic-success}` status).
- Never set body text below `{colors.ink-muted}` contrast for meaningful copy; reserve `{colors.ink-subtle}` for meta.
- Never use pill radius on cards — pills are for tabs/status badges only.
- Never set display type in weight 400 or body weights below 400.

## Responsive Behavior

- **Mobile (< 768px)**: card grids collapse to 1-up; nav collapses to a hamburger over full-screen overlay; type scales display-xl to ~40px; padding stacks to `{spacing.xs}`/`{spacing.sm}`.
- **Tablet (768–1024px)**: 2-up card grids; product screenshots keep full width; top-nav keeps inline links.
- **Desktop (> 1024px)**: 3-up grids, max content width 1280px; pill pricing tabs show inline; section spacing `{spacing.section}` 96px.
- Touch targets: buttons and inputs keep ≥ 8px vertical padding; minimum 32px tap height.

## Agent Prompt Guide

Quick references for generation prompts:

- **Colors**: canvas `{colors.canvas}` · ink `{colors.ink}` · primary `{colors.primary}` · surface-1 `{colors.surface-1}` · hairline `{colors.hairline}`
- **Type**: display-xl `{typography.display-xl}` (80px/600/-3.0px) · body `{typography.body}` (16px/400) · button `{typography.button}` (14px/500)
- **Radius**: buttons `{rounded.md}` · cards `{rounded.lg}` · screenshots `{rounded.xl}` · pills `{rounded.pill}`
- **Spacing**: card padding `{spacing.lg}` · section `{spacing.section}`

Prompt template: "Build a pricing page for {product}. Use DESIGN.md tokens: canvas
{colors.canvas}, surface-1 {colors.surface-1}, primary {colors.primary} for CTA, display-lg
{typography.display-lg} for headings, body {typography.body}, card radius {rounded.lg},
section spacing {spacing.section}. Elevation via surface ladder only — no shadows. One
chromatic accent only."