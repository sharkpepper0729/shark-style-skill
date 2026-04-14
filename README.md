# ui-spec — Shark-Style Web Admin Design System for Claude Code

A [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills) that injects a complete Shark Design Language-based design system into every UI code generation session.

Type `/ui-spec` and Claude instantly knows every color token, type scale, spacing rule, component spec, and animation timing — and applies them to whatever code it writes.

---

## Preview

Open [`preview.html`](./preview.html) in a browser to see the full visual specification:

- Color system (system colors, grays, semantic colors)
- Typography scale (11 levels, SF Pro / -apple-system)
- Spacing, border radius, shadow levels
- Components: Buttons, Inputs, Toggle, Checkbox, Segmented Control, Alert, Badge, Card, Modal, List, Navbar, Breadcrumb, Avatar

---

## What's inside

The skill provides exact values for:

| Category | Tokens |
|----------|--------|
| **Colors** | 9 system colors + 6 grays + semantic text/bg/fill/separator |
| **Typography** | 11-level type scale, font stacks, weight rules |
| **Spacing** | 8px-grid scale (4px → 80px) |
| **Border Radius** | 7 levels (4px → full capsule) |
| **Shadows** | 6 elevation levels + frosted glass material |
| **Components** | Button, Input, Toggle, Card, Modal, Alert, Badge, List, Navbar, Segmented Control, Search, Breadcrumb, Avatar |
| **Animation** | 4 duration tokens + 4 easing curves + motion rules |
| **Responsive** | 3 breakpoints (735 / 1068px) |

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
- **ui-spec** (`~/.claude/skills/ui-spec/SKILL.md`) - Shark-Style web admin UI design system. Trigger: `/ui-spec`
When the user types `/ui-spec`, invoke the Skill tool with `skill: "ui-spec"` before doing anything else.
Always apply this design system when writing any UI code for the user's web admin project.
```

### Option B — Manual

1. Copy `SKILL.md` to `~/.claude/skills/ui-spec/SKILL.md`
2. Add the block above to your `~/.claude/CLAUDE.md`

---

## Usage

```
/ui-spec build a user management table with search and filters
```

```
/ui-spec create a stats dashboard with 4 metric cards
```

```
/ui-spec write a login modal with email + password fields
```

Claude will output complete, working code (HTML/CSS, React, Vue — whatever you're using) that precisely follows the design system, including all interactive states and responsive behavior.

---

## Design principles

Shark-Style is a distilled design language for web admin products, inspired by the clarity and precision of modern system UI:

1. **Clarity** — Legible text (min 4.5:1 contrast), purposeful icons, UI serves content
2. **Deference** — Interface steps back; frosted glass lets content lead
3. **Depth** — Spring motion, layered materials, shadows communicate hierarchy

Key decisions:
- Primary action color: `#0071E3` (web-optimized blue)
- Primary text: `#1D1D1F` (not pure `#000000`)
- No dark mode (web admin context)

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
- Additional component specs (data table, pagination, date picker, tooltip, dropdown)
- Dark mode variant
- Tailwind config export
- Framework-specific starter templates

---

## License

MIT — use freely in personal and commercial projects.
