# Design System: Ferrari (ferrari.com)

## 1. Visual Theme & Atmosphere

Ferrari's digital presence is not a website — it is a curated gallery. Every section is a vignette, framed by void-black or bone-white, where a single photograph breathes in absolute silence before the next composition appears. The rhythm is cinematic: the page does not scroll through content, it turns pages. A black section gives way to a white section gives way to black again — the chiaroscuro pulse of alternating darkness and light that has defined Ferrari's editorial identity since the Prancing Horse first appeared on paper.

Color is wielded with monastic restraint. Rosso Corsa (`#DA291C`) — the most famous automotive red in existence — is treated not as a palette color but as a sacred element. It appears once per screen, maximum: on the Subscribe CTA, and nowhere else. This scarcity is the point. When Ferrari Red appears, it is an event. The rest of the interface lives in near-black, pure white, and three tones of gray, communicating through contrast and negative space rather than through decoration. Racing Yellow (`#FFF200`) surfaces only in motorsport heritage contexts, as a period-correct nod to the Giallo Modena that appeared on Scuderia vehicles. It never competes with the red — it defers to it.

Typography is FerrariSans, a proprietary typeface that carries the DNA of the brand even before any content is read. At weight 500 by default — neither bold nor light — it occupies a confident, measured register. Body-Font, the secondary face for captions and labels, is consistently set uppercase with 1px letter-spacing, creating the precise, instrumental cadence of a technical specification sheet. Together, these two typefaces communicate: this is not a consumer brand. This is an atelier automobilistico.

**Key Characteristics:**
- Chiaroscuro alternating sections: void-black cinematic / bone-white editorial, "page-turn" magazine cadence
- Ferrari Red used with extreme sparseness — MAX 1 red element visible per screen, Subscribe CTA only
- FerrariSans proprietary typeface at weight 500 default — measured, authoritative, never shouting
- Zero shadows on UI components — depth comes from surface color contrast, not elevation tricks
- Razor-precision border radius: 2px default for buttons/inputs, 8px only for modal dialogs
- Gallery-wall whitespace: sections breathe like framed photographs, never crowded
- Prancing Horse logo isolated on void-black, never placed on texture or color
- Racing Yellow restricted to motorsport heritage contexts only, never mixed with Rosso Corsa on the same element

---

## 2. Color System & Tokens

### Light Theme

| Token | Name | Hex | Role | CSS Variable |
|-------|------|-----|------|-------------|
| `bg-primary` | Pure White | `#FFFFFF` | Editorial canvas — main page background | `--color-bg-primary` |
| `bg-secondary` | Dark Surface | `#303030` | Footer, newsletter strip, secondary dark sections | `--color-bg-secondary` |
| `bg-tertiary` | Light Gray Surface | `#D2D2D2` | Dividers, subtle rule lines | `--color-bg-tertiary` |
| `bg-cinematic` | Absolute Black | `#000000` | Cinematic sections, Prancing Horse isolation, hero voids | `--color-bg-cinematic` |
| `text-primary` | Near Black | `#181818` | Body text on white — avoids hard black harshness | `--color-text-primary` |
| `text-secondary` | Dark Gray | `#666666` | Secondary text, sub-headings on light | `--color-text-secondary` |
| `text-tertiary` | Mid Gray | `#8F8F8F` | Tertiary text, metadata — FLAGGED (see contrast note) | `--color-text-tertiary` |
| `text-disabled` | Silver Gray | `#969696` | Placeholders, disabled states — placeholder ONLY | `--color-text-disabled` |
| `text-on-dark` | Pure White | `#FFFFFF` | All text on black/dark sections | `--color-text-on-dark` |
| `accent-primary` | Ferrari Red | `#DA291C` | Subscribe CTA ONLY — 1 element max per screen | `--color-accent-primary` |
| `accent-hover` | Dark Red | `#B01E0A` | Hover on Ferrari Red elements | `--color-accent-hover` |
| `accent-active` | Deep Red | `#9D2211` | Active/pressed state on Ferrari Red | `--color-accent-active` |
| `accent-heritage` | Racing Yellow | `#FFF200` | Heritage motorsport context ONLY | `--color-accent-heritage` |
| `accent-heritage-2` | Modena Yellow | `#F6E500` | Secondary heritage accent, Scuderia context | `--color-accent-heritage-2` |
| `interactive-hover` | Button Hover Teal | `#1EAEDB` | White button bg on hover — transition destination | `--color-interactive-hover` |
| `interactive-link` | Link Hover Blue | `#3860BE` | Interactive links on hover — not a brand color | `--color-interactive-link` |
| `border-default` | Border | `#CCCCCC` | Input borders, dividers, hairlines | `--color-border-default` |
| `border-light` | Light Gray Surface | `#D2D2D2` | Section dividers, subtle rule lines | `--color-border-light` |
| `status-error` | Warning Red | `#F13A2C` | Semantic error — visually distinct from brand red | `--color-status-error` |
| `status-success` | Success | `#03904A` | Form validation success | `--color-status-success` |
| `status-info` | Info Blue | `#4C98B9` | Informational messages | `--color-status-info` |
| `overlay` | Image Overlay | `hsla(0,0%,7%,0.8)` | Image captions, modal backdrops, cinematic overlays | `--color-overlay` |

### Dark Theme (Cinematic Sections)

Ferrari does not have a traditional dark mode toggle — the dark palette is used structurally for alternating cinematic sections on the same page. These tokens apply inside `.section-cinematic` or `[data-theme="dark"]` containers.

| Token | Hex (Dark) | Maps to Light Role | CSS Variable |
|-------|-----------|-------------------|-------------|
| `bg-primary` | `#000000` | White canvas | `--color-bg-primary` |
| `bg-secondary` | `#181818` | Section surface | `--color-bg-secondary` |
| `bg-tertiary` | `#303030` | Nested dark surface | `--color-bg-tertiary` |
| `text-primary` | `#FFFFFF` | Body text | `--color-text-primary` |
| `text-secondary` | `#8F8F8F` | Secondary text | `--color-text-secondary` |
| `text-tertiary` | `#666666` | Metadata | `--color-text-tertiary` |
| `text-disabled` | `#969696` | Placeholder | `--color-text-disabled` |
| `accent-primary` | `#DA291C` | Ferrari Red (same — brand is absolute) | `--color-accent-primary` |
| `border-default` | `rgba(255,255,255,0.15)` | Dividers on dark | `--color-border-default` |
| `overlay` | `hsla(0,0%,7%,0.8)` | Overlay | `--color-overlay` |

### Contrast Ratios (WCAG AA)

| Pair | Foreground | Background | Ratio | Pass AA | Pass AAA |
|------|-----------|-----------|-------|---------|----------|
| Body text (light) | `#181818` | `#FFFFFF` | 16.1:1 | Yes | Yes |
| Heading on white | `#000000` | `#FFFFFF` | 21:1 | Yes | Yes |
| Secondary text | `#666666` | `#FFFFFF` | 5.7:1 | Yes | No |
| White on Ferrari Red | `#FFFFFF` | `#DA291C` | 4.9:1 | Yes (large text / bold) | No |
| Body on dark | `#FFFFFF` | `#000000` | 21:1 | Yes | Yes |
| Teal hover on white text | `#FFFFFF` | `#1EAEDB` | 3.2:1 | Yes (large text / UI) | No |
| Link Blue on white | `#3860BE` | `#FFFFFF` | 5.2:1 | Yes | No |
| **Mid Gray FAIL** | `#8F8F8F` | `#FFFFFF` | **3.5:1** | **FAIL for <18px normal text** | No |
| Mid Gray (large text) | `#8F8F8F` | `#FFFFFF` | 3.5:1 | Yes (>=18px or bold 14px+) | No |
| Silver Gray FAIL | `#969696` | `#FFFFFF` | 2.7:1 | **FAIL — placeholder/decorative only** | No |

