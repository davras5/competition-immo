# Color Strategy Documentation

## Overview

This document describes the color strategy implemented in the Wettbewerb Cockpit application. The design follows a **restrained, purposeful color system** that prioritizes clarity and reduces visual noise.

---

## Design Principles

### 1. Color Should Be Earned
Saturated colors are reserved for **actionable or attention-worthy** information. Neutral tones (slate) are the default.

### 2. Semantic Consistency
Each color has a clear, consistent meaning across the application:
- **Emerald**: Positive outcomes, completion, success
- **Red**: Negative outcomes, errors, warnings
- **Amber**: Neutral ratings, active/in-progress states
- **Slate**: Default UI elements, text, borders

### 3. Reduced Visual Complexity
Theme differentiation uses **icons and position** rather than multiple saturated colors, keeping the focus on meaningful data.

---

## Color Palette

### CSS Custom Properties (Design Tokens)

```css
:root {
    /* Slate - Primary Neutral Palette */
    --color-slate-50: #f8fafc;   /* Page backgrounds */
    --color-slate-100: #f1f5f9;  /* Inset areas, hover states */
    --color-slate-200: #e2e8f0;  /* Borders, dividers */
    --color-slate-300: #cbd5e1;  /* Scrollbar thumb */
    --color-slate-400: #94a3b8;  /* Secondary icons, disabled */
    --color-slate-500: #64748b;  /* Secondary text, icons */
    --color-slate-600: #475569;  /* Tertiary text */
    --color-slate-700: #334155;  /* Dark backgrounds */
    --color-slate-800: #1e293b;  /* Sidebar background */
    --color-slate-900: #0f172a;  /* Primary text */

    /* Emerald - Positive/Success */
    --color-emerald-50: #ecfdf5;   /* Light backgrounds */
    --color-emerald-100: #d1fae5;  /* Rating/badge backgrounds */
    --color-emerald-400: #34d399;  /* Status dots */
    --color-emerald-500: #10b981;  /* Primary actions, progress fills */
    --color-emerald-600: #059669;  /* Positive delta text */
    --color-emerald-700: #047857;  /* Badge text */

    /* Amber - Neutral/Warning */
    --color-amber-50: #fffbeb;   /* Light backgrounds */
    --color-amber-100: #fef3c7;  /* Rating/badge backgrounds */
    --color-amber-400: #fbbf24;  /* Status dots */
    --color-amber-500: #f59e0b;  /* Neutral rating icons */
    --color-amber-600: #d97706;  /* Warning text */
    --color-amber-700: #b45309;  /* Badge text */

    /* Red - Negative/Error */
    --color-red-50: #fef2f2;   /* Light backgrounds */
    --color-red-100: #fee2e2;  /* Rating/badge backgrounds */
    --color-red-400: #f87171;  /* Status dots */
    --color-red-500: #ef4444;  /* Error indicators */
    --color-red-600: #dc2626;  /* Negative delta text */
    --color-red-700: #b91c1c;  /* Badge text */

    /* Blue - Informational (Limited Use) */
    --color-blue-100: #dbeafe;  /* Info badge background */
    --color-blue-500: #3b82f6;  /* Active project markers */
    --color-blue-700: #1d4ed8;  /* Info badge text */

    /* Violet - Reserved (Currently Unused) */
    --color-violet-500: #8b5cf6;
}
```

---

## Component Color Usage

### Status Badges

| Status | Background | Text | Dot |
|--------|------------|------|-----|
| **Active** | amber-100 | amber-700 | amber-400 |
| **Completed** | emerald-100 | emerald-700 | emerald-400 |
| **Draft** | slate-100 | slate-600 | slate-400 |
| **Error** | red-100 | red-700 | red-500 |
| **Success** | emerald-100 | emerald-700 | emerald-400 |
| **Info** | blue-100 | blue-700 | — |

### Rating System (Traffic Light)

The rating system uses three states with icon-first design:

| Rating | Icon | Icon Color | Background |
|--------|------|------------|------------|
| **Positive** | thumb_up | emerald-500/600 | emerald-100 |
| **Neutral** | sentiment_neutral | amber-500 | amber-100 |
| **Negative** | thumb_down | red-500/600 | red-100 |

**Implementation:**
- Rating indicators use muted backgrounds (100 shade) with colored icons
- Theme header badges display only colored icons with counts (no backgrounds)
- Comparison legend uses icon + text labels

### Theme Cards

Themes are differentiated by **icons only**, not colors:

| Element | Color |
|---------|-------|
| Card border | slate-200 (expanded: slate-300) |
| Icon wrapper | No background color |
| Icon | slate-500 |
| Header hover | slate-50 |
| Meta text | slate-500 |

### Progress Bars (Theme Completion)

| State | Fill Color |
|-------|------------|
| Complete (100%) | emerald-500 |
| Incomplete (<100%) | slate-400 |

### Kennwerte (Metric Bars)

The metric visualization uses **neutral bars with semantic delta text**:

| Element | Color |
|---------|-------|
| Bar background | slate-200 |
| Bar fill | slate-400 |
| Average marker | slate-600 |
| Positive delta text | emerald-600 |
| Negative delta text | red-600 |
| Rank text | slate-400 |

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

| Purpose | Class | Color |
|---------|-------|-------|
| Primary text | text-slate-900 | #0f172a |
| Secondary text | text-slate-700 | #334155 |
| Tertiary text | text-slate-600 | #475569 |
| Muted text | text-slate-500 | #64748b |
| Disabled text | text-slate-400 | #94a3b8 |
| Positive text | text-emerald-600 | #059669 |
| Warning text | text-amber-600 | #d97706 |
| Error/negative text | text-red-600 | #dc2626 |

---

## Background Hierarchy

| Level | Color | Usage |
|-------|-------|-------|
| Page | slate-50 | Main content area |
| Card | white | Elevated content containers |
| Inset | slate-100 | Nested areas, hover states |
| Sidebar | slate-800/900 | Navigation area |

---

## Interaction States

### Hover
- Buttons: `hover:bg-slate-100` or `hover:bg-slate-700` (dark)
- Table rows: `hover:bg-slate-50`
- Links/icons: `hover:text-slate-700`

### Focus
- Focus ring: slate-400 with 2px offset

### Disabled
- opacity-50 with cursor-not-allowed

---

## Accessibility

### Color + Shape Pairing
All semantic colors are paired with distinct icons:
- Positive: thumb_up + emerald
- Neutral: sentiment_neutral + amber
- Negative: thumb_down + red

### Contrast Ratios
- Primary text (slate-900 on white): 15.5:1 ✓
- Secondary text (slate-600 on white): 7.0:1 ✓
- Muted text (slate-500 on white): 4.6:1 ✓ (WCAG AA)

---

## Summary

| System | Implementation |
|--------|----------------|
| Theme differentiation | Icons + position only (no colored accents) |
| Rating visualization | Icon-first with muted backgrounds |
| Metric bars | Neutral slate bars, colored delta text only |
| Progress bars | Single color (emerald for complete, slate for incomplete) |
| Status badges | Semantic colors with light backgrounds |
| Color count per view | 2-3 saturated colors maximum |

**Result:** An information-focused interface with purposeful color highlights that reduce cognitive load and improve data comprehension.
