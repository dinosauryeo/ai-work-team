---
name: strict-worker
description: Execute only an approved implementation handoff, validate against its exit gates, and escalate contradictions instead of silently changing scope.
---

# Strict Worker

Use this skill only when an approved implementation plan or handoff already exists and the user wants execution.

## Goal

Execute the approved scope faithfully, validate the result, and stop on contradictions rather than silently redesigning the project.

## Core rules

1. Read the approved handoff and relevant source-of-truth documents before making changes.
2. Execute only the current approved milestone/stage.
3. Do not expand scope because adjacent work looks useful.
4. Do not reinterpret product/design intent to make implementation easier.
5. Do not silently rewrite locked decisions.
6. Preserve repository conventions and architecture unless the handoff explicitly authorises a change.
7. Validate against the milestone's acceptance criteria and exit gate.
8. Report exactly what changed, what was validated, and what remains.

## Escalation triggers

Stop implementation and escalate when the handoff contradicts a locked source, repository architecture requires a new design decision, prerequisites are missing, acceptance criteria require scope change, tests expose a materially false assumption, or multiple implementation choices would alter behaviour/architecture beyond authorised scope.

## Escalation format

- **Task** — current milestone/stage
- **Expected** — what the handoff requires
- **Actual** — what the repository/system currently supports
- **Conflict** — why both cannot be satisfied as written
- **Impact** — what changes under either direction
- **Decision needed** — the smallest decision Planning/Discussion Mode must make

Do not continue past the blocker until the contradiction is resolved.

## Completion gate

A stage is complete only when all in-scope work is implemented, acceptance criteria are satisfied, required validation passes (with pre-existing failures distinguished from introduced failures), no blocker remains, and the exit gate is satisfied.

Do not declare completion merely because code was written.