> **Contrast Warning — Mid Gray:** `#8F8F8F` on `#FFFFFF` is 3.5:1 — fails WCAG AA for normal text below 18px. Use ONLY for metadata text at 18px+ regular or 14px+ bold. Never use for body copy. Flag any instance of Body-Font uppercase labels in `#8F8F8F` at sizes below 18px as a known accepted tradeoff (captions at 12-13px are purely decorative/supplemental).

> **Ferrari Red note:** White on `#DA291C` is 4.9:1 — passes AA for large text (18px+). The Subscribe button at 16px/400 is borderline; use `font-weight: 700` or 18px to ensure clear AA passage.

> **Silver Gray note:** `#969696` at 2.7:1 is approved ONLY as input placeholder color. It must never carry any meaningful or required content.

### Gradients

Ferrari avoids gradients on UI components. The following exist for cinematic overlays only.

| Name | Value | Use |
|------|-------|-----|
| `overlay-caption` | `linear-gradient(to top, hsla(0,0%,7%,0.8) 0%, transparent 60%)` | Image caption overlays on cinematic cards |
| `overlay-hero` | `linear-gradient(180deg, transparent 40%, hsla(0,0%,7%,0.7) 100%)` | Full-bleed hero text legibility layer |

---

## 3. Typography System

### Font Stack

| Role | Family | Fallbacks | CSS Variable |
|------|--------|-----------|-------------|
| Primary | `FerrariSans` | `Arial, Helvetica, sans-serif` | `--font-primary` |
| Secondary (captions/labels) | `Body-Font` | `Arial, Helvetica, sans-serif` | `--font-secondary` |
| Mono | Not used in Ferrari UI | — | — |

**OpenType Features:** None required — FerrariSans is pre-optimized. Do not override `font-feature-settings`. Apply `letter-spacing` manually per token as specified in the type scale below.

### Type Scale

| Token | Size | Weight | Line Height | Letter Spacing | Fluid (clamp) | CSS Variable |
|-------|------|--------|-------------|----------------|---------------|-------------|
| `section-title` | 26px | 500 | 1.2 | 0px | `clamp(20px, 2.2vw, 26px)` | `--text-section-title` |
| `card-heading` | 24px | 400 | 1.25 | 0px | `clamp(18px, 2vw, 24px)` | `--text-card-heading` |
| `subheading` | 18px | 700 | 1.3 | 0px | `clamp(16px, 1.5vw, 18px)` | `--text-subheading` |
| `ui-heading` | 16px | 500 | 1.4 | 0.08px | — | `--text-ui-heading` |
| `body-bold` | 16px | 700 | 1.5 | 0px | — | `--text-body-bold` |
| `button-label` | 16px | 400 | 1.0 | 1.28px | — | `--text-button-label` |
| `small-button` | 14.4px | 700 | 1.0 | 0px | — | `--text-small-button` |
| `nav-link` | 13px | 600 | 1.0 | 0.13px | — | `--text-nav-link` |
| `caption` | 13px | 400 | 1.4 | 0.195px | — | `--text-caption` |
| `micro-button` | 12px | 700 | 1.0 | 0.96px | — | `--text-micro-button` |
| `label-upper` | 12px | 400 | 1.2 | 1px | — | `--text-label-upper` |
| `micro-label` | 11px | 400 | 1.2 | 1px | — | `--text-micro-label` |
| `cookie-consent` | 45px | 400 | 1.1 | 0px | — | `--text-cookie-consent` |

> Note: `Body-Font` captions and labels use `text-transform: uppercase` with 1px letter-spacing as standard. This is part of the visual system — do not override to sentence case or title case.

### Typography Principles
- **Weight 500 as default voice**: FerrariSans at 500 is the Ferrari speaking tone — measured, precise, never casual nor aggressive. Reserve 700 for subheadings and small UI labels only.
- **Tracking as craftsmanship signal**: Button labels at 1.28px, nav links at 0.13px, micro-labels at 1px — each spacing value is engineered to its specific size, not applied by formula.
- **Uppercase Body-Font as instrument panel**: Captions and labels in uppercase + 1px spacing read like instrumentation, not editorial prose. This creates a clear register distinction between editorial FerrariSans copy and functional Body-Font notation.
- **No typographic decoration**: No gradient text, no outlined headlines, no drop-shadow on type. Legibility through contrast, not through treatment.

---

## 4. Component Catalog

### 4.1 Buttons

**Primary White (default CTA for dark sections)**
- Background: `#FFFFFF` → `var(--color-bg-primary)`
- Text: `#000000`
- Padding: `12px 10px`
- Border Radius: `2px` → `var(--radius-sm)`
- Font: 16px / 400 / FerrariSans, letter-spacing 1.28px
- Border: `1px solid #000000`
- Shadow: none
- Hover: bg `#1EAEDB`, text `#FFFFFF`, opacity 0.9, border `1px solid #1EAEDB`
- Focus: bg `#1EAEDB`, text `#FFFFFF`, border `1px solid #FFFFFF`, outline `2px solid #000000` offset 2px
- Transition: `background-color 200ms cubic-bezier(0.25,0.1,0.25,1), color 200ms, border-color 200ms`

**Subscribe CTA — The ONLY Red Button**
- Background: `#DA291C` → `var(--color-accent-primary)`
- Text: `#FFFFFF`
- Padding: `12px 10px`
- Border Radius: `2px` → `var(--radius-sm)`
- Font: 16px / 400 / FerrariSans, letter-spacing 1.28px
- Border: none
- Hover: bg `#B01E0A` → `var(--color-accent-hover)`
- Active: bg `#9D2211` → `var(--color-accent-active)`, scale(0.99)
- Focus: outline `2px solid #9D2211`, offset 2px
- Use: Newsletter signup EXCLUSIVELY — never repurpose this button variant for any other action

**Ghost Button (dark/cinematic section backgrounds)**
- Background: transparent
- Text: `#FFFFFF`
- Padding: `12px 10px`
- Border Radius: `2px`
- Border: `1px solid #FFFFFF`
- Font: 16px / 400 / FerrariSans, letter-spacing 1.28px
- Hover: bg `rgba(255,255,255,0.08)`, border `1px solid rgba(255,255,255,0.6)`
- Focus: outline `2px solid #FFFFFF`, offset 2px

**Small Button**
- Font: 14.4px / 700 / FerrariSans
- Padding: `8px 10px`
- Border Radius: `2px`
- Follows same color variants (Primary White or Ghost) depending on section background

**Micro Button**
- Font: 12px / 700 / FerrariSans, letter-spacing 0.96px
- Padding: `6px 8px`
- Border Radius: `2px`
- Use: filter chips, quick actions within card grids

### 4.2 Inputs

**Text Input (newsletter, forms)**
- Background: transparent (on dark sections) / `#FFFFFF` (on light sections)
- Border: `1px solid #CCCCCC` → `var(--color-border-default)`
- Border Radius: `2px`
- Padding: `12px 10px`
- Font: 16px / 400 / FerrariSans
- Placeholder: `#969696` → `var(--color-text-disabled)`
- Color (typed text on dark): `#FFFFFF` / (on light): `#181818`
- Label: Body-Font uppercase 12px / 400 / 1px spacing — positioned above, `margin-bottom: 6px`
- Focus: border `#181818` (light) or `#FFFFFF` (dark), outline `2px solid #181818` or `#FFFFFF` offset 2px
- Error: border `#F13A2C`, helper text 12px / FerrariSans / `#F13A2C` below input

**Select** — same border/radius treatment, chevron icon right-aligned in section text color
**Textarea** — same as Text Input but `min-height: 120px`, `resize: vertical`
**Checkbox** — 16x16px, `border-radius: 1px`, checked bg `#181818`, check mark `#FFFFFF`
**Radio** — 16x16px, `border-radius: 50%`, selected dot `#181818`
**Toggle / Switch** — 40x22px track, 18px thumb. Off: track `#D2D2D2`, On: track `#181818`, thumb `#FFFFFF`

### 4.3 Cards

