---
name: Bug / AI output issue
about: The AI produced wrong output when using a DESIGN.md from this repo
title: "[bug] {brand} — AI generated wrong {component/token}"
labels: bug, ai-output
assignees: ''
---

## DESIGN.md used

`designs/{brand}/DESIGN.md`

## AI agent / tool

{e.g., Claude 4 Opus via Claude Code / Cursor / Copilot / ChatGPT}

## Prompt used

```
{paste the exact prompt you gave the AI}
```

## Expected output

What the AI should have produced (based on the DESIGN.md):

```jsx
{paste expected code or describe expected behavior}
```

## Actual output

What the AI actually produced:

```jsx
{paste actual code or describe actual behavior}
```

## Root cause (if known)

Where in the DESIGN.md is the ambiguity or gap that caused the AI to guess wrong?

- [ ] Token value was ambiguous
- [ ] State was not documented
- [ ] Code snippet was missing
- [ ] Philosophy not emphasized (e.g., "OpenType features required")
- [ ] Contrast issue not flagged
- [ ] Other: {describe}

## Proposed fix

What change to the DESIGN.md would prevent this in future?
