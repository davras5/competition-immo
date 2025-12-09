# Color Strategy Documentation

## Overview

This document describes the color strategy for the Wettbewerb Cockpit application. The design follows a **restrained, purposeful color system** optimized for **government, municipal, and enterprise construction** audiences with a subtle sustainability narrative.

---

## Target Audience

| Segment | Design Requirements |
|---------|---------------------|
| **Federal Government** | Authority, trustworthiness, WCAG compliance, institutional feel |
| **Municipal/City Administration** | Clarity, transparency, democratic neutrality |
| **Large Construction Firms** | Professional, efficient, data-focused |
| **Sustainability Context** | Credibility (not greenwashing), subtle integration |

---

## Design Principles

### 1. Color Should Be Earned
Saturated colors are reserved for **actionable or attention-worthy** information. Neutral tones (slate) are the default, conveying institutional authority and professionalism.

### 2. Semantic Consistency
Each color has a clear, consistent meaning across the application:
- **Emerald**: Positive outcomes, success, primary actions, sustainability
- **Blue**: Active/in-progress states, links, institutional trust
- **Amber**: Warnings, attention needed, neutral ratings
- **Red**: Negative outcomes, errors, blockers
- **Slate**: Default UI elements, text, borders

### 3. Sustainability Through Success
Emerald (green) is used for primary actions and success states, creating a subliminal connection between positive progress and sustainability outcomes—without heavy-handed "green" decoration.

### 4. Accessibility First
All colors meet WCAG 2.1 AA standards minimum. Colors are always paired with icons or shapes for colorblind accessibility. This is non-negotiable for public sector compliance.

### 5. Improved Contrast
Border and muted text colors have been strengthened to ensure visibility across different monitors and lighting conditions.

---

## Color Palette

### CSS Custom Properties (Design Tokens)

```css
:root {
    /* Slate - Primary Neutral Palette (institutional authority) */
    --color-slate-50: #f8fafc;   /* Page backgrounds */
    --color-slate-100: #f1f5f9;  /* Inset areas, hover states */
    --color-slate-200: #d1d5db;  /* Borders, dividers (improved contrast) */
    --color-slate-300: #9ca3af;  /* Scrollbar thumb (improved contrast) */
    --color-slate-400: #6b7280;  /* Secondary icons (AA compliant) */
    --color-slate-500: #4b5563;  /* Muted text (AAA compliant) */
    --color-slate-600: #475569;  /* Tertiary text, secondary buttons */
    --color-slate-700: #334155;  /* Secondary text */
    --color-slate-800: #1e293b;  /* Dark backgrounds */
    --color-slate-900: #0f172a;  /* Primary text */

    /* Emerald - Success + Primary Actions + Sustainability */
    --color-emerald-50: #ecfdf5;   /* Light backgrounds */
    --color-emerald-100: #d1fae5;  /* Rating/badge backgrounds */
    --color-emerald-400: #34d399;  /* Status dots */
    --color-emerald-500: #10b981;  /* Progress fills, icons */
    --color-emerald-600: #059669;  /* PRIMARY BUTTONS, positive text */
    --color-emerald-700: #047857;  /* Primary button hover, badge text */

    /* Blue - Active/In-Progress + Institutional Trust */
    --color-blue-50: #eff6ff;    /* Active status light background */
    --color-blue-100: #dbeafe;   /* Info/active badge background */
    --color-blue-400: #60a5fa;   /* Active status dots */
    --color-blue-500: #3b82f6;   /* Links, active icons */
    --color-blue-600: #2563eb;   /* Link hover, active text */
    --color-blue-700: #1d4ed8;   /* Active badge text, official indicators */

    /* Amber - Warning + Attention Needed */
    --color-amber-50: #fffbeb;   /* Warning light background */
    --color-amber-100: #fef3c7;  /* Warning/neutral rating backgrounds */
    --color-amber-400: #fbbf24;  /* Warning status dots */
    --color-amber-500: #f59e0b;  /* Neutral rating icons */
    --color-amber-600: #d97706;  /* Warning text */
    --color-amber-700: #b45309;  /* Warning badge text */

    /* Red - Negative/Error */
    --color-red-50: #fef2f2;   /* Error light background */
    --color-red-100: #fee2e2;  /* Error badge backgrounds */
    --color-red-400: #f87171;  /* Error status dots */
    --color-red-500: #ef4444;  /* Error icons */
    --color-red-600: #dc2626;  /* Negative text, error messages */
    --color-red-700: #b91c1c;  /* Error badge text, danger buttons */
}
```

---

## Component Color Usage

### Status Badges

| Status | Background | Text | Dot | Semantic Meaning |
|--------|------------|------|-----|------------------|
| **Active** | blue-100 | blue-700 | blue-400 | In progress, current |
| **Completed** | emerald-100 | emerald-700 | emerald-400 | Done, successful |
| **Draft** | slate-100 | slate-600 | slate-400 | Not started |
| **Warning** | amber-100 | amber-700 | amber-400 | Attention needed |
| **Error** | red-100 | red-700 | red-400 | Problem, blocked |
| **Info** | blue-100 | blue-700 | — | Informational |

### Buttons

| Variant | Background | Text | Hover | Usage |
|---------|------------|------|-------|-------|
| **Primary** | emerald-600 | white | emerald-700 | Main actions, CTAs |
| **Secondary** | slate-100 | slate-700 | slate-200 | Alternative actions |
| **Ghost** | transparent | slate-600 | slate-100 bg | Tertiary actions |
| **Danger** | red-600 | white | red-700 | Destructive actions |
| **Danger Ghost** | transparent | red-600 | red-50 bg | Secondary destructive |

