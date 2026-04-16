# Contributing to DESIGN.md v2.0

## Rules

1. **Every section is mandatory** — the 14-section format exists because v1.0 proved that missing sections = broken AI output
2. **No vague values** — "generous spacing" is banned. Write `96px` or `var(--space-section-lg)`
3. **Contrast ratios are measured, not guessed** — use WebAIM, Stark, or browser DevTools
4. **States are not optional** — every interactive component needs: default, hover, active, focus, disabled (minimum)
5. **Code snippets must compile** — JSX should be valid React, CSS should be valid CSS
6. **Test with an AI agent** — before submitting, paste your DESIGN.md into a project and ask an AI to generate a component. If it produces wrong output, your spec is incomplete

## Process

1. Open an issue describing which site you want to add
2. Get approval from maintainers
3. Fork, create branch, write the DESIGN.md following [TEMPLATE.md](TEMPLATE.md)
4. Open PR with:
   - The DESIGN.md file in `designs/{site-name}/DESIGN.md`
   - A brief note on what makes this site's design distinctive
   - Confirmation that you tested contrast ratios

## Quality Checklist

- [ ] All 14 sections present
- [ ] Color tokens include CSS custom property names
- [ ] Typography includes responsive scaling (clamp or breakpoint-based)
- [ ] Component catalog covers 15+ components
- [ ] State matrix covers all interactive components
- [ ] Spacing values are exact (px, rem, or CSS var)
- [ ] Motion section includes durations, easings, and reduced-motion fallback
- [ ] Accessibility section includes measured contrast ratios
- [ ] At least 3 code snippets (JSX + CSS)
- [ ] Do's and Don'ts include at least 8 items each
- [ ] Agent prompts reference exact tokens from the document
- [ ] File is 600+ lines (depth, not padding)
