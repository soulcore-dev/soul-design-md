# Design System: Notion (notion.so)

## 1. Visual Theme & Atmosphere

Notion's interface is the digital equivalent of a beautifully made paper notebook — warm, tactile, and focused on the act of writing. The canvas is not pure white but a soft off-white (`#f7f6f3`) that carries the warmth of aged paper, and the primary text is not pure black but a deep warm near-black (`#37352f`) that feels calligraphic rather than mechanical. Together, these two decisions — off-white surface, near-black ink — form the visual philosophy of the entire product: everything is slightly warm, slightly human, never cold or clinical.

Typography is where Notion makes its most distinctive statement. While every other productivity tool defaults to sans-serif, Notion chose serif as its display font. Charter, Sitka Text, and the `ui-serif` system stack appear at display and marketing sizes, lending a literary gravity to headlines that no amount of bold Inter can replicate. The serif choice communicates that this is a tool for thinkers, writers, and people who care about the texture of ideas. The application UI switches to system sans-serif for readability, but the moment a heading needs weight, the serif voice returns — consistent, unhurried, authoritative.

Color is used sparingly and with remarkable restraint. The accent blue (`#2383e2`) appears only where action is required: buttons, links, focus states, and interactive selection. There are no gradients in the UI, no glows, no ambient color washes. Instead, Notion offers a nine-color tagging palette — all soft, warm, muted tones — that functions as a labeling and categorization language. These nine colors (Gray, Brown, Orange, Yellow, Green, Blue, Purple, Pink, Red) all live in the same tonal register: light, warm, slightly de-saturated. They coexist without competing, like highlighter markers in a journal. The design is minimalism with warmth, restraint with personality.

**Key Characteristics:**
- Warm near-black text `#37352f` (NOT pure black) — ink on paper, not LCD pixels on glass
- Off-white canvas `#f7f6f3` — the SIGNATURE cream surface, paper metaphor throughout
- Serif headlines (Charter / Sitka Text / `ui-serif`) — literary authority, distinctive vs. all tech-sans competitors
- System sans-serif for UI text — readable, neutral, deferential to content
- Single interactive accent: blue `#2383e2` — appears only where action is needed, zero decoration
- Nine-color warm tagging palette — all soft muted tones, shared tonal register
- 708px page content width — Notion's famous reading-comfortable line length
- Small border-radius: 4px is the workhorse — conservative, document-like, not bubbly
- Borders at 16% opacity — almost invisible, structural but never dominant
- Motion is gentle and brief — 100-200ms ease-in-out, no aggressive animations

---

## 2. Color System & Tokens

### Light Theme

| Token | Name | Hex | Role | CSS Variable |
|-------|------|-----|------|-------------|
| `bg-primary` | Pure White | `#ffffff` | Page canvas, modal backgrounds | `--color-bg-primary` |
| `bg-secondary` | Cream Canvas | `#f7f6f3` | SIGNATURE warm off-white — sidebar, alternating sections, paper metaphor | `--color-bg-secondary` |
| `bg-tertiary` | Subtle Gray | `#ebeae8` | Hover surfaces, dividers, input backgrounds in dense views | `--color-bg-tertiary` |
| `text-primary` | Warm Near-Black | `#37352f` | All primary text — SIGNATURE warm tone, never pure black | `--color-text-primary` |
| `text-secondary` | Warm Gray 65% | `rgba(55,53,47,0.65)` | Secondary labels, metadata, captions | `--color-text-secondary` |
| `text-tertiary` | Warm Gray 50% | `rgba(55,53,47,0.5)` | Placeholder text, hints, deemphasized | `--color-text-tertiary` |
| `text-disabled` | Warm Gray 40% | `rgba(55,53,47,0.4)` | Disabled state text | `--color-text-disabled` |
| `accent-primary` | Notion Blue | `#2383e2` | Primary interactive — buttons, links, focus, selection highlight | `--color-accent-primary` |
| `accent-hover` | Blue Dark | `#0b6bcb` | Hover on accent elements | `--color-accent-hover` |
| `accent-active` | Blue Darker | `#0a5eaf` | Active/pressed accent | `--color-accent-active` |
| `border-default` | Warm Border | `rgba(55,53,47,0.16)` | Default borders — thin, almost invisible | `--color-border-default` |
| `border-subtle` | Subtle Border | `rgba(55,53,47,0.09)` | Hairline separators, row dividers in documents | `--color-border-subtle` |
| `border-focus` | Blue | `#2383e2` | Focus ring color | `--color-border-focus` |
| `status-success` | Green Text | `#0f7b6c` | Success states, confirmation | `--color-status-success` |
| `status-warning` | Orange Text | `#d9730d` | Warning states | `--color-status-warning` |
| `status-error` | Red Text | `#e03e3e` | Error states, destructive actions | `--color-status-error` |
| `status-info` | Blue Text | `#0b6e99` | Informational states | `--color-status-info` |
| `overlay` | Dark Backdrop | `rgba(15,15,15,0.4)` | Modal backdrop — softer than pure black | `--color-overlay` |

### Dark Theme

| Token | Hex (Dark) | Maps to Light | CSS Variable |
|-------|-----------|---------------|-------------|
| `bg-primary` | `#191919` | `#ffffff` | `--color-bg-primary` |
| `bg-secondary` | `#202020` | `#f7f6f3` | `--color-bg-secondary` |
| `bg-tertiary` | `#2a2a2a` | `#ebeae8` | `--color-bg-tertiary` |
| `text-primary` | `#ffffff` | `#37352f` | `--color-text-primary` |
| `text-secondary` | `rgba(255,255,255,0.81)` | `rgba(55,53,47,0.65)` | `--color-text-secondary` |
| `text-tertiary` | `rgba(255,255,255,0.6)` | `rgba(55,53,47,0.5)` | `--color-text-tertiary` |
| `text-disabled` | `rgba(255,255,255,0.4)` | `rgba(55,53,47,0.4)` | `--color-text-disabled` |
| `accent-primary` | `#2383e2` | `#2383e2` | `--color-accent-primary` |
| `accent-hover` | `#0b6bcb` | `#0b6bcb` | `--color-accent-hover` |
| `border-default` | `rgba(255,255,255,0.13)` | `rgba(55,53,47,0.16)` | `--color-border-default` |
| `border-subtle` | `rgba(255,255,255,0.07)` | `rgba(55,53,47,0.09)` | `--color-border-subtle` |
| `overlay` | `rgba(15,15,15,0.6)` | `rgba(15,15,15,0.4)` | `--color-overlay` |

### Notion Brand Color Palette (9-Color Tagging System)

All nine colors exist as background + text pairs. Backgrounds are soft warm fills; text variants are stronger saturations for readable labels.

| Color Name | Background | Text | CSS Variables |
|-----------|-----------|------|--------------|
| Gray | `#e3e2e0` | `#9b9a97` | `--notion-gray-bg` / `--notion-gray-text` |
| Brown | `#eee0da` | `#64473a` | `--notion-brown-bg` / `--notion-brown-text` |
| Orange | `#faebdd` | `#d9730d` | `--notion-orange-bg` / `--notion-orange-text` |
| Yellow | `#fbf3db` | `#dfab01` | `--notion-yellow-bg` / `--notion-yellow-text` |
| Green | `#ddedea` | `#0f7b6c` | `--notion-green-bg` / `--notion-green-text` |
| Blue | `#ddebf1` | `#0b6e99` | `--notion-blue-bg` / `--notion-blue-text` |
| Purple | `#eae4f2` | `#6940a5` | `--notion-purple-bg` / `--notion-purple-text` |
| Pink | `#f4dfeb` | `#ad1a72` | `--notion-pink-bg` / `--notion-pink-text` |
| Red | `#fbe4e4` | `#e03e3e` | `--notion-red-bg` / `--notion-red-text` |

