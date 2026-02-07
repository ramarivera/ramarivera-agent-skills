# MEMORIES

## Active Context
- Scope: Project
- Current focus: Skill consolidation for OpenAI Apps MCP + ChatGPT App Builder
- Open threads: None
- Last updated: 2026-02-07

## 2026-02-07

### Task: Initialize project memory file
- Problem: Project memory file was missing while AGENTS memory protocol requires both project and global memory context.
- Goal: Create `.codex/MEMORIES.md` with the required structure before substantive work.
- Attempt 1:
- Outcome: Worked
- Evidence/observation: Created project memory file with baseline template and active context.
- Decision/next step: Keep this file updated with durable lessons while executing the current task.
- Suggestion for Ramiro: If you want a stricter template, I can align this file to your preferred headings exactly.
- Reflection (optional): Establishing memory up front reduces missed protocol steps later in the turn.

## 2026-02-07

### Task: Merge external Apps SDK skill content into local skills
- Problem: Two relevant external skills existed (`openai-apps-mcp`, `chatgpt-app-builder`), but local skills lacked several operational and mcp-use workflow patterns.
- Goal: Download both external skill folders without installing, read them fully, and incorporate missing/relevant guidance into both local skills.
- Attempt 1:
- Outcome: Worked
- Evidence/observation: Cloned both source repos into `tmp/`, read all files under the target skill folders, and extracted overlap/gaps against local skill docs.
- Attempt 2:
- Outcome: Worked
- Evidence/observation: Added new references and routing updates across `chatgpt-apps-sdk-docs` and `chatgpt-apps-sdk-ui-docs`; added troubleshooting/runtime lifecycle guidance.
- Durable lessons learned: External skill packs often contain practical runtime failure patterns not present in official-summary docs; importing as scoped companion references preserves signal without bloating default context.
- Repo/tooling discovery: `rg` is unavailable in PATH but works via `mise exec -- rg`; this repo’s skills are reference-router style, so updates should bias toward routing table + focused reference additions.
- Prompt-gap analysis: Missing details were whether to vendor full external skill folders vs distill only relevant sections, and whether to keep downloaded sources in-repo after merge.
- Better prompt suggestion for Ramiro: "Download these two external skill folders into tmp, distill only missing operational/mcp-use guidance into the two local skills, and keep references concise with source provenance notes."
- Reflection (optional): Distilling instead of wholesale copying reduced risk of importing stale/version-locked claims.
- Decision/next step: Keep changes limited to local skill docs/references and present exact file-level deltas for review.