**Editorial Card (white sections)**
- Background: `#FFFFFF`
- Border: none
- Border Radius: 0px (flush, editorial — no softening on any edge)
- Padding: 0px (image flush to container edges, then 16px text area below image)
- Shadow: none
- Image: above, full-width, aspect-ratio 4/3, `brightness(1.03)` filter on hover (300ms)
- Heading: FerrariSans 24px/400, color `#181818`
- Caption: Body-Font uppercase 12px/400, 1px spacing, color `#8F8F8F`

**Dark Cinematic Card (black sections)**
- Background: `#000000`
- Full-bleed imagery with `hsla(0,0%,7%,0.8)` gradient overlay at image base for text legibility
- Border: none
- Shadow: none
- Border Radius: 0px
- Text over overlay: FerrariSans `#FFFFFF`

**Heritage Card (motorsport sections)**
- Background: `#000000`
- Racing Yellow (`#FFF200`) accent: 2px horizontal rule at card top — the only yellow element
- Typography: FerrariSans `#FFFFFF`, Body-Font uppercase `#8F8F8F`

### 4.4 Navigation

**Top Nav / Header**
- Background: `#FFFFFF` (light sections) / `#000000` (cinematic sections)
- Height: `56px`
- Backdrop: none — Ferrari avoids glass-morphism; no backdrop-blur, no translucency
- Position: NOT sticky — header scrolls off-screen naturally as page scrolls
- Logo: Ferrari wordmark + Prancing Horse, left-aligned; white variant on dark sections
- Links: Body-Font uppercase 13px / 600, letter-spacing 0.13px, `#181818`. Hover: `#3860BE` with underline
- CTA: none in main nav — Ferrari does not place action CTAs in the navigation bar
- Mobile: hamburger (44x44px touch target) → full-screen black overlay menu

**Footer**
- Background: `#303030` → `var(--color-bg-secondary)`
- 4-column grid on desktop: Brand column + Models + Experience + Corporate
- Link font: Body-Font uppercase 11px/400, 1px spacing, color `#969696`. Hover: `#FFFFFF`
- Social icons: 20px, `#969696`. Hover: `#FFFFFF`
- Bottom bar: copyright 11px Body-Font uppercase, `#666666`
- No border-top — `#303030` against page sections provides sufficient visual separation

**Breadcrumbs**
- Separator: `/` character, `#8F8F8F`
- Font: Body-Font uppercase 11px/400, 1px spacing, `#8F8F8F`

### 4.5 Modals & Dialogs

- Overlay: `hsla(0,0%,7%,0.8)` → `var(--color-overlay)`
- Container: bg `#FFFFFF`, radius `8px` (the only 8px radius in the entire system), shadow `rgb(153,153,153) 1px 1px 1px 0px`, max-width `560px`
- Header: FerrariSans 18px/700, close button top-right (24x24px touch area, icon `#181818`)
- Body: padding `24px`, overflow-y auto if content exceeds viewport
- Footer: padding `16px 24px`, buttons right-aligned, `gap: 12px`

**Cookie Consent Modal**
- Background: `#FFFFFF`, radius `8px`, shadow `rgb(153,153,153) 1px 1px 1px 0px`
- Headline: Arial 45px/400 (legacy component — pre-GDPR design, Arial only at this size)
- Body text: FerrariSans 16px/400 `#181818`
- Accept/Configure buttons: Primary White + Ghost variants (no red here — not a Subscribe action)

### 4.6 Dropdowns & Menus

- Container: bg `#FFFFFF`, border `1px solid #CCCCCC`, radius `2px`, shadow `rgb(153,153,153) 1px 1px 1px 0px`
- Item: padding `10px 16px`, Body-Font uppercase 12px/400, 1px spacing, color `#181818`, hover bg `#F5F5F5`
- Active item: text `#000000`, bg `#F0F0F0`
- Divider: `1px solid #D2D2D2`
- Group label: Body-Font uppercase 11px/400, 1px spacing, `#8F8F8F`, padding `8px 16px`

### 4.7 Badges & Tags

| Variant | Background | Text | Border | Radius | Padding |
|---------|-----------|------|--------|--------|---------|
| Default | `#F5F5F5` | `#181818` | none | `2px` | `4px 8px` |
| Heritage | `#000000` | `#FFF200` | none | `2px` | `4px 8px` |
| New Model | `#DA291C` | `#FFFFFF` | none | `2px` | `4px 8px` |
| Success | `rgba(3,144,74,0.1)` | `#03904A` | none | `2px` | `4px 8px` |
| Error | `rgba(241,58,44,0.1)` | `#F13A2C` | none | `2px` | `4px 8px` |
| Info | `rgba(76,152,185,0.1)` | `#4C98B9` | none | `2px` | `4px 8px` |

### 4.8 Tooltips

- Background: `#181818`
- Text: `#FFFFFF`, Body-Font uppercase 11px/400, 1px spacing
- Radius: `2px`
- Padding: `8px 10px`
- Arrow: `5px`, `#181818`
- Max width: `240px`
- Shadow: `rgb(153,153,153) 1px 1px 1px 0px`

### 4.9 Toasts & Notifications

- Container: bg `#FFFFFF`, radius `2px`, shadow `rgb(153,153,153) 1px 1px 1px 0px`, padding `16px`
- Icon: 16px, color per variant (success `#03904A` / error `#F13A2C` / info `#4C98B9`)
- Title: FerrariSans 14px/700, `#181818`
- Message: FerrariSans 14px/400, `#666666`
- Close button: 20x20px icon, `#8F8F8F`. Hover: `#181818`
- Position: `top-right`, offset `16px` from edges
- Stack: `gap: 8px`, max 3 visible

### 4.10 Tables

- Header: bg `#F5F5F5`, text Body-Font uppercase 11px/700, 1px spacing, `#666666`, border-bottom `2px solid #CCCCCC`
- Row: bg transparent, hover bg `#FAFAFA`, border-bottom `1px solid #D2D2D2`
- Cell: padding `12px 16px`, FerrariSans 14px/400, `#181818`
- Striped: alternate bg `#FAFAFA`

### 4.11 Tabs

- Container: border-bottom `1px solid #D2D2D2`
- Tab: padding `12px 16px`, Body-Font uppercase 12px/400, 1px spacing, color `#8F8F8F` (inactive), color `#181818` (active)
- Indicator: `2px solid #181818` bottom border on active tab
- Hover: color `#181818`

### 4.12 Avatars

| Size | Dimensions | Font Size | Radius |
|------|-----------|-----------|--------|
| xs | 24px | 10px | 50% |
| sm | 32px | 12px | 50% |
| md | 40px | 14px | 50% |
| lg | 56px | 18px | 50% |
| xl | 80px | 24px | 50% |

### 4.13 Pagination

- Button: 36x36px, radius `2px`, Body-Font uppercase 12px/400, 1px spacing
- Default: bg transparent, text `#8F8F8F`, border `1px solid transparent`
- Active: bg `#181818`, text `#FFFFFF`, border `1px solid #181818`
- Hover: border `1px solid #CCCCCC`, text `#181818`
- Disabled: opacity 0.4, cursor `not-allowed`
- Gap: `4px`
- Carousel dots: 8x8px, radius `50%`, active `#181818`, inactive `#D2D2D2`

### 4.14 Progress & Loading

- Progress bar: height `2px`, track `#D2D2D2`, fill `#181818`, radius `0px` (flush — Ferrari avoids rounded progress bars)
- Spinner: 20px, `#181818` on light / `#FFFFFF` on dark, stroke `1.5px`, `spin 1s linear infinite`
- Skeleton: bg `#F0F0F0`, no shimmer gradient (Ferrari static skeleton — no animation), radius matching component

---

## 5. Component State Matrix