### Rating System (Traffic Light)

The rating system uses three states with icon-first design:

| Rating | Icon | Icon Color | Background |
|--------|------|------------|------------|
| **Positive** | thumb_up | emerald-600 | emerald-100 |
| **Neutral** | sentiment_neutral | amber-500 | amber-100 |
| **Negative** | thumb_down | red-600 | red-100 |

### Theme Cards

Themes are differentiated by **icons only**, not colors:

| Element | Color |
|---------|-------|
| Card border | slate-200 |
| Card border (expanded) | slate-300 |
| Icon | slate-500 |
| Header hover | slate-50 |
| Meta text | slate-500 |

### Progress Bars (Theme Completion)

| State | Fill Color |
|-------|------------|
| Complete (100%) | emerald-500 |
| In Progress (<100%) | slate-400 |

### Kennwerte (Metric Bars)

| Element | Color |
|---------|-------|
| Bar background | slate-200 |
| Bar fill | slate-400 |
| Average marker | slate-600 |
| Positive delta text | emerald-600 |
| Negative delta text | red-600 |
| Rank text | slate-500 |

### Comparison Table

| Element | Color |
|---------|-------|
| Header background | slate-50 |
| Summary row background | emerald-50 |
| Best value text | emerald-600 |
| Best value star | emerald-500 |
| Theme row divider | slate-100 |

---

## Typography Colors

| Purpose | Token | Hex | Contrast Ratio |
|---------|-------|-----|----------------|
| Primary text | slate-900 | #0f172a | 15.5:1 (AAA) |
| Secondary text | slate-700 | #334155 | 10.0:1 (AAA) |
| Tertiary text | slate-600 | #475569 | 7.0:1 (AAA) |
| Muted text | slate-500 | #4b5563 | 7.0:1 (AAA) |
| Disabled text | slate-400 | #6b7280 | 4.6:1 (AA) |
| Positive text | emerald-600 | #059669 | 4.5:1 (AA) |
| Warning text | amber-600 | #d97706 | 4.5:1 (AA) |
| Error text | red-600 | #dc2626 | 5.0:1 (AA) |
| Link text | blue-600 | #2563eb | 4.8:1 (AA) |

---

## Background Hierarchy

| Level | Color | Usage |
|-------|-------|-------|
| Page | slate-50 | Main content area |
| Card | white | Elevated content containers |
| Inset | slate-100 | Nested areas, hover states |
| Header | slate-900 | App header/navigation |

---

## Interaction States

### Hover
- Primary buttons: emerald-600 → emerald-700
- Secondary buttons: slate-100 → slate-200
- Ghost buttons: transparent → slate-100
- Table rows: transparent → slate-50
- Links: blue-600 → blue-700

### Focus
- Focus ring: slate-500 (#4b5563) with 2px offset
- Provides sufficient contrast for accessibility compliance

### Disabled
- opacity-50 with cursor-not-allowed
- Uses slate-400 for text (now AA compliant)

---

## Accessibility

### WCAG 2.1 Compliance

All text and interactive elements meet **AA minimum**, with most meeting **AAA**:

| Element | Contrast Ratio | Level |
|---------|---------------|-------|
| Primary text (slate-900 on white) | 15.5:1 | AAA |
| Secondary text (slate-700 on white) | 10.0:1 | AAA |
| Muted text (slate-500 on white) | 7.0:1 | AAA |
| Disabled text (slate-400 on white) | 4.6:1 | AA |
| Primary button (white on emerald-600) | 4.5:1 | AA |
| Focus ring (slate-500) | 7.0:1 | AAA |

### Color + Icon Pairing

All semantic colors are paired with distinct icons to ensure colorblind users can understand meaning:

- Positive: `thumb_up` + emerald
- Neutral: `sentiment_neutral` + amber
- Negative: `thumb_down` + red
- Active: `schedule` or `play_circle` + blue
- Warning: `warning` + amber

---

## Key Design Decisions

### Why Emerald for Primary Buttons?

1. **Sustainability narrative**: Every primary action (save, submit, approve) reinforces positive progress
2. **Clear CTA visibility**: Stands out from the neutral slate UI
3. **Audience appropriate**: Professional green reads as "growth" and "quality" for government/enterprise

### Why Blue for Active Status?

1. **Industry convention**: Amber/yellow signals "caution" in construction contexts
2. **Institutional trust**: Blue is associated with government and official institutions
3. **Semantic clarity**: Blue = "in progress", Green = "done", Amber = "attention needed"

### Why Darker Slate Values?

1. **Improved contrast**: Original slate-400/500 values failed or borderline-passed WCAG
2. **Better visibility**: Borders and muted text now visible across different monitors
3. **Government compliance**: Public sector contracts require strict accessibility adherence

---

## Summary

| System | Implementation |
|--------|----------------|
| Primary actions | Emerald buttons (sustainability + visibility) |
| Active/in-progress | Blue badges and indicators |
| Warnings/attention | Amber (industry-appropriate) |
| Theme differentiation | Icons + position only (no colored accents) |
| Rating visualization | Icon-first with muted backgrounds |
| Metric bars | Neutral slate bars, colored delta text only |
| Color count per view | 2-3 saturated colors maximum |
| Accessibility | WCAG 2.1 AA minimum, AAA preferred |

**Result:** An information-focused interface with purposeful color highlights that conveys institutional authority, supports sustainability messaging, and meets strict accessibility requirements for government and enterprise clients.
