# Reference: window.openai and Metadata

## window.openai Capabilities

- `toolInput`, `toolOutput`, `toolResponseMetadata`
- `widgetState`, `setWidgetState(state)`
- `callTool(name, args)`
- `sendFollowUpMessage({ prompt })`
- `uploadFile(file)` and `getFileDownloadUrl({ fileId })`
- `requestDisplayMode({ mode })`
- `requestModal({ template })`
- `notifyIntrinsicHeight({ height })`
- `openExternal({ href })`
- `setOpenInAppUrl({ href })`

## Tool Descriptor _meta

- `openai/outputTemplate`: resource URI for the widget HTML.
- `openai/toolInvocation/invoking` and `openai/toolInvocation/invoked`.
- `openai/fileParams`: list of top-level file fields.

## Resource _meta

- `openai/widgetDescription` for a short widget summary.
- `openai/widgetPrefersBorder` to request a bordered card.
- `openai/widgetCSP` with connect/resource/frame/redirect domains.
- `openai/widgetDomain` for a dedicated origin.
