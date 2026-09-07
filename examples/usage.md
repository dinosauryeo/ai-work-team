# Usage Examples

## Discussion Mode

```text
@AI Work Team, discussion mode
I want to build a small management game. Ask one focused question at a time, summarise confirmed decisions as we go, and do not implement anything yet.
```

Expected behaviour: the model explores requirements, offers options where helpful, tracks decisions/TBDs, and finishes with a design handoff when the concept is sufficiently specified.

## Planning Mode

```text
@AI Work Team, planning mode
Read the approved design and current repository source of truth. Break the work into implementation milestones with scope, acceptance criteria, validation, and exit gates. Do not implement yet.
```

Expected behaviour: the model verifies the source of truth, identifies conflicts, then produces bounded handoff files rather than writing code.

## Strict Worker

```text
@AI Work Team, strict worker
Execute milestone M2.1 exactly as written in its approved handoff. Validate the exit gate. If the repository contradicts the handoff, stop and return an escalation instead of changing scope.
```

Expected behaviour: the model executes only the approved milestone, runs relevant validation, and reports completion only when the exit gate passes.

## Example escalation

```text
# ESCALATION

## Task
M3.1 customer purchase attempts

## Expected
Each customer must attempt 1–3 different product purchases.

## Actual
The current production scene can expose only two purchasable product types at once.

## Conflict
A three-attempt requirement cannot always produce three distinct products under the current locked scene constraint.

## Impact
Either the milestone rule or the earlier product-availability constraint must change.

## Decision needed
Planning Mode must decide which requirement has priority and update the handoff/source of truth before execution resumes.
```
