# Handoff Protocol

Handoffs are the contract between AI Work Team modes.

## Design handoff

Produced by Discussion Mode.

Recommended structure:

```markdown
# Design Handoff

## Project summary
## Confirmed decisions
## Constraints
## Non-goals
## Open questions / TBDs
## Known risks / dependencies
## Readiness for Planning Mode
```

## Implementation handoff

Produced by Planning Mode for Strict Worker.

Recommended structure:

```markdown
# <Milestone> Handoff

## Objective
## Source-of-truth references
## Preconditions
## In scope
## Out of scope
## Expected affected systems/files
## Implementation requirements
## Acceptance criteria
## Validation
## Exit gate
## Risks / known constraints
```

## Escalation

Produced by Strict Worker when the approved handoff cannot be executed faithfully.

```markdown
# ESCALATION

## Task
<current milestone/stage>

## Expected
<what the approved handoff requires>

## Actual
<what the repository/system currently supports>

## Conflict
<why the expected and actual states cannot both be satisfied>

## Impact
<what changes under the plausible resolutions>

## Decision needed
<smallest decision required from Planning or Discussion Mode>
```

## Rules

- Handoffs should be understandable without private chat context.
- References to project files should use stable repository paths where possible.
- Acceptance criteria should describe observable outcomes.
- Strict Worker must not rewrite the handoff simply to avoid an escalation.
- If a new decision materially changes later milestones, Planning Mode should update those handoffs before execution resumes.
