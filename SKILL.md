---
name: ui-spec
description: Shark-Style web admin UI design system — colors, typography, spacing, components, animations as precise CSS tokens and implementation rules
trigger: /ui-spec
---

# /ui-spec

Apply the Shark-Style design system when writing any frontend code (HTML, CSS, React, Vue, etc.). Never deviate from these tokens without explicit user instruction.

---

# DESIGN SYSTEM: Shark-Style Web Admin

## Core Philosophy
1. **Clarity** — Text is always legible (min contrast 4.5:1), icons are purposeful, UI serves content
2. **Deference** — Interface steps back; frosted glass and subtle color let content lead
3. **Depth** — Spring motion, layered materials, and shadow communicate hierarchy

---

## COLOR TOKENS

### System Colors
```css
--color-blue:        #007AFF;  /* dark: #0A84FF */
--color-green:       #34C759;  /* dark: #30D158 */
--color-red:         #FF3B30;  /* dark: #FF453A */
--color-orange:      #FF9500;  /* dark: #FF9F0A */
--color-yellow:      #FFCC00;  /* dark: #FFD60A */
--color-pink:        #FF2D55;  /* dark: #FF375F */
--color-purple:      #AF52DE;  /* dark: #BF5AF2 */
--color-teal:        #5AC8FA;  /* dark: #64D2FF */
--color-indigo:      #5856D6;  /* dark: #5E5CE6 */
```

### Grays (Light Mode)
```css
--gray-1: #8E8E93;   /* disabled text, icons */
--gray-2: #AEAEB2;   /* secondary icons */
--gray-3: #C7C7CC;   /* borders, dividers */
--gray-4: #D1D1D6;   /* light borders */
--gray-5: #E5E5EA;   /* secondary backgrounds, tag bg */
--gray-6: #F2F2F7;   /* page background */
```

### Text Colors
```css
--label:            #1D1D1F;                  /* primary text */
--secondary-label:  rgba(60, 60, 67, 0.60);   /* secondary text */
--tertiary-label:   rgba(60, 60, 67, 0.30);   /* tertiary text */
--placeholder-text: rgba(60, 60, 67, 0.30);   /* input placeholder */
```

### Backgrounds
```css
--bg-primary:   #FFFFFF;   /* cards, content areas */
--bg-secondary: #F2F2F7;   /* page background */
--bg-alt:       #F5F5F7;   /* alternating sections */
```

### Separators
```css
--separator:        rgba(60, 60, 67, 0.29);
--opaque-separator: #C6C6C8;
```

### Interactive Blue (Web)
```css
--color-action:        #0071E3;
--color-action-hover:  #0077ED;
--color-action-active: #006EDB;
--link:                #007AFF;
```

### Semantic Fill
```css
--fill:           rgba(120, 120, 128, 0.20);
--secondary-fill: rgba(120, 120, 128, 0.16);
--tertiary-fill:  rgba(118, 118, 128, 0.12);
```

---

## TYPOGRAPHY

### Font Stack
```css
--font-sans: "SF Pro Display", "SF Pro Text", -apple-system, BlinkMacSystemFont, "Helvetica Neue", Arial, sans-serif;
--font-mono: "SF Mono", "Menlo", "Monaco", "Courier New", monospace;
```

### Type Scale
| Token | Size | Line Height | Weight | Use |
|-------|------|-------------|--------|-----|
| `--text-large-title` | 34px | 41px | 400 | Page hero title |
| `--text-title-1` | 28px | 34px | 400 | Module title |
| `--text-title-2` | 22px | 28px | 400 | Section title |
| `--text-title-3` | 20px | 25px | 400 | Subsection title |
| `--text-headline` | 17px | 22px | **600** | Nav bar title, emphasis |
| `--text-body` | 17px | 22px | 400 | Body text |
| `--text-callout` | 16px | 21px | 400 | Callout text |
| `--text-subhead` | 15px | 20px | 400 | Secondary text |
| `--text-footnote` | 13px | 18px | 400 | Helper text |
| `--text-caption-1` | 12px | 16px | 400 | Labels, captions |
| `--text-caption-2` | 11px | 13px | 400 | Smallest text |