| Component | Default | Hover | Active/Pressed | Focus | Disabled | Loading | Error |
|-----------|---------|-------|---------------|-------|----------|---------|-------|
| **Button Primary White** | bg `#FFFFFF`, text `#000`, border `1px solid #000` | bg `#1EAEDB`, text `#FFF`, opacity 0.9 | bg `#1EAEDB`, scale(0.99) | `#1EAEDB` bg, `2px solid #000` outline offset 2px | opacity 0.4, `not-allowed` | spinner `#FFF` + text opacity 0.5 | — |
| **Button Subscribe Red** | bg `#DA291C`, text `#FFF`, no border | bg `#B01E0A` | bg `#9D2211`, scale(0.99) | outline `2px solid #9D2211`, offset 2px | opacity 0.4, `not-allowed` | spinner `#FFF` + text opacity 0.5 | — |
| **Button Ghost** | transparent, text `#FFF`, border `1px solid #FFF` | bg `rgba(255,255,255,0.08)`, border opacity 0.6 | bg `rgba(255,255,255,0.12)` | outline `2px solid #FFF`, offset 2px | opacity 0.4, `not-allowed` | spinner `#FFF` | — |
| **Input Text** | border `#CCCCCC` | border `#8F8F8F` | — | border `#181818`, outline `2px solid #181818`, offset 2px | bg `#F5F5F5`, cursor `not-allowed` | — | border `#F13A2C`, helper `#F13A2C` 12px below |
| **Checkbox** | border `1px solid #CCCCCC` | border `1px solid #8F8F8F` | — | outline `2px solid #181818`, offset 2px | opacity 0.4 | — | border `#F13A2C` |
| **Card Editorial** | no shadow, no border | cursor pointer, image `brightness(1.03)` 300ms | image `brightness(0.97)` | outline `2px solid #181818` | opacity 0.5 | skeleton `#F0F0F0` | — |
| **Card Cinematic** | full-bleed image, text overlay | cursor pointer, overlay opacity 0.9 | — | outline `2px solid #FFFFFF` | opacity 0.5 | — | — |
| **Link (light bg)** | color `#181818` | color `#3860BE`, underline | color `#3860BE` | outline `2px solid #181818`, offset 2px | color `#8F8F8F`, no pointer | — | — |
| **Link (dark bg)** | color `#FFFFFF` | color `rgba(255,255,255,0.7)`, underline | — | outline `2px solid #FFFFFF`, offset 2px | color `#969696` | — | — |
| **Tab** | color `#8F8F8F` | color `#181818` | color `#181818`, indicator `2px solid #181818` | outline `2px solid #181818`, offset 2px | opacity 0.4 | — | — |
| **Select** | border `#CCCCCC` | border `#8F8F8F` | — | border `#181818`, outline `2px solid #181818` | opacity 0.5 | spinner | border `#F13A2C` |
| **Toggle** | track `#D2D2D2` | track opacity 0.75 | — | outline `2px solid #181818`, offset 2px | opacity 0.4 | — | — |
| **Carousel Dot** | 8px `#D2D2D2`, radius `50%` | 8px `#8F8F8F` | — | outline `2px solid #181818` | opacity 0.3 | — | — |

### Focus Ring Standard
```css
/* Light sections */
outline: 2px solid var(--color-text-primary); /* #181818 */
outline-offset: 2px;

/* Cinematic/dark sections */
outline: 2px solid var(--color-text-on-dark); /* #FFFFFF */
outline-offset: 2px;
```

### Disabled Pattern
```css
opacity: 0.4;
cursor: not-allowed;
pointer-events: none;
```

---

## 6. Layout & Spacing System

### Spacing Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `space-0` | 0px | `p-0` | `--space-0` | Reset |
| `space-1` | 4px | `p-1` | `--space-1` | Tight inline, badge padding |
| `space-2` | 8px | `p-2` | `--space-2` | Icon gaps, micro-button padding |
| `space-3` | 12px | `p-3` | `--space-3` | Button/input padding vertical |
| `space-4` | 16px | `p-4` | `--space-4` | Card text area, component gap |
| `space-5` | 20px | `p-5` | `--space-5` | Section padding (mobile) |
| `space-6` | 24px | `p-6` | `--space-6` | Card base padding, modal padding |
| `space-8` | 32px | `p-8` | `--space-8` | Section sub-gap |
| `space-10` | 40px | `p-10` | `--space-10` | Section gap (mobile) |
| `space-12` | 48px | `p-12` | `--space-12` | Section gap (tablet) |
| `space-16` | 64px | `p-16` | `--space-16` | Section gap (desktop) |
| `space-20` | 80px | `p-20` | `--space-20` | Hero vertical padding |
| `space-24` | 96px | `p-24` | `--space-24` | Editorial section separation — gallery wall breathing room |
| `space-32` | 128px | `p-32` | `--space-32` | Maximum cinematic section padding |

### Grid

| Property | Value | CSS Variable |
|----------|-------|-------------|
| Max content width | `1920px` | `--grid-max-width` |
| Column count | 12 | `--grid-columns` |
| Gutter | `24px` | `--grid-gutter` |
| Margin (mobile small ≤375px) | `16px` | `--grid-margin-xs` |
| Margin (mobile 376-600px) | `20px` | `--grid-margin-sm` |
| Margin (tablet 601-960px) | `32px` | `--grid-margin-md` |
| Margin (desktop 961-1280px) | `48px` | `--grid-margin-lg` |
| Margin (large desktop 1281-1920px) | `80px` | `--grid-margin-xl` |

### Border Radius Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `radius-none` | 0px | `rounded-none` | `--radius-none` | Cards, images, sections — editorial flatness |
| `radius-xs` | 1px | `rounded-[1px]` | `--radius-xs` | Rare subtle softening on checkboxes |
| `radius-sm` | 2px | `rounded-[2px]` | `--radius-sm` | DEFAULT for all buttons, inputs, interactive elements |
| `radius-md` | 8px | `rounded-lg` | `--radius-md` | Modal dialogs ONLY — the softest radius in the system |
| `radius-full` | 50% | `rounded-full` | `--radius-full` | Circular elements only: carousel dots, avatars |

> Ferrari's border radius system is deliberate minimalism: 0px for content framing, 2px for UI interactions, 8px for dialogs. No pill shapes (9999px) anywhere in the system. No 12px, 16px, or 24px radius on rectangular elements.

---

## 7. Depth & Elevation

### Elevation Philosophy

Ferrari avoids decorative shadows on UI components. Depth is achieved through three legitimate sources:
1. **Surface color contrast** — absolute black section next to pure white section is the primary depth mechanism
2. **Photography** — studio-lit dimensional imagery provides inherent visual depth
3. **Overlay transparency** — `hsla(0,0%,7%,0.8)` for cinematic text legibility layers

### Shadow Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `shadow-none` | `none` | `shadow-none` | `--shadow-none` | Default for ALL cards and containers |
| `shadow-dialog` | `rgb(153,153,153) 1px 1px 1px 0px` | `shadow-[rgb(153,153,153)_1px_1px_1px_0px]` | `--shadow-dialog` | Modal dialogs, cookie consent ONLY |
| `shadow-dropdown` | `rgb(153,153,153) 1px 1px 1px 0px` | `shadow-[rgb(153,153,153)_1px_1px_1px_0px]` | `--shadow-dropdown` | Dropdowns and menus |

> **No gradients on UI. No glows. No blurs. No multi-layer box-shadows.** If a component seems to need elevation, question whether layout section contrast should instead create the depth.

### Z-Index Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `z-base` | 0 | `--z-base` | Default content |
| `z-image-overlay` | 1 | `--z-image-overlay` | Caption overlays on images |
| `z-dropdown` | 10 | `--z-dropdown` | Dropdowns, menus |
| `z-header` | 20 | `--z-header` | Non-sticky header when floating on hero |
| `z-overlay` | 60 | `--z-overlay` | Modal backdrop |
| `z-modal` | 70 | `--z-modal` | Modal content |
| `z-popover` | 80 | `--z-popover` | Popovers, tooltips |
| `z-toast` | 90 | `--z-toast` | Toast notifications |
| `z-top` | 100 | `--z-top` | Skip-to-content, critical overlays |

---

## 8. Motion & Animation System

