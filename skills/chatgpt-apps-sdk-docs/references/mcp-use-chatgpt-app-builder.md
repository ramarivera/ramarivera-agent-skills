# mcp-use ChatGPT App Builder Notes

This reference captures practical `mcp-use` patterns that are frequently requested alongside Apps SDK guidance.

## When to Load This

- User explicitly asks about `mcp-use`.
- User asks for a faster widget scaffolding path than manual Apps SDK setup.
- User asks about React widget lifecycle (`useWidget`, pending state, state persistence).

## Bootstrap Path

```bash
npx create-mcp-use-app my-chatgpt-app --template mcp-apps
cd my-chatgpt-app
yarn install
yarn dev
```

## Typical Project Shape

```text
my-chatgpt-app/
├── resources/            # widget entries (auto-registered)
├── public/               # static assets
├── index.ts              # MCP server entry
└── package.json
```

## Widget Authoring Conventions

- Single-file widget: `resources/<widget-name>.tsx`
- Folder widget: `resources/<widget-name>/widget.tsx` as entrypoint
- Export `widgetMetadata` plus default React component
- Prefer explicit loading guards (`isPending`) before reading widget props

## Metadata Model (Important)

- Preferred dual-protocol path: framework-level unified metadata (`metadata`).
- OpenAI-only overrides: `appsSdkMetadata` / `openai/*` keys only when needed.
- CSP metadata should explicitly list domains (`connectDomains`, `resourceDomains`, `frameDomains`).

## Runtime Patterns

- Keep widget state small and UI-scoped.
- Use widget state for view/filter/selection, not full datasets.
- Use tool calls for durable/authoritative updates.

## Tool + Widget Registration Pattern

- Define tool with widget linkage metadata.
- Return widget payload (`props`) and concise model-visible output.
- Keep tool descriptions action-oriented so discovery remains reliable.

## Testing Path

- Local iteration: framework inspector and local server logs.
- ChatGPT validation: add connector in developer mode and test explicit tool invocation prompts.
- Cross-client compatibility: validate behavior in both Apps SDK and MCP Apps-compatible clients if dual-protocol behavior matters.

## Common Failure Checks

- Widget not listed: missing `widgetMetadata` export or wrong file/entry naming.
- Props empty on first render: missing pending-state guard.
- Tool call from widget fails: missing callable-tool metadata on server side.
- CSP blocks resources: domain missing from metadata.

## Source Provenance

Derived from external skill packs:
- `jezweb/claude-skills@openai-apps-mcp`
- `mcp-use/skills@chatgpt-app-builder`

Prefer official OpenAI docs when guidance conflicts.
