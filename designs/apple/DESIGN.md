# Design System: Apple (apple.com)

## 1. Visual Theme & Atmosphere

Apple.com is the world's most studied commercial website — and its genius is the discipline of what it refuses to do. There are no gradients decorating UI components. No colorful illustrations. No competing accent colors. No drop shadows stacking on cards. What exists instead is a binary visual grammar: sections alternate between absolute black (`#000000`) and light gray (`#f5f5f7`) with the precision of a metronome. Each section is a stage, and each stage holds exactly one hero product. The photography does not share the frame. The background does not distract from the subject. The result is that every product Apple shows feels singular — even when there are fifteen of them across a page.

The typographic system is anchored in SF Pro, Apple's proprietary system typeface, deployed with a mechanism that most design systems ignore entirely: optical sizing. SF Pro Display is physically a different typeface from SF Pro Text — the letterforms have wider spacing, higher x-height adjustments, and subtly different stroke contrast. The boundary is 20px. Above it, only SF Pro Display is permitted; below it, only SF Pro Text. This rule is not stylistic preference — it is the reason Apple's typography feels optically balanced at every size where other systems using a single font do not. Combined with universally negative letter-spacing (even at 12px body text, tracking tightens slightly), SF Pro creates a density and authority that is unmistakably Apple across every product surface.

Color is managed as radical restraint. Apple Blue (`#0071e3`) is the singular chromatic accent in the entire system — one color, one role, one signal: interactive intent. Every CTA button, every focus state, every active indicator carries this blue. Nothing else in the palette is chromatic. The rest of the system is built from neutrals: pure black for immersive hero sections, light gray (`#f5f5f7`, not pure white — the subtle blue-gray tint prevents sterility) for alternate sections, near-black `#1d1d1f` for primary text, and five extremely close dark surface variants that each encode a specific elevation context. The signature glass navigation — `rgba(0,0,0,0.8)` with `backdrop-filter: saturate(180%) blur(20px)` — is the only persistent UI element on the page and communicates Apple's mastery of physical metaphor in digital interfaces.

**Key Characteristics:**
- Binary section rhythm: absolute black `#000000` hero sections alternating with light gray `#f5f5f7` editorial sections — never pure white
- Apple Blue `#0071e3` as the singular chromatic accent — zero additional hue in the system
- SF Pro Display above 20px / SF Pro Text at 19px and below — optical sizing is non-negotiable DNA
- Negative letter-spacing at ALL text sizes, from -0.28px at 56px headlines down to -0.08px at 10px nano text
- Glass navigation: `rgba(0,0,0,0.8)` + `backdrop-filter: saturate(180%) blur(20px)` — 48px height, always present
- Pill CTA links at 980px border-radius — echoes the 980px max content width, the most recognizable Apple detail
- Single diffuse shadow in the entire system: `rgba(0,0,0,0.22) 3px 5px 30px 0px` — photographic, soft, rare
- Product photography placed on solid color fields only — never on gradients, textures, or competing backgrounds
- Full-viewport product hero sections with 56px display headlines and paired pill CTAs
- Spring physics for product reveal animations; parallax on scroll-driven hero moments

---

## 2. Color System & Tokens

### Light Theme (Section bg: `#f5f5f7`)

| Token | Name | Hex | Role | CSS Variable |
|-------|------|-----|------|-------------|
| `bg-primary` | Light Gray | `#f5f5f7` | Default section background — the slight blue-gray tint prevents sterility | `--color-bg-primary` |
| `bg-hero` | Pure Black | `#000000` | Immersive hero and product showcase sections | `--color-bg-hero` |
| `bg-white` | White | `#ffffff` | Card surfaces, modal containers, nav dropdown | `--color-bg-white` |
| `bg-button-default` | Button Default Light | `#fafafc` | Unfocused state on light bg buttons | `--color-bg-button-default` |
| `bg-button-active` | Button Active Light | `#ededf2` | Pressed state on light bg buttons | `--color-bg-button-active` |
| `text-primary` | Near Black | `#1d1d1f` | Primary text on light backgrounds — editorial and UI copy | `--color-text-primary` |
| `text-secondary` | Black 80% | `rgba(0,0,0,0.8)` | Secondary text on light — nav links, card descriptions | `--color-text-secondary` |
| `text-tertiary` | Black 48% | `rgba(0,0,0,0.48)` | Tertiary text, disabled states, carousel controls on light | `--color-text-tertiary` |
| `accent-primary` | Apple Blue | `#0071e3` | THE singular chromatic accent — CTAs, focus states, interactive signals | `--color-accent-primary` |
| `accent-link-light` | Link Blue | `#0066cc` | Inline text links on light backgrounds | `--color-accent-link-light` |
| `border-focus` | Apple Blue | `#0071e3` | Focus rings — 2px solid, consistent with accent-primary | `--color-border-focus` |
| `overlay-media` | Media Overlay | `rgba(210,210,215,0.64)` | Media control scrims, frosted playback UI | `--color-overlay-media` |
| `overlay-dark` | Dark Overlay | `rgba(0,0,0,0.8)` | Nav background, modal backdrops | `--color-overlay-dark` |
| `status-success` | Green | `#28cd41` | Success states (iOS-derived) | `--color-status-success` |
| `status-warning` | Amber | `#ff9f0a` | Warning states (iOS-derived) | `--color-status-warning` |
| `status-error` | Red | `#ff3b30` | Error states, destructive actions (iOS-derived) | `--color-status-error` |
| `status-info` | Apple Blue | `#0071e3` | Informational states — reuses the accent | `--color-status-info` |

### Dark Theme (Section bg: `#000000`)

Apple does not use a global dark/light mode toggle on apple.com — dark is applied structurally per section. These tokens apply inside `.section-dark` or hero containers.

| Token | Hex (Dark Section) | Maps to Light Role | CSS Variable |
|-------|-------------------|-------------------|-------------|
| `bg-primary` | `#000000` | Section background | `--color-bg-primary` |
| `bg-surface-1` | `#272729` | First elevation above void — content containers | `--color-bg-surface-1` |
| `bg-surface-2` | `#262628` | Second elevation — nested cards on dark | `--color-bg-surface-2` |
| `bg-surface-3` | `#28282a` | Third elevation — modal surfaces on dark | `--color-bg-surface-3` |
| `bg-surface-4` | `#2a2a2d` | Fourth elevation — dropdown on dark | `--color-bg-surface-4` |
| `bg-surface-5` | `#242426` | Fifth elevation — input on dark | `--color-bg-surface-5` |
| `text-primary` | `#f5f5f7` | Primary text on dark sections | `--color-text-primary` |
| `text-secondary` | `rgba(255,255,255,0.8)` | Secondary text on dark | `--color-text-secondary` |
| `text-tertiary` | `rgba(255,255,255,0.48)` | Tertiary, disabled on dark | `--color-text-tertiary` |
| `accent-primary` | `#0071e3` | Apple Blue — identical in both contexts | `--color-accent-primary` |
| `accent-link-dark` | Bright Blue | `#2997ff` | Inline links on dark backgrounds (higher luminance for contrast) | `--color-accent-link-dark` |
| `modal-close-hover` | White 32% | `rgba(255,255,255,0.32)` | Hover state on dark modal close button | `--color-modal-close-hover` |
| `border-default` | White 16% | `rgba(255,255,255,0.16)` | Dividers and hairlines on dark sections | `--color-border-default` |
| `overlay-media` | Media Overlay | `rgba(210,210,215,0.64)` | Media controls remain consistent across themes | `--color-overlay-media` |

### Contrast Ratios (WCAG AA)

| Pair | Foreground | Background | Ratio | Pass AA | Pass AAA |
|------|-----------|-----------|-------|---------|----------|
| Primary text (light) | `#1d1d1f` | `#f5f5f7` | 17.4:1 | Yes | Yes |
| White on black hero | `#ffffff` | `#000000` | 21:1 | Yes | Yes |
| `#f5f5f7` text on black | `#f5f5f7` | `#000000` | 19.1:1 | Yes | Yes |
| Apple Blue CTA on white | `#0071e3` | `#ffffff` | 4.6:1 | Yes (borderline AA large text) | No |
| Apple Blue CTA on `#f5f5f7` | `#0071e3` | `#f5f5f7` | 4.5:1 | Yes (minimum AA threshold) | No |
| Link Blue on white | `#0066cc` | `#ffffff` | 5.9:1 | Yes | No |
| Bright Blue on black | `#2997ff` | `#000000` | 6.4:1 | Yes | Yes |
| Black 80% on `#f5f5f7` | `rgba(0,0,0,0.8)` | `#f5f5f7` | 12.2:1 | Yes | Yes |
| Black 48% on `#f5f5f7` | `rgba(0,0,0,0.48)` | `#f5f5f7` | 5.5:1 | Yes | No |
| White on Apple Blue | `#ffffff` | `#0071e3` | 4.6:1 | Yes (use 17px+ or bold) | No |

