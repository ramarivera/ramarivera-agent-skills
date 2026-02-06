# Build MCP Server

## Core Flow

1. Register UI template as a resource with MIME type `text/html;profile=mcp-app`.
2. Register tools with schema, descriptions, and `_meta.ui.resourceUri`.
3. Handle tool calls and return `structuredContent`, `content`, and `_meta`.
4. Serve `/mcp` over HTTPS for ChatGPT access.

## Resource Registration

- Use a unique resource URI for cache busting.
- Include `_meta.ui.csp` and `_meta.ui.domain` for submission.
- Optional: `_meta.openai/widgetDescription` and `prefersBorder` hints.

## Tool Descriptors

- Provide name, title, description, input schema.
- Use `_meta.ui.resourceUri` or `_meta["openai/outputTemplate"]`.
- Consider `_meta.ui.visibility` to limit model vs widget access.

## Annotations

- `readOnlyHint: true` for read-only tools.
- `openWorldHint: true` for tools that act outside the account.
- `destructiveHint: true` for delete or overwrite.

## Responses

- `structuredContent` is visible to the model and the widget.
- `_meta` is visible only to the widget.
- Keep `structuredContent` concise and idempotent.

## File Params

- Declare `_meta["openai/fileParams"]` for top-level file fields.
- File inputs are `{ download_url, file_id }` objects.

## CSP and Domains

- `connectDomains` for API calls.
- `resourceDomains` for static assets.
- `frameDomains` only if iframes are essential (higher scrutiny).

## Company Knowledge

- Implement `search` and `fetch` tool schemas to be eligible.
- Return JSON wrapped inside a single `content` item with `type: "text"`.
