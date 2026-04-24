---
name: ui-spec
description: Shark-Style unified design system for Web Admin (desktop) and Mobile C-End (iOS-style phone preview) — colors, typography, spacing, components, animations as precise CSS tokens and implementation rules.
trigger: /ui-spec, /mobile-spec
---

# Shark-Style Design System
## Web Admin + Mobile C-End Unified Spec

---

## ⚠️ PLATFORM BOUNDARY — READ FIRST

| 维度 | Web 端 Admin `/ui-spec` | 手机端 C端 `/mobile-spec` |
|------|------------------------|--------------------------|
| 容器 | 响应式，≥ 1068px 全布局 | 固定 430×932px，device shell |
| 系统 UI | 无 | 状态栏 + 灵动岛 + Home Bar |
| 安全区 | 无需 | padding-top:54px / bottom:34px |
| 滚动 | 页面级 | 内容区滚动，隐藏滚动条 |
| 组件扩展 | 侧边栏、面包屑、数据表格 | Tab Bar、轮播、FAB、商品卡片 |

**Never mix web layout rules into mobile container, or mobile safe-area rules into web layout.**

---

## SHARED DESIGN TOKENS (Web & Mobile)

### Color — System

```css
--color-blue:   #007AFF;   /* dark: #0A84FF */
--color-green:  #34C759;   /* dark: #30D158 */
--color-red:    #FF3B30;   /* dark: #FF453A */
--color-orange: #FF9500;   /* dark: #FF9F0A */
--color-yellow: #FFCC00;   /* dark: #FFD60A */
--color-pink:   #FF2D55;   /* dark: #FF375F */
--color-purple: #AF52DE;   /* dark: #BF5AF2 */
--color-teal:   #5AC8FA;   /* dark: #64D2FF */
--color-indigo: #5856D6;   /* dark: #5E5CE6 */
```

### Color — Grays (Light Mode)

```css
--gray-1: #8E8E93;   /* disabled text, icons */
--gray-2: #AEAEB2;   /* secondary icons */
--gray-3: #C7C7CC;   /* borders, dividers */
--gray-4: #D1D1D6;   /* light borders */
--gray-5: #E5E5EA;   /* secondary backgrounds */
--gray-6: #F2F2F7;   /* page background */
```

### Color — Text

```css
--label:            #1D1D1F;
--secondary-label:  rgba(60, 60, 67, 0.60);
--tertiary-label:   rgba(60, 60, 67, 0.30);
--placeholder-text: rgba(60, 60, 67, 0.30);
```

### Color — Backgrounds

```css
--bg-primary:   #FFFFFF;
--bg-secondary: #F2F2F7;
--bg-alt:       #F5F5F7;
```

### Color — Interactive

```css
--color-action:        #0071E3;
--color-action-hover:  #0077ED;
--color-action-active: #006EDB;
--link:                #007AFF;
```

### Color — Fill & Separator

```css
--fill:             rgba(120, 120, 128, 0.20);
--secondary-fill:   rgba(120, 120, 128, 0.16);
--tertiary-fill:    rgba(118, 118, 128, 0.12);
--separator:        rgba(60, 60, 67, 0.29);
--opaque-separator: #C6C6C8;
```

### Typography — Font Stack

```css
--font-sans: "SF Pro Display", "SF Pro Text", -apple-system, BlinkMacSystemFont, "Helvetica Neue", Arial, sans-serif;
--font-mono: "SF Mono", "Menlo", "Monaco", "Courier New", monospace;
```

### Typography — Type Scale

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

Rules: weights 400 / 500 / 600 / 700 only. Primary text #1D1D1F (not pure black).

### Spacing — 8px Grid

```css
--space-1:  4px;   --space-2:  8px;   --space-3:  12px;
--space-4:  16px;  --space-5:  20px;  --space-6:  24px;
--space-8:  32px;  --space-10: 40px;  --space-12: 48px;
--space-16: 64px;  --space-20: 80px;
```

### Border Radius

```css
--radius-xs:   4px;
--radius-sm:   8px;
--radius-md:   10px;
--radius-lg:   12px;
--radius-xl:   16px;
--radius-2xl:  20px;
--radius-full: 9999px;
```

Nesting rule: child radius = parent radius − padding between them.

### Shadows

