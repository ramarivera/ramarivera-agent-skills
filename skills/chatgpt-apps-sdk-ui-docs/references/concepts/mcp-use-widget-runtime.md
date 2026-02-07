# mcp-use Widget Runtime Patterns

This note complements Apps SDK UI references with framework-level patterns seen in `mcp-use` widget projects.

## When to Use

- User is building widgets with `mcp-use`.
- User asks why props/state/tool-calls behave differently between first paint and settled render.
- User asks how to map metadata between framework abstractions and OpenAI-specific keys.

## Widget Lifecycle Pattern

- Widget can render before tool execution is complete.
- Always guard first render with pending/loading checks before reading props.
- Keep fallback UI deterministic to avoid layout jumps.

## State Pattern

- Persist only UI state (selected IDs, filters, tab/view mode).
- Avoid storing full datasets/history in widget state.
- Use tool calls for durable data and authoritative state transitions.

## Metadata Mapping Pattern

- Prefer unified framework metadata for dual-protocol compatibility.
- Add OpenAI-specific metadata only for host-specific behavior.
- Keep CSP domain lists explicit and minimal.

## Component Tool-Call Pattern

- Component-driven tool calls require server-side callable-tool enablement.
- Validate this at both descriptor level and runtime, not only in component code.

## Static Asset Pattern

- Use public/static asset folders with stable paths.
- Ensure widget CSP/resource domain settings include external asset origins when needed.

## Common Failure Checks

- Widget missing in tool list: entrypoint/export naming mismatch.
- Props undefined on first render: missing pending guard.
- Tool call from UI fails: callable-tool flag not set server-side.
- CSP violation: missing domain in configured policy.

## Source Provenance

Derived from:
- `mcp-use/skills@chatgpt-app-builder`
- `jezweb/claude-skills@openai-apps-mcp`