**Rules:**
- Use weights: 400 (Regular), 500 (Medium), 600 (Semibold), 700 (Bold) only
- Avoid weights below 400 in UI
- Primary text color: `#1D1D1F` (not pure black)

---

## SPACING (8px grid)

```css
--space-1:  4px;
--space-2:  8px;
--space-3:  12px;
--space-4:  16px;   /* standard padding */
--space-5:  20px;   /* page edge margin (large screen) */
--space-6:  24px;
--space-8:  32px;
--space-10: 40px;
--space-12: 48px;
--space-16: 64px;
--space-20: 80px;
```

**Key layout values:**
- Page edge margin: 16px (small) / 20–24px (large)
- Card inner padding: 16px
- Navbar height: 44px
- Min tap target: 44×44px

---

## BORDER RADIUS

```css
--radius-xs:   4px;      /* checkboxes, small badges */
--radius-sm:   8px;      /* chips, small buttons, segmented control */
--radius-md:   10px;     /* inputs, standard cards */
--radius-lg:   12px;     /* modals, large containers */
--radius-xl:   16px;     /* large cards, alerts */
--radius-2xl:  20px;     /* hero sections */
--radius-full: 9999px;   /* capsule buttons, badges, toggles */
```

**Nesting rule:** child radius = parent radius − padding between them

---

## SHADOWS

```css
--shadow-0: none;
--shadow-1: 0 1px 2px rgba(0,0,0,.12), 0 1px 1px rgba(0,0,0,.08);    /* card at rest */
--shadow-2: 0 2px 8px rgba(0,0,0,.12), 0 1px 3px rgba(0,0,0,.08);    /* card hover, dropdown */
--shadow-3: 0 4px 16px rgba(0,0,0,.12), 0 2px 6px rgba(0,0,0,.08);   /* popovers */
--shadow-4: 0 8px 32px rgba(0,0,0,.16), 0 4px 12px rgba(0,0,0,.08);  /* modals */
--shadow-5: 0 16px 48px rgba(0,0,0,.20), 0 8px 16px rgba(0,0,0,.10); /* alert dialogs */
```

### Frosted Glass Material (navbar, sidebar)
```css
background: rgba(255, 255, 255, 0.72);
backdrop-filter: blur(20px) saturate(180%);
-webkit-backdrop-filter: blur(20px) saturate(180%);
```

---

## COMPONENTS

### Button
| Variant | Background | Text | Height | Radius | Font |
|---------|-----------|------|--------|--------|------|
| Primary | `#0071E3` | `#FFF` | 50px | `--radius-full` | 17px/600 |
| Secondary (tinted) | `rgba(0,113,227,.12)` | `#0071E3` | 34px | `--radius-full` | 15px/600 |
| Tertiary (gray) | `#E5E5EA` | `#1D1D1F` | 34px | `--radius-full` | 15px/600 |
| Ghost | transparent | `#0071E3` | 34px | `--radius-full` | 15px/400 |
| Danger | `#FF3B30` | `#FFF` | 50px | `--radius-full` | 17px/600 |

States: hover → brightness +5%; active → brightness -5%; disabled → opacity 38%

### Input / Text Field
```
height: 44px
border-radius: var(--radius-md)        /* 10px */
border: 1px solid #C7C7CC
focus border: 2px solid #0071E3
background: #FFFFFF
font: 17px/400 var(--font-sans)
padding: 0 12px
placeholder color: rgba(60,60,67,0.30)
```

### Toggle / Switch
```
size: 51×31px
track: fully rounded capsule
on-color: #34C759
off-color: #C7C7CC
thumb: #FFFFFF, ~27px diameter
animation: spring 300ms
```

### Card
```
background: #FFFFFF
border-radius: var(--radius-lg)        /* 12px */
padding: 16px
box-shadow: var(--shadow-1)
hover shadow: var(--shadow-2)
gap between cards: 8–16px
```

### Modal / Dialog
```
max-width: 560px
border-radius: var(--radius-xl)        /* 16px */
background: #FFFFFF
box-shadow: var(--shadow-4)
backdrop: rgba(0,0,0,0.40)
title: 17px/600
body: 13px/400
padding: 24px
```

