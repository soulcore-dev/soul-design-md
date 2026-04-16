# Design System: Stripe (stripe.com)

## 1. Visual Theme & Atmosphere

Stripe's visual identity is built on a single philosophical bet: that financial infrastructure can feel like an artisan product. The canvas is almost always white (`#ffffff`) or a barely-there sky tint (`#f6f9fc`), and within that space every element earns its presence. Nothing is there for decoration — even the accents labeled "decorative" (Ruby, Magenta) exist to give life to illustration gradients and orbital graphic motifs, never to communicate status. The primary brand expression is a Stripe Purple (`#533afd`) that reads as electric but never loud — it's the color of intelligence at work, not of a sale.

Typography is the core differentiator. Stripe uses `sohne-var`, a variable-weight humanist sans-serif, with OpenType feature set `"ss01"` enabled universally. The display weight is 300 — the opposite of every bold-as-authority convention in B2B SaaS. This "lightness as luxury" signature says: we don't need to shout. The tracking progression runs counter to convention too: larger type gets *more* negative tracking, pulling letterforms together into dense, authoritative bands. At 56px the tracking is -1.4px; by 16px it returns to normal. The combined effect is typography that feels engineered, not typeset.

Depth is handled through a signature multi-layer blue-tinted shadow system. Standard elevation is `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px` — the blue cast in the spread layer is not accidental. It's the ambient light of a world lit by the Stripe brand color. Dark sections use Brand Dark (`#1c1e54`) and Dark Navy (`#0d253d`) as full-bleed backgrounds, creating a day/night alternation that makes the interface feel like it has atmosphere and mass rather than being flat screens of color.

**Key Characteristics:**
- Weight 300 display type as signature: "lightness as luxury" — the anti-bold authority statement
- `sohne-var` with `"ss01"` OpenType feature enabled on ALL text (non-negotiable — affects glyph alternates)
- Progressive negative tracking: -1.4px at 56px → -0.96px at 48px → -0.64px at 32px → -0.26px at 26px → normal at 16px
- Conservative radius theology: max 8px for cards, 4px for buttons/inputs/badges — NO pills, NEVER 12px+
- Multi-layer blue-tinted shadows (`rgba(50,50,93,0.25)`) — blue cast is the brand's ambient light signature
- Triadic background system: white `#ffffff`, subtle blue `#f6f9fc`, light blue `#ebf4fa`
- Dark sections as chromatic counterpoint: Brand Dark `#1c1e54` and Dark Navy `#0d253d`
- Heading color is Deep Navy `#061b31` — never black (`#000000`), never generic gray
- Sticky nav casts a hairline shadow: `rgba(0,55,112,0.08) 0 1px 0` — restraint at its finest
- Mono code uses `SourceCodePro` at 12px/500 with line-height 2.0 — breathing room for density

---

## 2. Color System & Tokens

### Light Theme

| Token | Name | Hex | Role | CSS Variable |
|-------|------|-----|------|-------------|
| `bg-primary` | White | `#ffffff` | Main page background, card surfaces | `--color-bg-primary` |
| `bg-secondary` | Subtle Blue | `#f6f9fc` | Alternating sections, zebra backgrounds | `--color-bg-secondary` |
| `bg-tertiary` | Light Blue | `#ebf4fa` | Highlighted sections, info surfaces | `--color-bg-tertiary` |
| `text-primary` | Deep Navy | `#061b31` | All headings, display type | `--color-text-primary` |
| `text-secondary` | Label | `#273951` | Labels, emphasized body | `--color-text-secondary` |
| `text-tertiary` | Slate | `#64748d` | Body text, descriptions, captions | `--color-text-tertiary` |
| `text-disabled` | Disabled | `rgba(16,16,16,0.3)` | Disabled text (WARNING: 3.2:1 — fails AA) | `--color-text-disabled` |
| `accent-primary` | Stripe Purple | `#533afd` | Primary CTAs, links, interactive anchors | `--color-accent-primary` |
| `accent-hover` | Purple Hover | `#4434d4` | Hover on purple elements | `--color-accent-hover` |
| `accent-active` | Purple Deep | `#2e2b8c` | Active/pressed state | `--color-accent-active` |
| `accent-mid` | Purple Mid | `#665efd` | Secondary purple elements | `--color-accent-mid` |
| `accent-light` | Purple Light | `#b9b9f9` | Ghost button borders, subtle tints | `--color-accent-light` |
| `accent-soft` | Purple Soft | `#d6d9fc` | Input focus ring ambient, tinted surfaces | `--color-accent-soft` |
| `accent-dashed` | Purple Dashed | `#362baa` | Dashed borders, decorative dividers | `--color-accent-dashed` |
| `accent-decorative-ruby` | Ruby | `#ea2261` | Illustration gradients only — NOT status | `--color-accent-ruby` |
| `accent-decorative-magenta` | Magenta | `#f96bee` | Illustration gradients only — NOT status | `--color-accent-magenta` |
| `accent-decorative-magenta-light` | Magenta Light | `#ffd7ef` | Illustration soft tones only | `--color-accent-magenta-light` |
| `border-default` | Border Light | `#e5edf5` | Default input borders, card borders | `--color-border-default` |
| `border-strong` | Border Strong | `#d4dee9` | Active borders, strong dividers | `--color-border-strong` |
| `border-focus` | Stripe Purple | `#533afd` | Focus rings on interactive elements | `--color-border-focus` |
| `status-success` | Green | `#15be53` | Success icons, progress fills | `--color-status-success` |
| `status-success-text` | Green Dark | `#108c3d` | Success badge text | `--color-status-success-text` |
| `status-success-bg` | Green Tint | `rgba(21,190,83,0.2)` | Success badge background | `--color-status-success-bg` |
| `status-success-border` | Green Border | `rgba(21,190,83,0.4)` | Success badge border | `--color-status-success-border` |
| `status-warning` | Amber | `#f59e0b` | Warning states | `--color-status-warning` |
| `status-error` | Red | `#e53935` | Error states, destructive actions | `--color-status-error` |
| `status-info` | Blue | `#2874ad` | Info button text, informational states | `--color-status-info` |
| `overlay` | Overlay | `rgba(6,27,49,0.6)` | Modal backdrops (deep navy base) | `--color-overlay` |

### Dark Theme (Dark Sections — not a global dark mode)

> Stripe does not implement a global dark mode toggle. Dark sections are full-bleed background alternations used for feature marketing. Tokens below apply within `.section-dark` contexts only.

| Token | Hex (Dark Section) | Maps to Light | CSS Variable |
|-------|-------------------|---------------|-------------|
| `bg-primary` | `#1c1e54` | `#ffffff` | `--color-bg-primary` |
| `bg-secondary` | `#0d253d` | `#f6f9fc` | `--color-bg-secondary` |
| `bg-tertiary` | `rgba(255,255,255,0.05)` | `#ebf4fa` | `--color-bg-tertiary` |
| `text-primary` | `#ffffff` | `#061b31` | `--color-text-primary` |
| `text-secondary` | `rgba(255,255,255,0.85)` | `#273951` | `--color-text-secondary` |
| `text-tertiary` | `rgba(255,255,255,0.6)` | `#64748d` | `--color-text-tertiary` |
| `text-disabled` | `rgba(255,255,255,0.3)` | `rgba(16,16,16,0.3)` | `--color-text-disabled` |
| `accent-primary` | `#b9b9f9` | `#533afd` | `--color-accent-primary` |
| `accent-hover` | `#d6d9fc` | `#4434d4` | `--color-accent-hover` |
| `border-default` | `rgba(255,255,255,0.12)` | `#e5edf5` | `--color-border-default` |
| `border-strong` | `rgba(255,255,255,0.22)` | `#d4dee9` | `--color-border-strong` |
| `overlay` | `rgba(0,0,0,0.7)` | `rgba(6,27,49,0.6)` | `--color-overlay` |

### Contrast Ratios (WCAG AA)

