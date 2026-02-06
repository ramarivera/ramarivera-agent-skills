---
name: chatgpt-apps-sdk-ui-docs
description: "Retrieve and route OpenAI Apps SDK UI documentation from a curated local corpus. Use when implementing, reviewing, or troubleshooting Apps SDK UI usage in code, including component APIs and props, usage snippets, installation steps, design tokens, colors/icons, dark mode, responsive design, typography, and transition primitives."
---

# Apps SDK UI Docs

Use this skill as a deterministic router over the local Apps SDK UI corpus in `references/`.

## Core Workflow

1. Identify the topic and requested depth.
2. Route to the smallest relevant file set using the map below.
3. Read only those files.
4. Answer with direct guidance:
- Include import path and minimal usage snippet when asked to implement.
- Include prop details from `## Reference` or `## Props` sections when asked about APIs.
- Include caveats when content appears ambiguous or malformed.
5. Cite the exact reference file paths used.

## Routing Map

### Project setup and orientation
- `references/overview/introduction.md`
- `references/overview/installation.md`

### Concepts
- Dark mode: `references/concepts/dark-mode.md`
- Responsive design: `references/concepts/responsive-design.md`
- Typography: `references/concepts/typography.md`

### Foundations
- Colors: `references/foundations/colors.md`
- Design tokens: `references/foundations/design-tokens.md`
- Icons catalog: `references/foundations/icons.md`

### Components
- Alert: `references/components/alert.md`
- Avatar: `references/components/avatar.md`
- AvatarGroup: `references/components/avatargroup.md`
- Badge: `references/components/badge.md`
- Button: `references/components/button.md`
- ButtonLink: `references/components/buttonlink.md`
- Checkbox: `references/components/checkbox.md`
- CodeBlock: `references/components/codeblock.md`
- CopyTooltip: `references/components/copytooltip.md`
- DatePicker: `references/components/datepicker.md`
- DateRangePicker: `references/components/daterangepicker.md`
- EmptyMessage: `references/components/emptymessage.md`
- Indicators: `references/components/indicators.md`
- Input: `references/components/input.md`
- Markdown: `references/components/markdown.md`
- Menu: `references/components/menu.md`
- Popover: `references/components/popover.md`
- RadioGroup: `references/components/radiogroup.md`
- SegmentedControl: `references/components/segmentedcontrol.md`
- Select: `references/components/select.md`
- SelectControl: `references/components/selectcontrol.md`
- Slider: `references/components/slider.md`
- Switch: `references/components/switch.md`
- TagInput: `references/components/taginput.md`
- TextArea: `references/components/textarea.md`
- TextLink: `references/components/textlink.md`
- Tooltip: `references/components/tooltip.md`

### Transitions
- Animate: `references/transitions/animate.md`
- AnimateLayout: `references/transitions/animatelayout.md`
- AnimateLayoutGroup: `references/transitions/animatelayoutgroup.md`
- SlotTransitionGroup: `references/transitions/slottransitiongroup.md`
- TransitionGroup: `references/transitions/transitiongroup.md`

## Fast Lookup

- Use `references/doc-map.md` for section-first navigation.
- Use `references/manifest.tsv` for canonical URL-to-file mapping.
- Use `references/manifest.json` when JSON parsing is easier.

## Lookup Commands

```bash
# Find a topic or component file quickly
rg -n "button|select|dark mode|design token" references/doc-map.md references/**/*.md

# Resolve the exact local file from canonical URL path slug
rg -n "components-button--docs" references/manifest.tsv

# Open only the relevant section
rg -n "^## (Usage|Reference|Props)$" references/components/button.md
```

## Output Rules

- Prefer concise, implementation-ready guidance over broad summaries.
- Preserve literal import paths from references when available.
- Do not invent props or defaults; report only what is present in references.
- If requested information is absent, say so and point to nearest related file.