> **Usage rule:** Brand palette colors are ONLY for tagging, categorization, and inline content highlights — never for UI chrome. The nine-color system coexists within the same warm tonal register; none dominates.

### Contrast Ratios (WCAG AA)

| Pair | Foreground | Background | Ratio | Pass AA | Pass AAA |
|------|-----------|-----------|-------|---------|----------|
| Primary text on white | `#37352f` | `#ffffff` | 12.4:1 | Yes | Yes |
| Primary text on cream | `#37352f` | `#f7f6f3` | 11.9:1 | Yes | Yes |
| Secondary text on white | `rgba(55,53,47,0.65)` ≈ `#8a8984` | `#ffffff` | 6.3:1 | Yes | Yes |
| Tertiary text on white | `rgba(55,53,47,0.5)` ≈ `#9b9a97` | `#ffffff` | 4.0:1 | **FAIL** (3.95:1) | No |
| Accent blue on white | `#2383e2` | `#ffffff` | 4.6:1 | Yes (large text) | No |
| White on accent blue | `#ffffff` | `#2383e2` | 4.6:1 | Yes (large text) | No |
| Disabled text on white | `rgba(55,53,47,0.4)` ≈ `#b3b2b0` | `#ffffff` | 2.3:1 | No (by design) | No |

> **Known issues:** Tertiary text (`rgba(55,53,47,0.5)`) on white fails WCAG AA at 4.0:1. Use only for non-critical decorative labels or ensure font size ≥18px. Accent blue at 4.6:1 passes for large text (≥18px regular / ≥14px bold) but not small text — keep button text at 14px/500 or larger. Disabled text intentionally fails — exempt per WCAG 1.4.3 (disabled controls).

### Gradients

Notion uses no decorative gradients in the application UI. Marketing site uses minimal hover effects only.

| Name | Value | Use |
|------|-------|-----|
| `sidebar-fade-bottom` | `linear-gradient(180deg, transparent 0%, var(--color-bg-secondary) 100%)` | Sidebar scroll fade at bottom |
| `page-edge-fade` | `linear-gradient(90deg, rgba(247,246,243,0.8) 0%, transparent 20%, transparent 80%, rgba(247,246,243,0.8) 100%)` | Horizontal scroll hint on tables |

---

## 3. Typography System

### Font Stack

| Role | Family | Fallbacks | CSS Variable |
|------|--------|-----------|-------------|
| Display / Serif | `ui-serif` | `"Charter", "Bitstream Charter", "Sitka Text", Cambria, Georgia, serif` | `--font-display` |
| Body / Sans | `system-ui` | `-apple-system, "Segoe UI", "Helvetica Neue", Helvetica, Arial, sans-serif` | `--font-body` |
| Mono | `Menlo` | `Courier, "Courier New", monospace` | `--font-mono` |

**OpenType Features:** None required beyond browser defaults. Use `font-variant-numeric: tabular-nums` for database number fields and pricing. Notion does not apply custom OpenType features.

### Type Scale

| Token | Size | Weight | Line Height | Letter Spacing | Font Role | CSS Variable |
|-------|------|--------|-------------|----------------|-----------|-------------|
| `display-hero` | 72px | 600 | 1.1 | -1.8px | Serif (display) | `--text-display-hero` |
| `display-lg` | 56px | 600 | 1.15 | -1.4px | Serif (display) | `--text-display-lg` |
| `display-md` | 48px | 600 | 1.2 | -1.2px | Serif (display) | `--text-display-md` |
| `heading-lg` | 36px | 600 | 1.3 | -0.72px | Sans (app UI) or Serif (marketing) | `--text-heading-lg` |
| `heading-md` | 30px | 600 | 1.3 | -0.45px | Sans | `--text-heading-md` |
| `heading-sm` | 24px | 600 | 1.35 | -0.24px | Sans | `--text-heading-sm` |
| `body-lg` | 18px | 400 | 1.6 | normal | Sans | `--text-body-lg` |
| `body-md` | 16px | 400 | 1.55 | normal | Sans | `--text-body-md` |
| `body-sm` | 14px | 400 | 1.5 | normal | Sans | `--text-body-sm` |
| `label-lg` | 16px | 500 | 1.5 | normal | Sans | `--text-label-lg` |
| `label-md` | 14px | 500 | 1.4 | normal | Sans | `--text-label-md` |
| `label-sm` | 13px | 500 | 1.4 | normal | Sans | `--text-label-sm` |
| `caption` | 12px | 400 | 1.4 | normal | Sans | `--text-caption` |
| `micro` | 11px | 500 | 1.3 | 0.2px | Sans | `--text-micro` |
| `code-md` | 14px | 400 | 1.6 | normal | Mono | `--text-code-md` |
| `code-sm` | 12px | 400 | 1.5 | normal | Mono | `--text-code-sm` |

### Typography Principles
- **Serif for display, sans for UI:** Charter/`ui-serif` appears at display sizes (48px+) in marketing and as the in-app "Serif" page font option. Sans handles all interactive UI elements. This dual-font rhythm is Notion's identity.
- **Warm near-black only, never pure black:** `#37352f` is the warmth philosophy in action. Mixing RGB channels creates a brownish undertone that reads as "ink" rather than "screen." Pure `#000000` would break the paper metaphor.
- **Tracking tightens with size:** -1.8px at 72px, -0.72px at 36px, normal at 16px and below. Notion does not use aggressive tracking at body sizes — readability first.
- **Weight 600 for headings, 400 for body, 500 for labels:** The weight ladder is restrained. Weight 700+ is never used in the application chrome — it would overpower the content.
- **Line height opens at body:** 1.55-1.6 for body text creates comfortable reading in the 708px column width. Display sizes compress to 1.1 for impact without excess vertical spacing.

---

## 4. Component Catalog

### 4.1 Buttons

**Primary Blue**
- Background: `#2383e2` → `var(--color-accent-primary)`
- Text: `#ffffff`
- Padding: `6px 12px`
- Border Radius: `4px` → `var(--radius-md)`
- Font: 14px / 500 / sans
- Border: none
- Shadow: none
- Hover: bg `#0b6bcb`
- Transition: `background-color 150ms cubic-bezier(0.4,0,0.2,1)`

**Black Button (Signup / Primary CTA)**
- Background: `#37352f` → `var(--color-text-primary)`
- Text: `#ffffff`
- Padding: `6px 12px`
- Border Radius: `4px`
- Font: 14px / 500 / sans
- Border: none
- Hover: bg `#2f2d28`
- Note: The CTA uses warm near-black, NOT pure black — brand consistency

**Ghost / Outline**
- Background: transparent
- Text: `#37352f` → `var(--color-text-primary)`
- Padding: `6px 12px`
- Border Radius: `4px`
- Border: `1px solid rgba(55,53,47,0.16)` → `var(--color-border-default)`
- Font: 14px / 500 / sans
- Hover: bg `rgba(55,53,47,0.06)`
- Transition: `background-color 100ms cubic-bezier(0.4,0,0.2,1)`

**Text Button / Link Button**
- Background: transparent
- Text: `#2383e2` → `var(--color-accent-primary)`
- Padding: `4px 8px`
- Border Radius: `4px`
- Border: none
- Font: 14px / 400 / sans
- Hover: bg `rgba(35,131,226,0.07)`

**Danger**
- Background: `#e03e3e`
- Text: `#ffffff`
- Padding: `6px 12px`
- Border Radius: `4px`
- Font: 14px / 500 / sans
- Hover: bg `#c73737`