| Pair | Foreground | Background | Ratio | Pass AA | Pass AAA |
|------|-----------|-----------|-------|---------|----------|
| Heading on white | `#061b31` | `#ffffff` | 17.8:1 | Yes | Yes |
| Body text on white | `#64748d` | `#ffffff` | 5.1:1 | Yes | No |
| Label on white | `#273951` | `#ffffff` | 9.4:1 | Yes | Yes |
| Purple CTA on white | `#533afd` | `#ffffff` | 5.9:1 | Yes | No |
| White on purple CTA | `#ffffff` | `#533afd` | 5.9:1 | Yes | No |
| Success text on success bg | `#108c3d` | `rgba(21,190,83,0.2)` | 4.7:1 | Yes | No |
| Disabled text on white | `rgba(16,16,16,0.3)` | `#ffffff` | 3.2:1 | **FAIL** | No |
| Info text on white | `#2874ad` | `#ffffff` | 5.4:1 | Yes | No |

> **CRITICAL — Disabled Text Accessibility Failure:** `rgba(16,16,16,0.3)` on white yields 3.2:1 contrast — below the WCAG AA threshold of 4.5:1 for normal text. While WCAG 1.4.3 explicitly exempts disabled UI components from contrast requirements, any disabled *text* that conveys information must still meet 4.5:1. Use `#64748d` (5.1:1) as the accessible disabled text color in all informational contexts.

### Gradients

| Name | Value | Use |
|------|-------|-----|
| Hero gradient | `linear-gradient(135deg, #533afd 0%, #362baa 50%, #1c1e54 100%)` | Hero background graphic motifs |
| Decorative aurora | `linear-gradient(135deg, #ea2261 0%, #f96bee 50%, #533afd 100%)` | Illustration overlays only — never status |
| Soft purple wash | `linear-gradient(180deg, rgba(83,58,253,0.06) 0%, transparent 100%)` | Section transition fade |
| Card tint | `linear-gradient(135deg, rgba(83,58,253,0.03) 0%, transparent 100%)` | Featured card subtle background wash |
| Dark section fade | `linear-gradient(180deg, #1c1e54 0%, #0d253d 100%)` | Dark section full-bleed background |

---

## 3. Typography System

### Font Stack

| Role | Family | Fallbacks | CSS Variable |
|------|--------|-----------|-------------|
| Display | `sohne-var` | `sohne, "Helvetica Neue", Arial, sans-serif` | `--font-display` |
| Body | `sohne-var` | `sohne, "Helvetica Neue", Arial, sans-serif` | `--font-body` |
| Mono | `SourceCodePro` | `"Source Code Pro", "SF Mono", Consolas, "Courier New", monospace` | `--font-mono` |

**OpenType Features:**
- `"ss01"` — REQUIRED on ALL sohne-var text. Activates Stripe's curated glyph alternates (modified 'a', 'g', 'l', 'r'). This is not optional — it defines the visual identity.
- `"tnum"` — Tabular numerals on all financial data, dashboard metrics, price displays. NEVER combine with `"ss01"` in the same element — use one feature string per element.
- Default: `fontFeatureSettings: '"ss01"'` on every text element. Switch to `'"tnum"'` only for number-only spans.

### Type Scale

| Token | Size | Weight | Line Height | Letter Spacing | Fluid (clamp) | CSS Variable |
|-------|------|--------|-------------|----------------|---------------|-------------|
| `display-2xl` | 56px | 300 | 1.07 | -1.4px | `clamp(32px, 4.5vw, 56px)` | `--text-display-2xl` |
| `display-xl` | 48px | 300 | 1.08 | -0.96px | `clamp(28px, 4vw, 48px)` | `--text-display-xl` |
| `display-lg` | 32px | 300 | 1.12 | -0.64px | `clamp(24px, 3vw, 32px)` | `--text-display-lg` |
| `heading-lg` | 26px | 400 | 1.2 | -0.26px | `clamp(20px, 2.5vw, 26px)` | `--text-heading-lg` |
| `heading-md` | 22px | 400 | 1.25 | -0.2px | `clamp(18px, 2vw, 22px)` | `--text-heading-md` |
| `heading-sm` | 18px | 500 | 1.3 | -0.1px | `clamp(16px, 1.8vw, 18px)` | `--text-heading-sm` |
| `body-lg` | 18px | 300 | 1.6 | normal | — | `--text-body-lg` |
| `body-md` | 16px | 400 | 1.6 | normal | — | `--text-body-md` |
| `body-sm` | 14px | 400 | 1.5 | normal | — | `--text-body-sm` |
| `label-lg` | 16px | 500 | 1.5 | normal | — | `--text-label-lg` |
| `label-md` | 14px | 500 | 1.4 | normal | — | `--text-label-md` |
| `label-sm` | 12px | 500 | 1.3 | 0.3px | — | `--text-label-sm` |
| `caption` | 13px | 400 | 1.4 | normal | — | `--text-caption` |
| `micro` | 10px | 400 | 1.3 | 0.5px | — | `--text-micro` |
| `nano` | 8px | 500 | 1.2 | 0.6px | — | `--text-nano` |
| `code-md` | 12px | 500 | 2.0 | normal | — | `--text-code-md` |
| `code-sm` | 11px | 500 | 1.8 | normal | — | `--text-code-sm` |

### Typography Principles
- **Weight 300 as signature:** Display type at weight 300 is Stripe's most distinctive typographic decision. It creates authority through restraint — the opposite of the "bold = important" convention. Never use 300 below 22px; body sizes use 400.
- **Progressive negative tracking:** Letter-spacing tightens with size: -1.4px at 56px → -0.96px at 48px → -0.64px at 32px → -0.26px at 26px → normal at 16px and below. This creates visual cohesion across scale transitions.
- **`"ss01"` is non-negotiable:** Every sohne-var text element must include `fontFeatureSettings: '"ss01"'`. This activates Stripe's custom glyph alternates. Omitting it renders the wrong typeface visually.
- **`"tnum"` for financial data only:** Tabular numerals ensure digit columns align in price tables, dashboards, and transaction lists. Never apply to mixed text — only to spans containing numeric data.
- **Mono at line-height 2.0:** `SourceCodePro` code blocks at 12px/500/line-height 2.0. The generous line-height makes dense API docs readable at small sizes.

---

## 4. Component Catalog

### 4.1 Buttons

**Primary**
- Background: `#533afd` → `var(--color-accent-primary)`
- Text: `#ffffff`
- Padding: `8px 16px`
- Border Radius: `4px` → `var(--radius-sm)`
- Font: 16px / 400 / sohne-var with `"ss01"`
- Border: none
- Shadow: none (default); `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px` (hover)
- Transition: `background-color 150ms cubic-bezier(0.4,0,0.2,1), box-shadow 150ms cubic-bezier(0.4,0,0.2,1)`

**Ghost / Outline**
- Background: transparent
- Text: `#533afd` → `var(--color-accent-primary)`
- Padding: `8px 16px`
- Border Radius: `4px`
- Border: `1px solid #b9b9f9` → `var(--color-accent-light)`
- Font: 16px / 400 / sohne-var with `"ss01"`
- Hover: border-color `#533afd`, bg `rgba(83,58,253,0.04)`

**Info / Secondary**
- Background: transparent
- Text: `#2874ad` → `var(--color-status-info)`
- Padding: `8px 16px`
- Border Radius: `4px`
- Border: `1px solid rgba(43,145,223,0.2)`
- Font: 16px / 400 / sohne-var with `"ss01"`
- Hover: bg `rgba(40,116,173,0.06)`, border-color `rgba(43,145,223,0.4)`

**Danger**
- Background: `#e53935`
- Text: `#ffffff`
- Padding: `8px 16px`
- Border Radius: `4px`
- Font: 16px / 400 / sohne-var with `"ss01"`

**Icon Button**
- Background: transparent
- Padding: `8px`
- Border Radius: `4px`
- Color: `var(--color-text-tertiary)`
- Hover: background `rgba(83,58,253,0.06)`

### 4.2 Inputs

**Text Input**
- Background: `#ffffff` → `var(--color-bg-primary)`
- Border: `1px solid #e5edf5` → `var(--color-border-default)`
- Border Radius: `4px` → `var(--radius-sm)`
- Padding: `8px 12px`
- Font: 16px / 400 / sohne-var with `"ss01"`
- Placeholder color: `#64748d` → `var(--color-text-tertiary)`
- Label: 14px / 500 / `#273951` — positioned above, `margin-bottom: 6px`
- Helper text: 13px / 400 / `#64748d` — below input
- Focus: border `#533afd`, box-shadow `0 0 0 3px rgba(83,58,253,0.12)`

