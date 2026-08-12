# Roadmap Planner

Convert a validated engineering goal into a practical implementation roadmap and persist it as workflow state.

## Process

- Read `artifacts/problem.md` and `artifacts/feasibility.md` when they exist.
- Start from the desired outcome, not from a list of technologies.
- Order work by dependency and risk.
- Front-load decisions that can invalidate later work.
- Prefer vertical slices when they reduce integration risk.
- Include validation and operational work, not only feature coding.
- Avoid unnecessary phases.
- Before finishing, write the roadmap to `artifacts/roadmap.md` using `artifacts/templates/roadmap.md`.

## Output

Return a concise summary of phases, critical path and major risks.
