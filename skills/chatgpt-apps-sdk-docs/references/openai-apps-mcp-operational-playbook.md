# OpenAI Apps MCP Operational Playbook

Field-tested runtime notes for Apps SDK + MCP deployments, especially on Cloudflare Workers and other serverless environments.

## When to Load This

- User asks for Cloudflare-specific MCP deployment help.
- User reports runtime issues (CORS, widget 404, tool invocation not available, state mismatch).
- User asks for production hardening checklists instead of API-only docs.

## Critical Checklist

- MCP endpoint reachable over HTTPS at the configured connector URL.
- CORS policy allows ChatGPT origin on MCP routes.
- Tool metadata includes output template pointer (`openai/outputTemplate`) for widget-backed tools.
- Widget resources and metadata are registered and served consistently.
- Widget-invoked tool calls are explicitly allowed (`openai/widgetAccessible`).
- CSP metadata includes only required domains.
- Widget state remains compact and message-scoped.

## High-Frequency Failures and Fixes

### 1) CORS blocked requests

- Symptom: connector can reach server metadata but calls fail in ChatGPT.
- Check: CORS middleware/policy for ChatGPT origin on `/mcp` routes.
- Fix: explicit allowlist, avoid permissive wildcard-only assumptions in production.

### 2) Widget not rendering / 404 on template

- Symptom: tool executes but widget is missing.
- Check: template URI in tool metadata matches registered resource URI.
- Fix: keep URI paths deterministic and test with inspector before ChatGPT.

### 3) Widget API calls fail from component

- Symptom: `callTool` from UI silently fails or is rejected.
- Check: tool descriptor has `openai/widgetAccessible`.
- Fix: mark component-callable tools explicitly and re-test end-to-end.

### 4) State appears lost

- Symptom: widget state disappears after user continues chat.
- Check: message-scoped semantics and `setWidgetState` usage.
- Fix: keep state as lightweight UI context; persist durable data via tools/backend.

### 5) Serverless transport/session mismatches

- Symptom: multi-step transport failures in stateless hosting.
- Check: whether the chosen transport assumes process-local session state.
- Fix: prefer streamable HTTP style flows in serverless environments.

### 6) Cloudflare static asset binding mismatch

- Symptom: runtime fetch errors for widget HTML/static assets.
- Check: binding key in configuration exactly matches runtime binding access.
- Fix: align Worker config and runtime code binding names.

### 7) Edge runtime API limitations

- Symptom: certain SDK APIs fail in edge runtime environments.
- Check: whether feature depends on APIs not supported in edge constraints.
- Fix: route through tool arguments or non-edge flow for unsupported features.

## Runtime Tuning Notes

- Keep tool latency low for responsive widget UX.
- Prefer cached reads and paginated responses for heavy data flows.
- Minimize widget payload size and avoid sending redundant large objects.

## Verification Flow

1. Validate with local inspector and raw MCP calls.
2. Validate with ChatGPT connector in developer mode.
3. Validate with realistic tool prompts and follow-up UI interactions.
4. Re-check OAuth redirect settings for local vs production domains.

## Source Provenance

Derived from external skill packs:
- `jezweb/claude-skills@openai-apps-mcp`
- `mcp-use/skills@chatgpt-app-builder`

Treat this file as an operational companion; prefer official OpenAI documentation for canonical API behavior and policy.