**Icon Button**
- Background: transparent
- Padding: `6px`
- Border Radius: `4px`
- Color: `var(--color-text-secondary)`
- Hover: bg `rgba(55,53,47,0.06)`
- Size: 28px minimum touch area

### 4.2 Inputs

**Text Input**
- Background: `#ffffff` (light) / `#202020` (dark)
- Border: `1px solid rgba(55,53,47,0.16)`
- Border Radius: `4px`
- Padding: `6px 12px`
- Font: 14px / 400 / sans
- Placeholder: `var(--color-text-tertiary)`
- Label: 14px / 500 / `var(--color-text-secondary)` — positioned above, `margin-bottom: 4px`
- Helper text: 12px / 400 / `var(--color-text-secondary)` — below input, `margin-top: 4px`
- Focus: border `#2383e2` + ring `0 0 0 2px rgba(35,131,226,0.28)`

**Select** — same as Text Input; chevron 14px icon right-aligned in `var(--color-text-tertiary)`

**Textarea** — same as Text Input; `min-height: 80px`, `resize: vertical`

**Checkbox**
- Size: 14x14px
- Border Radius: 3px
- Unchecked: `1px solid rgba(55,53,47,0.3)`, bg `transparent`
- Checked: bg `#2383e2`, checkmark `#ffffff`
- Hover: border `#2383e2`

**Radio**
- Size: 14x14px
- Border Radius: 50%
- Selected dot: 6px, `#2383e2`
- Border: `1px solid rgba(55,53,47,0.3)`

**Toggle / Switch**
- Track: 40x22px, radius `9999px`
- Thumb: 18px circle, `#ffffff`
- Off: track `rgba(55,53,47,0.16)`
- On: track `#2383e2`
- Transition: `background-color 150ms`, `transform 150ms`

### 4.3 Cards