> **Apple Blue contrast note:** `#0071e3` on `#ffffff` is 4.6:1 — passes WCAG AA for normal text (4.5:1 minimum) by a slim margin. At `#f5f5f7` it is exactly 4.5:1. Always use 17px+ or weight 600+ for Apple Blue interactive text. For smaller sizes, `#0066cc` (5.9:1) is preferred.

> **Bright Blue note:** `#2997ff` on `#000000` is 6.4:1 — higher luminance specifically engineered for dark-background links. Never use on light backgrounds (2.7:1 on white — fails AA).

### Gradients

Apple avoids decorative gradients on UI components. The following are structural only.

| Name | Value | Use |
|------|-------|-----|
| None | — | Apple uses solid color fields only for product photography backgrounds |

> Apple's visual philosophy explicitly rejects gradients as backgrounds for product imagery. The solid `#000000` and `#f5f5f7` fields are the entire gradient story.

---

## 3. Typography System

### Font Stack

| Role | Family | Fallbacks | CSS Variable |
|------|--------|-----------|-------------|
| Display (20px+) | `SF Pro Display` | `SF Pro Icons, Helvetica Neue, Helvetica, Arial, sans-serif` | `--font-display` |
| Body (19px and below) | `SF Pro Text` | `SF Pro Icons, Helvetica Neue, Helvetica, Arial, sans-serif` | `--font-body` |
| Icons | `SF Pro Icons` | — | `--font-icons` |

**Optical Sizing — The Critical Rule:**
SF Pro Display and SF Pro Text are not stylistic variations of the same font — they are two distinct optical masters. SF Pro Display has wider letter-spacing, higher contrast strokes, and refined spacing optimized for large viewing distances. SF Pro Text has tighter spacing and adjusted x-heights for small on-screen reading. The 20px boundary is where the human visual system transitions between reading modes. Crossing it with the wrong font produces subtle but measurable legibility degradation. This is why the rule is absolute.

**Letter-Spacing — Negative at All Sizes:**
Apple tracks text negatively across the entire scale. This is not purely aesthetic — it compensates for the slightly wider default spacing in San Francisco at various optical sizes, and creates the characteristic dense, confident Apple typography rhythm.

### Type Scale

| Token | Size | Weight | Line Height | Letter Spacing | Font | CSS Variable |
|-------|------|--------|-------------|----------------|------|-------------|
| `display-hero` | 56px | 600 | 1.07 | -0.28px | SF Pro Display | `--text-display-hero` |
| `section-heading` | 40px | 600 | 1.10 | normal | SF Pro Display | `--text-section-heading` |
| `tile-heading` | 28px | 400 | 1.14 | 0.196px | SF Pro Display | `--text-tile-heading` |
| `card-title` | 21px | 700 | 1.19 | 0.231px | SF Pro Display | `--text-card-title` |
| `sub-heading` | 21px | 400 | 1.19 | 0.231px | SF Pro Display | `--text-sub-heading` |
| `nav-heading` | 34px | 600 | 1.47 | -0.374px | SF Pro Text | `--text-nav-heading` |
| `sub-nav` | 24px | 300 | 1.50 | normal | SF Pro Text | `--text-sub-nav` |
| `body` | 17px | 400 | 1.47 | -0.374px | SF Pro Text | `--text-body` |
| `body-emphasis` | 17px | 600 | 1.24 | -0.374px | SF Pro Text | `--text-body-emphasis` |
| `button-lg` | 18px | 300 | 1.00 | normal | SF Pro Text | `--text-button-lg` |
| `button` | 17px | 400 | 2.41 | normal | SF Pro Text | `--text-button` |
| `link` | 14px | 400 | 1.43 | -0.224px | SF Pro Text | `--text-link` |
| `caption` | 14px | 400 | 1.29 | -0.224px | SF Pro Text | `--text-caption` |
| `caption-bold` | 14px | 600 | 1.29 | -0.224px | SF Pro Text | `--text-caption-bold` |
| `micro` | 12px | 400 | 1.33 | -0.12px | SF Pro Text | `--text-micro` |
| `micro-bold` | 12px | 600 | 1.33 | -0.12px | SF Pro Text | `--text-micro-bold` |
| `nano` | 10px | 400 | 1.47 | -0.08px | SF Pro Text | `--text-nano` |

> **Fluid sizing:** Apple does not use CSS `clamp()` on apple.com — instead, font sizes change at specific breakpoints using the 8-breakpoint system. See Section 12.

### Typography Principles
- **Optical sizing is non-negotiable:** Never use SF Pro Display below 20px. Never use SF Pro Text above 19px. The fonts are physically different — mismatching breaks the optical calibration that makes Apple type feel effortless.
- **Weight lives at 400 and 600 almost entirely:** Weight 300 is rare and only for large decorative button text (`button-lg`). Weight 700 is rare and only for `card-title`. The system communicates hierarchy through size and optical font switch, not weight escalation.
- **Negative tracking is universal:** Even the smallest nano text (10px) tracks at -0.08px. This is Apple's most distinctive typographic signature — other brands only tighten tracking at display sizes.
- **Line-height compresses at scale:** 1.07 at 56px, 1.19 at 21px, 1.47 at 17px, 2.41 at button text. The extreme 2.41 line-height on button text is a deliberate touch-target padding mechanism built into typography itself.
- **Positive tracking is exceptional:** `tile-heading` (28px/0.196px) and `card-title` (21px/0.231px) track slightly positive — these are short tile labels that benefit from optical expansion at mid-size, a nuanced counter-rule to the global negative tracking pattern.

---

## 4. Component Catalog

### 4.1 Buttons

**Primary Blue CTA (The Apple Button)**
- Background: `#0071e3` → `var(--color-accent-primary)`
- Text: `#ffffff`
- Padding: `8px 15px`
- Border Radius: `8px` → `var(--radius-standard)`
- Font: SF Pro Text 17px / 400 / line-height 2.41
- Border: `1px solid transparent`
- Hover: bg brightens ~5% (CSS `filter: brightness(1.05)`)
- Active: bg darkens ~5% (CSS `filter: brightness(0.95)`)
- Focus: `2px solid #0071e3` outline, 2px offset
- Transition: `filter 250ms cubic-bezier(0.25,0.1,0.25,1)`

**Primary Dark CTA**
- Background: `#1d1d1f` → `var(--color-text-primary)`
- Text: `#ffffff`
- Padding: `8px 15px`
- Border Radius: `8px`
- Font: SF Pro Text 17px / 400
- Border: `1px solid transparent`
- Hover: bg `#3a3a3c` (slightly lighter near-black)
- Focus: `2px solid #0071e3` outline, 2px offset

**Pill Link CTA — "Learn more" / "Shop" (Signature Apple Element)**
- Background: transparent
- Text: `#0066cc` (on light sections) / `#2997ff` (on dark sections)
- Padding: `3px 8px`
- Border Radius: `980px` — the sacred pill radius that echoes the 980px max content width
- Border: `1px solid #0066cc` (light) / `1px solid #2997ff` (dark)
- Font: SF Pro Text 14-17px / 400
- Hover: opacity 0.8 on text and border color
- Focus: `2px solid #0071e3` outline, 2px offset
- Use: Every "Learn more →" and "Shop →" link throughout the site. The 980px radius is the most visually iconic Apple UI detail — its extreme curvature on a small element creates a distinctive organic tension.

**Filter / Search Input Button**
- Background: `#fafafc` → `var(--color-bg-button-default)`
- Text: `rgba(0,0,0,0.8)` → `var(--color-text-secondary)`
- Padding: `0 14px`
- Height: `32px`
- Border Radius: `11px` → `var(--radius-comfortable)`
- Border: `3px solid rgba(0,0,0,0.04)`
- Font: SF Pro Text 14px / 400

**Media Control Button**
- Background: `rgba(210,210,215,0.64)` → `var(--color-overlay-media)`
- Shape: circle — `border-radius: 50%`
- Size: 44px minimum (touch target)
- Active: `transform: scale(0.9)`
- Transition: `transform 150ms cubic-bezier(0.25,0.1,0.25,1)`

### 4.2 Inputs

