# Build ChatGPT UI

## window.openai Basics

- `toolInput` and `toolOutput` are the primary data bridge.
- Listen for `openai:set_globals` to react to updates.
- Use `callTool` for UI-initiated tool calls, and ensure the target tool is marked `openai/widgetAccessible`.

## Common APIs

- `sendFollowUpMessage({ prompt })` to insert a user-authored message.
- `setWidgetState(state)` to persist widget state for that message.
- `uploadFile(file)` and `getFileDownloadUrl({ fileId })` for file uploads (common image-first path, verify accepted MIME list for current host/runtime).
- `requestDisplayMode({ mode })` for fullscreen or PiP.
- `requestModal({ template })` for host modals.
- `openExternal({ href })` for safe external links.

## Widget State

- Widget state is message-scoped, not global.
- Use `ui/update-model-context` when the model should see UI state.
- Keep widget state small (under about 4k tokens).
- Persist identifiers, filters, and view mode in state; avoid storing large datasets/history in widget state.

## Framework Runtime Notes

- Framework wrappers (for example `mcp-use` with `useWidget`) should treat the first paint as pending and render a loading state before dereferencing props.
- Keep protocol-specific metadata explicit:
  - Unified metadata paths when supported by the framework.
  - OpenAI-specific overrides via `openai/*` metadata only when needed.

## Localization

- Read `window.openai.locale` and format dates/numbers accordingly.
- Use a localization library for translations.

## Bundling

- Use a bundler (esbuild, Vite) to create a single module.
- Inline JS and CSS into the resource HTML or host them on a CDN.