**Select** — same border/radius treatment, chevron icon right-aligned in `#64748d`
**Textarea** — same as Text Input, `min-height: 96px`, `resize: vertical`
**Checkbox** — 16x16px, `border-radius: 4px`, checked bg `#533afd`, check mark `#ffffff`, border `1px solid #d4dee9`
**Radio** — 16x16px, `border-radius: 50%`, selected dot `#533afd`, border `1px solid #d4dee9`
**Toggle / Switch** — 40x22px track, 18px thumb. Off: track `#d4dee9`, On: track `#533afd`, thumb `#ffffff`

### 4.3 Cards

**Standard Card**
- Background: `#ffffff`
- Border: `1px solid #e5edf5` → `var(--color-border-default)`
- Border Radius: `6px` → `var(--radius-md)`
- Padding: `24px`
- Shadow: `rgba(23,23,23,0.08) 0 15px 35px 0px`

**Featured Card (SIGNATURE)**
- Background: `#ffffff`
- Border: none
- Border Radius: `8px` → `var(--radius-lg)`
- Padding: `32px`
- Shadow: `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px`
- Hover: translateY(-4px), shadow deepens, transition 300ms `cubic-bezier(0.16,1,0.3,1)`

**Interactive Card**
- Same as Standard Card
- Hover: translateY(-4px), shadow `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px`, transition 300ms `cubic-bezier(0.16,1,0.3,1)`

### 4.4 Navigation

**Top Nav / Header**
- Background: `#ffffff` (default); `rgba(255,255,255,0.92)` with `backdrop-filter: blur(8px)` (sticky/scrolled)
- Height: `64px`
- Position: `sticky`, `top: 0`, `z-index: 50`
- Border-bottom (sticky): `box-shadow: rgba(0,55,112,0.08) 0 1px 0` (not a real border)
- Logo: Stripe wordmark, left-aligned, 32px height
- Links: 15px / 400 / `#273951` with `"ss01"`. Hover: `#533afd`. Transition 150ms
- Dropdown trigger: includes chevron icon `#64748d`
- CTA: "Start now" primary button (4px radius, 8px 16px padding)
- Secondary CTA: "Sign in" text link `#533afd`
- Mobile: hamburger → slide-in drawer, full-height, `z-index: 60`

**Footer**
- Background: `#0d253d` (Dark Navy)
- Text: `rgba(255,255,255,0.7)` body, `rgba(255,255,255,0.9)` headings
- 5-column grid: Products / Developers / Company / Blog / Legal
- Links: 14px / 400. Hover: `#ffffff`
- Bottom bar: Stripe logo + language picker + social icons
- Border-top: `1px solid rgba(255,255,255,0.1)`

### 4.5 Modals & Dialogs

- Overlay: `rgba(6,27,49,0.6)` → `var(--color-overlay)`
- Container: bg `#ffffff`, radius `8px`, shadow `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px`, max-width `520px`
- Header: `heading-md` (22px/400) with `"ss01"`, close button (icon button top-right, 4px radius)
- Body: padding `24px`, overflow-y auto if exceeds `60vh`
- Footer: padding `16px 24px`, buttons right-aligned, `gap: 8px`
- Enter animation: scale 0.95→1.0 + opacity 0→1, 300ms `cubic-bezier(0.16,1,0.3,1)`

### 4.6 Dropdowns & Menus

- Container: bg `#ffffff`, border `1px solid #e5edf5`, radius `6px`, shadow `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px`
- Item: padding `10px 16px`, font 14px/400 sohne-var with `"ss01"`, color `#273951`
- Item hover: bg `#f6f9fc`, text `#533afd`
- Active item: bg `rgba(83,58,253,0.06)`, text `#533afd`
- Divider: `1px solid #e5edf5`
- Group label: 11px/500/uppercase/`#64748d`, padding `8px 16px`, letter-spacing 0.6px

### 4.7 Badges & Tags

| Variant | Background | Text | Border | Radius | Padding |
|---------|-----------|------|--------|--------|---------|
| Default | `#f6f9fc` | `#273951` | `1px solid #e5edf5` | `4px` | `1px 6px` |
| Success | `rgba(21,190,83,0.2)` | `#108c3d` | `1px solid rgba(21,190,83,0.4)` | `4px` | `1px 6px` |
| Warning | `rgba(245,158,11,0.15)` | `#92400e` | `1px solid rgba(245,158,11,0.3)` | `4px` | `1px 6px` |
| Error | `rgba(229,57,53,0.1)` | `#b71c1c` | `1px solid rgba(229,57,53,0.25)` | `4px` | `1px 6px` |
| Info | `rgba(40,116,173,0.1)` | `#2874ad` | `1px solid rgba(43,145,223,0.2)` | `4px` | `1px 6px` |
| Purple | `rgba(83,58,253,0.1)` | `#533afd` | `1px solid #b9b9f9` | `4px` | `1px 6px` |

> All badges use sohne-var 10px/300 with `"ss01"`. The conservative 4px radius matches button/input radius — badges are part of the same typographic family.

### 4.8 Tooltips

- Background: `#061b31` (always Deep Navy, regardless of surrounding context)
- Text: `#ffffff`, 13px / 400 / sohne-var with `"ss01"`
- Radius: `4px`
- Padding: `6px 10px`
- Arrow: `5px`, same bg color
- Max width: `240px`
- Shadow: `rgba(6,27,49,0.2) 0 4px 12px`

### 4.9 Toasts & Notifications

- Container: bg `#ffffff`, radius `6px`, shadow `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px`, padding `14px 16px`, max-width `360px`
- Icon: 16px, color per variant (success `#15be53` / warning `#f59e0b` / error `#e53935` / info `#2874ad`)
- Title: 14px / 500 / `#061b31` with `"ss01"`
- Message: 13px / 400 / `#64748d` with `"ss01"`
- Close button: icon button 6px padding, top-right
- Position: `top-right`, offset `16px` from edges
- Stack: `gap: 8px` between toasts, max 3 visible
- Enter: translateX(100%)→0 + opacity 0→1, 300ms `cubic-bezier(0.16,1,0.3,1)`

### 4.10 Tables

- Header: bg `#f6f9fc`, text 12px/500/uppercase/`#64748d` with `"ss01"` + letter-spacing 0.6px, border-bottom `1px solid #d4dee9`
- Row: bg `#ffffff`, hover bg `#f6f9fc`, border-bottom `1px solid #e5edf5`
- Cell: padding `12px 16px`, text 14px/400/`#273951` with `"ss01"`
- Numeric cells: 14px/400 with `"tnum"` (tabular), right-aligned
- Striped variant: alternate bg `#f6f9fc`

### 4.11 Tabs

- Container: border-bottom `1px solid #e5edf5`
- Tab (inactive): padding `10px 16px`, font 14px/400/`#64748d` with `"ss01"`, no indicator
- Tab (active): color `#061b31`, border-bottom `2px solid #533afd`, font-weight 500
- Tab hover: color `#273951`
- Transition: color 150ms, border-color 150ms

### 4.12 Avatars

| Size | Dimensions | Font Size | Radius |
|------|-----------|-----------|--------|
| xs | 20px | 8px | 4px |
| sm | 28px | 11px | 4px |
| md | 36px | 14px | 6px |
| lg | 48px | 18px | 6px |
| xl | 64px | 24px | 8px |

> Stripe uses rectangular avatars (not circles) for merchant/company logos, with conservative 4-8px radius matching the system. Circle avatars (`border-radius: 50%`) used only for individual user portraits.

### 4.13 Pagination

- Button: 32x32px, radius `4px`, font 14px/400/sohne-var with `"ss01"`
- Default: bg transparent, text `#64748d`, border `1px solid #e5edf5`
- Active: bg `#533afd`, text `#ffffff`, border-color `#533afd`
- Hover: bg `#f6f9fc`, text `#273951`
- Disabled: opacity 0.4, cursor `not-allowed`
- Gap: `4px`
- Ellipsis: `#64748d`, same 32px container, no border

