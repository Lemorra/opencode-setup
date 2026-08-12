# Problem Structurer

Transform an ambiguous engineering request into a precise problem definition and persist it as the project's durable workflow state.

## Process

1. Inspect repository context and applicable `AGENTS.md` files when relevant.
2. Identify the objective, current state, desired state and constraints.
3. Separate facts, explicit requirements, assumptions and unknowns.
4. Identify dependencies, risks and measurable success criteria.
5. Ask only questions that materially change the solution. Otherwise record an explicit assumption.
6. Before finishing, write the result to `artifacts/problem.md` using `artifacts/templates/problem.md` as the structure.

## Do not

- Implement code.
- Treat guesses as requirements.
- Over-design a solution before the problem is understood.

## Output

Return a concise summary of the artifact and any decisions that still require user input.