**Page Block Card (Default)**
- Background: `#ffffff`
- Border: none (Notion's signature — blocks have NO visible border by default)
- Border Radius: `8px`
- Padding: `20px`
- Shadow: none
- Hover: bg `rgba(55,53,47,0.03)` — extremely subtle, "blocks appear on hover" philosophy

**Featured Card / Callout Block**
- Background: `#f7f6f3` → `var(--color-bg-secondary)`
- Border Radius: `12px`
- Padding: `32px`
- Border: none
- Shadow: `rgba(15,15,15,0.05) 0 1px 2px`
- Use: Marketing feature highlights, in-app callout blocks

**Database Card View**
- Background: `#ffffff`
- Border: `1px solid rgba(55,53,47,0.09)` → `var(--color-border-subtle)`
- Border Radius: `6px`
- Padding: `12px`
- Shadow: `rgba(15,15,15,0.05) 0 1px 2px`
- Hover: shadow `rgba(15,15,15,0.07) 0 4px 12px`, subtle lift

### 4.4 Navigation

**Marketing Top Nav**
- Background: `rgba(255,255,255,0.8)` with `backdrop-filter: blur(8px)`
- Height: `56px`
- Position: sticky, `top: 0`, `z-index: 50`
- Border-bottom: `1px solid rgba(55,53,47,0.09)` → `var(--color-border-subtle)`
- Logo: Notion wordmark, left-aligned
- Links: 14px / 400 / `var(--color-text-secondary)`, hover `var(--color-text-primary)`
- CTA: Black button ("Get Notion free"), right-aligned
- Mobile: hamburger → overlay drawer

**App Sidebar**
- Background: `#f7f6f3` → `var(--color-bg-secondary)`
- Width: 240px (fixed)
- Font: 14px / 500 / sans
- Item padding: `4px 8px`
- Item color: `var(--color-text-secondary)`
- Item hover: bg `rgba(55,53,47,0.06)`, color `var(--color-text-primary)`
- Item active: bg `rgba(55,53,47,0.08)`, color `var(--color-text-primary)`
- Border-right: none (Notion sidebar has no border — visual separation via bg color)
- Item border radius: `4px`

**Breadcrumbs**
- Font: 14px / 400 / sans
- Color: `var(--color-text-secondary)`
- Separator: `/` or `>` in `var(--color-text-tertiary)`
- Hover item: color `var(--color-text-primary)`

### 4.5 Modals & Dialogs

- Overlay: `rgba(15,15,15,0.4)` → `var(--color-overlay)`
- Container: bg `#ffffff`, radius `8px`, shadow `rgba(15,15,15,0.13) 0 12px 32px, rgba(15,15,15,0.05) 0 4px 12px`, max-width `560px`
- Header: 18px / 600 / sans, close button (icon button) top-right
- Body: padding `24px`, overflow-y `auto`
- Footer: padding `16px 24px`, buttons right-aligned, `gap: 8px`
- Animation: fade in (opacity 0→1) + scale (0.98→1.0), 200ms ease-out

### 4.6 Dropdowns & Menus

- Container: bg `#ffffff` (light) / `#2a2a2a` (dark), border `1px solid rgba(55,53,47,0.09)`, radius `6px`, shadow `rgba(15,15,15,0.13) 0 12px 32px, rgba(15,15,15,0.05) 0 4px 12px`
- Item: padding `6px 12px`, font 14px / 400, hover bg `rgba(55,53,47,0.06)`
- Active item: bg `rgba(55,53,47,0.08)`, text `var(--color-text-primary)`
- Divider: `1px solid rgba(55,53,47,0.09)`
- Group label: 11px / 500 / uppercase / `var(--color-text-tertiary)`, padding `8px 12px 4px`
- Min width: `160px`, max width: `320px`
- Animation: opacity 0→1 + translateY(-4px → 0), 150ms ease-out

### 4.7 Badges & Tags

All Notion tags use the 9-color brand palette. No status-color badges (no green/red/amber) in the traditional sense — the brand palette handles all categorization.

| Variant | Background | Text | Border | Radius | Padding | Font |
|---------|-----------|------|--------|--------|---------|------|
| Gray | `#e3e2e0` | `#9b9a97` | none | `3px` | `2px 6px` | 12px/400 |
| Brown | `#eee0da` | `#64473a` | none | `3px` | `2px 6px` | 12px/400 |
| Orange | `#faebdd` | `#d9730d` | none | `3px` | `2px 6px` | 12px/400 |
| Yellow | `#fbf3db` | `#dfab01` | none | `3px` | `2px 6px` | 12px/400 |
| Green | `#ddedea` | `#0f7b6c` | none | `3px` | `2px 6px` | 12px/400 |
| Blue | `#ddebf1` | `#0b6e99` | none | `3px` | `2px 6px` | 12px/400 |
| Purple | `#eae4f2` | `#6940a5` | none | `3px` | `2px 6px` | 12px/400 |
| Pink | `#f4dfeb` | `#ad1a72` | none | `3px` | `2px 6px` | 12px/400 |
| Red | `#fbe4e4` | `#e03e3e` | none | `3px` | `2px 6px` | 12px/400 |

### 4.8 Tooltips

- Background: `#37352f` (always dark warm near-black, regardless of theme)
- Text: `#ffffff`, 12px / 400 / sans
- Radius: `4px`
- Padding: `6px 10px`
- Arrow: 5px, same bg
- Max width: `240px`
- Shadow: `rgba(15,15,15,0.1) 0 4px 12px`
- Animation: opacity 0→1, 100ms ease-out, delay 500ms

### 4.9 Toasts & Notifications

- Container: bg `#37352f`, radius `6px`, shadow `rgba(15,15,15,0.1) 0 8px 24px, rgba(15,15,15,0.04) 0 2px 8px`, padding `12px 16px`
- Text: `#ffffff`, 14px / 400 / sans
- Icon: 16px, `#ffffff` (monochrome — Notion toasts are minimal)
- Close: 14px icon, `rgba(255,255,255,0.6)`, hover `#ffffff`
- Max width: `320px`
- Position: bottom-center, `24px` from bottom edge
- Stack: `gap: 8px`, max 3 visible, oldest fades first
- Animation: translateY(8px → 0) + opacity 0→1, 200ms ease-out

### 4.10 Tables

- Header: bg `transparent`, text 12px / 600 / uppercase / `var(--color-text-secondary)`, border-bottom `1px solid rgba(55,53,47,0.16)`
- Row: bg transparent, hover bg `rgba(55,53,47,0.03)`, border-bottom `1px solid rgba(55,53,47,0.09)`
- Cell: padding `8px 12px`, text 14px / 400 / `var(--color-text-primary)`
- Striped: alternate bg `rgba(55,53,47,0.02)` — barely visible, subtle rhythm

### 4.11 Tabs

- Container: border-bottom `1px solid rgba(55,53,47,0.16)`
- Tab: padding `8px 16px`, font 14px / 500, color `var(--color-text-secondary)` (inactive)
- Active: color `var(--color-text-primary)`, indicator `2px solid #37352f` bottom border
- Hover: color `var(--color-text-primary)`
- Gap between tabs: `0` (borderless, continuous strip)

### 4.12 Avatars

| Size | Dimensions | Font Size | Radius |
|------|-----------|-----------|--------|
| xs | 20px | 9px | 50% |
| sm | 28px | 12px | 50% |
| md | 36px | 14px | 50% |
| lg | 48px | 18px | 50% |
| xl | 72px | 28px | 50% |

### 4.13 Pagination

- Button: 28x28px, radius `4px`, font 13px / 400
- Default: bg transparent, text `var(--color-text-secondary)`
- Active: bg `rgba(55,53,47,0.08)`, text `var(--color-text-primary)`
- Hover: bg `rgba(55,53,47,0.06)`
- Disabled: opacity 0.4, cursor `not-allowed`
- Gap: `2px`
- Ellipsis: `•••` in `var(--color-text-tertiary)`

### 4.14 Progress & Loading

- Progress bar: height `3px`, track `rgba(55,53,47,0.09)`, fill `#2383e2`, radius `9999px`
- Spinner: 16px, `rgba(55,53,47,0.4)`, stroke 2px, animation `spin 0.8s linear infinite`
- Skeleton: bg `rgba(55,53,47,0.06)`, shimmer `linear-gradient(90deg, transparent, rgba(55,53,47,0.04), transparent)`, radius matching component, animation `shimmer 1.5s infinite`

### 4.15 Document Page Container (SIGNATURE)

- Background: `#ffffff`
- Max-width: `708px` — Notion's famous content width. This number is deliberate: at 16px body with 1.55 line-height, 708px produces ~70-75 characters per line, the typography research optimum for sustained reading. It also creates equal breathing room on a 1280px screen: (1280-708)/2 = 286px per side.
- Padding: `96px 96px 48px` (top / horizontal / bottom) on desktop; `24px` horizontal on mobile
- The page width is not a grid choice — it is a reading choice.

---

## 5. Component State Matrix

| Component | Default | Hover | Active/Pressed | Focus | Disabled | Loading | Error |
|-----------|---------|-------|---------------|-------|----------|---------|-------|
| **Button Primary (Blue)** | bg `#2383e2` | bg `#0b6bcb` | bg `#0a5eaf`, scale `0.99` | ring `0 0 0 2px rgba(35,131,226,0.28)` | bg `#2383e2`, opacity 0.4, `not-allowed` | spinner white + opacity 0.7 | — |
| **Button Black (CTA)** | bg `#37352f` | bg `#2f2d28` | bg `#28261f`, scale `0.99` | ring `0 0 0 2px rgba(55,53,47,0.28)` | opacity 0.4, `not-allowed` | spinner white | — |
| **Button Ghost** | border `rgba(55,53,47,0.16)` | bg `rgba(55,53,47,0.06)` | bg `rgba(55,53,47,0.1)` | ring `0 0 0 2px rgba(35,131,226,0.28)` | opacity 0.4, `not-allowed` | — | — |
| **Input Text** | border `rgba(55,53,47,0.16)` | border `rgba(55,53,47,0.3)` | — | border `#2383e2`, ring `0 0 0 2px rgba(35,131,226,0.28)` | bg `rgba(55,53,47,0.04)`, `not-allowed` | — | border `#e03e3e`, ring `0 0 0 2px rgba(224,62,62,0.2)` |
| **Checkbox** | border `rgba(55,53,47,0.3)` | border `#2383e2` | — | ring `0 0 0 2px rgba(35,131,226,0.28)` | opacity 0.4 | — | border `#e03e3e` |
| **Card (Page Block)** | bg `#ffffff`, no shadow | bg `rgba(55,53,47,0.03)` | bg `rgba(55,53,47,0.05)` | ring `0 0 0 2px rgba(35,131,226,0.28)` | opacity 0.5 | skeleton shimmer | — |
| **Link** | color `#2383e2`, no underline | color `#0b6bcb`, underline | color `#0a5eaf` | ring `0 0 0 2px rgba(35,131,226,0.28)` | color `var(--color-text-disabled)`, no pointer | — | — |
| **Tab** | color `var(--text-secondary)` | color `var(--text-primary)` | color `var(--text-primary)`, indicator | ring `0 0 0 2px rgba(35,131,226,0.28)` | opacity 0.4 | — | — |
| **Select** | border `rgba(55,53,47,0.16)` | border `rgba(55,53,47,0.3)` | — | border `#2383e2`, ring `0 0 0 2px rgba(35,131,226,0.28)` | opacity 0.4 | spinner | border `#e03e3e` |
| **Toggle** | track `rgba(55,53,47,0.16)` | track `rgba(55,53,47,0.25)` | — | ring `0 0 0 2px rgba(35,131,226,0.28)` | opacity 0.4 | — | — |
| **Sidebar Item** | transparent | bg `rgba(55,53,47,0.06)` | bg `rgba(55,53,47,0.08)` | ring inset `0 0 0 2px rgba(35,131,226,0.28)` | opacity 0.4 | — | — |

### Focus Ring Standard
```css
box-shadow: 0 0 0 2px rgba(35, 131, 226, 0.28);
/* Subtle blue halo — soft, not hard outline */
outline: none; /* remove default, use box-shadow ring */
```

### Disabled Pattern
```css
opacity: 0.4;
cursor: not-allowed;
pointer-events: none;
```

### Error Input Pattern
```css
border-color: #e03e3e;
box-shadow: 0 0 0 2px rgba(224, 62, 62, 0.2);
```

---

## 6. Layout & Spacing System

### Spacing Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `space-0` | 0px | `p-0` | `--space-0` | Reset |
| `space-1` | 4px | `p-1` | `--space-1` | Icon gaps, tight inline padding |
| `space-2` | 8px | `p-2` | `--space-2` | Badge padding, button icon gap |
| `space-3` | 12px | `p-3` | `--space-3` | Button padding, dropdown item padding |
| `space-4` | 16px | `p-4` | `--space-4` | Card internal gap, toast padding |
| `space-5` | 20px | `p-5` | `--space-5` | Card padding (blocks) |
| `space-6` | 24px | `p-6` | `--space-6` | Section sub-gap, modal footer |
| `space-8` | 32px | `p-8` | `--space-8` | Featured card padding, section gap (mobile) |
| `space-10` | 40px | `p-10` | `--space-10` | Section gap (tablet) |
| `space-12` | 48px | `p-12` | `--space-12` | Page bottom padding, section gap (desktop) |
| `space-16` | 64px | `p-16` | `--space-16` | Large section separation |
| `space-20` | 80px | `p-20` | `--space-20` | Hero vertical padding |
| `space-24` | 96px | `p-24` | `--space-24` | Page horizontal padding desktop, top padding |

### Grid

| Property | Value | CSS Variable |
|----------|-------|-------------|
| Page content width | `708px` | `--grid-page-width` |
| App sidebar width | `240px` | `--grid-sidebar-width` |
| Max marketing width | `1200px` | `--grid-max-width` |
| Column count | 12 | `--grid-columns` |
| Gutter | `24px` | `--grid-gutter` |
| Margin (mobile) | `16px` | `--grid-margin-sm` |
| Margin (desktop) | `auto` (centered) | `--grid-margin-lg` |

> **708px: the reading width philosophy.** Notion's page content is constrained to 708px not by grid constraints but by typography research. At 16px/1.55 line height, this width yields ~70-75 characters per line — the optimal range for sustained focus reading. Users feel comfortable, not cramped or sprawling. The width is famous because it is correct.

### Border Radius Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `radius-none` | 0px | `rounded-none` | `--radius-none` | Table cells, flat list items |
| `radius-xs` | 3px | `rounded-sm` | `--radius-xs` | Tags, badges — document-like |
| `radius-sm` | 4px | `rounded` | `--radius-sm` | Buttons, inputs — WORKHORSE radius |
| `radius-md` | 6px | `rounded-md` | `--radius-md` | Dropdowns, database cards |
| `radius-lg` | 8px | `rounded-lg` | `--radius-lg` | Modals, page block cards |
| `radius-xl` | 12px | `rounded-xl` | `--radius-xl` | Featured cards, callout blocks |
| `radius-full` | 9999px | `rounded-full` | `--radius-full` | Avatars, toggle tracks |

> **Radius philosophy:** 4px is the Notion signature. The UI is conservative — no bubbly 16px+ cards in the application chrome. Small radii communicate "document tool" rather than "consumer app."

---

## 7. Depth & Elevation

### Shadow Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `shadow-xs` | `rgba(15,15,15,0.05) 0 1px 2px` | `shadow-sm` | `--shadow-xs` | Hover lift on minimal cards |
| `shadow-sm` | `rgba(15,15,15,0.07) 0 4px 12px` | `shadow` | `--shadow-sm` | Database cards, hover state |
| `shadow-md` | `rgba(15,15,15,0.1) 0 8px 24px, rgba(15,15,15,0.04) 0 2px 8px` | `shadow-md` | `--shadow-md` | Modals, panels, peek previews |
| `shadow-lg` | `rgba(15,15,15,0.13) 0 12px 32px, rgba(15,15,15,0.05) 0 4px 12px` | `shadow-lg` | `--shadow-lg` | Full modals, dropdowns, context menus |
| `shadow-dark-sm` | `rgba(0,0,0,0.3) 0 4px 12px` | — | `--shadow-dark-sm` | Cards and panels in dark mode |
| `focus-ring` | `0 0 0 2px rgba(35,131,226,0.28)` | — | `--shadow-focus` | All interactive element focus |

> **Shadow warmth:** Notion uses `rgba(15,15,15,...)` — a near-black with slight warmth — rather than pure `rgba(0,0,0,...)`. This keeps shadows from reading as cold or metallic. Even elevation carries the warm philosophy.

### Z-Index Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `z-base` | 0 | `--z-base` | Default page content |
| `z-sticky` | 10 | `--z-sticky` | Sticky table headers, inline toolbars |
| `z-nav` | 50 | `--z-nav` | Top navigation bar, sidebar |
| `z-dropdown` | 100 | `--z-dropdown` | Dropdowns, context menus, pickers |
| `z-overlay` | 200 | `--z-overlay` | Modal backdrop |
| `z-modal` | 300 | `--z-modal` | Modal containers |
| `z-popover` | 400 | `--z-popover` | Tooltips, popovers, hover cards |
| `z-toast` | 500 | `--z-toast` | Toast notifications |

---

## 8. Motion & Animation System

### Duration Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `duration-instant` | 0ms | `--duration-instant` | Immediate state changes |
| `duration-micro` | 100ms | `--duration-micro` | Micro-interactions, icon swaps |
| `duration-fast` | 150ms | `--duration-fast` | Button hover, link color, focus ring |
| `duration-normal` | 200ms | `--duration-normal` | Dropdown open, modal enter, tab switch |
| `duration-moderate` | 300ms | `--duration-moderate` | Sidebar expand/collapse, complex transitions |
| `duration-slow` | 500ms | `--duration-slow` | Page transitions, onboarding animations |

### Easing Functions

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `ease-default` | `cubic-bezier(0.4, 0, 0.2, 1)` | `--ease-default` | General transitions (Material standard — Notion's choice everywhere) |
| `ease-out-quad` | `cubic-bezier(0.25, 0.46, 0.45, 0.94)` | `--ease-out-quad` | Elements entering — feels gentle, warm |
| `ease-in` | `cubic-bezier(0.4, 0, 1, 1)` | `--ease-in` | Elements exiting view |
| `ease-out` | `cubic-bezier(0, 0, 0.2, 1)` | `--ease-out` | Elements entering view |
| `ease-spring-gentle` | `cubic-bezier(0.22, 1, 0.36, 1)` | `--ease-spring-gentle` | Block drag-and-drop (gentle spring, NOT bouncy) |

> **Motion philosophy:** Notion's animations are gentle and brief. No bounce, no elastic overshoot, no dramatic entrances. Everything ease-in-out. The interface defers to the content — motion should be felt as smoothness, not noticed as spectacle. Block drag interactions use a gentle spring (0.22, 1, 0.36, 1) that implies physical weight without cartoonish bounce.

### Common Transitions

| Interaction | Property | Duration | Easing |
|------------|----------|----------|--------|
| Button hover | `background-color` | 150ms | ease-default |
| Link hover | `color` | 100ms | ease-default |
| Card hover | `background-color, box-shadow` | 200ms | ease-default |
| Modal enter | `opacity, transform (scale 0.98→1)` | 200ms | ease-out |
| Modal exit | `opacity, transform` | 150ms | ease-in |
| Dropdown open | `opacity, transform (translateY -4px→0)` | 150ms | ease-out-quad |
| Dropdown close | `opacity` | 100ms | ease-in |
| Sidebar expand | `width, opacity` | 300ms | ease-default |
| Focus ring | `box-shadow` | 150ms | ease-default |
| Toast enter | `transform (translateY 8px→0), opacity` | 200ms | ease-out-quad |
| Toast exit | `opacity, transform` | 150ms | ease-in |
| Block drag | `transform, box-shadow` | continuous | ease-spring-gentle |
| Toggle switch | `background-color, transform` | 150ms | ease-default |

### Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

---

## 9. Icon System

| Property | Value |
|----------|-------|
| Library | Custom SVG + Lucide React (app UI) |
| Default size | 16px (UI chrome), 20px (feature sections) |
| Stroke width | 1.5px |
| Color | `currentColor` (inherits from parent) |
| Style | Outline, not filled — matches Notion's lightweight visual weight |

### Icon Sizes

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `icon-xs` | 12px | `--icon-xs` | Inline text icons, micro controls |
| `icon-sm` | 14px | `--icon-sm` | Badge icons, input prefix icons |
| `icon-md` | 16px | `--icon-md` | Navigation, button icons (default) |
| `icon-lg` | 20px | `--icon-lg` | Sidebar items, card actions |
| `icon-xl` | 24px | `--icon-xl` | Feature sections, empty states |
| `icon-2xl` | 32px | `--icon-2xl` | Page type selectors, onboarding |

### Page Emoji / Cover (Notion-specific)
- Page icon: emoji or custom 32x32px image
- Cover image: full-width, 180px height, `object-fit: cover`
- Emoji picker: 16-column grid, 24px per emoji, hover bg `rgba(55,53,47,0.06)`, radius `4px`

---

## 10. Accessibility Contract

### Targets

| Criterion | Target | Standard |
|-----------|--------|----------|
| Color contrast (normal text) | 4.5:1 minimum | WCAG AA |
| Color contrast (large text ≥18px or bold ≥14px) | 3:1 minimum | WCAG AA |
| Color contrast (UI components, icons) | 3:1 minimum | WCAG AA |
| Touch target size | 44x44px minimum | WCAG 2.5.8 |
| Focus indicator | 2px ring equivalent, 3:1 contrast | WCAG 2.4.7 |
| Motion | Respect `prefers-reduced-motion` | WCAG 2.3.3 |

### Known Contrast Issues (flag + fix)

| Element | Computed Ratio | Status | Fix |
|---------|---------------|--------|-----|
| Tertiary text on white (`rgba(55,53,47,0.5)`) | ~4.0:1 | **FAIL AA** | Use only at ≥18px; for small labels switch to `rgba(55,53,47,0.65)` |
| Disabled text on white (`rgba(55,53,47,0.4)`) | ~2.3:1 | Exempt | WCAG 1.4.3 exempts disabled controls |
| Accent blue on white (`#2383e2`) | 4.6:1 | Passes large text only | Ensure button text ≥14px/500 or ≥18px/400 |
| Yellow tag text on yellow bg (`#dfab01` on `#fbf3db`) | ~2.1:1 | **FAIL** | Use only for decorative tags, never for critical status |

### Focus Management

- All interactive elements use `box-shadow: 0 0 0 2px rgba(35,131,226,0.28)` — the subtle blue halo
- Focus order follows document flow (logical tab order)
- Modal traps focus within dialog; `Escape` closes
- Skip-to-content link as first focusable element: `<a href="#main" class="sr-only focus:not-sr-only">`
- Sidebar and block navigation are fully keyboard accessible
- Drag-and-drop operations have keyboard alternatives (cut/paste, up/down arrow)

### ARIA Patterns

| Component | Role | Key Attributes |
|-----------|------|---------------|
| Modal | `dialog` | `aria-modal="true"`, `aria-labelledby` |
| Dropdown | `menu` / `menuitem` | `aria-expanded`, `aria-haspopup="true"` |
| Sidebar tree | `tree` / `treeitem` | `aria-expanded`, `aria-level`, `aria-selected` |
| Tabs | `tablist` / `tab` / `tabpanel` | `aria-selected`, `aria-controls` |
| Toast | `status` or `alert` | `role="alert"` for errors, `role="status"` for info |
| Toggle | `switch` | `aria-checked` |
| Tooltip | `tooltip` | `aria-describedby` on trigger |
| Page block | `region` | `aria-label` with block type |
| Checkbox | `checkbox` | `aria-checked` |

### Keyboard Navigation

| Component | Key | Action |
|-----------|-----|--------|
| Button | `Enter`, `Space` | Activate |
| Modal | `Escape` | Close |
| Dropdown | `Arrow Up/Down` | Navigate items |
| Dropdown | `Enter` | Select item |
| Dropdown | `Escape` | Close |
| Tabs | `Arrow Left/Right` | Switch tab |
| Checkbox | `Space` | Toggle |
| Toggle | `Space`, `Enter` | Toggle on/off |
| Sidebar tree | `Arrow Right` | Expand node |
| Sidebar tree | `Arrow Left` | Collapse node |
| Block list | `/` | Open command menu |

---

## 11. Do's and Don'ts

### Do
1. Use serif (`ui-serif` / Charter / Sitka Text) for all display and hero headlines — it is Notion's most distinctive typographic signature and differentiates it from every other SaaS product
2. Use warm near-black `#37352f` for ALL primary text — never substitute pure `#000000`, which breaks the paper warmth metaphor
3. Use off-white `#f7f6f3` as the sidebar and secondary surface color — it reads as cream paper, not as a neutral gray
4. Constrain page content to 708px maximum width — this is a reading comfort decision, not a grid decision; honor it in all document views
5. Use `rgba()` tokens for borders and text at reduced opacity — this ensures borders and secondary text automatically adapt to any background tint
6. Apply the 9-color brand palette exclusively for tags and categorization — these colors share a tonal register and never compete with each other
7. Keep border-radius small: 4px on buttons and inputs, 6-8px on cards — the conservative radius communicates "document tool," not "consumer app"
8. Use the accent blue `#2383e2` only for interactive signals — CTAs, links, selection highlights, focus indicators. Never for decorative use
9. Shadows use `rgba(15,15,15,...)` (warm near-black) rather than pure `rgba(0,0,0,...)` — elevation stays warm
10. Test all focus states: the `0 0 0 2px rgba(35,131,226,0.28)` ring must be clearly visible against both white and cream backgrounds

### Don't
1. Don't use sans-serif for large display or hero text — swapping Charter for Inter at 72px destroys the literary character that makes Notion's marketing unforgettable
2. Don't use pure black `#000000` for any text — it reads as cold and digital; `#37352f` is warmer, more ink-like
3. Don't use pure white `#ffffff` for the sidebar or secondary surfaces — the cream `#f7f6f3` is the paper metaphor; pure white on pure white creates no visual depth
4. Don't use the brand palette colors (Gray, Orange, Blue, etc.) for UI chrome or status indicators — they are a labeling vocabulary, not a semantic status system
5. Don't add aggressive animations: no bounce, no spring overshoot, no elastic easing — Notion motion is gentle ease-in-out at 100-200ms
6. Don't use border-radius above 12px in the application UI — large radii belong to consumer apps, not document tools
7. Don't add decorative gradients, glows, or color washes to backgrounds — Notion has zero background decoration; surfaces are flat and warm
8. Don't use weight 700+ in the application chrome — weight 600 maximum for headings; heavier weights overpower the content
9. Don't use tertiary text (`rgba(55,53,47,0.5)`) for actionable elements smaller than 18px — it fails WCAG AA at 4.0:1 on white
10. Don't center-align body paragraphs longer than 2 lines — left-aligned text in the 708px column is the reading standard; center alignment creates uncomfortable eye-tracking

---

## 12. Responsive Behavior

### Breakpoints

| Token | Width | CSS | Tailwind | Key Changes |
|-------|-------|-----|----------|-------------|
| `sm` | 600px | `@media (min-width: 600px)` | `sm:` | Mobile layout ends, 2-col options begin |
| `md` | 768px | `@media (min-width: 768px)` | `md:` | Sidebar appears, full nav visible, page padding increases |
| `lg` | 1024px | `@media (min-width: 1024px)` | `lg:` | Full desktop layout, sidebar fixed, marketing grid 3-col |
| `xl` | 1280px | `@media (min-width: 1280px)` | `xl:` | Marketing max content width, generous margins |
| `2xl` | 1536px | `@media (min-width: 1536px)` | `2xl:` | Ultra-wide: extra breathing room, centered content |

### Responsive Type Scale

| Token | Mobile (<600) | Tablet (768) | Desktop (1024+) |
|-------|--------------|-------------|----------------|
| `display-hero` | 40px | 56px | 72px |
| `display-lg` | 32px | 44px | 56px |
| `display-md` | 28px | 36px | 48px |
| `heading-lg` | 28px | 32px | 36px |
| `heading-md` | 24px | 28px | 30px |
| `body-md` | 16px | 16px | 16px |

### Layout Shifts

| Component | Mobile (<768) | Tablet (768-1023) | Desktop (1024+) |
|-----------|--------------|-------------------|----------------|
| Nav | Hamburger → overlay drawer | Full horizontal | Full horizontal, sticky |
| App sidebar | Hidden (off-canvas, swipe or button) | Collapsible panel, overlay | Fixed left 240px |
| Page content | Full width, padding 16px | Centered, padding 32px | Centered 708px, padding 96px |
| Marketing hero | Stacked, padding 40px top | Stacked, padding 60px | Stacked centered, padding 80px |
| Feature grid | 1 column | 2 columns | 3 columns |
| Database cards | 1 column | 2 columns | 3-4 columns |
| Sidebar | Off-canvas, bottom sheet trigger | Collapsible overlay | Fixed persistent |

### Touch Targets
- Minimum size: 44x44px on mobile
- Minimum gap between targets: 8px
- Mobile CTA buttons: full width, 48px height
- Sidebar items on mobile: 44px height minimum
- Icon buttons in nav: 44x44px touch area (icon may be 16px internally)

---

## 13. Code Snippets

### Button Primary Blue (JSX + Tailwind)

```jsx
<button
  className="bg-[#2383e2] hover:bg-[#0b6bcb] text-white text-sm font-medium px-3 py-1.5 rounded transition-colors duration-150 ease-[cubic-bezier(0.4,0,0.2,1)] focus:outline-none focus:shadow-[0_0_0_2px_rgba(35,131,226,0.28)] disabled:opacity-40 disabled:cursor-not-allowed"
>
  Get started
</button>
```

### Button Black CTA (JSX + Tailwind)

```jsx
<button
  className="bg-[#37352f] hover:bg-[#2f2d28] text-white text-sm font-medium px-3 py-1.5 rounded transition-colors duration-150 ease-[cubic-bezier(0.4,0,0.2,1)] focus:outline-none focus:shadow-[0_0_0_2px_rgba(55,53,47,0.28)] disabled:opacity-40 disabled:cursor-not-allowed"
>
  Get Notion free
</button>
```

### Page Block Card (JSX + Tailwind)

```jsx
<div
  className="bg-white rounded-lg p-5 transition-colors duration-200 hover:bg-[rgba(55,53,47,0.03)] focus-within:shadow-[0_0_0_2px_rgba(35,131,226,0.28)] cursor-pointer"
>
  <h3 className="text-base font-semibold text-[#37352f] mb-1">{title}</h3>
  <p className="text-sm text-[rgba(55,53,47,0.65)] leading-relaxed">{description}</p>
</div>
```

### Notion Tag / Badge (JSX + Tailwind)

```jsx
{/* Orange tag example */}
<span
  className="inline-flex items-center px-1.5 py-0.5 rounded-[3px] text-xs bg-[#faebdd] text-[#d9730d]"
>
  In Progress
</span>
```

### App Sidebar Item (JSX + Tailwind)

```jsx
<li>
  <a
    href={href}
    className={`flex items-center gap-1.5 px-2 py-1 rounded text-sm font-medium transition-colors duration-100 ${
      active
        ? 'bg-[rgba(55,53,47,0.08)] text-[#37352f]'
        : 'text-[rgba(55,53,47,0.65)] hover:bg-[rgba(55,53,47,0.06)] hover:text-[#37352f]'
    }`}
  >
    <span className="w-4 h-4 text-current">{icon}</span>
    {label}
  </a>
</li>
```

### CSS Custom Properties (Root)

```css
:root {
  /* Surfaces */
  --color-bg-primary: #ffffff;
  --color-bg-secondary: #f7f6f3;  /* SIGNATURE cream canvas */
  --color-bg-tertiary: #ebeae8;

  /* Text — warm, never pure black */
  --color-text-primary: #37352f;  /* SIGNATURE warm near-black */
  --color-text-secondary: rgba(55, 53, 47, 0.65);
  --color-text-tertiary: rgba(55, 53, 47, 0.5);
  --color-text-disabled: rgba(55, 53, 47, 0.4);

  /* Accent */
  --color-accent-primary: #2383e2;
  --color-accent-hover: #0b6bcb;
  --color-accent-active: #0a5eaf;

  /* Borders — almost invisible */
  --color-border-default: rgba(55, 53, 47, 0.16);
  --color-border-subtle: rgba(55, 53, 47, 0.09);
  --color-border-focus: #2383e2;

  /* Status */
  --color-status-success: #0f7b6c;
  --color-status-warning: #d9730d;
  --color-status-error: #e03e3e;
  --color-status-info: #0b6e99;

  /* Overlay */
  --color-overlay: rgba(15, 15, 15, 0.4);

  /* Typography */
  --font-display: ui-serif, "Charter", "Bitstream Charter", "Sitka Text", Cambria, Georgia, serif;
  --font-body: system-ui, -apple-system, "Segoe UI", "Helvetica Neue", Helvetica, Arial, sans-serif;
  --font-mono: Menlo, Courier, "Courier New", monospace;

  /* Layout */
  --grid-page-width: 708px;
  --grid-sidebar-width: 240px;
  --grid-max-width: 1200px;

  /* Spacing */
  --space-1: 4px;   --space-2: 8px;   --space-3: 12px;
  --space-4: 16px;  --space-5: 20px;  --space-6: 24px;
  --space-8: 32px;  --space-10: 40px; --space-12: 48px;
  --space-16: 64px; --space-20: 80px; --space-24: 96px;

  /* Border radius — conservative, document-like */
  --radius-xs: 3px;   /* badges, tags */
  --radius-sm: 4px;   /* WORKHORSE — buttons, inputs */
  --radius-md: 6px;   /* dropdowns, database cards */
  --radius-lg: 8px;   /* cards, modals */
  --radius-xl: 12px;  /* featured cards, callouts */
  --radius-full: 9999px; /* avatars, toggles */

  /* Shadows — warm, soft */
  --shadow-xs: rgba(15, 15, 15, 0.05) 0 1px 2px;
  --shadow-sm: rgba(15, 15, 15, 0.07) 0 4px 12px;
  --shadow-md: rgba(15, 15, 15, 0.10) 0 8px 24px, rgba(15, 15, 15, 0.04) 0 2px 8px;
  --shadow-lg: rgba(15, 15, 15, 0.13) 0 12px 32px, rgba(15, 15, 15, 0.05) 0 4px 12px;
  --shadow-focus: 0 0 0 2px rgba(35, 131, 226, 0.28);

  /* Motion */
  --duration-micro: 100ms;
  --duration-fast: 150ms;
  --duration-normal: 200ms;
  --duration-moderate: 300ms;
  --duration-slow: 500ms;
  --ease-default: cubic-bezier(0.4, 0, 0.2, 1);
  --ease-out-quad: cubic-bezier(0.25, 0.46, 0.45, 0.94);
  --ease-spring-gentle: cubic-bezier(0.22, 1, 0.36, 1);

  /* Notion brand palette (bg / text pairs) */
  --notion-gray-bg: #e3e2e0;   --notion-gray-text: #9b9a97;
  --notion-brown-bg: #eee0da;  --notion-brown-text: #64473a;
  --notion-orange-bg: #faebdd; --notion-orange-text: #d9730d;
  --notion-yellow-bg: #fbf3db; --notion-yellow-text: #dfab01;
  --notion-green-bg: #ddedea;  --notion-green-text: #0f7b6c;
  --notion-blue-bg: #ddebf1;   --notion-blue-text: #0b6e99;
  --notion-purple-bg: #eae4f2; --notion-purple-text: #6940a5;
  --notion-pink-bg: #f4dfeb;   --notion-pink-text: #ad1a72;
  --notion-red-bg: #fbe4e4;    --notion-red-text: #e03e3e;
}

.dark {
  --color-bg-primary: #191919;
  --color-bg-secondary: #202020;
  --color-bg-tertiary: #2a2a2a;
  --color-text-primary: #ffffff;
  --color-text-secondary: rgba(255, 255, 255, 0.81);
  --color-text-tertiary: rgba(255, 255, 255, 0.6);
  --color-text-disabled: rgba(255, 255, 255, 0.4);
  --color-border-default: rgba(255, 255, 255, 0.13);
  --color-border-subtle: rgba(255, 255, 255, 0.07);
  --color-overlay: rgba(15, 15, 15, 0.6);
  --shadow-sm: rgba(0, 0, 0, 0.3) 0 4px 12px;
  --shadow-md: rgba(0, 0, 0, 0.4) 0 8px 24px, rgba(0, 0, 0, 0.2) 0 2px 8px;
  --shadow-lg: rgba(0, 0, 0, 0.5) 0 12px 32px, rgba(0, 0, 0, 0.2) 0 4px 12px;
}
```

### Tailwind Config Extension

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        notion: {
          // Core surfaces
          white: '#ffffff',
          cream: '#f7f6f3',    // SIGNATURE — sidebar, paper bg
          gray: '#ebeae8',     // hover surfaces
          ink: '#37352f',      // SIGNATURE warm near-black text
          // Accent
          blue: '#2383e2',
          'blue-hover': '#0b6bcb',
          // 9-color brand palette (bg)
          'tag-gray': '#e3e2e0',
          'tag-brown': '#eee0da',
          'tag-orange': '#faebdd',
          'tag-yellow': '#fbf3db',
          'tag-green': '#ddedea',
          'tag-blue-light': '#ddebf1',
          'tag-purple': '#eae4f2',
          'tag-pink': '#f4dfeb',
          'tag-red': '#fbe4e4',
          // Dark mode surfaces
          'dark-primary': '#191919',
          'dark-secondary': '#202020',
          'dark-panel': '#2a2a2a',
        }
      },
      fontFamily: {
        display: ['ui-serif', 'Charter', 'Bitstream Charter', 'Sitka Text', 'Cambria', 'Georgia', 'serif'],
        body: ['system-ui', '-apple-system', 'Segoe UI', 'Helvetica Neue', 'Helvetica', 'Arial', 'sans-serif'],
        mono: ['Menlo', 'Courier', 'Courier New', 'monospace'],
      },
      maxWidth: {
        'notion-page': '708px',
        'notion-sidebar': '240px',
        'notion-marketing': '1200px',
      },
      borderRadius: {
        'tag': '3px',
        'notion': '4px',   // workhorse
      },
      boxShadow: {
        'notion-sm': 'rgba(15,15,15,0.07) 0 4px 12px',
        'notion-md': 'rgba(15,15,15,0.10) 0 8px 24px, rgba(15,15,15,0.04) 0 2px 8px',
        'notion-lg': 'rgba(15,15,15,0.13) 0 12px 32px, rgba(15,15,15,0.05) 0 4px 12px',
        'notion-focus': '0 0 0 2px rgba(35,131,226,0.28)',
      }
    }
  }
}
```

---

## 14. Agent Prompt Guide

### Quick Reference

| Element | Value |
|---------|-------|
| Primary CTA color | `#2383e2` (Notion Blue) |
| Primary CTA hover | `#0b6bcb` |
| Black CTA (signup) | `#37352f` (warm near-black, NOT pure black) |
| Background primary | `#ffffff` |
| Background secondary | `#f7f6f3` (SIGNATURE cream canvas) |
| Background dark | `#191919` primary, `#202020` secondary |
| Text primary (light) | `#37352f` (warm near-black — never `#000000`) |
| Text primary (dark) | `#ffffff` |
| Text secondary | `rgba(55,53,47,0.65)` |
| Display font | `ui-serif, Charter, Sitka Text, Georgia, serif` |
| Body font | `system-ui, -apple-system, Segoe UI, sans-serif` |
| Mono font | `Menlo, Courier New, monospace` |
| Default radius | `4px` (buttons/inputs), `8px` (cards), `3px` (tags) |
| Page content width | `708px` |
| Primary shadow | `rgba(15,15,15,0.07) 0 4px 12px` |
| Focus ring | `0 0 0 2px rgba(35,131,226,0.28)` |

