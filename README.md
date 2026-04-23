# ui-spec — Shark-Style Unified Design System for Claude Code

A [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills) that injects a complete Shark Design Language into every UI code generation session — covering both **Web Admin** (desktop) and **Mobile C-End** (iOS-style phone preview).

Type `/ui-spec` for web admin dashboards, or `/mobile-spec` for mobile app screens. Claude instantly knows every color token, type scale, spacing rule, component spec, and animation timing — and applies them precisely to whatever code it writes.

---

## Preview

[![Live Preview](https://img.shields.io/badge/Live%20Preview-Open-0071E3?style=flat-square&logo=github)](https://sharkpepper0729.github.io/shark-style-skill/preview.html)

> 直接在浏览器中查看完整视觉规范：**https://sharkpepper0729.github.io/shark-style-skill/preview.html**

Open [`preview.html`](./preview.html) locally, or visit the live link above to see the full visual specification:

- Color system (system colors, grays, semantic colors)
- Typography scale (11 levels, SF Pro / -apple-system)
- Spacing, border radius, shadow levels
- Web components: Buttons, Inputs, Toggle, Segmented Control, Alert, Badge, Card, Modal, List, Navbar, Breadcrumb, Search
- Mobile components: Device shell, Status bar, Dynamic Island, Tab Bar, Product Card, Carousel, FAB

---

## What's inside

### Shared Design Tokens (Web & Mobile)

| Category | Tokens |
|----------|--------|
| **Colors** | 9 system colors + 6 grays + semantic text / bg / fill / separator |
| **Typography** | 11-level type scale, SF Pro font stack, weight rules |
| **Spacing** | 8px-grid scale (4px → 80px) |
| **Border Radius** | 7 levels (4px → full capsule) |
| **Shadows** | 5 elevation levels + frosted glass material |
| **Animation** | 4 duration tokens + 4 easing curves + motion rules |

### Web Admin (`/ui-spec`)

| Category | Details |
|----------|---------|
| **Layout** | 3 breakpoints (735 / 1068px), sidebar, navbar |
| **Components** | Button, Input, Toggle, Card, Modal, Alert, Badge, List, Navbar, Segmented Control, Search, Breadcrumb |

### Mobile C-End (`/mobile-spec`)

| Category | Details |
|----------|---------|
| **Device Shell** | 430×932px, border-radius 55px, overflow hidden |
| **System UI** | Status bar (54px), Dynamic Island, Home Indicator |
| **Safe Zones** | padding-top: 54px / padding-bottom: 34px |
| **Components** | Tab Bar, Product Card, Carousel, FAB, Full-width Button, Section Header |

---

## Platform boundary

| Dimension | Web Admin `/ui-spec` | Mobile C-End `/mobile-spec` |
|-----------|---------------------|----------------------------|
| Container | Responsive, ≥ 1068px full layout | Fixed 430×932px device shell |
| System UI | None | Status bar + Dynamic Island + Home Bar |
| Safe area | Not required | padding-top: 54px / bottom: 34px |
| Scroll | Page-level | Content area, hidden scrollbar |
| Extra components | Sidebar, Breadcrumb, Data table | Tab Bar, Carousel, FAB, Product card |

**Never mix web layout rules into the mobile container, or mobile safe-area rules into web layout.**

---

## Installation

### Option A — One command

```bash
mkdir -p ~/.claude/skills/ui-spec && \
curl -fsSL https://raw.githubusercontent.com/sharkpepper0729/shark-style-skill/main/SKILL.md \
  -o ~/.claude/skills/ui-spec/SKILL.md
```

Then add the trigger to your `~/.claude/CLAUDE.md`:

```markdown
# ui-spec
- **ui-spec** (`~/.claude/skills/ui-spec/SKILL.md`) - Shark-Style unified design system (Web Admin + Mobile C-End). Trigger: `/ui-spec`, `/mobile-spec`
When the user types `/ui-spec` or `/mobile-spec`, invoke the Skill tool with `skill: "ui-spec"` before doing anything else.
Always apply this design system when writing any UI code for the user's web admin or mobile project.
```

### Option B — Manual

1. Copy `SKILL.md` to `~/.claude/skills/ui-spec/SKILL.md`
2. Add the block above to your `~/.claude/CLAUDE.md`

---

## Usage

**Web Admin:**
```
/ui-spec build a user management table with search and filters
/ui-spec create a stats dashboard with 4 metric cards
/ui-spec write a login modal with email + password fields
```

**Mobile C-End:**
```
/mobile-spec design a product listing page with carousel and cards
/mobile-spec create a checkout flow screen with bottom CTA
/mobile-spec build an app home screen with tab bar navigation
```

Claude will output complete, working code (HTML/CSS, React, Vue — whatever you're using) that precisely follows the design system, including all interactive states, responsive behavior, and — for mobile — the full device shell with status bar, Dynamic Island, and home indicator.

---

## Design principles

Shark-Style is a unified design language for both web admin products and mobile C-end apps, inspired by the clarity and precision of modern system UI:

1. **Clarity** — Legible text (min 4.5:1 contrast), purposeful icons, UI serves content
2. **Deference** — Interface steps back; frosted glass lets content lead
3. **Depth** — Spring motion, layered materials, shadows communicate hierarchy

Key decisions:
- Primary action color: `#0071E3` (web-optimized blue)
- Primary text: `#1D1D1F` (not pure `#000000`)
- Mobile device shell: 430×932px iPhone Pro Max proportions
- No dark mode (admin and C-end context)

---

## Customizing

Fork this repo and edit `SKILL.md` to override any token. Common customizations:

```css
/* Change primary action color to your brand */
--color-action: #your-brand-color;

/* Adjust card radius for a sharper look */
--radius-lg: 8px;   /* was 12px */
```

---

## Contributing

PRs welcome for:
- Additional web components (data table, pagination, date picker, tooltip, dropdown)
- Additional mobile patterns (onboarding, empty state, loading skeleton)
- Dark mode variant
- Tailwind config export
- Framework-specific starter templates (React, Vue, Next.js)

---

## License

MIT — use freely in personal and commercial projects.
