---
name: planning-mode
description: Convert an approved design and project source of truth into bounded implementation milestones, acceptance criteria, validation, and handoff documents without implementing.
---

# Planning Mode

Use this skill after the product/design direction is sufficiently defined and before implementation begins.

## Goal

Transform the approved design and persistent project context into an implementation-ready plan and handoff that another agent/session can execute without hidden context.

## Source-of-truth order

When available, use this priority:

1. Locked decisions / approved source-of-truth documents
2. Approved design handoff
3. Current repository architecture, tests, and implementation state
4. Current user instructions that do not conflict with higher-priority sources
5. Clearly labelled assumptions

If two higher-priority sources conflict, do not silently choose one. Surface the conflict and resolve or escalate it before implementation.

## Behaviour

1. Inspect the relevant repository/documents before planning when available.
2. Confirm the proposed plan does not drift from the source of truth.
3. Break work into bounded milestones or stages small enough to validate independently.
4. For each milestone define objective, in-scope work, out-of-scope work, dependencies, likely affected systems/files, implementation notes where useful, acceptance criteria, validation/tests, exit gate, and known risks.
5. Identify sequencing constraints and what must be locked before later stages begin.
6. Produce persistent handoff documents when the project uses a repository or shared workspace.
7. Do not implement the plan while Planning Mode is active.

## Handoff quality bar

A handoff should be detailed enough that Strict Worker can execute it without needing to redesign the feature or infer missing product requirements.

Avoid vague instructions such as "make it better", "add the system", "fix the UX", or "implement as discussed". Define observable outcomes and boundaries instead.

## Exit gate

Planning Mode is complete only when required milestones are defined, scope boundaries are explicit, acceptance criteria are observable, important dependencies/conflicts are addressed, and the first implementation stage can be executed without new design decisions.

If that is not true, return to Discussion Mode or mark the unresolved issue as a planning blocker.