### Example Prompts

- "Create a Notion-style hero section on white background (#ffffff). Headline 'Where great work happens' at clamp(40px, 5.5vw, 72px) using font-family: ui-serif, Charter, Georgia, serif, weight 600, line-height 1.1, letter-spacing -1.8px, color #37352f. Subheadline in 20px/400 sans-serif rgba(55,53,47,0.65). CTA: 'Get Notion free' black button (bg #37352f, white text, 4px radius, 6px 16px padding, 14px/500), secondary ghost button (border rgba(55,53,47,0.16), same size). No gradients, no glows."

- "Build a Notion-style document page: max-width 708px, centered, bg #ffffff, padding 96px 96px 48px. Serif h1 at 36px/600 color #37352f. Body paragraphs 16px/400 sans-serif, color #37352f, line-height 1.55. Horizontal rule: 1px solid rgba(55,53,47,0.16). Callout block: bg #f7f6f3, 12px radius, 24px padding, 14px sans body."

- "Design a Notion app sidebar: bg #f7f6f3, width 240px, fixed left. Items: 14px/500 sans, padding 4px 8px, 4px radius. Default color rgba(55,53,47,0.65), hover bg rgba(55,53,47,0.06) + color #37352f, active bg rgba(55,53,47,0.08) + color #37352f. Each item: 16px outline icon left + label. No border-right — sidebar separates via bg color contrast."