### 4.14 Progress & Loading

- Progress bar: height `4px`, track `#e5edf5`, fill `#533afd`, radius `4px`
- Spinner: 18px, `#533afd`, stroke 2px, animation `spin 700ms linear infinite`
- Skeleton: bg `#f6f9fc`, shimmer `linear-gradient(90deg, transparent, rgba(83,58,253,0.04), transparent)`, radius matching component, animation `shimmer 1.5s infinite`
- Code block loading: 12px SourceCodePro placeholder with shimmer, line-height 2.0 maintained

---

## 5. Component State Matrix

| Component | Default | Hover | Active/Pressed | Focus | Disabled | Loading | Error |
|-----------|---------|-------|---------------|-------|----------|---------|-------|
| **Button Primary** | bg `#533afd` | bg `#4434d4`, shadow elevated | bg `#2e2b8c`, scale(0.98) | ring `0 0 0 3px rgba(83,58,253,0.3)` | bg `#533afd`, opacity 0.45, `not-allowed` | spinner `#ffffff` 16px + text opacity 0.6 | — |
| **Button Ghost** | border `#b9b9f9`, text `#533afd` | border `#533afd`, bg `rgba(83,58,253,0.04)` | bg `rgba(83,58,253,0.08)`, scale(0.98) | ring `0 0 0 3px rgba(83,58,253,0.3)` | opacity 0.4, `not-allowed` | spinner `#533afd` 16px | — |
| **Button Info** | border `rgba(43,145,223,0.2)`, text `#2874ad` | bg `rgba(40,116,173,0.06)`, border `rgba(43,145,223,0.4)` | bg `rgba(40,116,173,0.1)`, scale(0.98) | ring `0 0 0 3px rgba(40,116,173,0.2)` | opacity 0.4, `not-allowed` | spinner `#2874ad` 16px | — |
| **Input Text** | border `#e5edf5` | border `#d4dee9` | — | border `#533afd`, ring `0 0 0 3px rgba(83,58,253,0.12)` | bg `#f6f9fc`, opacity 0.6, `not-allowed` | — | border `#e53935`, ring `0 0 0 3px rgba(229,57,53,0.12)`, helper text `#e53935` |
| **Select** | border `#e5edf5` | border `#d4dee9` | — | border `#533afd`, ring `0 0 0 3px rgba(83,58,253,0.12)` | opacity 0.5, `not-allowed` | spinner `#533afd` 14px | border `#e53935` |
| **Checkbox** | border `#d4dee9` | border `#533afd` | — | ring `0 0 0 3px rgba(83,58,253,0.2)` | opacity 0.4 | — | border `#e53935` |
| **Card Interactive** | shadow standard | shadow elevated, translateY(-4px) | shadow ambient, translateY(-2px) | ring `0 0 0 3px rgba(83,58,253,0.2)` | opacity 0.5 | skeleton shimmer | — |
| **Link** | color `#533afd`, no underline | color `#4434d4`, underline | color `#2e2b8c` | ring `0 0 0 3px rgba(83,58,253,0.2)`, offset 2px | color `#64748d`, no pointer | — | — |
| **Tab** | color `#64748d`, no indicator | color `#273951` | color `#061b31`, `2px solid #533afd` bottom | ring inset `0 0 0 2px #533afd` | opacity 0.4 | — | — |
| **Toggle** | track `#d4dee9`, thumb `#ffffff` | track `#b9b9f9` (off) / `#4434d4` (on) | — | ring `0 0 0 3px rgba(83,58,253,0.2)` | opacity 0.4 | — | — |

### Focus Ring Standard
```css
/* Stripe uses box-shadow for focus — preserves border-radius, no outline flicker */
box-shadow: 0 0 0 3px rgba(83, 58, 253, 0.3);
outline: none;

/* For simple links without visible bg: */
outline: 2px solid var(--color-border-focus);
outline-offset: 2px;
```

### Disabled Pattern
```css
opacity: 0.45;
cursor: not-allowed;
pointer-events: none;
/* Accessible disabled text — use instead of rgba(16,16,16,0.3): */
color: #64748d; /* 5.1:1 on white — passes AA */
```

### Error Input Pattern
```css
border-color: #e53935;
box-shadow: 0 0 0 3px rgba(229, 57, 53, 0.12);
```

---

## 6. Layout & Spacing System

### Spacing Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `space-0` | 0px | `p-0` | `--space-0` | Reset |
| `space-px` | 1px | `p-px` | `--space-px` | Hairline borders |
| `space-1` | 4px | `p-1` | `--space-1` | Badge padding, icon gaps |
| `space-2` | 8px | `p-2` | `--space-2` | Button padding-y, badge padding-x, tight gaps |
| `space-3` | 12px | `p-3` | `--space-3` | Input padding, component internal gaps |
| `space-4` | 16px | `p-4` | `--space-4` | Button padding-x, component gap |
| `space-5` | 20px | `p-5` | `--space-5` | Section padding mobile |
| `space-6` | 24px | `p-6` | `--space-6` | Card padding standard, section sub-gap |
| `space-8` | 32px | `p-8` | `--space-8` | Featured card padding, form section gaps |
| `space-10` | 40px | `p-10` | `--space-10` | Section gap mobile |
| `space-12` | 48px | `p-12` | `--space-12` | Section gap tablet |
| `space-16` | 64px | `p-16` | `--space-16` | Section gap desktop, nav height |
| `space-20` | 80px | `p-20` | `--space-20` | Hero padding, large section gap |
| `space-24` | 96px | `p-24` | `--space-24` | Extra-large section separation |

### Grid

| Property | Value | CSS Variable |
|----------|-------|-------------|
| Max content width | `1080px` | `--grid-max-width` |
| Column count | 12 | `--grid-columns` |
| Gutter | `24px` | `--grid-gutter` |
| Margin (mobile) | `16px` | `--grid-margin-sm` |
| Margin (tablet) | `24px` | `--grid-margin-md` |
| Margin (desktop) | `auto` (centered) | `--grid-margin-lg` |

### Border Radius Scale

> Stripe's radius philosophy is CONSERVATIVE. The scale stops at 8px. There are no 12px, 16px, or pill (9999px) radii. Roundness implies consumer playfulness; Stripe implies infrastructure precision.

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `radius-none` | 0px | `rounded-none` | `--radius-none` | Tables, full-bleed sections |
| `radius-xs` | 1px | — | `--radius-xs` | Hairline insets, image borders |
| `radius-sm` | 4px | `rounded` | `--radius-sm` | Buttons, inputs, badges, checkboxes, tooltips |
| `radius-md` | 6px | `rounded-md` | `--radius-md` | Standard cards, dropdowns, toasts |
| `radius-lg` | 8px | `rounded-lg` | `--radius-lg` | Featured cards, modals — MAXIMUM allowed |

---

## 7. Depth & Elevation

### Shadow Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `shadow-xs` | `rgba(23,23,23,0.06) 0 3px 6px` | — | `--shadow-xs` | Ambient lift on flat elements |
| `shadow-sm` | `rgba(23,23,23,0.08) 0 15px 35px 0px` | `shadow` | `--shadow-sm` | Standard cards, dropdowns |
| `shadow-md` | `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px` | `shadow-lg` | `--shadow-md` | Featured cards (SIGNATURE), modals |
| `shadow-lg` | `rgba(3,3,39,0.25) 0 14px 21px -14px, rgba(0,0,0,0.1) 0 8px 17px -8px` | `shadow-xl` | `--shadow-lg` | Deep elevation for popovers |
| `shadow-nav` | `rgba(0,55,112,0.08) 0 1px 0` | — | `--shadow-nav` | Sticky nav hairline |
| `shadow-ambient` | `rgba(23,23,23,0.06) 0 3px 6px` | `shadow-sm` | `--shadow-ambient` | Micro-elevation, thumbnails |

> **Blue-tinted shadows are the Stripe signature.** The `rgba(50,50,93,...)` in `shadow-md` is not incidental — the blue cast connects elevation to brand color. Never substitute with neutral grays on key elevation moments.

