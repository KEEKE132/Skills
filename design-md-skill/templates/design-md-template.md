---
version: alpha
name: {brand-slug}-design-analysis
description: "{1-3 sentence single-line summary: canvas, ink, primary accent, surface behavior, type character, depth philosophy. Double-quoted.}"
colors:
  primary: "#XXXXXX"
  primary-hover: "#XXXXXX"
  primary-focus: "#XXXXXX"
  ink: "#XXXXXX"
  ink-muted: "#XXXXXX"
  ink-subtle: "#XXXXXX"
  canvas: "#XXXXXX"
  surface-1: "#XXXXXX"
  surface-2: "#XXXXXX"
  hairline: "#XXXXXX"
  on-primary: "#XXXXXX"
  semantic-success: "#XXXXXX"
  semantic-overlay: "#XXXXXX"
typography:
  display-xl:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 72px
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: -2.0px
  display-lg:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 48px
    fontWeight: 600
    lineHeight: 1.10
    letterSpacing: -1.0px
  display-md:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 36px
    fontWeight: 600
    lineHeight: 1.15
    letterSpacing: -0.5px
  headline:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 24px
    fontWeight: 600
    lineHeight: 1.25
    letterSpacing: -0.2px
  body-lg:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 18px
    fontWeight: 400
    lineHeight: 1.50
    letterSpacing: 0
  body:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.50
    letterSpacing: 0
  body-sm:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.50
    letterSpacing: 0
  caption:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.40
    letterSpacing: 0
  button:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 500
    lineHeight: 1.20
    letterSpacing: 0
  eyebrow:
    fontFamily: "Brand Sans, system-ui, sans-serif"
    fontSize: 13px
    fontWeight: 500
    lineHeight: 1.30
    letterSpacing: 0.4px
  mono:
    fontFamily: "ui-monospace, SF Mono, Menlo, monospace"
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
  pill: 9999px
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
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
    textColor: "{colors.on-primary}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
    padding: 8px 14px
  button-secondary:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.button}"
    rounded: "{rounded.md}"
    padding: 8px 14px
  feature-card:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: 24px
  text-input:
    backgroundColor: "{colors.surface-1}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: 8px 12px
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

{2-3 paragraphs: canvas, accent discipline, type character, layout rhythm. End with 5-8 Key Characteristics bullets.}

**Key Characteristics:**
- {characteristic}
- {characteristic}
- {characteristic}

## Colors

> Source pages: {source URLs or "user-provided material"}.

### Brand & Accent
- **{Name}** ({colors.primary}): {role and usage}.

### Surface
- **Canvas** ({colors.canvas}): {role}.

### Text
- **Ink** ({colors.ink}): {role}.

### Semantic
- **Success** ({colors.semantic-success}): {role}.

## Typography

### Font Family
{family stack + free substitute recommendation if proprietary.}

### Hierarchy

| Token | Size | Weight | Line Height | Letter Spacing | Use |
|---|---|---|---|---|---|
| `{typography.display-xl}` | 72px | 600 | 1.05 | -2.0px | Largest hero headline |
| `{typography.body}` | 16px | 400 | 1.50 | 0 | Default body |

### Principles
- {principle}

## Layout

### Spacing System
- **Base unit**: {n}px.
- **Tokens**: `{spacing.xs}` npx · `{spacing.md}` npx · `{spacing.section}` npx.

### Grid & Container
- Max content width: {n}px. Cards: {n}-up desktop → {n}-up tablet → 1-up mobile.

### Whitespace Philosophy
- {philosophy}

## Elevation & Depth

| Level | Treatment | Use |
|---|---|---|
| 0 (flat) | No shadow, no border | Default body type |
| 1 (surface lift) | `{colors.surface-1}` + 1px `{colors.hairline}` | Default cards |

## Shapes

### Border Radius Scale

| Token | Value | Use |
|---|---|---|
| `{rounded.md}` | 8px | Buttons, inputs |

## Components

### Buttons
**`button-primary`** — {description}.
- Background `{colors.primary}`, text `{colors.on-primary}`, type `{typography.button}`, padding 8px 14px, rounded `{rounded.md}`.

### Cards & Containers
**`feature-card`** — {description}.

### Inputs & Forms
**`text-input`** — {description}.

## Do's and Don'ts

**Do**
- {rule}
- {rule}

**Don't**
- {rule}
- {rule}
- {rule}

## Responsive Behavior

- **Mobile (< 768px)**: {collapse strategy}.
- **Tablet (768–1024px)**: {adjustment}.
- **Desktop (> 1024px)**: {layout}.

## Agent Prompt Guide

Quick references for generation prompts:

- **Colors**: canvas `{colors.canvas}` · ink `{colors.ink}` · primary `{colors.primary}`
- **Type**: display `{typography.display-xl}` · body `{typography.body}` · button `{typography.button}`
- **Radius**: buttons `{rounded.md}` · cards `{rounded.lg}` · pills `{rounded.pill}`

Prompt template: "Build a {page-type} for {product}. Use DESIGN.md tokens: canvas
{colors.canvas}, primary {colors.primary}, display type {typography.display-xl}, card radius
{rounded.lg}, section spacing {spacing.section}. Follow the Do/Don't guardrails."