Ferrari motion is controlled, precise, and never theatrical. Luxury communicates through restraint. A Ferrari at rest draws more attention than a lesser car at full throttle — the same principle governs animation. A transition that completes in 200ms without bounce is more authoritative than one that springs and overshoots. Motion confirms a state change; it does not entertain the viewer.

### Duration Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `duration-instant` | 0ms | `--duration-instant` | Immediate feedback (toggle color) |
| `duration-fast` | 100ms | `--duration-fast` | Hover state color and border changes |
| `duration-normal` | 200ms | `--duration-normal` | Button background transition, link color |
| `duration-moderate` | 300ms | `--duration-moderate` | Modal entry, menu open, overlay fade |
| `duration-slow` | 400ms | `--duration-slow` | Image transitions, carousel cross-fade |
| `duration-carousel` | 6000ms | `--duration-carousel` | Carousel auto-advance interval |

### Easing Functions

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `ease-default` | `cubic-bezier(0.25,0.1,0.25,1)` | `--ease-default` | All restrained transitions — the Ferrari standard |
| `ease-material` | `cubic-bezier(0.4,0,0.2,1)` | `--ease-material` | Button state changes, form interactions |
| `ease-in` | `cubic-bezier(0.4,0,1,1)` | `--ease-in` | Elements exiting view |
| `ease-out` | `cubic-bezier(0,0,0.2,1)` | `--ease-out` | Elements entering view |

> **Prohibited easings:** Any easing with a control point Y > 1 or Y < 0 — this includes `cubic-bezier(0.34,1.56,0.64,1)` and all spring/bounce variants. Ferrari motion never overshoots. Bounce communicates playfulness. Ferrari communicates precision. These are incompatible.

### Common Transitions

| Interaction | Property | Duration | Easing |
|------------|----------|----------|--------|
| Button hover | `background-color, color, border-color` | 200ms | ease-default |
| Link hover | `color` | 100ms | ease-default |
| Image card hover | `filter (brightness)` | 300ms | ease-default |
| Modal enter | `opacity` | 300ms | ease-out |
| Modal exit | `opacity` | 200ms | ease-in |
| Overlay fade in | `opacity` | 300ms | ease-out |
| Carousel cross-fade | `opacity` | 400ms | ease-default |
| Carousel auto-advance | — | 6000ms interval | — |
| Dropdown open | `opacity, transform (translateY -4px to 0)` | 200ms | ease-out |
| Toast enter | `transform (translateX), opacity` | 300ms | ease-out |
| Focus ring | `outline` | 100ms | ease-default |
| Navigation overlay | `opacity` | 300ms | ease-out |

> **Page transitions:** Fade only (`opacity: 0 to 1`). No transform-based page transitions. No slides, no scales, no reveals. A gallery does not animate between rooms.

> **Carousel specifics:** Auto-advance at 6s per slide. Manual override is instant (0ms cross-fade triggers on interaction, then resumes 6s timer). Pause auto-advance on hover for `prefers-hover: hover` environments.

### Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
  /* Carousel: disable auto-advance entirely, require manual navigation only */
  .carousel[data-auto-advance] {
    animation: none !important;
  }
}
```

---

## 9. Icon System

| Property | Value |
|----------|-------|
| Library | Custom Ferrari SVG icons (proprietary) + PrimeIcons for functional UI fallbacks |
| Default size | 20px |
| Stroke width | 1px (refined — not the 1.5px or 2px common in consumer apps) |
| Color | `currentColor` (inherits from parent text color) |
| Style | Filled for brand moments, outlined for functional UI |

### Icon Sizes

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `icon-xs` | 12px | `--icon-xs` | Inline text, breadcrumb separators |
| `icon-sm` | 16px | `--icon-sm` | Button icons, nav micro-icons |
| `icon-md` | 20px | `--icon-md` | Standard UI: navigation, dropdowns |
| `icon-lg` | 24px | `--icon-lg` | Card actions, feature callouts |
| `icon-xl` | 40px | `--icon-xl` | Heritage section accents |
| `icon-2xl` | 64px | `--icon-2xl` | Empty states, hero accent marks |

### Prancing Horse
- The Prancing Horse (Cavallino Rampante) is NOT a UI icon — it is the brand mark
- Always rendered at SVG quality, minimum 80px display size
- Must appear on `#000000` void-black background ONLY — never on white, never on red, never on texture
- Minimum clear space: equal to the height of the horse symbol on all sides
- Never used as a repeating or decorative pattern element

---

## 10. Accessibility Contract

### Targets

| Criterion | Target | Standard |
|-----------|--------|----------|
| Color contrast (normal text <18px) | 4.5:1 minimum | WCAG AA |
| Color contrast (large text >=18px or bold >=14px) | 3:1 minimum | WCAG AA |
| Color contrast (UI components, focus rings) | 3:1 minimum | WCAG AA |
| Touch target size | 44x44px minimum | WCAG 2.5.8 |
| Focus indicator | 2px outline, 3:1 contrast vs adjacent background | WCAG 2.4.7 |
| Motion | Respect `prefers-reduced-motion` — disable carousel auto-advance | WCAG 2.3.3 |

### Known Contrast Issues (enforce in implementation)

| Element | Color | Background | Current Ratio | Required Action |
|---------|-------|-----------|--------------|----------------|
| Mid Gray tertiary text | `#8F8F8F` | `#FFFFFF` | 3.5:1 | Use only at 18px+ regular or 14px+ bold. NEVER body copy. |
| Silver Gray placeholder | `#969696` | `#FFFFFF` | 2.7:1 | Placeholder ONLY — never carry meaningful content |
| White on Ferrari Red CTA | `#FFFFFF` | `#DA291C` | 4.9:1 | Subscribe button: use 16px/700 or 18px/400 to pass AA |
| White on Teal hover | `#FFFFFF` | `#1EAEDB` | 3.2:1 | Acceptable for button-size UI text (>=16px). Warn for smaller. |

### Focus Management

- All interactive elements have visible focus: `2px solid #181818`, offset `2px` (light sections) / `2px solid #FFFFFF` (dark/cinematic sections)
- Focus order follows visual layout — left-to-right, top-to-bottom
- Modal traps focus within dialog until dismissed (Escape key or close button)
- Skip-to-content as first focusable element: `<a href="#main-content" class="sr-only focus:not-sr-only">`
- Carousel is keyboard-navigable: Arrow keys navigate slides, dots are focusable

### ARIA Patterns

| Component | Role | Key Attributes |
|-----------|------|---------------|
| Modal | `dialog` | `aria-modal="true"`, `aria-labelledby` |
| Dropdown | `listbox` | `aria-expanded`, `aria-activedescendant` |
| Tabs | `tablist` / `tab` / `tabpanel` | `aria-selected`, `aria-controls` |
| Toast | `alert` or `status` | `role="alert"` for errors, `role="status"` for info |
| Toggle | `switch` | `aria-checked` |
| Tooltip | `tooltip` | `aria-describedby` on trigger |
| Carousel | `region` | `aria-label="Model gallery"`, `aria-roledescription="carousel"` |
| Carousel slide | — | `aria-roledescription="slide"`, `aria-label="Slide N of M"` |

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
| Carousel | `Arrow Left/Right` | Previous / Next slide |
| Carousel | `Home` / `End` | First / Last slide |

---

## 11. Do's and Don'ts

