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

## Scenario Triggers (MANDATORY)

| User intent | Primary reference | Optional secondary reference |
|---|---|---|
| Component API/props question | `references/components/<component>.md` | `references/doc-map.md` |
| Visual tokens/colors/icons | `references/foundations/design-tokens.md`, `references/foundations/colors.md`, or `references/foundations/icons.md` | `references/doc-map.md` |
| Theming / dark mode / responsive / typography | `references/concepts/dark-mode.md`, `references/concepts/responsive-design.md`, or `references/concepts/typography.md` | `references/overview/introduction.md` |
| mcp-use widget runtime/lifecycle/state patterns | `references/concepts/mcp-use-widget-runtime.md` | `references/overview/introduction.md` |
| Animation/transitions | `references/transitions/<topic>.md` | `references/doc-map.md` |
| Setup / install | `references/overview/installation.md` | `references/overview/introduction.md` |

## Do NOT Load (unless needed)

- Do not load all component files for a single component question.
- Do not load transition docs for non-animation questions.
- Do not load foundations docs when the user asks only about one component prop.
- Do not load overview docs when the request is strictly API-level and already scoped.
- Do not load mcp-use runtime notes unless the user asks about framework lifecycle, pending-state behavior, or metadata mapping.

## Routing Map

### Project setup and orientation
- `references/overview/introduction.md`
- `references/overview/installation.md`

### Concepts
- Dark mode: `references/concepts/dark-mode.md`
- Responsive design: `references/concepts/responsive-design.md`
- Typography: `references/concepts/typography.md`
- mcp-use runtime/lifecycle: `references/concepts/mcp-use-widget-runtime.md`

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

## NEVER Do

- Never invent component props, defaults, or import paths.
- Never summarize broadly when the user requested exact API details.
- Never omit exact reference file paths when returning technical guidance.
- Never pretend a section exists (`Usage`, `Reference`, `Props`) if it is not present in the file.

## Fallback Rules

- If a component file lacks `Usage`/`Reference`/`Props`, extract available headings and state what is missing.
- If component name is ambiguous, resolve via `references/doc-map.md` first, then open one best-match component file.
- If a requested detail is absent, explicitly say it is not documented in the loaded references and point to nearest related file.
