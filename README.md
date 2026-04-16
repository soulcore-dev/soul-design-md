# DESIGN.md v2.0 — Production-Grade Design Systems for AI Agents

> The original [awesome-design-md](https://github.com/VoltAgent/awesome-design-md) gave AI agents eyes. We gave them depth perception.

**DESIGN.md v2.0** is an evolution of the Google Stitch DESIGN.md format. Where v1.0 files describe *how a site looks*, v2.0 files describe *how to build it* — with exact tokens, interactive states, motion specs, accessibility contracts, and copy-paste code snippets.

## Why v2.0?

We audited every DESIGN.md in the original collection (68 files). They average ~300 lines and share the same gaps:

| Gap in v1.0 | Impact | Fixed in v2.0 |
|---|---|---|
| No interactive states (disabled, loading, error, focus) | AI generates buttons without states | Section 5: Component State Matrix |
| No animation/motion specs | Static UI, no micro-interactions | Section 8: Motion & Animation System |
| No accessibility specs | Zero WCAG compliance | Section 10: Accessibility Contract |
| Vague spacing ("~1200px", "generous") | AI can't code "generous" | Exact values with CSS custom properties |
| Shallow component coverage (~4 components) | Missing 40%+ of typical UI | 20+ components with full anatomy |
| No dark/light mode mapping | No theme switching logic | Section 2: dual-theme token mapping |
| No CSS variables or Tailwind classes | Tokens without implementation | Every token maps to `--var` + `tw-class` |
| No code snippets | Prose only, nothing copy-pasteable | Section 13: JSX + CSS + Tailwind |
| ~300 lines | Superficial | 600-900 lines: production depth |

## Format: 14 Sections

| # | Section | What v1.0 Had | What v2.0 Adds |
|---|---------|---------------|----------------|
| 1 | Visual Theme & Atmosphere | Narrative description | Same — this works well |
| 2 | Color System & Tokens | Hex + names | + CSS vars + dark/light map + WCAG contrast ratios |
| 3 | Typography System | Font + hierarchy table | + fluid `clamp()` + responsive scaling rules |
| 4 | Component Catalog | Buttons, cards, nav | + 20 components with full anatomy + variants |
| 5 | **Component State Matrix** | *Missing* | disabled/loading/error/focus/active per component |
| 6 | Layout & Spacing System | Vague values | Exact px + CSS vars + Tailwind mapping + grid spec |
| 7 | Depth & Elevation | Shadow descriptions | + CSS vars + z-index scale |
| 8 | **Motion & Animation System** | *Missing* | durations, easings, enter/exit, prefers-reduced-motion |
| 9 | **Icon System** | *Missing* | sizes, stroke weights, library, naming convention |
| 10 | **Accessibility Contract** | *Missing* | WCAG AA targets, contrast, ARIA, focus, touch targets |
| 11 | Do's and Don'ts | Guardrails | Same — expanded with code examples |
| 12 | Responsive Behavior | Breakpoints table | + exact media queries + container queries + fluid |
| 13 | **Code Snippets** | *Missing* | JSX/HTML + CSS + Tailwind per key component |
| 14 | Agent Prompt Guide | Copy-paste prompts | Same — expanded with state-aware prompts |

## Collection

### Flagship (v2.0 Original)

- [**SoulCore**](designs/soulcore/DESIGN.md) — AI consciousness platform. Void-black canvas, electric violet accent, terminal-native aesthetic with spiritual undertones

### Tech & SaaS

- [**Stripe**](designs/stripe/DESIGN.md) — Payment infrastructure. Signature purple gradients, weight-300 elegance, blue-tinted shadows
- [**Linear**](designs/linear/DESIGN.md) — Project management. Ultra-minimal dark, precise violet accent, weight-510 signature

### Luxury & Automotive

- [**Ferrari**](designs/ferrari/DESIGN.md) — Luxury automotive. Chiaroscuro editorial, Rosso Corsa with extreme sparseness

*More coming — contributions welcome.*

## Quick Start

1. Copy any `DESIGN.md` into your project root
2. Tell your AI agent: *"Use DESIGN.md as the design system reference for all UI work"*
3. The agent now has production-grade specs: tokens, states, motion, a11y, code

## vs. awesome-design-md (v1.0)

| Dimension | v1.0 (avg) | v2.0 |
|-----------|-----------|------|
| Typography | 8/10 | 9.5/10 |
| Colors | 7/10 | 9/10 |
| Components | 4/10 | 8.5/10 |
| Spacing | 3/10 | 9/10 |
| Motion | 0/10 | 8/10 |
| Accessibility | 1/10 | 8.5/10 |
| Interactive States | 2/10 | 9/10 |
| Code Snippets | 0/10 | 8/10 |
| Lines per file | ~300 | 600-900 |

## Contributing

We welcome contributions. Each DESIGN.md must follow the [v2.0 template](TEMPLATE.md).

**To add a new design:**
1. Study the target website thoroughly (inspect element, not just visual impression)
2. Fill every section of the template — no "TBD" or "generous" allowed
3. Include exact CSS values, not approximations
4. Test contrast ratios with a real tool (not eyeball)
5. Open a PR with the DESIGN.md + a brief summary of what makes this site's design distinctive

## License

MIT — see [LICENSE](LICENSE)

Design tokens are extracted from publicly visible CSS. We do not claim ownership of any brand's visual identity.

---

Built by [IRIS](https://github.com/soulcore-dev) — Frontend Universal + UX, SOUL CORE ecosystem.