### Do
1. **Use Ferrari Red (`#DA291C`) on exactly ONE element per screen** — the Subscribe CTA is its designated home. Its scarcity is its power. A page full of red is not Ferrari; it is a warning sign.
2. **Alternate black cinematic and white editorial sections** — the chiaroscuro page-turn rhythm is Ferrari's visual grammar. Black breathes, white breathes, they do not compete.
3. **Treat whitespace as the gallery wall** — a section with one full-bleed image, one heading, and 96px of vertical breathing room is correct Ferrari editorial. The emptiness is not absence — it is the frame.
4. **Set all captions and labels in Body-Font uppercase with 1px letter-spacing** — this is the instrument-panel register that separates Ferrari from generic brands. It reads like a dashboard readout, not a marketing tag.
5. **Use `2px` border radius as the default for all interactive elements** — buttons, inputs, dropdowns, all 2px. Razor-precision softening, barely perceptible. 0px feels unfinished; 4px feels consumer.
6. **Isolate the Prancing Horse on void-black (`#000000`) always** — never place it on white, red, a texture, a photograph, or a gradient. The horse requires a void.
7. **Use Racing Yellow (`#FFF200`) only in motorsport heritage contexts** — Scuderia timeline, F1 livery references, historical sections. Never in current-model commercial contexts, never near Ferrari Red.
8. **Keep motion controlled and under 400ms** — transitions confirm state, they do not perform. The button changes color. That is sufficient.
9. **Use border-based and surface-contrast depth instead of shadows** — `1px solid #CCCCCC` defines an input. `#000000` section next to `#FFFFFF` section creates depth. Box-shadows are not needed.
10. **Keep the navigation non-sticky** — Ferrari pages scroll naturally; the header moves off-screen. Photography and content own the viewport. The chrome does not linger.

### Don't
1. **Don't use Ferrari Red for anything except the Subscribe CTA** — no hero CTAs in red, no "Configure" in red, no pricing highlights in red. One red element per screen is the maximum. Zero is also acceptable.
2. **Don't add border-radius above 8px to rectangular UI elements** — no 12px, no 16px, no pill shapes on buttons or cards. The 8px modal radius is the system's softest edge and it is reserved for dialogs alone.
3. **Don't use `#8F8F8F` (Mid Gray) for body copy** — 3.5:1 fails WCAG AA for normal text. It is approved only for captions and metadata at 18px+ or as supplemental decorative labeling. Flag all uses at 12-13px as known contrast exceptions.
4. **Don't mix Racing Yellow and Ferrari Red on the same component or card** — these are context-specific heritage accents. When Yellow appears, Red does not; when Red appears, Yellow does not. They are categorical, not combinatorial.
5. **Don't make the navigation sticky** — Ferrari's editorial rhythm requires the header to scroll away. A persistent sticky bar competes with the photography. The absence of chrome is a design decision.
6. **Don't add glass-morphism, backdrop-blur, or translucency to any component** — no frosted glass, no blur layers behind nav or cards. Ferrari UI is opaque and absolute, like the lacquer on the bodywork.
7. **Don't use bounce, spring, or overshoot easings** — any `cubic-bezier` with Y control point above 1 is prohibited. Bounce communicates playfulness. Ferrari communicates precision. They are mutually exclusive.
8. **Don't shadow-lift cards on hover** — Ferrari editorial cards do not float. A subtle `brightness(1.03)` on the image is the full hover response. Shadow on hover is not an upgrade; it is visual noise.
9. **Don't center-align body paragraphs exceeding three lines** — editorial copy is left-aligned. Center-alignment is reserved for single-line display headings in cinematic hero sections and for the isolated Prancing Horse section.
10. **Don't use Link Hover Blue (`#3860BE`) or Button Hover Teal (`#1EAEDB`) as brand colors** — these are interaction-state utilities visible for 100-200ms during active user engagement. They must never appear in static designs, mockups, or screenshots as palette representatives.

---

## 12. Responsive Behavior

### Breakpoints

| Token | Width | CSS | Tailwind | Key Changes |
|-------|-------|-----|----------|-------------|
| `xs` | 375px | `@media (max-width: 375px)` | — | Mobile small: single column, compact typography |
| `sm` | 600px | `@media (min-width: 376px)` | `sm:` | Mobile: full single-column layout, hamburger nav |
| `md` | 768px | `@media (min-width: 601px)` | `md:` | Tablet small: 2-col editorial cards begin |
| `lg` | 960px | `@media (min-width: 769px)` | `lg:` | Tablet: full 2-col editorial, condensed nav visible |
| `xl` | 1280px | `@media (min-width: 961px)` | `xl:` | Desktop: 3-col grids, full horizontal navigation |
| `2xl` | 1920px | `@media (min-width: 1281px)` | `2xl:` | Large desktop: max-width 1920px, generous editorial margins |

### Responsive Type Scale

| Token | Mobile (<=600px) | Tablet (601-960px) | Desktop (961px+) |
|-------|-----------------|-------------------|-----------------|
| `section-title` | 20px | 23px | 26px |
| `card-heading` | 18px | 21px | 24px |
| `subheading` | 16px | 17px | 18px |
| `ui-heading` | 15px | 16px | 16px |
| `button-label` | 15px | 16px | 16px |
| `nav-link` | — (hamburger) | 12px | 13px |

### Layout Shifts

| Component | Mobile (<=600px) | Tablet (601-960px) | Desktop (961px+) |
|-----------|-----------------|-------------------|--------------------|
| Nav | Hamburger → full-screen black overlay | Hamburger → overlay | Full horizontal, non-sticky, static position |
| Hero cinematic | Image full-width above, text below, padding 20px | Image 60vh then text, padding 32px | Full-bleed image with text overlay, padding 80px |
| Editorial grid | 1 column, cards full-width, stacked | 2 columns | 2-3 columns, image/text alternating sides |
| Model showcase | 1 per row, full-width image | 2 per row | 3 per row or full-bleed with side text panel |
| Footer | Single column stacked | 2x2 grid | 4-column grid |
| Newsletter strip | Stacked: heading above, input+button below | Side-by-side | Side-by-side, max-width 800px centered |
| Prancing Horse section | Horse 80vw centered, 40px vertical padding | Horse 60vw, 64px padding | Horse 40vw or fixed 480px, 128px padding |

### Touch Targets
- Minimum size: 44x44px for all interactive elements
- Minimum gap between adjacent touch targets: 8px
- Mobile CTA buttons: full width, 48px min height
- Nav hamburger button: 44x44px touch area
- Carousel prev/next controls: 44x44px touch area (even when arrow icon is 20px)

---

## 13. Code Snippets

### Button Primary White (JSX + Tailwind)

```jsx
// Primary white CTA — standard Ferrari action button for dark/cinematic sections
<button
  className="
    inline-flex items-center justify-center
    bg-white text-black
    border border-black
    px-[10px] py-[12px]
    rounded-[2px]
    text-base font-normal tracking-[1.28px]
    transition-[background-color,color,border-color]
    duration-200
    [transition-timing-function:cubic-bezier(0.25,0.1,0.25,1)]
    hover:bg-[#1EAEDB] hover:text-white hover:border-[#1EAEDB] hover:opacity-90
    focus:bg-[#1EAEDB] focus:text-white focus:border-white
    focus:outline focus:outline-2 focus:outline-black focus:outline-offset-2
    disabled:opacity-40 disabled:cursor-not-allowed
    [font-family:'FerrariSans',Arial,Helvetica,sans-serif]
  "
>
  Configure Your Ferrari
</button>
```

### Subscribe CTA — The ONLY Red Button (JSX + Tailwind)

```jsx
// Ferrari Red (#DA291C) is used HERE and NOWHERE ELSE
// This is the newsletter subscribe button exclusively
<button
  className="
    inline-flex items-center justify-center
    bg-[#DA291C] text-white
    px-[10px] py-[12px]
    rounded-[2px]
    text-base font-normal tracking-[1.28px]
    transition-[background-color]
    duration-200
    [transition-timing-function:cubic-bezier(0.25,0.1,0.25,1)]
    hover:bg-[#B01E0A]
    active:bg-[#9D2211] active:scale-[0.99]
    focus:outline focus:outline-2 focus:outline-[#9D2211] focus:outline-offset-2
    disabled:opacity-40 disabled:cursor-not-allowed
    [font-family:'FerrariSans',Arial,Helvetica,sans-serif]
  "
>
  Subscribe
</button>
```

### Editorial Card — White Section (JSX + Tailwind)

