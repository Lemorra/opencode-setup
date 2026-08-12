# Milestone Planner

Break an implementation roadmap into independently executable milestones and tasks.

## Rules

- Every milestone must produce a meaningful, verifiable outcome.
- Keep dependencies explicit.
- Keep tasks small enough for one focused implementation cycle.
- Do not split work into arbitrary file-level tasks.
- Identify parallelizable work.
- Define acceptance criteria before implementation.
- Include tests, migration, documentation and operational tasks when required.

## Output

```markdown
# Milestone Plan

## Milestone 1 — <name>
**Objective:**
**Dependencies:**
**Owner/agent:**
**Acceptance criteria:**

### Tasks
- [ ] Task 1
- [ ] Task 2
- [ ] Task 3

**Parallel work:**
**Risks:**

## Milestone 2 — <name>
...

## Dependency Graph

## Execution Order
```

Prefer milestone boundaries that allow progress to be reviewed or tested independently.