**Text Input**
- Background: `#ffffff` (light) / `#242426` → `var(--color-bg-surface-5)` (dark)
- Border: `1px solid rgba(0,0,0,0.16)` (light) / `1px solid rgba(255,255,255,0.16)` (dark)
- Border Radius: `8px`
- Padding: `11px 14px`
- Font: SF Pro Text 17px / 400 / -0.374px tracking
- Placeholder: `rgba(0,0,0,0.48)` (light) / `rgba(255,255,255,0.48)` (dark)
- Label: SF Pro Text 14px / 400 / -0.224px — positioned above, `margin-bottom: 4px`, color `#1d1d1f`
- Helper text: SF Pro Text 12px / 400 / -0.12px, color `rgba(0,0,0,0.48)` — below input
- Focus: `2px solid #0071e3` outline, 2px offset

**Select** — same treatment as Text Input, chevron icon right-aligned in `rgba(0,0,0,0.48)`
**Textarea** — same as Text Input, `min-height: 100px`, `resize: vertical`
**Checkbox** — 18x18px, `border-radius: 4px`, checked bg `#0071e3`, check `#ffffff`
**Radio** — 18x18px, `border-radius: 50%`, selected dot `#0071e3`
**Toggle / Switch** — iOS-style 51x31px track, 27px thumb. Off: track `rgba(0,0,0,0.16)`, On: track `#34c759` (iOS Green), thumb `#ffffff` with shadow `0 1px 4px rgba(0,0,0,0.3)`

### 4.3 Cards

**Product Tile Card**
- Background: `#f5f5f7` (on white bg) / `#1d1d1f` (on dark bg)
- Border: none — Apple almost never uses visible borders on cards
- Border Radius: `8px` → `var(--radius-standard)`
- Padding: `24px`
- Shadow: none by default
- Hover shadow: `rgba(0,0,0,0.22) 3px 5px 30px 0px` — the one shadow in the system
- Product image: centered in card, on solid color field (no gradient backdrop)

**Feature Section Card**
- Background: `#f5f5f7` (light) / `#000000` (dark immersive)
- Full section, no border, no border-radius at section level
- Typography: display-hero 56px centered, then pill CTA pair below

**Media Card (Videos, App store, etc.)**
- Border Radius: `12px` → `var(--radius-large)`
- Overflow: hidden
- Media control overlaid with `rgba(210,210,215,0.64)` scrim

### 4.4 Navigation

**Top Nav — The Signature Glass Bar**
- Background: `rgba(0,0,0,0.8)` — dark translucent, always on both light and dark sections
- Backdrop: `backdrop-filter: saturate(180%) blur(20px)` — THE Apple glass signature
- Height: `48px`
- Position: `sticky`, `top: 0`, `z-index: 9999`
- Logo (Apple logo mark): `17px` width × `48px` height, white SVG, centered
- Nav links: SF Pro Text 12px / 400, `#f5f5f7`, `letter-spacing: -0.01em`
- Hover: opacity 0.8
- Mobile: hamburger icon (white, 44x44px touch) → full-screen dark overlay menu with 17px SF Pro Text links
- The glass effect is non-negotiable — it must persist as the single chrome element across all sections

**Footer**
- Background: `#f5f5f7`
- 4-column grid: Shop + More ways to shop + About Apple + For Education
- Links: SF Pro Text 12px / 400, `rgba(0,0,0,0.8)`. Hover: underline
- Bottom bar: copyright, legal links — 12px / 400 / `rgba(0,0,0,0.48)`
- Border-top: `1px solid rgba(0,0,0,0.08)`

**Mega-Menu Dropdown**
- Background: `#f5f5f7` — maintains section rhythm even in nav dropdown
- Products: full-width, organized by category
- Card within dropdown: no border, image + name + price + "Buy" pill link

**Breadcrumbs**
- Separator: `>` character in `rgba(0,0,0,0.48)`
- Font: SF Pro Text 12px / 400 / -0.12px, `rgba(0,0,0,0.8)`

### 4.5 Modals & Dialogs

- Overlay: `rgba(0,0,0,0.8)` → `var(--color-overlay-dark)`
- Container: bg `#ffffff`, radius `12px` → `var(--radius-large)`, shadow `rgba(0,0,0,0.22) 3px 5px 30px 0px`, max-width `600px`
- Header: SF Pro Display 21px / 700 / 0.231px, close button top-right
- Close button: 28x28px circle, `rgba(0,0,0,0.08)` bg, `×` symbol. Hover: bg `rgba(255,255,255,0.32)`
- Body: padding `24px`, overflow-y auto if content exceeds viewport
- Footer: padding `16px 24px`, buttons right-aligned, `gap: 12px`

### 4.6 Dropdowns & Menus

- Container: bg `#ffffff`, border `none`, radius `8px`, shadow `rgba(0,0,0,0.22) 3px 5px 30px 0px`
- Item: padding `10px 16px`, SF Pro Text 14px / 400 / -0.224px, `#1d1d1f`. Hover: bg `#f5f5f7`
- Active item: text `#0071e3`, bg `rgba(0,113,227,0.08)`
- Divider: `1px solid rgba(0,0,0,0.08)`
- Group label: SF Pro Text 11px / 600, uppercase, `rgba(0,0,0,0.48)`, padding `8px 16px`

### 4.7 Badges & Tags

| Variant | Background | Text | Border | Radius | Padding |
|---------|-----------|------|--------|--------|---------|
| Default | `rgba(0,0,0,0.08)` | `#1d1d1f` | none | `980px` | `3px 8px` |
| Blue | `rgba(0,113,227,0.1)` | `#0066cc` | none | `980px` | `3px 8px` |
| New | `#0071e3` | `#ffffff` | none | `980px` | `3px 8px` |
| Success | `rgba(40,205,65,0.15)` | `#1a7f37` | none | `980px` | `3px 8px` |
| Warning | `rgba(255,159,10,0.15)` | `#b45309` | none | `980px` | `3px 8px` |
| Error | `rgba(255,59,48,0.12)` | `#d70015` | none | `980px` | `3px 8px` |

> Badges use the 980px pill radius consistent with Apple CTAs — even small UI elements follow the sacred radius rule.

### 4.8 Tooltips

- Background: `#1d1d1f` (always near-black, regardless of section theme)
- Text: `#f5f5f7`, SF Pro Text 13px / 400
- Radius: `8px`
- Padding: `8px 12px`
- Arrow: `6px`, same bg color
- Max width: `280px`
- Shadow: `rgba(0,0,0,0.22) 3px 5px 30px 0px`

### 4.9 Toasts & Notifications

- Container: bg `#ffffff`, radius `12px`, shadow `rgba(0,0,0,0.22) 3px 5px 30px 0px`, padding `16px`
- Icon: 20px, color per variant
- Title: SF Pro Text 14px / 600 / -0.224px / `#1d1d1f`
- Message: SF Pro Text 14px / 400 / -0.224px / `rgba(0,0,0,0.8)`
- Close button: 20px circle, `rgba(0,0,0,0.08)` bg
- Position: `top-center`, offset `16px` from top
- Stack: `gap: 8px`, max 3 visible

### 4.10 Tables

- Header: bg `#f5f5f7`, SF Pro Text 12px / 600 / uppercase / `rgba(0,0,0,0.48)`, border-bottom `1px solid rgba(0,0,0,0.08)`
- Row: bg transparent, hover bg `rgba(0,0,0,0.04)`, border-bottom `1px solid rgba(0,0,0,0.08)`
- Cell: padding `12px 16px`, SF Pro Text 14px / 400 / -0.224px, `#1d1d1f`
- Striped: alternate bg `rgba(0,0,0,0.02)`

### 4.11 Tabs

- Container: border-bottom `1px solid rgba(0,0,0,0.08)`
- Tab: padding `12px 16px`, SF Pro Text 14px / 400 / -0.224px, color `rgba(0,0,0,0.48)` (inactive), `#1d1d1f` (active)
- Indicator: `2px solid #0071e3` bottom border on active tab
- Hover: color `rgba(0,0,0,0.8)`

### 4.12 Avatars

| Size | Dimensions | Font Size | Radius |
|------|-----------|-----------|--------|
| xs | 24px | 10px | 50% |
| sm | 32px | 12px | 50% |
| md | 40px | 14px | 50% |
| lg | 56px | 18px | 50% |
| xl | 80px | 24px | 50% |

### 4.13 Pagination

- Button: 36x36px, radius `8px`, SF Pro Text 14px / 400 / -0.224px
- Default: bg transparent, text `rgba(0,0,0,0.48)`
- Active: bg `#0071e3`, text `#ffffff`
- Hover: bg `rgba(0,0,0,0.04)`
- Disabled: opacity 0.4, cursor `not-allowed`
- Gap: `4px`
- Carousel indicator dots: 6x6px, radius `50%`, active `#1d1d1f`, inactive `rgba(0,0,0,0.24)`

### 4.14 Progress & Loading

