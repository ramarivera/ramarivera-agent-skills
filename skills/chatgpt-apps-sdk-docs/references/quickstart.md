# Quickstart Summary

## Core Requirements

- Build an MCP server that defines tools and exposes `/mcp`.
- Optionally build a web component rendered in an iframe inside ChatGPT.

## Minimal UI Pattern

- Read initial state from `window.openai.toolOutput`.
- Listen for `openai:set_globals` to refresh state after tool calls.
- Use `window.openai.callTool(name, payload)` to invoke tools from the UI.

## MCP Server Basics

1. Install SDK and schema helpers.
2. Register UI resource (template) if you have a widget.
3. Register tools with input schema, descriptions, and metadata.
4. Return `structuredContent` for the model and `_meta` for the widget.

## Local Run

1. Start server at `http://localhost:<port>/mcp`.
2. Ensure `type: module` if using Node ESM.
3. Use MCP Inspector to test list-tools and call-tool.

## Expose to ChatGPT

1. Tunnel your server (ngrok or similar).
2. In ChatGPT developer mode, create a connector with the HTTPS `/mcp` URL.
3. Add the connector to a chat and test prompts.

## Refreshing

- After tool or metadata changes, refresh the connector in ChatGPT settings.
