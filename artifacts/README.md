# Workflow Artifacts

This directory contains the durable state of the OpenCode engineering workflow.

Artifacts are intentionally stored in the **current project**, not in the global OpenCode configuration repository. The configuration repository provides the workflow; the project owns the resulting decisions.

## Lifecycle

```text
problem.md
    ↓
feasibility.md
    ↓
roadmap.md
    ↓
milestones.md
    ↓
implementation
    ↓
review.md
    ↓
rework / ship
```

## Rules

- Create or update an artifact only when that workflow stage has actually been completed.
- Preserve previous decisions unless new evidence invalidates them.
- Keep artifacts concise and factual.
- Mark assumptions explicitly.
- Do not put secrets, credentials or sensitive environment values in artifacts.
- `review.md` is the final independent assessment and must not be edited by the reviewer.

The templates in this directory define the expected structure. They are copied into the target project's `artifacts/` directory when starting a workflow; they are not themselves workflow state.