### Z-Index Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `z-base` | 0 | `--z-base` | Default content flow |
| `z-raised` | 1 | `--z-raised` | Inline lifted elements |
| `z-dropdown` | 10 | `--z-dropdown` | Dropdowns, menus |
| `z-sticky` | 50 | `--z-sticky` | Sticky nav, table headers |
| `z-overlay` | 60 | `--z-overlay` | Modal backdrop |
| `z-modal` | 70 | `--z-modal` | Modal content |
| `z-popover` | 80 | `--z-popover` | Popovers, tooltips |
| `z-toast` | 90 | `--z-toast` | Toast notifications |

---

## 8. Motion & Animation System

### Duration Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `duration-instant` | 0ms | `--duration-instant` | Immediate state changes |
| `duration-fast` | 150ms | `--duration-fast` | Button hover, link color, micro-interactions |
| `duration-normal` | 200ms | `--duration-normal` | Tab switches, badge transitions |
| `duration-moderate` | 300ms | `--duration-moderate` | Card hover lift, dropdown open, modal enter |
| `duration-slow` | 400ms | `--duration-slow` | Complex panel transitions |
| `duration-slower` | 600ms | `--duration-slower` | Page transitions, orchestrated sequences |

### Easing Functions

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `ease-default` | `cubic-bezier(0.4, 0, 0.2, 1)` | `--ease-default` | General transitions |
| `ease-in` | `cubic-bezier(0.4, 0, 1, 1)` | `--ease-in` | Elements exiting view |
| `ease-out` | `cubic-bezier(0, 0, 0.2, 1)` | `--ease-out` | Elements entering view |
| `ease-in-out` | `cubic-bezier(0.4, 0, 0.2, 1)` | `--ease-in-out` | Elements repositioning |
| `ease-fintech` | `cubic-bezier(0.16, 1, 0.3, 1)` | `--ease-fintech` | Stripe signature — card lifts, modal enters, drawer open |

> `ease-fintech` (`cubic-bezier(0.16,1,0.3,1)`) is Stripe's motion signature. It's a fast-start, eased-out spring: the element arrives confidently and decelerates into place. Use it for all premium interactions: card hover, modal entry, drawer open.

### Common Transitions

| Interaction | Property | Duration | Easing |
|------------|----------|----------|--------|
| Button hover | `background-color, box-shadow` | 150ms | ease-default |
| Button active | `transform` | 100ms | ease-default |
| Link hover | `color` | 150ms | ease-default |
| Card hover | `transform, box-shadow` | 300ms | ease-fintech |
| Modal enter | `opacity, transform (scale 0.95→1)` | 300ms | ease-fintech |
| Modal exit | `opacity, transform` | 200ms | ease-in |
| Toast enter | `transform (translateX), opacity` | 300ms | ease-fintech |
| Toast exit | `opacity` | 200ms | ease-in |
| Dropdown open | `opacity, transform (translateY -4px→0)` | 200ms | ease-out |
| Focus ring | `box-shadow` | 150ms | ease-default |
| Nav shadow on scroll | `box-shadow` | 200ms | ease-default |

### Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
  /* Orbital graphic motifs: keep visible but remove rotation */
  .stripe-orbital { animation: none !important; }
}
```

---

## 9. Icon System

| Property | Value |
|----------|-------|
| Library | Custom Stripe icons (internal) + Heroicons v2 (outline) for generic UI |
| Default size | 18px |
| Stroke width | 1.5px |
| Color | `currentColor` (inherits from parent text color) |

### Icon Sizes

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `icon-xs` | 12px | `--icon-xs` | Inline badge icons, micro indicators |
| `icon-sm` | 14px | `--icon-sm` | Input prefix/suffix, button icons |
| `icon-md` | 18px | `--icon-md` | Navigation items, card actions, default |
| `icon-lg` | 24px | `--icon-lg` | Feature section headings |
| `icon-xl` | 32px | `--icon-xl` | Product logos, empty states |
| `icon-2xl` | 48px | `--icon-2xl` | Hero sections, large product graphics |

### Feature Icon Container
- Square: `48px`, bg `rgba(83,58,253,0.08)`, icon `#533afd` 24px, radius `6px`
- Product logo container: `40px`, border `1px solid #e5edf5`, bg `#ffffff`, radius `6px`, shadow `--shadow-xs`

---

## 10. Accessibility Contract

### Targets

| Criterion | Target | Standard |
|-----------|--------|----------|
| Color contrast (normal text) | 4.5:1 minimum | WCAG AA |
| Color contrast (large text >=18px / bold >=14px) | 3:1 minimum | WCAG AA |
| Color contrast (UI components, focus indicators) | 3:1 minimum | WCAG AA |
| Touch target size | 44x44px minimum | WCAG 2.5.8 |
| Focus indicator | 3px ring, 3:1 contrast against adjacent colors | WCAG 2.4.7 |
| Motion | Respect `prefers-reduced-motion` | WCAG 2.3.3 |

### Known Contrast Issues (must fix or document)

| Element | Current | Ratio | Fix |
|---------|---------|-------|-----|
| Disabled text `rgba(16,16,16,0.3)` on white | `#ffffff` bg | 3.2:1 | **FAILS AA for informational text.** Use `#64748d` (5.1:1) as accessible disabled text. WCAG 1.4.3 exempts disabled *components* but NOT informational disabled text (e.g., placeholder-style labels, hint copy). |
| Purple light `#b9b9f9` on white | `#ffffff` bg | 2.2:1 | Decorative / border use only. Never as text color. |
| Purple soft `#d6d9fc` on white | `#ffffff` bg | 1.5:1 | Background tint only. Never text. |
| Magenta `#f96bee` on white | `#ffffff` bg | 2.0:1 | Illustration gradients only. Never text, never actionable UI. |
| Ruby `#ea2261` on white | `#ffffff` bg | 4.2:1 | Decorative only. Fails AA for normal-weight small text. |

### Focus Management

- All interactive elements: `box-shadow: 0 0 0 3px rgba(83,58,253,0.3)` on `:focus-visible`
- Focus order follows DOM order (logical left-to-right, top-to-bottom)
- Modal traps focus within dialog until Escape or explicit close
- Skip-to-content link: `<a href="#main-content" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4">`
- All nav items keyboard-accessible with visible focus ring

### ARIA Patterns

| Component | Role | Key Attributes |
|-----------|------|---------------|
| Modal | `dialog` | `aria-modal="true"`, `aria-labelledby="modal-title"` |
| Dropdown / Mega Menu | `navigation` / `menu` | `aria-expanded`, `aria-haspopup="true"` |
| Tabs | `tablist` / `tab` / `tabpanel` | `aria-selected`, `aria-controls`, `aria-orientation="horizontal"` |
| Toast | `status` or `alert` | `role="alert"` for errors, `role="status"` for success/info |
| Toggle | `switch` | `aria-checked` |
| Tooltip | `tooltip` | `aria-describedby` on trigger element |
| Progress bar | `progressbar` | `aria-valuenow`, `aria-valuemin="0"`, `aria-valuemax="100"` |
| Pricing table | `table` | `<th scope="col">`, `<th scope="row">` for row headers |

### Keyboard Navigation

| Component | Key | Action |
|-----------|-----|--------|
| Button | `Enter`, `Space` | Activate |
| Modal | `Escape` | Close and return focus to trigger |
| Dropdown | `Arrow Up / Down` | Navigate items |
| Dropdown | `Enter` | Select item |
| Dropdown | `Escape` | Close dropdown |
| Tabs | `Arrow Left / Right` | Switch tab |
| Checkbox | `Space` | Toggle checked |
| Toggle | `Space`, `Enter` | Toggle on/off |
| Select | `Arrow Up / Down` | Navigate options |

---

## 11. Do's and Don'ts

