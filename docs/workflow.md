# Workflow

AI Work Team separates project work into three explicit stages so requirements, planning, and implementation do not drift into each other.

## 1. Discussion Mode

Use this while the project is still being defined.

Outputs should converge toward a stable design handoff containing confirmed decisions, constraints, non-goals, safe-to-defer TBDs, and any known risks.

The model should ask one focused question at a time by default and should not implement.

## 2. Planning Mode

Use this after the design is sufficiently stable.

Planning Mode reads the design handoff plus any repository/source-of-truth documents, then produces bounded milestones with acceptance criteria and exit gates.

A milestone should be small enough that Strict Worker can complete and validate it independently.

## 3. Strict Worker

Use this only after a milestone/handoff is approved.

Strict Worker executes the current scope and validates it. It does not expand the milestone or make design decisions on its own.

If reality contradicts the plan, it escalates rather than improvising.

## Return paths

The workflow is intentionally reversible:

```text
Discussion → Planning → Strict Worker
    ↑           ↑            |
    └───────────┴─ escalation ┘
```

Typical return cases:

- Missing product decision → Discussion Mode
- Plan/repository contradiction → Planning Mode
- Scope change requested during execution → Planning Mode first
- Acceptance criteria reveal ambiguous intent → Discussion or Planning depending on the ambiguity

## Persistent context

For longer projects, keep important decisions and handoffs in persistent project files rather than relying on chat history. A new session should be able to recover intent by reading those files.
