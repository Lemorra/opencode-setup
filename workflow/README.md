# Workflow Engine

The workflow engine is implemented as agent policy rather than a separate runtime. This keeps the setup portable across OpenCode installations while giving the manager deterministic rules for advancing a project.

## Project state directory

The target project stores workflow state under:

```text
.opencode/workflow/
├── problem.md
├── feasibility.md
├── roadmap.md
├── milestones.md
├── status.md
└── review.md
```

This location is intentional: it keeps OpenCode-specific workflow state separate from application source code while allowing the agents to have narrowly scoped write permissions.

## Manager loop

1. Inspect `AGENTS.md` and the repository.
2. Inspect `.opencode/workflow/`.
3. Determine the current state using `STATE_MACHINE.md`.
4. Validate the latest artifact before advancing.
5. Delegate the next stage to the appropriate specialist.
6. Persist the resulting artifact in `.opencode/workflow/`.
7. Repeat until implementation is reviewed and accepted.

## Why artifacts instead of hidden state?

- They survive context-window changes.
- They are inspectable by humans.
- They can be reviewed and versioned with Git.
- Another agent can continue the work later.
- Decisions remain traceable to project history.

The artifact layer is a coordination contract, not a replacement for Git history or issue tracking.