### Alert Banner
| Variant | Left Border | Icon Color | Background |
|---------|-------------|------------|------------|
| Info | `#007AFF` | `#007AFF` | `rgba(0,122,255,.06)` |
| Success | `#34C759` | `#34C759` | `rgba(52,199,89,.06)` |
| Warning | `#FF9500` | `#FF9500` | `rgba(255,149,0,.06)` |
| Error | `#FF3B30` | `#FF3B30` | `rgba(255,59,48,.06)` |

```
border-radius: var(--radius-md)
border-left: 3px solid [variant color]
padding: 12px 16px
title: 15px/600
body: 13px/400
```

### Badge / Tag
```
font: 12px/700
padding: 3px 8px
border-radius: var(--radius-full)
min-width: height (circle for single char)
text: #FFFFFF
```

### Navigation Bar
```
height: 44px (large title: 96px)
background: rgba(255,255,255,0.72) + backdrop-filter: blur(20px) saturate(180%)
title: 17px/600
large title: 34px/700
border-bottom: 0.5px solid rgba(60,60,67,0.29)
```

### List Row
```
min-height: 44px
padding: 0 16px
separator: 0.5px solid rgba(60,60,67,0.29) with 16px left inset
section header: 13px/400 uppercase var(--secondary-label)
selected bg: #E5E5EA
```

### Segmented Control
```
height: 32px
background: rgba(118,118,128,.12)
selected bg: #FFFFFF
selected shadow: var(--shadow-1)
border-radius: var(--radius-sm)        /* 8px */
font: 13px/600
padding: 0 12px
```

### Breadcrumb
```
font: 13px/400
separator: chevron › color var(--gray-2)
active item: var(--label)
inactive items: var(--secondary-label)
hover: var(--color-action)
gap: 4px
```

### Search Field
```
height: 36px
background: rgba(118,118,128,.12)
border-radius: var(--radius-full)
padding: 0 12px 0 32px    /* left: icon space */
icon: magnifying glass, var(--gray-1), 14px
clear button: × var(--gray-1), appears on input
font: 15px/400
```

---

## ANIMATION

```css
--duration-fast:     150ms;   /* hover, micro-interactions */
--duration-standard: 250ms;   /* most transitions */
--duration-medium:   350ms;   /* modal appear */
--duration-slow:     500ms;   /* complex layout changes */

--ease-default: cubic-bezier(0.42, 0.00, 0.58, 1.00);
--ease-enter:   cubic-bezier(0.00, 0.00, 0.20, 1.00);
--ease-exit:    cubic-bezier(0.40, 0.00, 1.00, 1.00);
--ease-spring:  cubic-bezier(0.175, 0.885, 0.32, 1.275);
```

**Rules:**
- Animate only `transform` and `opacity` (GPU-accelerated)
- Always include `@media (prefers-reduced-motion: reduce)` override
- Prefer spring easing for interactive elements

---

## RESPONSIVE BREAKPOINTS

| Name | Width | Layout |
|------|-------|--------|
| mobile | ≤ 735px | Single column, sidebar hidden |
| tablet | ≤ 1068px | Two column, sidebar collapsed |
| desktop | > 1068px | Full layout with sidebar |

---

## IMPLEMENTATION RULES

When writing code with this design system:
1. **Always** use CSS custom properties (variables) from this spec
2. **Never** use hard-coded color values outside this spec without justification
3. **Always** ensure text meets WCAG AA contrast (4.5:1 normal, 3:1 large)
4. **Always** provide hover, focus, active, and disabled states for interactive elements
5. **Focus rings** must be visible: `outline: 2px solid var(--color-action); outline-offset: 2px;`
6. For React: use CSS Modules or Tailwind with a custom theme extending these tokens
7. For Vue: use CSS variables in `:root` and component scoped styles
8. For plain CSS/HTML: declare all `:root` variables at the top of your stylesheet

## OUTPUT FORMAT

When implementing UI with this design system, always:
1. Output complete, working code (not snippets)
2. Include all states (hover, focus, active, disabled)
3. Include responsive behavior
4. Add `prefers-reduced-motion` media query for animated elements
5. Comment non-obvious design decisions referencing spec token names
