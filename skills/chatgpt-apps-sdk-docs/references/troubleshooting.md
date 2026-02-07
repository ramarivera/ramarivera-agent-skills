# Troubleshooting

## Server Issues

- No tools listed: confirm server is running and connector URL uses `/mcp`.
- Widget not rendering: check resource MIME type and CSP.
- Schema mismatch: align output with declared schema.
- CORS failures in ChatGPT: allow `https://chatgpt.com` on MCP routes.
- Stateless deployment transport mismatch: prefer streamable HTTP over legacy stateful SSE on serverless hosts.
- Cloudflare static widget serving issues: ensure Worker binding names match runtime usage (`ASSETS` vs configured binding).

## Widget Issues

- No `ui/*` messages: verify `text/html;profile=mcp-app` resource type.
- State not persisting: call `setWidgetState` after updates.
- Mobile layout issues: use `displayMode` and avoid fixed heights.
- Widget `callTool` failing silently: mark callable tools with `openai/widgetAccessible`.
- Large state payloads degrading UX: keep widget state below roughly 4k tokens and persist only UI state.
- First render has empty data: handle pending/loading lifecycle before reading tool output.

## Discovery Issues

- Tool not triggering: refine descriptions and test with golden prompts.
- Wrong tool chosen: narrow descriptions and split tools.
- Tool unavailable from component UI: confirm widget tool annotations include `openai/outputTemplate` and callable metadata.

## Auth Issues

- 401 loops: ensure `WWW-Authenticate` header and valid discovery metadata.
- DCR failures: confirm registration endpoint and client settings.
- Local vs production callback confusion: configure separate OAuth clients or redirect URIs per environment.