### Do
1. Apply `fontFeatureSettings: '"ss01"'` to every sohne-var text element — omitting it renders the wrong typeface
2. Use weight 300 for display type (56px, 48px, 32px) — it IS the brand signature, not an oversight
3. Use Deep Navy `#061b31` for all headings — never `#000000` or generic `#1a1a2e`
4. Keep border-radius at 4px for buttons and inputs, 6px for cards, 8px max for featured cards — this ceiling is absolute
5. Use the signature blue-tinted shadow (`rgba(50,50,93,0.25) 0 30px 45px -30px`) for all featured/elevated cards
6. Apply `"tnum"` feature to financial data displays (prices, transaction amounts, dashboard metrics)
7. Use `#64748d` (5.1:1) as the accessible disabled text color — never the raw `rgba(16,16,16,0.3)` token in informational contexts
8. Keep max content width at 1080px — tighter than most B2B sites, creates the focused "infrastructure precision" feel
9. Apply `ease-fintech` (`cubic-bezier(0.16,1,0.3,1)`) for card lifts, modal enters, and drawer opens
10. Use `SourceCodePro` at 12px/500/line-height 2.0 for all code blocks — the generous line-height is intentional for density readability

### Don't
1. Don't use pill-shaped buttons (border-radius >= 12px or 9999px) — Stripe's radius theology is conservative; pills signal consumer apps, not infrastructure
2. Don't use Ruby (`#ea2261`) or Magenta (`#f96bee`) for status indicators — they exist only in illustration gradients
3. Don't hardcode `rgba(16,16,16,0.3)` as disabled text for informational content — it's 3.2:1, below WCAG AA
4. Don't use weight 300 below 22px — at body sizes it becomes too light for sufficient contrast at reading sizes
5. Don't apply both `"ss01"` and `"tnum"` to the same element — separate them into distinct spans within the same container
6. Don't use `#533afd` for decorative fills or background washes — it's the interactive signal color; use `#d6d9fc` or `#f6f9fc` for tints
7. Don't add card border-radius above 8px — `radius-lg` (8px) is the absolute ceiling; `rounded-xl` and above are banned
8. Don't use neutral gray shadows on featured cards — the blue cast in `rgba(50,50,93,...)` is the brand's visual fingerprint
9. Don't center-align body paragraphs over 2 lines — Stripe body text is always left-aligned; centered text is reserved for hero eyebrow labels only
10. Don't override the nav shadow with a visible `border-bottom` — the `rgba(0,55,112,0.08) 0 1px 0` box-shadow approach is intentionally hairline and blue-tinted

---

## 12. Responsive Behavior

### Breakpoints

| Token | Width | CSS | Tailwind | Key Changes |
|-------|-------|-----|----------|-------------|
| `sm` | 640px | `@media (min-width: 640px)` | `sm:` | 2-col grids unlock, stacked CTAs go side-by-side |
| `md` | 768px | `@media (min-width: 768px)` | `md:` | Nav expands, form layouts go 2-column |
| `lg` | 1024px | `@media (min-width: 1024px)` | `lg:` | Full desktop nav, 3-col feature grids, 1080px content width |
| `xl` | 1280px | `@media (min-width: 1280px)` | `xl:` | Visible page gutters, generous side margins |
| `2xl` | 1536px | `@media (min-width: 1536px)` | `2xl:` | Large-monitor breathing room |

### Responsive Type Scale

| Token | Mobile (<640) | Tablet (768) | Desktop (1024+) |
|-------|--------------|-------------|----------------|
| `display-2xl` | 32px | 42px | 56px |
| `display-xl` | 28px | 36px | 48px |
| `display-lg` | 22px | 26px | 32px |
| `heading-lg` | 20px | 22px | 26px |
| `heading-md` | 18px | 20px | 22px |

### Layout Shifts

| Component | Mobile (<768) | Tablet (768-1023) | Desktop (1024+) |
|-----------|--------------|-------------------|----------------|
| Nav | Hamburger → slide-in drawer | Hamburger → drawer | Full horizontal with mega-dropdown |
| Hero | Stacked, padding 24px, type 32px | Stacked, padding 48px, type 42px | Split layout or stacked, padding 80px, type 56px |
| Feature grid | 1 column stacked | 2 columns | 3-4 columns |
| Pricing cards | 1 column stacked, scroll | 2 columns | 3 columns side-by-side |
| Code panels | Full-width stacked | Full-width | Side-by-side with UI preview |
| Footer | Stacked single column | 2x3 grid | 5-column grid |
| CTA pairs | Full-width stacked, 48px height | Side-by-side, auto width | Side-by-side, auto width |

### Touch Targets
- Minimum size: 44x44px
- Minimum gap between adjacent targets: 8px
- Mobile CTA buttons: full width, 48px min height
- Nav hamburger: 44x44px touch area
- Icon buttons: minimum 44x44px touch area even when icon is 14-16px

---

## 13. Code Snippets

### Button Primary (JSX + Tailwind)

```jsx
<button
  className="bg-[#533afd] hover:bg-[#4434d4] active:bg-[#2e2b8c] active:scale-[0.98] text-white px-4 py-2 rounded text-base font-normal transition-[background-color,box-shadow] duration-150 focus:outline-none focus:shadow-[0_0_0_3px_rgba(83,58,253,0.3)] disabled:opacity-45 disabled:cursor-not-allowed hover:shadow-[rgba(50,50,93,0.25)_0_30px_45px_-30px,rgba(0,0,0,0.1)_0_18px_36px_-18px]"
  style={{ fontFamily: 'sohne-var, sohne, "Helvetica Neue", Arial, sans-serif', fontFeatureSettings: '"ss01"' }}
>
  Start now
</button>
```

### Button Ghost (JSX + Tailwind)

```jsx
<button
  className="bg-transparent hover:bg-[rgba(83,58,253,0.04)] text-[#533afd] px-4 py-2 rounded text-base font-normal border border-[#b9b9f9] hover:border-[#533afd] transition-all duration-150 focus:outline-none focus:shadow-[0_0_0_3px_rgba(83,58,253,0.3)] disabled:opacity-40 disabled:cursor-not-allowed"
  style={{ fontFeatureSettings: '"ss01"' }}
>
  Sign in
</button>
```

### Featured Card (JSX + Tailwind)

```jsx
<div
  className="bg-white rounded-lg p-8 hover:-translate-y-1 transition-[transform,box-shadow] cursor-pointer focus:outline-none focus:shadow-[0_0_0_3px_rgba(83,58,253,0.2)]"
  style={{
    boxShadow: 'rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px',
    transitionDuration: '300ms',
    transitionTimingFunction: 'cubic-bezier(0.16,1,0.3,1)',
  }}
  tabIndex={0}
>
  <div
    className="w-12 h-12 rounded-md flex items-center justify-center mb-5"
    style={{ background: 'rgba(83,58,253,0.08)' }}
  >
    <CreditCard className="w-6 h-6 text-[#533afd]" />
  </div>
  <h3
    className="text-[22px] font-light text-[#061b31] mb-3 leading-snug tracking-[-0.2px]"
    style={{ fontFeatureSettings: '"ss01"' }}
  >
    Global payments
  </h3>
  <p
    className="text-base font-normal text-[#64748d] leading-relaxed"
    style={{ fontFeatureSettings: '"ss01"' }}
  >
    Accept payments from customers worldwide with a single integration.
  </p>
</div>
```

### Success Badge (JSX + Tailwind)

```jsx
<span
  className="inline-flex items-center text-[10px] font-light rounded px-1.5 py-px"
  style={{
    background: 'rgba(21,190,83,0.2)',
    color: '#108c3d',
    border: '1px solid rgba(21,190,83,0.4)',
    fontFeatureSettings: '"ss01"',
  }}
>
  Paid
</span>
```

### Financial Data Table Cell (JSX — with tnum)

```jsx
<td
  className="px-4 py-3 text-sm font-normal text-[#273951] text-right tabular-nums"
  style={{ fontFeatureSettings: '"tnum"', fontVariantNumeric: 'tabular-nums' }}
>
  $4,320.00
</td>
```

### Sticky Nav (JSX + Tailwind)