- Progress bar: height `3px`, track `rgba(0,0,0,0.08)`, fill `#0071e3`, radius `9999px`
- Spinner: 20px, `#0071e3` stroke, 2px stroke width, `spin 1s linear infinite`
- Skeleton: bg `rgba(0,0,0,0.06)`, shimmer `linear-gradient(90deg, transparent 0%, rgba(255,255,255,0.6) 50%, transparent 100%)`, radius matching component

---

## 5. Component State Matrix

| Component | Default | Hover | Active/Pressed | Focus | Disabled | Loading | Error |
|-----------|---------|-------|---------------|-------|----------|---------|-------|
| **Button Blue CTA** | bg `#0071e3` | `filter: brightness(1.05)` | `filter: brightness(0.95)`, scale(0.99) | `2px solid #0071e3` ring, offset 2px | opacity 0.4, `not-allowed` | spinner `#ffffff` + text opacity 0.6 | — |
| **Button Dark CTA** | bg `#1d1d1f` | bg `#3a3a3c` | bg `#2a2a2d`, scale(0.99) | `2px solid #0071e3` ring, offset 2px | opacity 0.4, `not-allowed` | spinner `#ffffff` | — |
| **Pill Link CTA** | transparent, border + text `#0066cc` | opacity 0.8 | opacity 0.6, scale(0.98) | `2px solid #0071e3` ring, offset 2px | opacity 0.4, no pointer | — | — |
| **Pill Link CTA (dark)** | transparent, border + text `#2997ff` | opacity 0.8 | opacity 0.6 | `2px solid #0071e3` ring, offset 2px | opacity 0.4 | — | — |
| **Input Text** | border `rgba(0,0,0,0.16)` | border `rgba(0,0,0,0.32)` | — | `2px solid #0071e3` outline, offset 2px | bg `rgba(0,0,0,0.04)`, `not-allowed` | — | border `#ff3b30`, helper `#ff3b30` 12px below |
| **Checkbox** | border `rgba(0,0,0,0.32)` | border `#0071e3` | scale(0.96) | `2px solid #0071e3` ring | opacity 0.4 | — | border `#ff3b30` |
| **Card Product** | shadow none | shadow `rgba(0,0,0,0.22) 3px 5px 30px 0px`, translateY(-2px) | shadow `rgba(0,0,0,0.12) 2px 4px 16px 0px` | `2px solid #0071e3` ring | opacity 0.5 | skeleton shimmer | — |
| **Media Control** | bg `rgba(210,210,215,0.64)` | bg `rgba(210,210,215,0.8)` | scale(0.9), 150ms | `2px solid #0071e3` ring | opacity 0.4 | — | — |
| **Link** | color `#0066cc` | opacity 0.8, underline | color `#004499` | `2px solid #0071e3` ring | color `rgba(0,0,0,0.32)`, no pointer | — | — |
| **Link (dark bg)** | color `#2997ff` | opacity 0.8, underline | color `#007aff` | `2px solid #0071e3` ring | opacity 0.4 | — | — |
| **Tab** | color `rgba(0,0,0,0.48)` | color `rgba(0,0,0,0.8)` | color `#1d1d1f`, `2px solid #0071e3` indicator | `2px solid #0071e3` ring | opacity 0.4 | — | — |
| **Select** | border `rgba(0,0,0,0.16)` | border `rgba(0,0,0,0.32)` | — | `2px solid #0071e3` outline | opacity 0.5 | spinner | border `#ff3b30` |
| **Toggle** | track `rgba(0,0,0,0.16)` | track `rgba(0,0,0,0.24)` | — | `2px solid #0071e3` ring | opacity 0.4 | — | — |

### Focus Ring Standard
```css
outline: 2px solid #0071e3;
outline-offset: 2px;
```

### Disabled Pattern
```css
opacity: 0.4;
cursor: not-allowed;
pointer-events: none;
```

### Error Input Pattern
```css
outline: 2px solid #ff3b30;
outline-offset: 0;
/* Helper text */
color: #ff3b30;
font-size: 12px;
margin-top: 4px;
```

---

## 6. Layout & Spacing System

### Spacing Scale

| Token | Value | Tailwind Approx. | CSS Variable | Use |
|-------|-------|-----------------|-------------|-----|
| `space-0` | 0px | `p-0` | `--space-0` | Reset |
| `space-1` | 4px | `p-1` | `--space-1` | Tight inline, badge padding |
| `space-2` | 8px | `p-2` | `--space-2` | Icon gaps, pill CTA padding |
| `space-3` | 12px | `p-3` | `--space-3` | Card internal padding tight |
| `space-4` | 16px | `p-4` | `--space-4` | Input padding, component gap |
| `space-5` | 20px | `p-5` | `--space-5` | Section padding mobile |
| `space-6` | 24px | `p-6` | `--space-6` | Card base padding |
| `space-8` | 32px | `p-8` | `--space-8` | Section sub-gap |
| `space-10` | 40px | `p-10` | `--space-10` | Section gap mobile |
| `space-12` | 48px | `p-12` | `--space-12` | Section gap tablet |
| `space-16` | 64px | `p-16` | `--space-16` | Section gap desktop |
| `space-20` | 80px | `p-20` | `--space-20` | Hero section vertical padding |
| `space-24` | 96px | `p-24` | `--space-24` | Large section separation |
| `space-32` | 128px | `p-32` | `--space-32` | Full-bleed hero breathing room |

### Grid

| Property | Value | CSS Variable |
|----------|-------|-------------|
| Max content width | `980px` | `--grid-max-width` |
| Column count | 12 | `--grid-columns` |
| Gutter | `20px` | `--grid-gutter` |
| Margin (mobile small) | `16px` | `--grid-margin-xs` |
| Margin (mobile standard) | `20px` | `--grid-margin-sm` |
| Margin (tablet) | `32px` | `--grid-margin-md` |
| Margin (desktop) | `auto` (centered) | `--grid-margin-lg` |

> **The 980px max content width is sacred for a reason:** The pill CTA border-radius of 980px echoes this exact number. When a pill link sits within the content container, its border-radius matches the container width — the outer boundary of the page is encoded in the curvature of every "Learn more" button. This is deliberate systemic coherence: from the macro layout to the micro interaction, the same number governs proportion.

### Border Radius Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `radius-micro` | 5px | `--radius-micro` | Small UI affordances, image thumbnails |
| `radius-standard` | 8px | `--radius-standard` | Buttons, cards, inputs, dropdowns |
| `radius-comfortable` | 11px | `--radius-comfortable` | Search inputs, filter chips |
| `radius-large` | 12px | `--radius-large` | Panels, modals, media cards |
| `radius-pill` | 980px | `--radius-pill` | CTA links ("Learn more", "Shop") — THE sacred radius |
| `radius-circle` | 50% | `--radius-circle` | Media controls, carousel dots, avatars |

> **The 980px radius is not a typo.** Apple's pill CTAs use exactly 980px — a value large enough to guarantee a perfect semicircle on any button regardless of width, and numerically identical to the page's max content width. It is the most distinctive single detail in the Apple UI vocabulary.

---

## 7. Depth & Elevation

### Elevation Philosophy

Apple creates depth through three mechanisms, in priority order:
1. **Section color contrast** — the binary alternation of `#000000` and `#f5f5f7` sections generates the most visible depth in the system. No shadow can compete.
2. **The singular diffuse shadow** — `rgba(0,0,0,0.22) 3px 5px 30px 0px` — a large, soft, photographic shadow that mimics studio product lighting. Applied sparingly on hover or on floating elements.
3. **The glass nav effect** — `backdrop-filter: saturate(180%) blur(20px)` — blur-based elevation for the persistent navigation layer.

There are no multi-layer box-shadows. No colored shadows. No inset shadows. The design communicates elevation through layout contrast, not decoration.

### Shadow Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `shadow-none` | `none` | `--shadow-none` | Default for all cards and containers |
| `shadow-product` | `rgba(0,0,0,0.22) 3px 5px 30px 0px` | `--shadow-product` | THE only box-shadow in the system — hover on product cards, modals, dropdowns |
| `shadow-glass` | `backdrop-filter: saturate(180%) blur(20px)` | `--shadow-glass` | Nav bar — not a box-shadow, a filter |

> No other shadow values exist in the Apple system. When in doubt, the answer is `none`.

### Z-Index Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `z-base` | 0 | `--z-base` | Default content |
| `z-image-overlay` | 1 | `--z-image-overlay` | Caption overlays on product images |
| `z-dropdown` | 100 | `--z-dropdown` | Mega-menu dropdowns |
| `z-sticky` | 9999 | `--z-sticky` | The glass nav — always topmost |
| `z-overlay` | 10000 | `--z-overlay` | Modal backdrop |
| `z-modal` | 10001 | `--z-modal` | Modal content |
| `z-popover` | 10002 | `--z-popover` | Popovers, tooltips |
| `z-toast` | 10003 | `--z-toast` | Toast notifications |
| `z-top` | 10100 | `--z-top` | Skip-to-content, critical system overlays |

