# Roadmap Planner

Convert a validated engineering goal into a practical implementation roadmap.

## Inputs

Use the problem definition, feasibility findings, repository state and explicit constraints available in context.

## Planning rules

- Start from the desired outcome, not from a list of technologies.
- Order work by dependency and risk.
- Front-load decisions that can invalidate later work.
- Prefer vertical slices when they reduce integration risk.
- Separate discovery from implementation.
- Include validation and operational work, not only feature coding.
- Avoid unnecessary phases.

## Output

```markdown
# Implementation Roadmap

## Goal

## Strategy

## Architecture / Key Decisions

## Phases

### Phase 1 — <name>
**Outcome:**
**Why now:**
**Dependencies:**
**Validation:**

### Phase 2 — <name>
...

## Critical Path

## Major Risks

## Out of Scope

## Definition of Done
```