```css
--shadow-1: 0 1px 2px rgba(0,0,0,.12), 0 1px 1px rgba(0,0,0,.08);
--shadow-2: 0 2px 8px rgba(0,0,0,.12), 0 1px 3px rgba(0,0,0,.08);
--shadow-3: 0 4px 16px rgba(0,0,0,.12), 0 2px 6px rgba(0,0,0,.08);
--shadow-4: 0 8px 32px rgba(0,0,0,.16), 0 4px 12px rgba(0,0,0,.08);
--shadow-5: 0 16px 48px rgba(0,0,0,.20), 0 8px 16px rgba(0,0,0,.10);
```

Frosted Glass (navbar, sidebar, tab bar):
```css
background: rgba(255, 255, 255, 0.72);
backdrop-filter: blur(20px) saturate(180%);
-webkit-backdrop-filter: blur(20px) saturate(180%);
```

### Animation

```css
--duration-fast:     150ms;
--duration-standard: 250ms;
--duration-medium:   350ms;
--duration-slow:     500ms;

--ease-default: cubic-bezier(0.42, 0.00, 0.58, 1.00);
--ease-enter:   cubic-bezier(0.00, 0.00, 0.20, 1.00);
--ease-exit:    cubic-bezier(0.40, 0.00, 1.00, 1.00);
--ease-spring:  cubic-bezier(0.175, 0.885, 0.32, 1.275);
```

Rules: animate only `transform` and `opacity`. Always include `@media (prefers-reduced-motion: reduce)`.

---

## WEB ADMIN SPEC (`/ui-spec`)

### Responsive Breakpoints

| Name | Width | Layout |
|------|-------|--------|
| mobile | ≤ 735px | Single column, sidebar hidden |
| tablet | ≤ 1068px | Two column, sidebar collapsed |
| desktop | > 1068px | Full layout with sidebar |

### Layout Key Values
- Page edge margin: 16px (small) / 20–24px (large)
- Card inner padding: 16px
- Navbar height: 44px
- Min tap target: 44×44px

### Components

**Button**
| Variant | Background | Text | Height | Radius | Font |
|---------|-----------|------|--------|--------|------|
| Primary | `#0071E3` | `#FFF` | 50px | `--radius-full` | 17px/600 |
| Secondary | `rgba(0,113,227,.12)` | `#0071E3` | 34px | `--radius-full` | 15px/600 |
| Tertiary | `#E5E5EA` | `#1D1D1F` | 34px | `--radius-full` | 15px/600 |
| Ghost | transparent | `#0071E3` | 34px | `--radius-full` | 15px/400 |
| Danger | `#FF3B30` | `#FFF` | 50px | `--radius-full` | 17px/600 |

States: hover → brightness +5%; active → brightness -5%; disabled → opacity 38%

**Input / Text Field**
```
height: 44px | border-radius: var(--radius-md)
border: 1px solid #C7C7CC | focus: 2px solid #0071E3
font: 17px/400 | padding: 0 12px
```

**Card**
```
background: #FFFFFF | border-radius: var(--radius-lg)
padding: 16px | shadow: var(--shadow-1) → hover: var(--shadow-2)
gap between cards: 8–16px
```

**Navigation Bar**
```
height: 44px (large title: 96px)
background: rgba(255,255,255,0.72) + backdrop-filter: blur(20px) saturate(180%)
title: 17px/600 | large title: 34px/700
border-bottom: 0.5px solid rgba(60,60,67,0.29)
```

**Modal / Dialog**
```
max-width: 560px | border-radius: var(--radius-xl)
shadow: var(--shadow-4) | backdrop: rgba(0,0,0,0.40)
title: 17px/600 | body: 13px/400 | padding: 24px
```

**Alert Banner**
| Variant | Border | Background |
|---------|--------|------------|
| Info | `#007AFF` | `rgba(0,122,255,.06)` |
| Success | `#34C759` | `rgba(52,199,89,.06)` |
| Warning | `#FF9500` | `rgba(255,149,0,.06)` |
| Error | `#FF3B30` | `rgba(255,59,48,.06)` |

```
border-left: 3px solid [color] | padding: 12px 16px
title: 15px/600 | body: 13px/400 | border-radius: var(--radius-md)
```

**Toggle / Switch**
```
size: 51×31px | on: #34C759 | off: #C7C7CC
thumb: #FFF ~27px | animation: spring 300ms
```

**List Row**
```
min-height: 44px | padding: 0 16px
separator: 0.5px solid rgba(60,60,67,0.29) with 16px left inset
section header: 13px/400 uppercase var(--secondary-label)
```

**Segmented Control**
```
height: 32px | bg: rgba(118,118,128,.12)
selected bg: #FFF | selected shadow: var(--shadow-1)
border-radius: var(--radius-sm) | font: 13px/600
```