---

## 8. Motion & Animation System

Apple motion operates on a philosophical foundation: physics, not timing. The most celebrated Apple animations (the product reveal on scroll, the iPhone spin in a hero section) use spring physics that feels weight-bearing — as if the device has actual mass being moved by actual forces. Hover transitions are swift and confident. Page transitions are slow and cinematic. The distinction is never arbitrary — duration tracks the perceived complexity of the state change.

### Duration Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `duration-micro` | 150ms | `--duration-micro` | Hover state changes, focus rings, scale(0.9) on media controls |
| `duration-normal` | 250ms | `--duration-normal` | Button hover, pill link transitions, nav link opacity |
| `duration-moderate` | 400ms | `--duration-moderate` | Modal entry, dropdown open, carousel transitions |
| `duration-slow` | 800ms | `--duration-slow` | Page section transitions, element entry animations |
| `duration-hero` | 2000ms+ | `--duration-hero` | Hero product reveals, scroll-driven parallax entrances |

### Easing Functions

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `ease-apple` | `cubic-bezier(0.25, 0.1, 0.25, 1)` | `--ease-apple` | Apple's signature default easing — smooth, decisive, no overshoot |
| `ease-in-out` | `cubic-bezier(0.42, 0, 0.58, 1)` | `--ease-in-out` | Symmetrical element repositioning |
| `ease-out` | `cubic-bezier(0, 0, 0.2, 1)` | `--ease-out` | Elements entering view |
| `ease-in` | `cubic-bezier(0.4, 0, 1, 1)` | `--ease-in` | Elements exiting view |
| `ease-spring` | Spring physics via JS | `--ease-spring` | Hero product animations — cannot be expressed as CSS cubic-bezier; uses requestAnimationFrame or GSAP |

### Common Transitions

| Interaction | Property | Duration | Easing |
|------------|----------|----------|--------|
| Button hover | `filter (brightness)` | 250ms | ease-apple |
| Pill link hover | `opacity` | 250ms | ease-apple |
| Media control active | `transform: scale(0.9)` | 150ms | ease-apple |
| Card product hover | `transform, box-shadow` | 250ms | ease-out |
| Modal enter | `opacity, transform (scale 0.96→1)` | 400ms | ease-out |
| Modal exit | `opacity, transform (scale 1→0.96)` | 250ms | ease-in |
| Dropdown open | `opacity, transform (translateY -8px→0)` | 250ms | ease-out |
| Carousel slide | `transform (translateX)` | 400ms | ease-apple |
| Focus ring | `outline` | 150ms | ease-apple |
| Hero product reveal | `transform, opacity` via scroll | 2000ms+ | Spring physics |
| Glass nav on scroll | `backdrop-filter, background` | 300ms | ease-apple |
| Page section entrance | `opacity, translateY` | 800ms | ease-out |

### Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
  /* Disable parallax and scroll-driven product reveals */
  [data-hero-parallax] {
    transform: none !important;
    animation: none !important;
  }
}
```

---

## 9. Icon System

| Property | Value |
|----------|-------|
| Library | SF Symbols (system icons — Apple proprietary) |
| Default size | 20px (1x) / 40px (2x retina rendering) |
| Stroke width | Thin to Regular weight, matching surrounding text weight |
| Color | `currentColor` (inherits from parent text) |
| Style | Monochrome — no multicolor icons in UI context |

### Icon Sizes

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `icon-xs` | 12px | `--icon-xs` | Inline text, breadcrumb chevrons |
| `icon-sm` | 16px | `--icon-sm` | Navigation arrows, inline UI |
| `icon-md` | 20px | `--icon-md` | Standard UI: nav, cards, controls |
| `icon-lg` | 24px | `--icon-lg` | Feature callouts, section headers |
| `icon-xl` | 40px | `--icon-xl` | Hero accent marks, empty states |
| `icon-2xl` | 80px | `--icon-2xl` | App icon representations in App Store contexts |

### SF Symbols Usage Rules
- Always use monochrome rendering in UI contexts — multicolor mode only for product screenshots
- Match icon weight to surrounding text weight (SF Pro Text 400 → Regular symbol weight)
- The Apple logo mark is not an SF Symbol — it is a brand asset rendered at SVG quality, minimum 17px

---

## 10. Accessibility Contract

### Targets

| Criterion | Target | Standard |
|-----------|--------|----------|
| Color contrast (normal text) | 4.5:1 minimum | WCAG AA |
| Color contrast (large text ≥18px or bold ≥14px) | 3:1 minimum | WCAG AA |
| Color contrast (UI components) | 3:1 minimum | WCAG AA |
| Touch target size | 44x44px minimum | WCAG 2.5.8 |
| Focus indicator | 2px `#0071e3` ring, offset 2px | WCAG 2.4.7 |
| Motion | Respect `prefers-reduced-motion` | WCAG 2.3.3 |

### Known Contrast Edge Cases

| Element | Foreground | Background | Ratio | Required Action |
|---------|-----------|-----------|-------|----------------|
| Apple Blue on `#f5f5f7` | `#0071e3` | `#f5f5f7` | 4.5:1 | Exactly AA minimum — use 17px+ or weight 600. Never smaller. |
| Apple Blue on `#ffffff` | `#0071e3` | `#ffffff` | 4.6:1 | Passes AA — thin margin. Same rule: 17px+ or 600 weight. |
| Black 48% on `#f5f5f7` | `rgba(0,0,0,0.48)` ≈ `#808080` | `#f5f5f7` | 4.1:1 | Fails AA for normal text. Use only for decorative/tertiary roles, minimum 18px. |
| Bright Blue on white | `#2997ff` | `#ffffff` | 2.7:1 | FAIL — dark backgrounds only. Never use on `#f5f5f7` or `#ffffff`. |

### Focus Management

- All interactive elements have `outline: 2px solid #0071e3; outline-offset: 2px;`
- Focus order follows visual reading order — left-to-right, section by section
- Modal traps focus within dialog; Escape key closes
- Skip-to-content as first focusable element: `<a href="#main" class="sr-only focus:not-sr-only">`
- The glass nav receives focus when sticky and must have visible focus styles against its translucent background

### ARIA Patterns

| Component | Role | Key Attributes |
|-----------|------|---------------|
| Modal | `dialog` | `aria-modal="true"`, `aria-labelledby` |
| Mega-menu | `navigation` | `aria-expanded`, `aria-label` |
| Dropdown | `listbox` | `aria-expanded`, `aria-activedescendant` |
| Tabs | `tablist` / `tab` / `tabpanel` | `aria-selected`, `aria-controls` |
| Toast | `status` or `alert` | `role="alert"` for errors, `role="status"` for info |
| Toggle | `switch` | `aria-checked` |
| Tooltip | `tooltip` | `aria-describedby` on trigger |
| Carousel | `region` | `aria-label`, `aria-roledescription="carousel"` |
| Slide | — | `aria-roledescription="slide"`, `aria-label="Slide N of M"` |
| Media player | `region` | `aria-label="Video player"` |

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
| Carousel | `Arrow Left/Right` | Previous / Next |
| Carousel | `Home` / `End` | First / Last slide |
| Media control | `Space` | Play/Pause |
| Media scrubber | `Arrow Left/Right` | Seek ±5s |

---

## 11. Do's and Don'ts

### Do
1. **Use Apple Blue (`#0071e3`) exclusively as the singular accent** — every CTA, every focus ring, every active indicator. Its singular role is what makes it feel decisive rather than decorative.
2. **Alternate sections between `#000000` (hero) and `#f5f5f7` (editorial)** — the binary rhythm is the page's heartbeat. No pure white sections, no consecutive same-color sections without architectural justification.
3. **Enforce the 20px optical sizing boundary without exception** — SF Pro Display above 20px, SF Pro Text at 19px and below. Both directions are violations: Display at small sizes looks too loose, Text at large sizes looks too tight.
4. **Use the 980px pill radius on every "Learn more" and "Shop" link** — this is the most visually recognizable Apple UI detail. Its extreme curvature on small text creates an elegant organic quality that echoes the 980px content container width.
5. **Apply negative letter-spacing at every text size** — from -0.28px at 56px down to -0.08px at 10px. Universal tight tracking is Apple's typographic signature.
6. **Place product photography on solid color fields only** — `#000000` or `#f5f5f7`. Products never float on gradients, patterns, or competing visual noise.
7. **Maintain the glass nav `saturate(180%) blur(20px)`** — this backdrop filter is non-negotiable. It must appear on a dark translucent surface (`rgba(0,0,0,0.8)`) regardless of the underlying section color.
8. **Use the one shadow `rgba(0,0,0,0.22) 3px 5px 30px 0px` sparingly** — on product card hover, modals, dropdowns. Its restraint makes each use feel significant.
9. **Keep dark section surfaces in the five close gray variants** (`#272729`, `#262628`, `#28282a`, `#2a2a2d`, `#242426`) — never use generic `#333333` or similar — the specific values encode Apple's precise elevation language.
10. **Use spring physics for hero product animations** — CSS cubic-bezier is insufficient for Apple's product reveals. GSAP, Framer Motion spring configs, or `requestAnimationFrame` with actual spring integration is required.

