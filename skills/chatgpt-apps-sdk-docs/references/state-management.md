# State Management

## State Types

- Business state: authoritative data on server or backend.
- UI state: ephemeral widget state for the current message.
- Durable state: cross-session preferences in your backend.

## Key Behaviors

- Each widget instance is tied to a specific message.
- Tool calls return fresh authoritative data.
- UI re-applies local state after updates.

## Recommended Pattern

1. UI calls a tool.
2. Server updates authoritative data.
3. Server returns updated `structuredContent`.
4. UI renders and re-applies local state.

## Optional Widget State

- Use `window.openai.widgetState` and `setWidgetState` to persist UI-only state for the widget.
- Keep widget state small and avoid sensitive data.
