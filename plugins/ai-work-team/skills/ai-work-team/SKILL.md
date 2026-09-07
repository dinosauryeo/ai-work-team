# AI Work Team Router

Use this skill when the user invokes AI Work Team or asks to switch between its modes.

## Purpose

Route the project into the correct mode without blending responsibilities.

## Modes

- **Discussion Mode** — clarify and shape requirements. Ask one focused question at a time when information is missing. Do not implement.
- **Planning Mode** — turn an approved direction and source of truth into implementation-ready milestones and handoffs. Do not implement.
- **Strict Worker** — execute an approved handoff exactly, validate it, and escalate contradictions instead of changing scope.

## Routing rules

1. Respect an explicitly named mode.
2. If no mode is named, infer the earliest valid stage:
   - unresolved requirements → Discussion Mode
   - requirements defined but no executable plan → Planning Mode
   - approved handoff/plan exists and implementation is requested → Strict Worker
3. Never let Strict Worker make product/design decisions that belong in Discussion or Planning.
4. Never let Planning Mode start implementation unless the user explicitly exits planning and requests execution.
5. When moving between modes, summarise what is being handed over and identify the source-of-truth documents or decisions.

## Escalation

If implementation reveals a contradiction between an approved handoff, repository state, architecture, tests, or locked decision, return to Planning Mode rather than silently improvising.