### Don't
1. **Don't add any chromatic color beyond Apple Blue** — no secondary accent, no gradient hero colors, no colored icons. Adding a second hue breaks the singular-accent language that makes Apple Blue feel authoritative.
2. **Don't use pure white (`#ffffff`) as a section background** — Apple uses `#f5f5f7` for all "light" sections. The slight blue-gray tint at full-page scale prevents the sterility and harshness of pure white against black hero sections.
3. **Don't mix SF Pro Display and SF Pro Text at the wrong size** — placing SF Pro Display below 20px or SF Pro Text above 19px violates the optical sizing contract. The fonts are different optical masters, not stylistic variants.
4. **Don't use the 980px pill radius on rectangular UI elements** — it belongs exclusively on small CTA links ("Learn more", "Shop"). Applied to large buttons, cards, or containers it becomes absurd rather than iconic.
5. **Don't use positive letter-spacing on display headlines** — only `tile-heading` (28px) and `card-title` (21px) track positive, as a deliberate exception. All other display and body text tracks negative. Positive tracking on large text reads as amateurish in the SF Pro context.
6. **Don't apply multiple shadows or colored shadows** — the system has one shadow: `rgba(0,0,0,0.22) 3px 5px 30px 0px`. No additional layer, no colored tint, no inset variant. Deviation introduces visual noise foreign to the Apple language.
7. **Don't use `#2997ff` (Bright Blue) on light backgrounds** — it is specifically engineered for dark backgrounds only (2.7:1 on white — fails AA). On light sections, `#0066cc` is the correct link color.
8. **Don't animate with spring/bounce easings on UI micro-interactions** — spring physics belongs to hero product reveals (2s+ duration). For button hovers, focus rings, and UI transitions, use `cubic-bezier(0.25, 0.1, 0.25, 1)`. Spring + 250ms = overshoot that feels wrong.
9. **Don't use weight 800 or 900 at any size** — Apple's display range is 300-700. The SF Pro system is calibrated for this weight range. Weight 800+ creates uncharacteristic optical expansion that Apple has never used on apple.com.
10. **Don't make the glass nav opaque or non-sticky** — the `rgba(0,0,0,0.8) + backdrop-filter` combination is identity-defining. A solid opaque nav or a nav that scrolls away destroys the spatial relationship Apple has built between persistent chrome and full-bleed content sections.

---

## 12. Responsive Behavior

### Breakpoints (Apple's 8-Breakpoint System)

Apple uses the most granular breakpoint system in commercial web design. Each breakpoint corresponds to a specific device or viewport class, and typography + layout shift at each. This level of granularity is why Apple's site feels pixel-correct on every device.

| Token | Width | CSS | Key Changes at This Breakpoint |
|-------|-------|-----|-------------------------------|
| `nano` | <360px | `@media (max-width: 359px)` | Ultra-compact: nav collapses fully, hero text to 28px, single-column only, max padding 12px |
| `xs` | 360–480px | `@media (min-width: 360px)` | Mobile small: hamburger nav, hero headline 32–36px, 16px side margins, 1-col layout |
| `sm` | 480–640px | `@media (min-width: 480px)` | Mobile large: hero headline 40px, margins expand to 20px, CTA buttons full-width |
| `md` | 640–834px | `@media (min-width: 640px)` | Mobile landscape / small tablet: 2-col product grid begins, 28px side margins |
| `lg` | 834–1024px | `@media (min-width: 834px)` | iPad: full nav visible, hero headline 48px, 3-col product grids possible, 40px margins |
| `xl` | 1024–1070px | `@media (min-width: 1024px)` | Pre-desktop: full nav + all nav items visible, hero 48–52px, content width approaching 980px max |
| `2xl` | 1070–1440px | `@media (min-width: 1070px)` | Desktop: 980px max content width locked, hero headline 56px, side margins auto-centering |
| `3xl` | >1440px | `@media (min-width: 1440px)` | Large display: section hero sections expand to 100vw, content constrained to 980px, generous breathing room |

> Apple targets specific Apple device viewports (375px iPhone SE, 390px iPhone 15, 428px iPhone 15 Plus, 744px iPad mini, 834px iPad Air, 1024px iPad Pro) — hence the unusual 834px and 1070px breakpoints rather than standard 768px/1024px/1280px.

### Responsive Type Scale

| Token | Mobile <640px | Tablet 640–1024px | Desktop 1024px+ |
|-------|--------------|------------------|----------------|
| `display-hero` | 32px | 48px | 56px |
| `section-heading` | 28px | 36px | 40px |
| `tile-heading` | 21px | 24px | 28px |
| `card-title` | 17px | 19px | 21px |
| `body` | 17px | 17px | 17px |
| `caption` | 12px | 14px | 14px |

### Layout Shifts

| Component | Mobile (<640px) | Tablet (640–1024px) | Desktop (1024px+) |
|-----------|----------------|--------------------|--------------------|
| Nav | Hamburger → full-screen overlay | Hamburger → overlay (same) | Full 12-item horizontal glass nav |
| Product Hero | Stacked: image above text, padding 20px, text 32px | Image 60vh hero with text below, padding 40px, text 48px | Full-viewport bleed, text overlay centered, 56px |
| Product Grid | 1 column full-width | 2 columns within 980px max | 2–3 columns within 980px max |
| Comparison Table | Scroll-horizontal, 1 product visible | 2 products side-by-side | 3–4 products side-by-side, full table |
| Footer | Stacked accordion sections | 2×2 grid | 4-column horizontal grid |
| Pill CTAs | Full width stacked | Side-by-side centered | Side-by-side centered |
| Section alternation | Binary rhythm maintained — never broken | Binary rhythm maintained | Binary rhythm maintained |

### Touch Targets
- Minimum size: 44x44px for all interactive elements (WCAG 2.5.8 + Apple HIG)
- Minimum gap between adjacent targets: 8px
- Mobile CTA buttons: full width, 48px minimum height
- Nav hamburger: exactly 44x44px touch area
- Media control buttons: exactly 44x44px regardless of icon size
- Pill CTA links: minimum 44px height via `min-height: 44px` on small screens

---

## 13. Code Snippets

### Primary Blue CTA Button (JSX + Tailwind)

```jsx
<button
  className="
    inline-flex items-center justify-center
    bg-[#0071e3] text-white
    px-[15px] py-[8px]
    rounded-[8px]
    border border-transparent
    text-[17px] font-normal leading-[2.41]
    transition-[filter]
    duration-[250ms]
    [transition-timing-function:cubic-bezier(0.25,0.1,0.25,1)]
    hover:brightness-105
    active:brightness-95 active:scale-[0.99]
    focus:outline focus:outline-2 focus:outline-[#0071e3] focus:outline-offset-2
    disabled:opacity-40 disabled:cursor-not-allowed
  "
  style={{ fontFamily: "'SF Pro Text', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif" }}
>
  Buy
</button>
```

### Pill Link CTA — "Learn more" / "Shop" (JSX + Tailwind)

```jsx
// The sacred 980px radius — Apple's most recognizable micro-detail
// On light background: #0066cc text + border
// On dark background: #2997ff text + border
<a
  href="#"
  className="
    inline-flex items-center gap-[3px]
    bg-transparent text-[#0066cc]
    border border-[#0066cc]
    px-[8px] py-[3px]
    rounded-[980px]
    text-[14px] font-normal leading-[1.43] tracking-[-0.224px]
    transition-opacity duration-[250ms]
    [transition-timing-function:cubic-bezier(0.25,0.1,0.25,1)]
    hover:opacity-80
    focus:outline focus:outline-2 focus:outline-[#0071e3] focus:outline-offset-2
  "
  style={{ fontFamily: "'SF Pro Text', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif" }}
>
  Learn more
  <span aria-hidden="true">›</span>
</a>
```

### Product Hero Section — Full Viewport (JSX + Tailwind)

