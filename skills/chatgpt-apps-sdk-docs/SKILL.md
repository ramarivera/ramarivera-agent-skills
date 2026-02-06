---
name: chatgpt-apps-sdk-docs
description: Concise reference and workflow for the ChatGPT Apps SDK (MCP servers, widget UI, auth, state, deployment, submission, UX/UI). Use when answering questions about building, testing, deploying, or submitting ChatGPT apps/connectors, or when summarizing Apps SDK concepts and requirements.
---

# ChatGPT Apps SDK Docs

## Overview

Use this skill to answer Apps SDK questions quickly and consistently using the bundled references. Keep responses grounded in the documented flows, schemas, and constraints.

## Quick Workflow

1. Identify the topic area (plan, build, UI, auth, state, deploy, submit, UX/UI, reference APIs).
2. Open the matching reference file in `references/` and pull the needed details.
3. If the user asks for the latest changes or requests verification, check the official OpenAI docs before answering.

## Documentation Map

- `references/quickstart.md`: End-to-end quickstart, local dev, MCP inspector, add app to ChatGPT.
- `references/planning.md`: Use cases, tool design, component planning.
- `references/build-mcp-server.md`: MCP server setup, resources, tools, metadata, CSP, annotations, file params, search/fetch.
- `references/build-chatgpt-ui.md`: `window.openai` bridge, widget APIs, state, localization, bundling.
- `references/auth.md`: OAuth 2.1 requirements, protected resource metadata, DCR, linking UI.
- `references/state-management.md`: Authoritative vs UI vs durable state patterns.
- `references/monetization.md`: External checkout vs Instant Checkout (beta), requestCheckout flow.
- `references/deploy.md`: Local dev, hosting options, connect, testing, submission.
- `references/ux-ui-guidelines.md`: UX principles, UI guidelines, display modes, visual rules.
- `references/security-privacy.md`: Security, privacy, CSP, prompt injection guidance.
- `references/optimize-metadata.md`: Metadata tuning and golden prompts.
- `references/app-submission-guidelines.md`: App submission requirements and policy highlights.
- `references/reference-window-openai.md`: `window.openai` API and tool/resource metadata reference.
- `references/troubleshooting.md`: Common failure modes and fixes.

## Notes

- Prefer the bundled references for answers; they are the baseline.
- When the user needs the latest policy details or release changes, verify with official OpenAI docs and call out the date you checked.
- Keep answers concise and action oriented; include code snippets only when asked or when it removes ambiguity.