```jsx
<header
  className="sticky top-0 z-50 bg-white/95 backdrop-blur-sm"
  style={{ boxShadow: 'rgba(0,55,112,0.08) 0 1px 0' }}
>
  <nav className="max-w-[1080px] mx-auto px-6 h-16 flex items-center justify-between gap-8">
    <img src="/stripe-logo.svg" alt="Stripe" className="h-8" />
    <div className="hidden lg:flex items-center gap-6">
      {['Products', 'Solutions', 'Developers', 'Resources', 'Pricing'].map(link => (
        <a
          key={link}
          className="text-[15px] font-normal text-[#273951] hover:text-[#533afd] transition-colors duration-150 focus:outline-none focus:shadow-[0_0_0_3px_rgba(83,58,253,0.3)] rounded-sm"
          style={{ fontFeatureSettings: '"ss01"' }}
          href={`/${link.toLowerCase()}`}
        >
          {link}
        </a>
      ))}
    </div>
    <div className="flex items-center gap-3">
      <a
        className="text-[15px] text-[#533afd] hover:text-[#4434d4] transition-colors duration-150"
        style={{ fontFeatureSettings: '"ss01"' }}
        href="/login"
      >
        Sign in
      </a>
      <button
        className="bg-[#533afd] hover:bg-[#4434d4] text-white px-4 py-2 rounded text-sm transition-colors duration-150 focus:outline-none focus:shadow-[0_0_0_3px_rgba(83,58,253,0.3)]"
        style={{ fontFeatureSettings: '"ss01"' }}
      >
        Start now
      </button>
    </div>
  </nav>
</header>
```

### CSS Custom Properties (Root)

```css
:root {
  /* === BRAND === */
  --stripe-purple:        #533afd;
  --stripe-purple-hover:  #4434d4;
  --stripe-purple-deep:   #2e2b8c;
  --stripe-purple-mid:    #665efd;
  --stripe-purple-light:  #b9b9f9;
  --stripe-purple-soft:   #d6d9fc;
  --stripe-purple-dashed: #362baa;
  --stripe-brand-dark:    #1c1e54;
  --stripe-dark-navy:     #0d253d;

  /* === TEXT === */
  --color-text-primary:            #061b31;
  --color-text-secondary:          #273951;
  --color-text-tertiary:           #64748d;
  --color-text-disabled:           rgba(16, 16, 16, 0.3); /* WARNING: 3.2:1 — fails AA */
  --color-text-disabled-accessible: #64748d;              /* 5.1:1 — use this instead */

  /* === BACKGROUNDS === */
  --color-bg-primary:   #ffffff;
  --color-bg-secondary: #f6f9fc;
  --color-bg-tertiary:  #ebf4fa;
  --color-bg-dark:      #1c1e54;
  --color-bg-dark-navy: #0d253d;

  /* === INTERACTIVE === */
  --color-accent-primary: #533afd;
  --color-accent-hover:   #4434d4;
  --color-accent-active:  #2e2b8c;
  --color-accent-mid:     #665efd;
  --color-accent-light:   #b9b9f9;
  --color-accent-soft:    #d6d9fc;

  /* === BORDERS === */
  --color-border-default: #e5edf5;
  --color-border-strong:  #d4dee9;
  --color-border-focus:   #533afd;

  /* === STATUS === */
  --color-status-success:        #15be53;
  --color-status-success-text:   #108c3d;
  --color-status-success-bg:     rgba(21, 190, 83, 0.2);
  --color-status-success-border: rgba(21, 190, 83, 0.4);
  --color-status-warning:        #f59e0b;
  --color-status-error:          #e53935;
  --color-status-info:           #2874ad;
  --color-overlay:               rgba(6, 27, 49, 0.6);

  /* === TYPOGRAPHY === */
  --font-display: 'sohne-var', 'sohne', 'Helvetica Neue', Arial, sans-serif;
  --font-body:    'sohne-var', 'sohne', 'Helvetica Neue', Arial, sans-serif;
  --font-mono:    'SourceCodePro', 'Source Code Pro', 'SF Mono', Consolas, 'Courier New', monospace;
  --font-feature-default: "ss01";
  --font-feature-numeric: "tnum";

  /* === SPACING === */
  --space-1:  4px;   --space-2:  8px;   --space-3:  12px;
  --space-4:  16px;  --space-5:  20px;  --space-6:  24px;
  --space-8:  32px;  --space-10: 40px;  --space-12: 48px;
  --space-16: 64px;  --space-20: 80px;  --space-24: 96px;

  /* === RADIUS (conservative — max 8px) === */
  --radius-none: 0px;
  --radius-xs:   1px;
  --radius-sm:   4px;
  --radius-md:   6px;
  --radius-lg:   8px;

  /* === SHADOWS (blue-tinted signature) === */
  --shadow-xs:      rgba(23, 23, 23, 0.06) 0 3px 6px;
  --shadow-sm:      rgba(23, 23, 23, 0.08) 0 15px 35px 0px;
  --shadow-md:      rgba(50, 50, 93, 0.25) 0 30px 45px -30px, rgba(0, 0, 0, 0.1) 0 18px 36px -18px;
  --shadow-lg:      rgba(3, 3, 39, 0.25) 0 14px 21px -14px, rgba(0, 0, 0, 0.1) 0 8px 17px -8px;
  --shadow-nav:     rgba(0, 55, 112, 0.08) 0 1px 0;
  --shadow-ambient: rgba(23, 23, 23, 0.06) 0 3px 6px;

  /* === MOTION === */
  --duration-fast:     150ms;
  --duration-normal:   200ms;
  --duration-moderate: 300ms;
  --duration-slow:     400ms;
  --ease-default:  cubic-bezier(0.4, 0, 0.2, 1);
  --ease-in:       cubic-bezier(0.4, 0, 1, 1);
  --ease-out:      cubic-bezier(0, 0, 0.2, 1);
  --ease-fintech:  cubic-bezier(0.16, 1, 0.3, 1);

  /* === Z-INDEX === */
  --z-base:     0;
  --z-raised:   1;
  --z-dropdown: 10;
  --z-sticky:   50;
  --z-overlay:  60;
  --z-modal:    70;
  --z-popover:  80;
  --z-toast:    90;

  /* === GRID === */
  --grid-max-width: 1080px;
  --grid-gutter:    24px;
  --grid-columns:   12;
}

/* Dark sections (full-bleed marketing alternations — not a global dark mode) */
.section-dark {
  --color-bg-primary:   #1c1e54;
  --color-bg-secondary: #0d253d;
  --color-text-primary: #ffffff;
  --color-text-secondary: rgba(255, 255, 255, 0.85);
  --color-text-tertiary:  rgba(255, 255, 255, 0.6);
  --color-border-default: rgba(255, 255, 255, 0.12);
  --color-accent-primary: #b9b9f9;
}
```

