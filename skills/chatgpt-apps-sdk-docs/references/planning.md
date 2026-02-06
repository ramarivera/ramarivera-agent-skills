# Planning: Use Cases, Tools, Components

## Use Case Research

- Capture user jobs-to-be-done and the prompts users will say.
- Define direct prompts, indirect prompts, and negative prompts.
- Document personas, context, and success criteria per scenario.

## Tool Design

- One job per tool. Separate read from write tools.
- Keep inputs explicit and minimal. Use enums when possible.
- Define predictable outputs with IDs and status fields.
- Write descriptions that start with "Use this when...".

## Components

- Decide viewer vs editor, single-shot vs multi-turn.
- Choose inline vs fullscreen vs PiP based on task complexity.
- Define structuredContent payload and what lives in `_meta`.
- Plan state ownership: server data, UI state, durable state.