- "Create a Notion database card grid (3 columns desktop, 1 mobile): each card bg #ffffff, border 1px solid rgba(55,53,47,0.09), 6px radius, 12px padding, shadow rgba(15,15,15,0.05) 0 1px 2px. Hover: shadow rgba(15,15,15,0.07) 0 4px 12px, transition 200ms ease. Tags using Notion palette: orange bg #faebdd text #d9730d, green bg #ddedea text #0f7b6c, 3px radius, 2px 6px padding, 12px/400."

- "Build a Notion-style context menu dropdown: bg #ffffff, border 1px solid rgba(55,53,47,0.09), 6px radius, shadow rgba(15,15,15,0.13) 0 12px 32px, min-width 200px. Items: 14px/400 sans, 6px 12px padding, hover bg rgba(55,53,47,0.06). Divider: 1px solid rgba(55,53,47,0.09). Group label: 11px/500 uppercase rgba(55,53,47,0.5), 8px 12px 4px. Animation: opacity 0→1 + translateY(-4px→0), 150ms cubic-bezier(0.25,0.46,0.45,0.94)."

### Pre-flight Checklist for Generated UI

1. Every interactive element has visible focus state: `box-shadow: 0 0 0 2px rgba(35,131,226,0.28)`
2. Text color uses `#37352f` (warm near-black), NOT `#000000` — check all hardcoded black values
3. Backgrounds use `#f7f6f3` (not `#f5f5f5` or `#fafafa`) for sidebar and secondary surfaces
4. Serif font stack applied to all display text (≥48px headings in marketing contexts)
5. Page content containers respect 708px max-width where applicable
6. Touch targets are minimum 44x44px on mobile
7. Animations respect `prefers-reduced-motion` with the standard media query
8. Tags and badges use ONLY Notion's 9-color brand palette (background + matching text pair)
9. Focus trap active in modals; `Escape` closes all modals and dropdowns
10. Semantic HTML throughout: `<button>` for actions, `<a>` for navigation, headings in hierarchy
11. Border-radius stays ≤12px in application UI (4px workhorse, 8px cards, 12px featured)
12. No decorative gradients, glows, or background color washes — surfaces are flat and warm