**Search Field**
```
height: 36px | bg: rgba(118,118,128,.12)
border-radius: var(--radius-full) | padding: 0 12px 0 32px
icon: 14px var(--gray-1) | font: 15px/400
```

**Breadcrumb**
```
font: 13px/400 | separator: › var(--gray-2)
active: var(--label) | inactive: var(--secondary-label)
hover: var(--color-action) | gap: 4px
```

**Badge / Tag**
```
font: 12px/700 | padding: 3px 8px
border-radius: var(--radius-full) | text: #FFF
```

---

## MOBILE C-END SPEC (`/mobile-spec`)

### Device Container Structure

```
.device-wrapper            outer neutral bg, centers the phone
  └── .device-shell        430x932px, border-radius:55px, overflow:hidden
        ├── .status-bar    absolute, top:0, h:54px, z-index:100
        ├── .dynamic-island  absolute, top:12px, centered, z-index:200
        ├── .content-area  absolute inset, overflow-y:auto, safe area padding
        └── .home-indicator  absolute, bottom:8px, centered, z-index:100
```

### Device Shell

```css
.device-wrapper {
  background: #E8E8ED;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}

.device-shell {
  width: 430px;
  height: 932px;
  border-radius: 55px;
  overflow: hidden;
  position: relative;
  background: #000;
  box-shadow:
    0 0 0 1px rgba(255,255,255,0.15),
    0 0 0 11px #1a1a1a,
    0 0 0 13px #3a3a3a,
    0 30px 80px rgba(0,0,0,0.5);
}
```

### Status Bar

```css
.status-bar {
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 54px;
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  padding: 0 28px 8px;
  z-index: 100;
  font-family: system-ui, -apple-system;
  font-size: 15px;
  font-weight: 500;
}
/* Left: time "09:41" | Right: signal + wifi + battery SVG icons */
```

### Dynamic Island

```css
.dynamic-island {
  position: absolute;
  top: 12px;
  left: 50%;
  transform: translateX(-50%);
  width: 125px;
  height: 37px;
  border-radius: 20px;
  background: #000000;
  z-index: 200;
}
```

### Home Indicator

```css
.home-indicator {
  position: absolute;
  bottom: 8px;
  left: 50%;
  transform: translateX(-50%);
  width: 135px;
  height: 5px;
  border-radius: 5px;
  z-index: 100;
  background: rgba(0, 0, 0, 0.20);   /* light page default */
  /* dark page: background: rgba(255,255,255,0.35); */
}
```

### Content Area (Safe Zone)

```css
.content-area {
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  overflow-y: auto;
  padding-top: 54px;
  padding-bottom: 34px;
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.content-area::-webkit-scrollbar { display: none; }
```

### Mobile-Only Components

**Bottom Tab Bar**
```
height: 83px | background: frosted glass (rgba(255,255,255,0.72) + blur)
border-top: 0.5px solid rgba(60,60,67,0.29)
icon: 24px | label: 10px/500 | active: var(--color-action)
position: absolute bottom:0 left:0 right:0
```

**Product Card**
```
border-radius: var(--radius-xl) | shadow: var(--shadow-1)
image: 16:9 or 1:1, top corners match card radius
padding: 12px
title: 15px/600 | price: 17px/700 var(--color-red) | sub: 12px/400
```

**Carousel / Banner**
```
width: 100% | border-radius: var(--radius-lg)
dots: 6px circle, bottom-center, active: var(--color-action)
edge gap: var(--space-4)
```

**Floating Action Button (FAB)**
```
size: 56x56px | border-radius: var(--radius-full)
background: var(--color-action) | icon: #FFF 24px
shadow: var(--shadow-3)
position: absolute bottom:90px right:20px
```

**Full-Width Primary Button**
```
width: 100% | height: 50px | border-radius: var(--radius-full)
background: var(--color-action) | text: #FFF 17px/600
```

**Section Header**
```
font: 22px/700 | color: var(--label)
padding: 20px 16px 8px
```

---

## UNIVERSAL IMPLEMENTATION RULES

1. Always use CSS custom properties from this spec
2. Never hard-code colors outside this spec without justification
3. Text contrast >= WCAG AA (4.5:1 normal, 3:1 large)
4. All interactive elements: hover + focus + active + disabled states
5. Focus rings: outline: 2px solid var(--color-action); outline-offset: 2px
6. Animate only transform and opacity (GPU-accelerated)
7. Always include @media (prefers-reduced-motion: reduce) override
8. Output complete working code — not snippets
9. Web: declare all :root variables at stylesheet top
10. Mobile: always render full device shell — status bar + dynamic island + content area + home indicator
