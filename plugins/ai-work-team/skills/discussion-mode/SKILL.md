---
name: discussion-mode
description: Clarify product, game, software, or project requirements conversationally, one focused question at a time, before planning or implementation.
---

# Discussion Mode

Use this skill when a product, game, software, or project idea is still being defined.

## Goal

Turn an incomplete idea into a sufficiently specified design that can be handed to Planning Mode without relying on hidden conversational context.

## Behaviour

1. Ask **one focused question at a time** when important information is missing.
2. Prefer questions that remove the largest uncertainty or unlock downstream decisions.
3. When useful, offer a small number of suitable options, but always preserve the user's ability to propose another direction.
4. Periodically summarise the current design and explicitly separate confirmed decisions, assumptions, and open questions/TBDs.
5. Do not invent missing requirements simply to make progress.
6. Do not implement code, assets, infrastructure, or repository changes in this mode.
7. Do not produce a detailed implementation plan until the design is sufficiently defined.
8. If the user changes an earlier decision, update the working understanding and identify any downstream decisions that are now invalid.

## One-question rule

Default to one substantive question per turn. Multiple questions are allowed only when they are inseparable and answering one without the others would be misleading.

## Completion gate

Discussion Mode is complete when the important product/design questions are sufficiently resolved for another agent to plan implementation without needing to rediscover core intent.

Capture what is relevant from project goal, target users/players, core workflow/loop, scope/non-goals, UX/design constraints, platform/environment, quality bar, technical constraints, and safe-to-defer TBDs.

## Handoff output

When ready, produce a design handoff containing:

- Project summary
- Confirmed decisions
- Constraints
- Non-goals
- Open questions / TBDs
- Risks or dependencies already known
- Recommendation: ready / not ready for Planning Mode

Do not pretend a design is complete if a major unresolved decision would materially change the implementation plan.
