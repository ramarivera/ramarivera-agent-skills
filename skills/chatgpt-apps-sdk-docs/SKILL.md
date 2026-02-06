---
name: chatgpt-apps-sdk-docs
description: Concise reference and workflow for the ChatGPT Apps SDK (MCP servers, widget UI, auth, state, deployment, submission, UX/UI). Use when answering questions about building, testing, deploying, or submitting ChatGPT apps/connectors, or when summarizing Apps SDK concepts and requirements.
---

# ChatGPT Apps SDK Docs

## Overview

Use this skill to answer Apps SDK questions quickly and consistently using the bundled references. Keep responses grounded in the documented flows, schemas, and constraints.

## Quick Workflow

1. Identify the topic area (plan, build, UI, auth, state, deploy, submit, UX/UI, reference APIs).
2. Open the smallest matching file set in `references/` (usually one primary file, optionally one secondary file) and pull only the needed details.
3. If the user asks for the latest changes or requests verification, check the official OpenAI docs before answering.

## Intent Routing (MANDATORY)

| User intent | Primary reference | Optional secondary reference |
|---|---|---|
| Initial setup / local dev / connecting app | `references/quickstart.md` | `references/deploy.md` |
| Tool/server implementation | `references/build-mcp-server.md` | `references/reference-window-openai.md` |
| ChatGPT UI bridge / widget behavior | `references/build-chatgpt-ui.md` | `references/reference-window-openai.md` |
| Auth / OAuth / account linking | `references/auth.md` | `references/security-privacy.md` |
| State strategy questions | `references/state-management.md` | `references/planning.md` |
| UX and UI guidance | `references/ux-ui-guidelines.md` | `references/optimize-metadata.md` |
| Submission / policy readiness | `references/app-submission-guidelines.md` | `references/security-privacy.md` |

## Do NOT Load (unless explicitly needed)

- Do not load all reference files by default.
- Do not load monetization docs unless checkout/pricing is part of the request.
- Do not load submission/policy docs for pure implementation questions.

## NEVER Do

- Never invent APIs, tool metadata fields, or SDK behavior not present in the references.
- Never claim “latest” without verifying against official docs and stating the date checked.
- Never answer from memory when a mapped local reference exists.
- Never omit file-path citations for non-trivial answers.

## Fallback Rules

- If no direct topic match exists, start with `references/planning.md` and one closest technical file.
- If two references conflict, prefer the most specific reference for the asked feature and explicitly note the conflict.
- If requested detail is absent in references, say it is absent and point to the nearest related file.
- For latest/policy-sensitive requests, verify with official OpenAI docs and include the verification date.

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