```jsx
// No border, no shadow, no border-radius — editorial flatness is intentional
<article className="group cursor-pointer">
  <div className="overflow-hidden">
    <img
      src={model.image}
      alt={model.name}
      className="w-full aspect-[4/3] object-cover transition-[filter] duration-300 [transition-timing-function:cubic-bezier(0.25,0.1,0.25,1)] group-hover:brightness-[1.03]"
    />
  </div>
  <div className="pt-4">
    <h3
      className="text-[24px] font-normal leading-[1.25] text-[#181818] mb-2"
      style={{ fontFamily: "'FerrariSans', Arial, Helvetica, sans-serif" }}
    >
      {model.name}
    </h3>
    <p
      className="text-[12px] font-normal tracking-[1px] text-[#8F8F8F] uppercase"
      style={{ fontFamily: "'Body-Font', Arial, Helvetica, sans-serif" }}
    >
      {model.category}
    </p>
  </div>
</article>
```

### Dark Cinematic Section (JSX + Tailwind)

```jsx
// Chiaroscuro alternating section — void-black, full-bleed, text-over-overlay
<section className="bg-black relative overflow-hidden min-h-[80vh] flex items-end">
  <img
    src={heroImage}
    alt="Ferrari Roma"
    className="absolute inset-0 w-full h-full object-cover"
  />
  {/* Caption gradient overlay — the only gradient in the system */}
  <div
    className="absolute inset-0 z-[1]"
    style={{ background: 'linear-gradient(to top, hsla(0,0%,7%,0.8) 0%, transparent 60%)' }}
  />
  <div className="relative z-[2] p-[80px] max-w-2xl">
    <p
      className="text-[12px] font-normal tracking-[1px] text-[#8F8F8F] uppercase mb-4"
      style={{ fontFamily: "'Body-Font', Arial, Helvetica, sans-serif" }}
    >
      Berlinetta
    </p>
    <h2
      className="text-[26px] font-[500] leading-[1.2] text-white mb-8"
      style={{ fontFamily: "'FerrariSans', Arial, Helvetica, sans-serif" }}
    >
      Roma
    </h2>
    {/* Primary White button — Teal on hover, NO red here */}
    <button
      className="inline-flex items-center justify-center bg-white text-black border border-black px-[10px] py-[12px] rounded-[2px] text-base font-normal tracking-[1.28px] hover:bg-[#1EAEDB] hover:text-white hover:border-[#1EAEDB] transition-[background-color,color,border-color] duration-200"
      style={{ fontFamily: "'FerrariSans', Arial, Helvetica, sans-serif" }}
    >
      Discover
    </button>
  </div>
</section>
```

### Newsletter Strip with Subscribe CTA (JSX + Tailwind)

```jsx
// The one place Ferrari Red appears — newsletter subscription only
<section className="bg-[#303030] py-[64px] px-[48px]">
  <div className="max-w-[800px] mx-auto flex flex-col sm:flex-row items-center gap-6">
    <div className="flex-1">
      <h3
        className="text-[18px] font-bold text-white mb-2"
        style={{ fontFamily: "'FerrariSans', Arial, Helvetica, sans-serif" }}
      >
        Stay Connected
      </h3>
      <p
        className="text-[12px] tracking-[1px] text-[#8F8F8F] uppercase"
        style={{ fontFamily: "'Body-Font', Arial, Helvetica, sans-serif" }}
      >
        News from Maranello
      </p>
    </div>
    <div className="flex gap-3 w-full sm:w-auto">
      <input
        type="email"
        placeholder="Your email address"
        className="flex-1 bg-transparent border border-[#CCCCCC] rounded-[2px] px-[10px] py-[12px] text-white text-base placeholder-[#969696] focus:border-white focus:outline focus:outline-2 focus:outline-white focus:outline-offset-2"
        style={{ fontFamily: "'FerrariSans', Arial, Helvetica, sans-serif" }}
      />
      {/* Ferrari Red — Subscribe is its only home in the entire UI */}
      <button
        className="bg-[#DA291C] text-white rounded-[2px] px-[10px] py-[12px] text-base font-normal tracking-[1.28px] hover:bg-[#B01E0A] active:bg-[#9D2211] transition-[background-color] duration-200 whitespace-nowrap"
        style={{ fontFamily: "'FerrariSans', Arial, Helvetica, sans-serif" }}
      >
        Subscribe
      </button>
    </div>
  </div>
</section>
```

### CSS Custom Properties (Root)

```css
:root {
  /* Ferrari Brand Colors */
  --ferrari-red: #DA291C;
  --ferrari-red-hover: #B01E0A;
  --ferrari-red-active: #9D2211;
  --ferrari-yellow: #FFF200;
  --ferrari-yellow-2: #F6E500;

  /* Surface Colors */
  --color-bg-primary: #FFFFFF;
  --color-bg-secondary: #303030;
  --color-bg-cinematic: #000000;

  /* Text Colors */
  --color-text-primary: #181818;
  --color-text-secondary: #666666;
  --color-text-tertiary: #8F8F8F;   /* WARNING: 3.5:1 on white — 18px+ only */
  --color-text-disabled: #969696;   /* Placeholder only — 2.7:1 */
  --color-text-on-dark: #FFFFFF;

  /* Accent — Ferrari Red is Subscribe ONLY */
  --color-accent-primary: #DA291C;
  --color-accent-hover: #B01E0A;
  --color-accent-active: #9D2211;
  --color-accent-heritage: #FFF200;     /* Motorsport context only */
  --color-interactive-hover: #1EAEDB;   /* White button hover state */
  --color-interactive-link: #3860BE;    /* Link hover only */

  /* Borders */
  --color-border-default: #CCCCCC;
  --color-border-light: #D2D2D2;

  /* Status (semantic — visually distinct from brand) */
  --color-status-error: #F13A2C;
  --color-status-success: #03904A;
  --color-status-info: #4C98B9;

  /* Overlay */
  --color-overlay: hsla(0, 0%, 7%, 0.8);

  /* Typography */
  --font-primary: 'FerrariSans', Arial, Helvetica, sans-serif;
  --font-secondary: 'Body-Font', Arial, Helvetica, sans-serif;

  /* Type sizes */
  --text-section-title: 26px;
  --text-card-heading: 24px;
  --text-subheading: 18px;
  --text-ui-heading: 16px;
  --text-button-label: 16px;
  --text-nav-link: 13px;
  --text-caption: 13px;
  --text-label-upper: 12px;
  --text-micro-label: 11px;
  --text-cookie-consent: 45px;

  /* Spacing */
  --space-1: 4px;    --space-2: 8px;    --space-3: 12px;
  --space-4: 16px;   --space-5: 20px;   --space-6: 24px;
  --space-8: 32px;   --space-10: 40px;  --space-12: 48px;
  --space-16: 64px;  --space-20: 80px;  --space-24: 96px;
  --space-32: 128px;

  /* Grid */
  --grid-max-width: 1920px;
  --grid-columns: 12;
  --grid-gutter: 24px;

  /* Border Radius — Razor Precision */
  --radius-none: 0px;         /* cards, images, editorial content */
  --radius-xs: 1px;           /* checkboxes — rare subtle softening */
  --radius-sm: 2px;           /* DEFAULT: all buttons, inputs, interactive */
  --radius-md: 8px;           /* modal dialogs ONLY */
  --radius-full: 50%;         /* circular elements only */

  /* Shadows — Minimal */
  --shadow-none: none;
  --shadow-dialog: rgb(153,153,153) 1px 1px 1px 0px;
  --shadow-dropdown: rgb(153,153,153) 1px 1px 1px 0px;

  /* Motion */
  --duration-fast: 100ms;
  --duration-normal: 200ms;
  --duration-moderate: 300ms;
  --duration-slow: 400ms;
  --duration-carousel: 6000ms;
  --ease-default: cubic-bezier(0.25, 0.1, 0.25, 1);
  --ease-material: cubic-bezier(0.4, 0, 0.2, 1);
  --ease-in: cubic-bezier(0.4, 0, 1, 1);
  --ease-out: cubic-bezier(0, 0, 0.2, 1);

  /* Z-Index */
  --z-base: 0;
  --z-image-overlay: 1;
  --z-dropdown: 10;
  --z-header: 20;
  --z-overlay: 60;
  --z-modal: 70;
  --z-popover: 80;
  --z-toast: 90;
  --z-top: 100;
}

/* Cinematic / dark section overrides */
.section-cinematic,
[data-theme="dark"] {
  --color-bg-primary: #000000;
  --color-bg-secondary: #181818;
  --color-bg-tertiary: #303030;
  --color-text-primary: #FFFFFF;
  --color-text-secondary: #8F8F8F;
  --color-border-default: rgba(255, 255, 255, 0.15);
}
```

