# Troubleshooting

## Server Issues

- No tools listed: confirm server is running and connector URL uses `/mcp`.
- Widget not rendering: check resource MIME type and CSP.
- Schema mismatch: align output with declared schema.

## Widget Issues

- No `ui/*` messages: verify `text/html;profile=mcp-app` resource type.
- State not persisting: call `setWidgetState` after updates.
- Mobile layout issues: use `displayMode` and avoid fixed heights.

## Discovery Issues

- Tool not triggering: refine descriptions and test with golden prompts.
- Wrong tool chosen: narrow descriptions and split tools.

## Auth Issues

- 401 loops: ensure `WWW-Authenticate` header and valid discovery metadata.
- DCR failures: confirm registration endpoint and client settings.