```jsx
// Binary rhythm: this is the black hero section
// Alternate with #f5f5f7 section above and below
<section className="bg-black min-h-screen flex flex-col items-center justify-center text-center px-5 py-[80px]">
  {/* Eyebrow label */}
  <p
    className="text-[#f5f5f7] text-[17px] font-normal leading-[1.47] tracking-[-0.374px] mb-3"
    style={{ fontFamily: "'SF Pro Text', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif" }}
  >
    iPhone 16 Pro
  </p>

  {/* Display hero headline — SF Pro Display at 56px */}
  <h1
    className="text-white text-[56px] font-semibold leading-[1.07] tracking-[-0.28px] mb-4 max-w-[980px]"
    style={{ fontFamily: "'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif" }}
  >
    Hello, Apple Intelligence.
  </h1>

  {/* Pill CTA pair — the Apple signature */}
  <div className="flex flex-wrap gap-[12px] items-center justify-center mt-6">
    {/* Learn more pill — dark section uses #2997ff */}
    <a
      href="#"
      className="inline-flex items-center gap-[3px] bg-transparent text-[#2997ff] border border-[#2997ff] px-[8px] py-[3px] rounded-[980px] text-[17px] leading-[1.47] tracking-[-0.374px] hover:opacity-80 transition-opacity duration-[250ms] focus:outline focus:outline-2 focus:outline-[#0071e3] focus:outline-offset-2"
      style={{ fontFamily: "'SF Pro Text', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif" }}
    >
      Learn more ›
    </a>
    {/* Shop pill */}
    <a
      href="#"
      className="inline-flex items-center gap-[3px] bg-[#0071e3] text-white border border-transparent px-[15px] py-[8px] rounded-[8px] text-[17px] leading-[1.47] tracking-[-0.374px] hover:brightness-105 transition-[filter] duration-[250ms] focus:outline focus:outline-2 focus:outline-[#0071e3] focus:outline-offset-2"
      style={{ fontFamily: "'SF Pro Text', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif" }}
    >
      Shop ›
    </a>
  </div>

  {/* Product image — on solid black field, never on gradient */}
  <img
    src="/images/iphone-16-pro.png"
    alt="iPhone 16 Pro in Natural Titanium"
    className="mt-12 max-w-[600px] w-full"
  />
</section>
```

### Glass Navigation Bar (JSX + Tailwind)

```jsx
// THE Apple glass signature — rgba(0,0,0,0.8) + saturate(180%) blur(20px)
// Always 48px height. Always sticky top-0. Always z-[9999].
<header
  className="sticky top-0 z-[9999] h-[48px] flex items-center"
  style={{ background: 'rgba(0,0,0,0.8)', backdropFilter: 'saturate(180%) blur(20px)' }}
>
  <nav className="w-full max-w-[980px] mx-auto px-5 flex items-center justify-between">
    {/* Apple logo — 17px wide, SVG, white */}
    <a href="/" aria-label="Apple" className="flex-shrink-0 focus:outline focus:outline-2 focus:outline-[#0071e3] focus:outline-offset-2">
      <svg width="17" height="48" viewBox="0 0 17 48" fill="white" aria-hidden="true">
        {/* Apple logo SVG path */}
      </svg>
    </a>

    {/* Nav links */}
    <ul className="hidden lg:flex items-center gap-6">
      {['Store', 'Mac', 'iPad', 'iPhone', 'Watch', 'Vision', 'AirPods', 'TV & Home', 'Entertainment', 'Accessories', 'Support'].map(item => (
        <li key={item}>
          <a
            href="#"
            className="text-[#f5f5f7] text-[12px] font-normal leading-[1.33] tracking-[-0.12px] hover:opacity-80 transition-opacity duration-[250ms] focus:outline focus:outline-2 focus:outline-[#0071e3] focus:outline-offset-2"
            style={{ fontFamily: "'SF Pro Text', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif" }}
          >
            {item}
          </a>
        </li>
      ))}
    </ul>

    {/* Search + Bag icons */}
    <div className="flex items-center gap-4">
      <button className="text-[#f5f5f7] w-[44px] h-[44px] flex items-center justify-center hover:opacity-80 focus:outline focus:outline-2 focus:outline-[#0071e3]" aria-label="Search">
        {/* Search icon SVG */}
      </button>
      <button className="text-[#f5f5f7] w-[44px] h-[44px] flex items-center justify-center hover:opacity-80 focus:outline focus:outline-2 focus:outline-[#0071e3]" aria-label="Shopping Bag">
        {/* Bag icon SVG */}
      </button>
      {/* Mobile hamburger */}
      <button className="lg:hidden text-[#f5f5f7] w-[44px] h-[44px] flex items-center justify-center" aria-label="Menu">
        {/* Hamburger icon SVG */}
      </button>
    </div>
  </nav>
</header>
```

### CSS Custom Properties (Root)

```css
:root {
  /* Apple Brand Colors */
  --apple-blue: #0071e3;
  --apple-link-light: #0066cc;
  --apple-link-dark: #2997ff;

  /* Section Backgrounds */
  --color-bg-primary: #f5f5f7;      /* Light section — NOT pure white */
  --color-bg-hero: #000000;         /* Dark/immersive section */
  --color-bg-white: #ffffff;        /* Card surfaces, modals */
  --color-bg-button-default: #fafafc;
  --color-bg-button-active: #ededf2;

  /* Dark Surface Elevation (5 close variants) */
  --color-bg-surface-1: #272729;
  --color-bg-surface-2: #262628;
  --color-bg-surface-3: #28282a;
  --color-bg-surface-4: #2a2a2d;
  --color-bg-surface-5: #242426;

  /* Text Colors */
  --color-text-primary: #1d1d1f;
  --color-text-secondary: rgba(0, 0, 0, 0.8);
  --color-text-tertiary: rgba(0, 0, 0, 0.48);
  --color-text-on-dark: #f5f5f7;

  /* Accent */
  --color-accent-primary: #0071e3;
  --color-accent-link-light: #0066cc;
  --color-accent-link-dark: #2997ff;

  /* Overlays */
  --color-overlay-dark: rgba(0, 0, 0, 0.8);
  --color-overlay-media: rgba(210, 210, 215, 0.64);
  --color-modal-close-hover: rgba(255, 255, 255, 0.32);

  /* Status */
  --color-status-success: #28cd41;
  --color-status-warning: #ff9f0a;
  --color-status-error: #ff3b30;
  --color-status-info: #0071e3;

  /* Typography — Optical Sizing Boundary at 20px */
  --font-display: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif;
  --font-body: 'SF Pro Text', 'SF Pro Icons', 'Helvetica Neue', Helvetica, Arial, sans-serif;

  /* Type sizes */
  --text-display-hero: 56px;       /* SF Pro Display — ABOVE 20px */
  --text-section-heading: 40px;
  --text-tile-heading: 28px;
  --text-card-title: 21px;
  --text-sub-heading: 21px;
  --text-nav-heading: 34px;        /* SF Pro Text — boundary zone */
  --text-sub-nav: 24px;
  --text-body: 17px;               /* SF Pro Text — BELOW 20px */
  --text-button: 17px;
  --text-button-lg: 18px;
  --text-link: 14px;
  --text-caption: 14px;
  --text-micro: 12px;
  --text-nano: 10px;

  /* Spacing */
  --space-1: 4px;   --space-2: 8px;   --space-3: 12px;
  --space-4: 16px;  --space-5: 20px;  --space-6: 24px;
  --space-8: 32px;  --space-10: 40px; --space-12: 48px;
  --space-16: 64px; --space-20: 80px; --space-24: 96px;
  --space-32: 128px;

  /* Grid */
  --grid-max-width: 980px;          /* Sacred — echoed in --radius-pill */
  --grid-columns: 12;
  --grid-gutter: 20px;

  /* Border Radius */
  --radius-micro: 5px;
  --radius-standard: 8px;          /* Buttons, cards, inputs */
  --radius-comfortable: 11px;      /* Search, filter chips */
  --radius-large: 12px;            /* Modals, media cards */
  --radius-pill: 980px;            /* SACRED — CTA links, echoes max content width */
  --radius-circle: 50%;            /* Media controls */

  /* The ONE Shadow */
  --shadow-product: rgba(0, 0, 0, 0.22) 3px 5px 30px 0px;

  /* Motion */
  --duration-micro: 150ms;
  --duration-normal: 250ms;
  --duration-moderate: 400ms;
  --duration-slow: 800ms;
  --ease-apple: cubic-bezier(0.25, 0.1, 0.25, 1);
  --ease-in-out: cubic-bezier(0.42, 0, 0.58, 1);
  --ease-out: cubic-bezier(0, 0, 0.2, 1);
  --ease-in: cubic-bezier(0.4, 0, 1, 1);

  /* Z-Index */
  --z-base: 0;
  --z-image-overlay: 1;
  --z-dropdown: 100;
  --z-sticky: 9999;
  --z-overlay: 10000;
  --z-modal: 10001;
  --z-popover: 10002;
  --z-toast: 10003;
  --z-top: 10100;
}

/* Dark section context — applies inside .section-dark or hero sections */
.section-dark,
[data-section="hero"] {
  --color-bg-primary: #000000;
  --color-text-primary: #f5f5f7;
  --color-text-secondary: rgba(255, 255, 255, 0.8);
  --color-text-tertiary: rgba(255, 255, 255, 0.48);
  --color-accent-link: #2997ff;
  --color-border-default: rgba(255, 255, 255, 0.16);
}
```