### Tailwind Config Extension

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        ferrari: {
          red: '#DA291C',
          'red-hover': '#B01E0A',
          'red-active': '#9D2211',
          yellow: '#FFF200',
          'yellow-2': '#F6E500',
          black: '#000000',
          'near-black': '#181818',
          'dark-surface': '#303030',
          white: '#FFFFFF',
        },
        brand: {
          'interactive-hover': '#1EAEDB',
          'interactive-link': '#3860BE',
          'text-primary': '#181818',
          'text-secondary': '#666666',
          'text-tertiary': '#8F8F8F',
          'text-disabled': '#969696',
          'border': '#CCCCCC',
          'border-light': '#D2D2D2',
          'status-error': '#F13A2C',
          'status-success': '#03904A',
          'status-info': '#4C98B9',
        }
      },
      fontFamily: {
        primary: ["'FerrariSans'", 'Arial', 'Helvetica', 'sans-serif'],
        secondary: ["'Body-Font'", 'Arial', 'Helvetica', 'sans-serif'],
      },
      borderRadius: {
        'ferrari': '2px',   // default for all interactive elements
        'dialog': '8px',    // modal dialogs only
      },
      boxShadow: {
        'ferrari-dialog': 'rgb(153,153,153) 1px 1px 1px 0px',
        'ferrari-none': 'none',
      },
      letterSpacing: {
        'ferrari-button': '1.28px',
        'ferrari-label': '1px',
        'ferrari-micro': '0.96px',
        'ferrari-nav': '0.13px',
        'ferrari-caption': '0.195px',
        'ferrari-ui': '0.08px',
      },
      transitionTimingFunction: {
        'ferrari': 'cubic-bezier(0.25, 0.1, 0.25, 1)',
        'ferrari-material': 'cubic-bezier(0.4, 0, 0.2, 1)',
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
| Subscribe CTA (only red button) | `#DA291C` bg, `#FFFFFF` text, `2px` radius, no border |
| Primary CTA (white) | `#FFFFFF` bg, `#000000` text, `1px solid #000000` border, `2px` radius |
| White CTA hover destination | `#1EAEDB` bg, `#FFFFFF` text |
| Cinematic section bg | `#000000` |
| Editorial section bg | `#FFFFFF` |
| Footer / newsletter bg | `#303030` |
| Primary text (light sections) | `#181818` |
| Secondary text | `#666666` |
| Tertiary text (caution: 3.5:1) | `#8F8F8F` — 18px+ only |
| Primary font | `FerrariSans`, 500 default weight |
| Caption / label font | `Body-Font`, uppercase, 1px letter-spacing |
| Default interactive radius | `2px` |
| Modal dialog radius | `8px` — the only 8px in the system |
| Card / image radius | `0px` — editorial flatness |
| Dialog / dropdown shadow | `rgb(153,153,153) 1px 1px 1px 0px` |
| Card shadow | `none` |
| Motion max duration | `400ms` |
| Carousel auto-advance | `6000ms` |
| Focus ring (light) | `2px solid #181818`, offset 2px |
| Focus ring (dark) | `2px solid #FFFFFF`, offset 2px |

### Example Prompts

1. **Chiaroscuro hero section (cinematic opening):** "Create a full-viewport hero section with `#000000` background. Full-bleed studio photograph of a Ferrari at `position: absolute, inset: 0, object-fit: cover`. Apply gradient overlay `linear-gradient(to top, hsla(0,0%,7%,0.8) 0%, transparent 60%)` at `z-index: 1`. Bottom-left text zone at `z-index: 2`, padding 80px desktop / 20px mobile: Body-Font uppercase 12px `#8F8F8F` 1px spacing (model category), then FerrariSans 26px/500 `#FFFFFF` (model name), then Primary White button (bg `#FFFFFF`, text `#000000`, border `1px solid #000`, 2px radius, 12px 10px padding, 1.28px tracking). Hover: button bg `#1EAEDB`, text `#FFFFFF`, 200ms transition. NO red on this section."

2. **Editorial model grid (white section, gallery wall):** "Build a 3-column grid on `#FFFFFF` background with 96px vertical padding — gallery-wall breathing. Each card: zero border, zero shadow, zero border-radius. Image aspect-ratio 4/3, full-width; on hover `brightness(1.03)` filter, 300ms. Below image: FerrariSans 24px/400 `#181818` model name. Then Body-Font uppercase 12px `#8F8F8F` 1px spacing category label. Mobile: 1 column. Tablet: 2 columns. No card hover lift — editorial stillness is the intention."

3. **Newsletter strip with the only red element:** "Build a newsletter section with bg `#303030`. Max-width 800px centered, 64px vertical padding. Left: FerrariSans 18px/700 `#FFFFFF` heading, Body-Font uppercase 12px `#8F8F8F` subtitle. Right: transparent input with `1px solid #CCCCCC` border, 2px radius, white text, `#969696` placeholder; then the Subscribe button: bg `#DA291C` (Ferrari Red — this is the ONLY red element in the entire UI), `#FFFFFF` text 1.28px tracking, 2px radius, hover `#B01E0A`. The entire strip should have exactly one red element and nothing else competing for attention."

4. **Prancing Horse section (cinematic isolation):** "Create a section with `#000000` background, 128px vertical padding. Center the Prancing Horse SVG at 320px width on desktop / 200px on mobile. Absolute visual isolation — no other content shares this section's frame. Body-Font uppercase 11px `#969696` 1px spacing below: 'Scuderia Ferrari — Maranello'. This section communicates through silence: the horse, the void, and one line of label text. No CTA. No heading. No copy. The emptiness is the message."

5. **Motorsport heritage timeline card (Racing Yellow context):** "Build a heritage card on `#000000` background. At card top: Racing Yellow `#FFF200` horizontal rule, 2px height, full card width — the ONLY yellow element. FerrariSans 26px/500 `#FFFFFF` race year. Body-Font uppercase 13px `#8F8F8F` 0.13px spacing race event title. FerrariSans 16px/400 `#FFFFFF` description. Bottom: Ghost button (transparent, `#FFFFFF` text, `1px solid #FFFFFF`, 2px radius). Yellow and black only — zero red on this card. Yellow and red must never coexist on the same component."

### Pre-flight Checklist for Generated UI

1. Ferrari Red (`#DA291C`) appears on at most ONE element in the current viewport — the Subscribe CTA
2. Section rhythm alternates: cinematic black / editorial white — no two consecutive same-color sections without architectural justification
3. All captions and labels use Body-Font uppercase with 1px letter-spacing — never FerrariSans lowercase for label elements
4. Border radius on buttons and inputs is exactly `2px` — not `4px`, not `rounded-md` (8px), not default Tailwind `rounded` (4px)
5. No box-shadow on cards in any state — neither default nor hover
6. `#8F8F8F` text only appears at 18px+ regular or 14px+ bold — zero body copy in this color
7. Navigation is NOT sticky (`position: static`) — the header scrolls off-screen
8. Touch targets are minimum 44x44px on mobile — verify button height with all padding included
9. `prefers-reduced-motion`: all transitions drop to 0.01ms, carousel auto-advance disabled
10. Prancing Horse appears on `#000000` only — check background before placing
11. No transition exceeds 400ms maximum duration
12. Focus rings are `2px solid #181818` (light sections) or `2px solid #FFFFFF` (cinematic sections) with 2px offset
