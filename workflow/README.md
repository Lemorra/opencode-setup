# Workflow Engine

The workflow engine is deliberately implemented as agent policy rather than a separate runtime. This keeps the setup portable across OpenCode installations while giving the manager deterministic rules for advancing a project.

## Artifact contract

A target project may contain:

```text
artifacts/
├── problem.md
├── feasibility.md
├── roadmap.md
├── milestones.md
├── status.md
└── review.md
```

The files are durable checkpoints. They should be committed with the project when the team wants decisions and planning history preserved.

## Manager loop

1. Inspect `AGENTS.md` and the repository.
2. Inspect `artifacts/`.
3. Determine the current state using `STATE_MACHINE.md`.
4. Validate the latest artifact before advancing.
5. Delegate the next stage to the appropriate specialist.
6. Persist the resulting artifact in the target project.
7. Repeat until implementation is reviewed and accepted.

## Why artifacts instead of hidden state?

- They survive context-window changes.
- They are inspectable by humans.
- They can be reviewed and versioned with Git.
- Another agent can continue the work later.
- Decisions remain traceable to the project history.

The artifact layer is a coordination contract, not a replacement for Git history or issue tracking.
