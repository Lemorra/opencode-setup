# Artifact Contract

Artifacts are the hand-off protocol between workflow stages.

## `problem.md`

Purpose: define what must be solved.

Must contain:
- objective
- desired outcome
- requirements
- constraints
- assumptions
- unknowns
- success criteria

## `feasibility.md`

Purpose: determine whether and how the goal should be implemented.

Must contain:
- findings
- alternatives when meaningful
- recommendation
- risks / unknowns
- validation steps
- decision

## `roadmap.md`

Purpose: describe the implementation strategy and sequence.

Must contain:
- goal
- strategy
- key decisions
- phases
- critical path
- risks
- definition of done

## `milestones.md`

Purpose: turn the roadmap into executable work.

Must contain:
- milestones
- tasks
- dependencies
- acceptance criteria
- execution order

## `review.md`

Purpose: independently evaluate the implementation.

Must contain:
- verdict
- findings
- test coverage
- residual risks

## `status.md`

Purpose: provide a concise pointer to the current workflow state.

## Handoff rule

An agent should read the latest relevant artifacts before acting. It should not silently replace an earlier decision. If new evidence invalidates an earlier artifact, explicitly identify the changed assumption and update the artifact before proceeding.