### Tailwind Config Extension

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        stripe: {
          purple:         '#533afd',
          'purple-hover': '#4434d4',
          'purple-deep':  '#2e2b8c',
          'purple-mid':   '#665efd',
          'purple-light': '#b9b9f9',
          'purple-soft':  '#d6d9fc',
          'purple-dashed':'#362baa',
          'brand-dark':   '#1c1e54',
          'dark-navy':    '#0d253d',
        },
        heading:  '#061b31',
        label:    '#273951',
        body:     '#64748d',
        surface: {
          primary:   '#ffffff',
          secondary: '#f6f9fc',
          tertiary:  '#ebf4fa',
        },
        'border-light':  '#e5edf5',
        'border-strong': '#d4dee9',
        success: {
          DEFAULT: '#15be53',
          text:    '#108c3d',
          bg:      'rgba(21,190,83,0.2)',
          border:  'rgba(21,190,83,0.4)',
        },
      },
      fontFamily: {
        display: ['sohne-var', 'sohne', '"Helvetica Neue"', 'Arial', 'sans-serif'],
        body:    ['sohne-var', 'sohne', '"Helvetica Neue"', 'Arial', 'sans-serif'],
        mono:    ['SourceCodePro', '"Source Code Pro"', '"SF Mono"', 'Consolas', 'monospace'],
      },
      fontSize: {
        'display-2xl': ['56px', { lineHeight: '1.07', letterSpacing: '-1.4px', fontWeight: '300' }],
        'display-xl':  ['48px', { lineHeight: '1.08', letterSpacing: '-0.96px', fontWeight: '300' }],
        'display-lg':  ['32px', { lineHeight: '1.12', letterSpacing: '-0.64px', fontWeight: '300' }],
        'heading-lg':  ['26px', { lineHeight: '1.2',  letterSpacing: '-0.26px', fontWeight: '400' }],
        'heading-md':  ['22px', { lineHeight: '1.25', letterSpacing: '-0.2px',  fontWeight: '400' }],
      },
      maxWidth: {
        'stripe': '1080px',
      },
      borderRadius: {
        'sm': '4px',
        'md': '6px',
        'lg': '8px',
        // NO 'xl', NO '2xl', NO 'full' — Stripe does not use large radii
      },
      boxShadow: {
        'stripe-xs':      'rgba(23,23,23,0.06) 0 3px 6px',
        'stripe-sm':      'rgba(23,23,23,0.08) 0 15px 35px 0px',
        'stripe-md':      'rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px',
        'stripe-lg':      'rgba(3,3,39,0.25) 0 14px 21px -14px, rgba(0,0,0,0.1) 0 8px 17px -8px',
        'stripe-nav':     'rgba(0,55,112,0.08) 0 1px 0',
        'stripe-focus':   '0 0 0 3px rgba(83,58,253,0.3)',
        'stripe-focus-sm':'0 0 0 3px rgba(83,58,253,0.12)',
      },
      transitionTimingFunction: {
        'fintech': 'cubic-bezier(0.16, 1, 0.3, 1)',
        'stripe':  'cubic-bezier(0.4, 0, 0.2, 1)',
      },
    },
  },
}
```

---

## 14. Agent Prompt Guide

### Quick Reference

| Element | Value |
|---------|-------|
| Primary CTA color | `#533afd` (Stripe Purple) |
| CTA hover | `#4434d4` |
| CTA active | `#2e2b8c` |
| Background primary | `#ffffff` |
| Background secondary | `#f6f9fc` |
| Background tertiary | `#ebf4fa` |
| Heading color | `#061b31` (Deep Navy — NOT black) |
| Label color | `#273951` |
| Body text | `#64748d` (Slate, 5.1:1 on white) |
| Font (all roles) | `sohne-var` with `fontFeatureSettings: '"ss01"'` |
| Font mono | `SourceCodePro` 12px / 500 / line-height 2.0 |
| Display weight | 300 (signature) |
| Body weight | 400 |
| Button radius | `4px` |
| Card radius standard | `6px` |
| Card radius featured | `8px` — ABSOLUTE MAXIMUM |
| Signature shadow | `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px` |
| Nav shadow | `rgba(0,55,112,0.08) 0 1px 0` |
| Focus ring | `box-shadow: 0 0 0 3px rgba(83,58,253,0.3)` |
| Motion signature | `cubic-bezier(0.16,1,0.3,1)` (ease-fintech) |
| Grid max width | `1080px` |

### Example Prompts

- "Create a Stripe-style hero section on `#ffffff` background. Display heading 'The new standard for payments' at `clamp(32px,4.5vw,56px)`, font-weight 300, color `#061b31`, letter-spacing -1.4px, sohne-var with `fontFeatureSettings: '"ss01"'`. Subheading 18px/300/`#64748d` with `"ss01"`. Two CTAs: primary (`#533afd` bg, white text, 4px radius, 8px 16px padding, hover shadow `rgba(50,50,93,0.25) 0 30px 45px -30px`) and ghost (transparent bg, `#533afd` text, `1px solid #b9b9f9` border, 4px radius, hover border `#533afd`)."

- "Build a Stripe-style product card grid (3 cols on desktop, 1 on mobile). Cards: `bg-white`, no border, 8px radius, 32px padding, shadow `rgba(50,50,93,0.25) 0 30px 45px -30px, rgba(0,0,0,0.1) 0 18px 36px -18px`. Hover: `translateY(-4px)`, shadow deepens, 300ms `cubic-bezier(0.16,1,0.3,1)`. Icon container: 48px, 6px radius, `rgba(83,58,253,0.08)` bg, `#533afd` icon 24px. Title: 22px/400/`#061b31`/`"ss01"`. Body: 16px/400/`#64748d`/`"ss01"`."

- "Design a Stripe-style sticky nav: `bg-white/95`, `backdrop-filter: blur(8px)`, `box-shadow: rgba(0,55,112,0.08) 0 1px 0`, h-16, max-width 1080px. Logo left. Links: 15px/400/`#273951` with `"ss01"`, hover `#533afd`, 150ms transition. Right: 'Sign in' text link `#533afd` + 'Start now' primary button (4px radius, 8px 16px padding)."

- "Create a financial transaction table with Stripe styling: header `#f6f9fc` bg, 12px/500/uppercase/`#64748d` with `"ss01"`, letter-spacing 0.6px, `border-bottom: 1px solid #d4dee9`. Rows: `#ffffff` bg, hover `#f6f9fc`, `border-bottom: 1px solid #e5edf5`. Numeric cells: `fontFeatureSettings: '"tnum"'`, right-aligned, 14px/400/`#273951`. Status badges: Success = `rgba(21,190,83,0.2)` bg / `#108c3d` text / `rgba(21,190,83,0.4)` border / 4px radius / 1px 6px padding / 10px/300/`"ss01"`."

- "Build a Stripe-style payment form: inputs `bg-white`, `1px solid #e5edf5` border, 4px radius, `8px 12px` padding, 16px sohne-var `"ss01"`. Labels: 14px/500/`#273951` above each input, margin-bottom 6px. Focus: `border-color: #533afd` + `box-shadow: 0 0 0 3px rgba(83,58,253,0.12)`. Error: `border-color: #e53935` + `box-shadow: 0 0 0 3px rgba(229,57,53,0.12)` + 13px/`#e53935` error text below. Disabled fields: use `color: #64748d` (NOT `rgba(16,16,16,0.3)` which fails AA). Submit: primary button full-width with 48px min height on mobile."

- "Implement a Stripe dark section (full-bleed marketing block, not a dark mode): background `#1c1e54`, gradient to `#0d253d`. Headings `#ffffff` weight 300, body `rgba(255,255,255,0.6)`, borders `rgba(255,255,255,0.12)`. Cards: `rgba(255,255,255,0.05)` bg, `rgba(255,255,255,0.1)` border, 8px radius, 32px padding, same blue-tinted shadow. Accent links use `#b9b9f9` (purple light). All text uses sohne-var with `"ss01"`."

### Pre-flight Checklist for Generated UI

1. Every `<button>`, `<a>`, `<input>`, `<select>`, `<textarea>` has a visible focus state (`box-shadow: 0 0 0 3px rgba(83,58,253,0.3)` on `:focus-visible`)
2. All headings use `#061b31` (Deep Navy) — NOT `#000000`, NOT `#111827`, NOT any generic dark
3. `fontFeatureSettings: '"ss01"'` is on every sohne-var text element — every single one
4. Numeric / financial data uses `fontFeatureSettings: '"tnum"'` in a separate span (not combined with `"ss01"`)
5. No button, input, badge, or card has border-radius above 8px — strip any `rounded-xl`, `rounded-2xl`, or `rounded-full` from non-avatar elements
6. Disabled informational text uses `#64748d` (5.1:1), NOT `rgba(16,16,16,0.3)` (3.2:1 — fails WCAG AA)
7. Featured/elevated cards use the signature blue-tinted shadow, not a neutral `drop-shadow` or `shadow-lg`
8. Touch targets are minimum 44x44px on mobile — check buttons, nav links, icon buttons, and badge actions
9. All animations and transitions are wrapped in `@media (prefers-reduced-motion: reduce)` suppression
10. `SourceCodePro` code blocks use 12px / 500 / line-height 2.0 — the generous line-height is intentional for readability
11. Letter-spacing scales with type size: -1.4px at 56px → -0.96px at 48px → -0.64px at 32px → -0.26px at 26px → normal at 16px
12. Display type at 56px, 48px, 32px uses font-weight 300 — never 400, 500, or 600 at these sizes
13. Focus trap is active in all modals/dialogs — Escape key closes and returns focus to the trigger element
14. Modal enter animation uses scale 0.95→1.0 + opacity 0→1 at 300ms `cubic-bezier(0.16,1,0.3,1)` (ease-fintech)