### Tailwind Config Extension

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        apple: {
          blue: '#0071e3',
          'link-light': '#0066cc',
          'link-dark': '#2997ff',
          'near-black': '#1d1d1f',
          'light-gray': '#f5f5f7',
          black: '#000000',
          white: '#ffffff',
          'button-default': '#fafafc',
          'button-active': '#ededf2',
          // Dark surfaces (5 close variants — each encodes specific elevation)
          'surface-1': '#272729',
          'surface-2': '#262628',
          'surface-3': '#28282a',
          'surface-4': '#2a2a2d',
          'surface-5': '#242426',
        },
        status: {
          success: '#28cd41',
          warning: '#ff9f0a',
          error: '#ff3b30',
        }
      },
      fontFamily: {
        // Use based on font-size: display for 20px+, body for 19px and below
        display: ["'SF Pro Display'", "'SF Pro Icons'", "'Helvetica Neue'", 'Helvetica', 'Arial', 'sans-serif'],
        body: ["'SF Pro Text'", "'SF Pro Icons'", "'Helvetica Neue'", 'Helvetica', 'Arial', 'sans-serif'],
      },
      borderRadius: {
        'micro': '5px',
        'standard': '8px',
        'comfortable': '11px',
        'large-panel': '12px',
        'pill': '980px',          // The sacred Apple radius — do NOT change
      },
      boxShadow: {
        'product': 'rgba(0,0,0,0.22) 3px 5px 30px 0px',  // The ONE shadow in the system
        'none': 'none',
      },
      letterSpacing: {
        'display': '-0.28px',
        'body': '-0.374px',
        'caption': '-0.224px',
        'micro': '-0.12px',
        'nano': '-0.08px',
        'tile': '0.196px',    // Positive — tile-heading exception
        'card': '0.231px',    // Positive — card-title exception
      },
      transitionTimingFunction: {
        'apple': 'cubic-bezier(0.25, 0.1, 0.25, 1)',
        'apple-in-out': 'cubic-bezier(0.42, 0, 0.58, 1)',
      },
      maxWidth: {
        'apple': '980px',           // Max content width — also the pill radius origin
      },
    }
  }
}
```

---

## 14. Agent Prompt Guide

### Quick Reference

| Element | Value |
|---------|-------|
| The singular accent color | `#0071e3` (Apple Blue) — CTAs, focus states only |
| Light section background | `#f5f5f7` — never pure `#ffffff` |
| Dark/hero section background | `#000000` |
| Card surface | `#ffffff` |
| Primary text (light sections) | `#1d1d1f` |
| Secondary text (light) | `rgba(0,0,0,0.8)` |
| Tertiary text / disabled | `rgba(0,0,0,0.48)` |
| Link color (light bg) | `#0066cc` |
| Link color (dark bg) | `#2997ff` |
| Display font (20px+) | `SF Pro Display` |
| Body font (19px and below) | `SF Pro Text` |
| Button CTA radius | `8px` |
| Pill link radius | `980px` (sacred) |
| Modal radius | `12px` |
| The one shadow | `rgba(0,0,0,0.22) 3px 5px 30px 0px` |
| Glass nav | `background: rgba(0,0,0,0.8); backdrop-filter: saturate(180%) blur(20px)` |
| Focus ring | `2px solid #0071e3, offset 2px` |
| Max content width | `980px` |
| Hero headline size | `56px / 600 / 1.07 / -0.28px / SF Pro Display` |

### Example Prompts

1. **Hero section (dark) with product reveal:** "Create a full-viewport hero section with background `#000000`. Centered content within 980px max-width. Eyebrow text: SF Pro Text 17px / 400 / `#f5f5f7` / line-height 1.47 / -0.374px tracking. Headline: 'Hello, Apple Intelligence.' — SF Pro Display 56px / 600 / line-height 1.07 / -0.28px / white. Below: two pill CTAs side-by-side: 'Learn more ›' (transparent bg, `#2997ff` text and border, 980px radius, 14px SF Pro Text) and 'Shop ›' (bg `#0071e3`, white text, 8px radius). Product PNG below on the black field — no gradient, just the product floating on void. Entire section 100vh minimum."

2. **Alternating light editorial section:** "Build a section with background `#f5f5f7`. 980px max-width centered. Section heading: SF Pro Display 40px / 600 / 1.10 / normal tracking / `#1d1d1f`. Body copy: SF Pro Text 17px / 400 / 1.47 / -0.374px / `#1d1d1f`. Below: 3-column product card grid. Each card: bg `#f5f5f7`, 8px radius, no border, product PNG centered on solid field, 21px / 700 / 0.231px card title in `#1d1d1f`, 'Learn more ›' pill link (`#0066cc`, 980px radius, 14px SF Pro Text). Hover: card shadow `rgba(0,0,0,0.22) 3px 5px 30px 0px`, translateY(-2px), 250ms ease-apple."

3. **Glass nav bar:** "Sticky nav at top-0, height 48px, z-index 9999. Background: `rgba(0,0,0,0.8)`. Backdrop-filter: `saturate(180%) blur(20px)`. White Apple SVG logo 17x48px centered. Nav links: SF Pro Text 12px / 400 / `#f5f5f7` / -0.12px / gap 24px. Right: search icon + bag icon, each 44x44px touch targets, `#f5f5f7`. Mobile: hide links, show hamburger 44x44px. All hover: opacity 0.8 / 250ms ease-apple. Focus: `2px solid #0071e3` outline offset 2px."

4. **Filter/search bar:** "Build a search input: background `#fafafc`, 11px radius, 3px border solid `rgba(0,0,0,0.04)`, 32px height, 0 14px padding, SF Pro Text 14px / 400 / -0.224px / `rgba(0,0,0,0.8)`. Placeholder: 'Search apple.com' in `rgba(0,0,0,0.48)`. Focus: `2px solid #0071e3` outline offset 2px. Transition: `border-color 250ms cubic-bezier(0.25,0.1,0.25,1)`."

5. **Product comparison table (spec sheet):** "Build a 3-column product comparison table on `#f5f5f7` section background. Header row: product names in SF Pro Display 21px / 700 / 0.231px / `#1d1d1f`. Feature rows: SF Pro Text 14px / 400 / -0.224px / `#1d1d1f`. Checkmarks in `#0071e3`. Row separator: 1px `rgba(0,0,0,0.08)`. Hover row: bg `rgba(0,0,0,0.04)`. Buy button per column: bg `#0071e3`, white text, 8px radius, 8px 15px padding. Mobile: horizontal scroll, 1 product visible at a time."

### Pre-flight Checklist for Generated UI

1. Apple Blue `#0071e3` is the ONLY chromatic accent in the viewport — no secondary hues
2. Light section backgrounds are `#f5f5f7` — never pure `#ffffff`
3. Section rhythm alternates `#000000` hero and `#f5f5f7` editorial — never two consecutive same-color
4. SF Pro Display is used at 20px and above ONLY — SF Pro Text at 19px and below ONLY
5. All text has negative letter-spacing (except tile-heading +0.196px and card-title +0.231px)
6. Pill link CTAs use exactly `border-radius: 980px` — not `9999px`, not `999px`, not `rounded-full`
7. Glass nav has `background: rgba(0,0,0,0.8)` AND `backdrop-filter: saturate(180%) blur(20px)` — both required
8. The one shadow is `rgba(0,0,0,0.22) 3px 5px 30px 0px` — no other box-shadow exists
9. Link color on dark is `#2997ff` — never `#0066cc` on dark backgrounds (fails AA at 2.7:1)
10. Touch targets are minimum 44x44px on mobile — verify with all padding applied
11. `prefers-reduced-motion`: transitions drop to 0.01ms, scroll-driven parallax disabled
12. Product imagery placed on solid color fields only (`#000000` or `#f5f5f7`) — never on gradients
13. Focus ring is `2px solid #0071e3` with `outline-offset: 2px` — consistent across light and dark
14. Weight 300 only on `button-lg` decorative text. Weight 700 only on `card-title`. No weight 800+.
