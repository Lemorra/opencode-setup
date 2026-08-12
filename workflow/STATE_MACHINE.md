# Workflow State Machine

The OpenCode setup treats project execution as a small, explicit state machine. The state is represented by artifacts in the target project.

## States

| State | Required artifact | Next state |
|---|---|---|
| `NEW` | none | `STRUCTURED` |
| `STRUCTURED` | `artifacts/problem.md` | `FEASIBILITY` or `ROADMAP` |
| `FEASIBILITY` | `artifacts/feasibility.md` | `ROADMAP` |
| `ROADMAP` | `artifacts/roadmap.md` | `MILESTONED` |
| `MILESTONED` | `artifacts/milestones.md` | `BUILDING` |
| `BUILDING` | implementation + validation | `REVIEW` |
| `REVIEW` | `artifacts/review.md` | `DONE` or `REWORK` |
| `REWORK` | actionable review findings | `BUILDING` |
| `DONE` | passing review | terminal |

## Transition rules

### NEW → STRUCTURED
Create or update `artifacts/problem.md`.

### STRUCTURED → FEASIBILITY
Use this when feasibility is materially uncertain: new technology, external integration, unusual constraints, hardware/runtime limits, significant scale, cost or security uncertainty.

### STRUCTURED → ROADMAP
Skip feasibility only when the implementation approach is already sufficiently established and low-risk.

### FEASIBILITY → ROADMAP
The feasibility artifact must contain a recommendation, known risks and validation steps.

### ROADMAP → MILESTONED
The roadmap must have a coherent implementation strategy and definition of done.

### MILESTONED → BUILDING
Milestones must have acceptance criteria and dependency order.

### BUILDING → REVIEW
Run relevant tests/checks and record their result before review.

### REVIEW → REWORK
Any BLOCKER or HIGH finding requires rework. MEDIUM findings should normally be resolved unless explicitly accepted. LOW/NOTE findings do not block completion.

### REVIEW → DONE
The reviewer returns `PASS`, or all blocking findings have been resolved and a follow-up review passes.

## State detection

The manager should inspect the target project's artifact directory at the start of a workflow. Missing artifacts indicate that a stage has not completed. Existing artifacts are evidence, not proof of correctness; inspect their status and consistency before advancing.

## Important constraint

The setup repository defines the workflow. The target project owns its `artifacts/` state. Never write a project's workflow artifacts into this configuration repository.
