# Wettbewerb Cockpit Style Guide

A comprehensive design system documentation for the Wettbewerb Cockpit application.

---

## Table of Contents

1. [Design Philosophy](#design-philosophy)
2. [Target Audience](#target-audience)
3. [Color System](#color-system)
4. [Typography](#typography)
5. [Spacing & Layout](#spacing--layout)
6. [Components](#components)
7. [Iconography](#iconography)
8. [Motion & Transitions](#motion--transitions)
9. [Responsive Design](#responsive-design)
10. [Accessibility](#accessibility)
11. [Design Tokens Reference](#design-tokens-reference)

---

## Design Philosophy

### Core Principles

#### 1. Color Should Be Earned
Saturated colors are reserved for **actionable or attention-worthy** information. Neutral tones (slate) are the default, conveying institutional authority and professionalism. Every colored element must justify its presence.

#### 2. Semantic Consistency
Each color has a clear, consistent meaning across the application:
- **Emerald**: Positive outcomes, success, primary actions, sustainability
- **Blue**: Active/in-progress states, links, institutional trust
- **Amber**: Warnings, attention needed, neutral ratings
- **Red**: Negative outcomes, errors, blockers
- **Slate**: Default UI elements, text, borders

#### 3. Sustainability Through Success
Emerald (green) is used for primary actions and success states, creating a subliminal connection between positive progress and sustainability outcomes—without heavy-handed "green" decoration.

#### 4. Accessibility First
All colors meet WCAG 2.1 AA standards minimum. Colors are always paired with icons or shapes for colorblind accessibility. This is non-negotiable for public sector compliance.

#### 5. Visual Hierarchy Through Restraint
The interface achieves clarity through careful use of whitespace, typography weight, and subtle elevation—not through color saturation. Information density is balanced with breathing room.

---

## Target Audience

| Segment | Design Requirements |
|---------|---------------------|
| **Federal Government** | Authority, trustworthiness, WCAG compliance, institutional feel |
| **Municipal/City Administration** | Clarity, transparency, democratic neutrality |
| **Large Construction Firms** | Professional, efficient, data-focused |
| **Sustainability Context** | Credibility (not greenwashing), subtle integration |

---

## Color System

### Primary Palette: Slate

The slate palette forms the foundation of the interface, conveying institutional authority with improved contrast values for accessibility.

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-slate-50` | `#f8fafc` | Page backgrounds |
| `--color-slate-100` | `#f1f5f9` | Inset areas, hover states |
| `--color-slate-200` | `#d1d5db` | Borders, dividers |
| `--color-slate-300` | `#9ca3af` | Scrollbar thumb, secondary borders |
| `--color-slate-400` | `#6b7280` | Secondary icons, disabled text |
| `--color-slate-500` | `#4b5563` | Muted text |
| `--color-slate-600` | `#475569` | Tertiary text |
| `--color-slate-700` | `#334155` | Secondary text |
| `--color-slate-800` | `#1e293b` | Dark backgrounds, header |
| `--color-slate-900` | `#0f172a` | Primary text |

### Semantic Colors

#### Emerald — Success & Sustainability
```css
--color-emerald-50: #ecfdf5;   /* Light backgrounds */
--color-emerald-100: #d1fae5;  /* Badge/rating backgrounds */
--color-emerald-400: #34d399;  /* Status dots */
--color-emerald-500: #10b981;  /* Progress fills, icons */
--color-emerald-600: #059669;  /* Primary buttons, positive text */
--color-emerald-700: #047857;  /* Primary button hover, badge text */
```

#### Blue — Active & Institutional Trust
```css
--color-blue-50: #eff6ff;    /* Active status light background */
--color-blue-100: #dbeafe;   /* Info/active badge background */
--color-blue-400: #60a5fa;   /* Active status dots */
--color-blue-500: #3b82f6;   /* Links, active icons */
--color-blue-600: #2563eb;   /* Link hover, active text */
--color-blue-700: #1d4ed8;   /* Active badge text */
```

#### Amber — Warning & Attention
```css
--color-amber-50: #fffbeb;   /* Warning light background */
--color-amber-100: #fef3c7;  /* Warning/neutral rating backgrounds */
--color-amber-400: #fbbf24;  /* Warning status dots */
--color-amber-500: #f59e0b;  /* Neutral rating icons */
--color-amber-600: #d97706;  /* Warning text */
--color-amber-700: #b45309;  /* Warning badge text */
```

#### Red — Error & Negative
```css
--color-red-50: #fef2f2;   /* Error light background */
--color-red-100: #fee2e2;  /* Error badge backgrounds */
--color-red-400: #f87171;  /* Error status dots */
--color-red-500: #ef4444;  /* Error icons */
--color-red-600: #dc2626;  /* Negative text, error messages */
--color-red-700: #b91c1c;  /* Error badge text, danger buttons */
```

#### Violet — Qualitative (Frameworks)
```css
--color-violet-50: #f5f3ff;
--color-violet-100: #ede9fe;
--color-violet-400: #a78bfa;
--color-violet-500: #8b5cf6;
--color-violet-600: #7c3aed;
--color-violet-700: #6d28d9;
```

### Semantic Mappings

```css
/* Backgrounds */
--color-bg-page: var(--color-slate-50);
--color-bg-card: #ffffff;
--color-bg-inset: var(--color-slate-100);
--color-bg-sidebar: var(--color-slate-800);

/* Typography */
--color-text-primary: var(--color-slate-900);
--color-text-secondary: var(--color-slate-700);
--color-text-tertiary: var(--color-slate-600);
--color-text-muted: var(--color-slate-500);
--color-text-disabled: var(--color-slate-400);
--color-text-inverse: #ffffff;

/* Borders */
--color-border: var(--color-slate-200);
--color-border-dark: var(--color-slate-300);
```

### Background Hierarchy

| Level | Color | Usage |
|-------|-------|-------|
| Page | `slate-50` | Main content area |
| Card | `white` | Elevated content containers |
| Inset | `slate-100` | Nested areas, hover states |
| Header | `slate-900` | App header/navigation |
| Sidebar | `slate-800` | Vertical navigation |

---

## Typography

### Font Family

**Primary:** Source Sans 3 (Google Fonts)

```css
--font-family: 'Source Sans 3', -apple-system, BlinkMacSystemFont,
               'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
```

**Monospace:** (for code, IDs, technical data)
```css
font-family: ui-monospace, SFMono-Regular, "SF Mono", Menlo, Consolas, monospace;
```

### Type Scale

| Token | Size | Pixels | Usage |
|-------|------|--------|-------|
| `--text-xs` | 0.75rem | 12px | Meta text, labels, helper text |
| `--text-sm` | 0.875rem | 14px | Body text, default |
| `--text-base` | 1rem | 16px | Emphasized body |
| `--text-lg` | 1.125rem | 18px | Subheadings |
| `--text-xl` | 1.25rem | 20px | Section headers |
| `--text-2xl` | 1.5rem | 24px | Page section titles |
| `--text-3xl` | 1.875rem | 30px | Major headings |
| `--text-4xl` | 2.25rem | 36px | Hero text |
| `--text-5xl` | 3rem | 48px | Page titles |

### Font Weights

| Token | Weight | Usage |
|-------|--------|-------|
| `--font-light` | 300 | Decorative, hero text |
| `--font-normal` | 400 | Body text, default |
| `--font-medium` | 500 | Buttons, emphasized text |
| `--font-semibold` | 600 | Headings, labels |
| `--font-bold` | 700 | Page titles, strong emphasis |

### Line Heights

| Token | Value | Usage |
|-------|-------|-------|
| `--leading-none` | 1 | Single-line elements, icons |
| `--leading-tight` | 1.25 | Headings |
| `--leading-snug` | 1.375 | Subheadings |
| `--leading-normal` | 1.5 | Body text |
| `--leading-relaxed` | 1.625 | Long-form content |

### Typography Hierarchy

| Element | Token/Class | Size | Weight | Line Height |
|---------|-------------|------|--------|-------------|
| Page Title | `.heading-1` | 48px | 700 | 1.1 |
| Section Title | `.heading-2` | 30px | 600 | 1.2 |
| Subsection | `.heading-3` | 20px | 600 | 1.3 |
| Subheading | `.subheading` | 18px | 500 | 1.5 |
| Body | default | 14px | 400 | 1.5 |
| Small | `.text-xs` | 12px | 400 | 1.5 |
| Label | `.label-value-label` | 12px | 400 | — |

### Text Color Contrast

| Purpose | Token | Hex | Contrast Ratio |
|---------|-------|-----|----------------|
| Primary text | `slate-900` | #0f172a | 15.5:1 (AAA) |
| Secondary text | `slate-700` | #334155 | 10.0:1 (AAA) |
| Tertiary text | `slate-600` | #475569 | 7.0:1 (AAA) |
| Muted text | `slate-500` | #4b5563 | 7.0:1 (AAA) |
| Disabled text | `slate-400` | #6b7280 | 4.6:1 (AA) |
| Positive text | `emerald-600` | #059669 | 4.5:1 (AA) |
| Warning text | `amber-600` | #d97706 | 4.5:1 (AA) |
| Error text | `red-600` | #dc2626 | 5.0:1 (AA) |
| Link text | `blue-600` | #2563eb | 4.8:1 (AA) |

---

## Spacing & Layout

### 4px Grid System

All spacing values are based on a 4px grid to ensure visual harmony.

| Token | Value | Pixels |
|-------|-------|--------|
| `--space-0` | 0 | 0px |
| `--space-0-5` | 0.125rem | 2px |
| `--space-1` | 0.25rem | 4px |
| `--space-1-5` | 0.375rem | 6px |
| `--space-2` | 0.5rem | 8px |
| `--space-2-5` | 0.625rem | 10px |
| `--space-3` | 0.75rem | 12px |
| `--space-4` | 1rem | 16px |
| `--space-5` | 1.25rem | 20px |
| `--space-6` | 1.5rem | 24px |
| `--space-8` | 2rem | 32px |
| `--space-10` | 2.5rem | 40px |
| `--space-12` | 3rem | 48px |
| `--space-16` | 4rem | 64px |
| `--space-20` | 5rem | 80px |
| `--space-24` | 6rem | 96px |

### Layout Constants

| Token | Value | Usage |
|-------|-------|-------|
| `--max-width` | 1200px | Maximum content width |
| `--header-height` | 64px | Fixed header height |

### Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| `--radius-sm` | 4px | Small elements, tags |
| `--radius-md` | 6px | Buttons, inputs |
| `--radius-lg` | 8px | Cards, containers |
| `--radius-xl` | 12px | Large cards, modals |
| `--radius-2xl` | 16px | Hero sections |
| `--radius-full` | 9999px | Pills, avatars |

### Shadows (Elevation)

| Token | Usage |
|-------|-------|
| `--shadow-sm` | Subtle lift (cards at rest) |
| `--shadow-md` | Standard elevation (dropdowns) |
| `--shadow-lg` | Prominent elevation (hover states) |
| `--shadow-xl` | Maximum elevation (modals, overlays) |

```css
--shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
--shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
--shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
--shadow-xl: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
```

---

## Components

### Buttons

#### Variants

| Variant | Background | Text | Hover | Usage |
|---------|------------|------|-------|-------|
| **Primary** | `emerald-600` | white | `emerald-700` | Main actions, CTAs |
| **Secondary** | `slate-100` | `slate-700` | `slate-200` | Alternative actions |
| **Ghost** | transparent | `slate-600` | `slate-100` bg | Tertiary actions |
| **Danger** | `red-600` | white | `red-700` | Destructive actions |
| **Danger Ghost** | transparent | `red-600` | `red-50` bg | Secondary destructive |

#### Sizes

| Size | Padding | Font Size | Class |
|------|---------|-----------|-------|
| Small | 8px 16px | 14px | `.btn-sm` |
| Medium | 12px 24px | 16px | `.btn-md` |
| Large | 16px 32px | 18px | `.btn-lg` |

```html
<!-- Primary Button -->
<button class="btn-primary btn-md">
    <span class="material-symbols-outlined">save</span>
    Save Changes
</button>

<!-- Secondary Button -->
<button class="btn-secondary btn-md">Cancel</button>

<!-- Ghost Button -->
<button class="btn-ghost btn-sm">More Options</button>
```

### Status Badges

| Status | Background | Text | Dot | Meaning |
|--------|------------|------|-----|---------|
| **Active** | `blue-100` | `blue-700` | `blue-400` | In progress |
| **Completed** | `emerald-100` | `emerald-700` | `emerald-400` | Done, successful |
| **Draft** | `slate-100` | `slate-600` | `slate-400` | Not started |
| **Warning** | `amber-100` | `amber-700` | `amber-400` | Attention needed |
| **Error** | `red-100` | `red-700` | `red-400` | Problem, blocked |
| **Info** | `blue-100` | `blue-700` | — | Informational |

```html
<span class="badge-md badge-active">
    <span class="badge-dot"></span>
    Aktiv
</span>
```

### Cards

Standard card styling with elevation and borders:

```css
.card {
    background: white;
    border: 1px solid var(--color-slate-200);
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-sm);
}

.card:hover {
    border-color: var(--color-slate-300);
    box-shadow: var(--shadow-md);
}
```

| Element | Style |
|---------|-------|
| Background | white |
| Border | 1px `slate-200` |
| Border radius | 8px (`--radius-lg`) |
| Shadow | `--shadow-sm` |
| Hover border | `slate-300` |
| Hover shadow | `--shadow-md` |

### Rating System

Icon-first design with semantic colors:

| Rating | Icon | Icon Color | Background |
|--------|------|------------|------------|
| **Positive** | `thumb_up` | `emerald-600` | `emerald-100` |
| **Neutral** | `sentiment_neutral` | `amber-500` | `amber-100` |
| **Negative** | `thumb_down` | `red-600` | `red-100` |

```html
<button class="rating-btn rating-btn-positive">
    <span class="material-symbols-outlined">thumb_up</span>
</button>
```

### Form Inputs

```html
<div class="input-wrapper">
    <label class="input-label">
        Field Label
        <span class="input-required">*</span>
    </label>
    <input type="text" class="input" placeholder="Enter value...">
    <span class="input-help">Helper text here</span>
</div>
```

| State | Border | Background |
|-------|--------|------------|
| Default | `slate-200` | white |
| Focus | `slate-500` + ring | white |
| Error | `red-500` | `red-50` |
| Disabled | `slate-200` | `slate-100` |

### Progress Bars

| State | Fill Color |
|-------|------------|
| Complete (100%) | `emerald-500` |
| In Progress (<100%) | `slate-400` |

```html
<div class="progress-bar progress-bar-md">
    <div class="progress-bar-fill progress-bar-emerald" style="width: 75%"></div>
</div>
```

### Collapsible Sections

```html
<div class="collapsible">
    <button class="collapsible-header">
        <span class="collapsible-icon-wrapper">
            <span class="material-symbols-outlined">expand_more</span>
        </span>
        Section Title
    </button>
    <div class="collapsible-content">
        Content here...
    </div>
</div>
```

| Element | Color |
|---------|-------|
| Border | `slate-200` |
| Border (expanded) | `slate-300` |
| Icon | `slate-500` |
| Header hover | `slate-50` bg |

### Theme Cards

Themes are differentiated by **icons only**, not colors:

| Element | Color |
|---------|-------|
| Card border | `slate-200` |
| Card border (expanded) | `slate-300` |
| Icon | `slate-500` |
| Header hover | `slate-50` |
| Meta text | `slate-500` |

### Comparison Table

| Element | Color |
|---------|-------|
| Header background | `slate-50` |
| Summary row background | `emerald-50` |
| Best value text | `emerald-600` |
| Best value star | `emerald-500` |
| Theme row divider | `slate-100` |

### Modals

```css
.modal-backdrop {
    background: rgba(0, 0, 0, 0.5);
    z-index: var(--z-modal);
}

.modal {
    background: white;
    border-radius: var(--radius-xl);
    box-shadow: var(--shadow-xl);
    max-width: 600px;
}
```

### Dropdowns

```css
.dropdown-menu {
    background: white;
    border: 1px solid var(--color-slate-200);
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-lg);
    z-index: var(--z-dropdown);
}

.dropdown-item:hover {
    background: var(--color-slate-50);
}

.dropdown-item.active {
    background: var(--color-slate-100);
}
```

---

## Iconography

### Icon Library

**Material Symbols Outlined** (Google Fonts)

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
```

### Default Icon Settings

```css
.material-symbols-outlined {
    font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
    vertical-align: middle;
}
```

### Icon Sizes

| Context | Size | Settings |
|---------|------|----------|
| Inline text | 18px | `font-size: 18px` |
| Buttons | 20px | `font-size: 20px` |
| Navigation | 24px | Default |
| Hero/Feature | 32-48px | `font-size: 32px` |

### Semantic Icon Pairing

Colors are always paired with icons for colorblind accessibility:

| Semantic | Icon | Color |
|----------|------|-------|
| Positive | `thumb_up` | emerald |
| Neutral | `sentiment_neutral` | amber |
| Negative | `thumb_down` | red |
| Active | `schedule`, `play_circle` | blue |
| Warning | `warning` | amber |
| Error | `error` | red |
| Success | `check_circle` | emerald |
| Info | `info` | blue |

### Common Icons

| Usage | Icon Name |
|-------|-----------|
| Add | `add` |
| Edit | `edit` |
| Delete | `delete` |
| Save | `save` |
| Close | `close` |
| Menu | `menu` |
| Search | `search` |
| Filter | `filter_list` |
| Settings | `settings` |
| User | `person` |
| Expand | `expand_more` |
| Collapse | `expand_less` |
| Navigate | `arrow_forward` |
| Back | `arrow_back` |
| Download | `download` |
| Upload | `upload` |

---

## Motion & Transitions

### Timing Functions

| Token | Duration | Usage |
|-------|----------|-------|
| `--transition-fast` | 150ms | Quick feedback (hover states) |
| `--transition-base` | 200ms | Standard interactions |
| `--transition-slow` | 300ms | Important transitions (modals) |

All use `ease` timing function.

### Common Transitions

```css
/* Color transitions */
transition: color var(--transition-fast),
            background-color var(--transition-fast),
            border-color var(--transition-fast);

/* Transform transitions */
transition: transform var(--transition-base);

/* All properties */
transition: all var(--transition-base);
```

### Hover Animations

| Element | Animation |
|---------|-----------|
| Cards | Shadow increase + border darken |
| Buttons | Background color shift |
| Links | Color darken |
| Thumbnails | Scale 1.05 |
| Icons | Opacity change |

### Focus Animations

Focus states appear instantly (no transition) for accessibility.

```css
:focus {
    outline: none;
    box-shadow: 0 0 0 2px white, 0 0 0 4px var(--color-slate-400);
}
```

---

## Responsive Design

### Breakpoints

| Breakpoint | Width | Target |
|------------|-------|--------|
| Desktop | > 1024px | Full layout |
| Tablet | 768px - 1024px | Adapted columns |
| Mobile | < 768px | Single column |
| Small Mobile | < 640px | Compressed spacing |

### Responsive Patterns

#### Grid Columns

| Element | Desktop | Tablet | Mobile |
|---------|---------|--------|--------|
| Gallery grid | 3 cols | 2 cols | 1 col |
| Value grid | 3 cols | 2 cols | 1 col |
| Features grid | 3 cols | 2 cols | 1 col |
| Steps | 3 cols | 2 cols | 1 col |

#### Typography Scaling

| Element | Desktop | Tablet | Mobile |
|---------|---------|--------|--------|
| Page title | 48px | 36px | 30px |
| Section title | 30px | 24px | 20px |
| Body | 14px | 14px | 14px |

#### Layout Changes

- **Navigation**: Full horizontal → hamburger menu
- **Sidebar**: Visible → hidden/overlay
- **Footer**: Multi-column → stacked
- **Cards**: Side-by-side → stacked
- **Tables**: Scroll horizontal on overflow

### Implementation

```css
/* Tablet */
@media (max-width: 1024px) {
    .grid-cols-3 { grid-template-columns: repeat(2, 1fr); }
}

/* Mobile */
@media (max-width: 768px) {
    .heading-1 { font-size: var(--text-3xl); }
    .grid-cols-3, .grid-cols-2 { grid-template-columns: 1fr; }
    .nav { display: none; }
}

/* Small Mobile */
@media (max-width: 640px) {
    .gallery-grid { grid-template-columns: 1fr; }
}
```

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

### Focus States

All interactive elements have visible focus indicators:

```css
:focus-visible {
    outline: none;
    box-shadow: 0 0 0 2px white, 0 0 0 4px var(--color-slate-500);
}
```

### Color + Icon Pairing

All semantic colors are paired with distinct icons:

- Never rely on color alone to convey meaning
- Icons provide redundant semantic information
- Patterns and shapes supplement color coding

### Keyboard Navigation

- All interactive elements are focusable
- Logical tab order follows visual hierarchy
- Escape closes modals and dropdowns
- Arrow keys navigate within components

### Screen Reader Support

- Semantic HTML structure
- ARIA labels on icon-only buttons
- Live regions for dynamic content
- Skip links for main content

### Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}
```

---

## Design Tokens Reference

### Z-Index Scale

| Token | Value | Usage |
|-------|-------|-------|
| `--z-dropdown` | 10 | Dropdowns, popovers |
| `--z-sticky` | 20 | Sticky headers, sidebars |
| `--z-modal` | 50 | Modals, dialogs |
| `--z-tooltip` | 100 | Tooltips |

### Complete Token File

All design tokens are centralized in `/styles/tokens.css`. This file is the single source of truth for:

- Colors (primitives and semantic)
- Spacing scale
- Typography (sizes, weights, line heights)
- Layout constants
- Border radius values
- Shadow definitions
- Transition timings
- Z-index scale

---

## Design Decisions Rationale

### Why Emerald for Primary Buttons?

1. **Sustainability narrative**: Every primary action reinforces positive progress
2. **Clear CTA visibility**: Stands out from the neutral slate UI
3. **Audience appropriate**: Professional green reads as "growth" and "quality" for government/enterprise

### Why Blue for Active Status?

1. **Industry convention**: Amber/yellow signals "caution" in construction contexts
2. **Institutional trust**: Blue is associated with government and official institutions
3. **Semantic clarity**: Blue = "in progress", Green = "done", Amber = "attention needed"

### Why Darker Slate Values?

1. **Improved contrast**: Original slate-400/500 values failed WCAG standards
2. **Better visibility**: Borders and muted text visible across different monitors
3. **Government compliance**: Public sector contracts require strict accessibility adherence

### Why Theme Differentiation by Icons Only?

1. **Reduced visual noise**: Avoids rainbow of colors that dilute semantic meaning
2. **Focus on content**: Users focus on evaluation data, not decorative colors
3. **Consistency**: All themes treated equally without implicit ranking through color

### Why Icon-First Rating System?

1. **Colorblind accessibility**: Icons communicate meaning independently
2. **Touch targets**: Icon buttons provide clear, tappable areas
3. **Reduced cognitive load**: Familiar iconography (thumbs) is universally understood

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
| Spacing | 4px grid system |
| Typography | Source Sans 3, 9-step type scale |
| Motion | 150ms-300ms ease transitions |

**Result:** An information-focused interface with purposeful color highlights that conveys institutional authority, supports sustainability messaging, and meets strict accessibility requirements for government and enterprise clients.
