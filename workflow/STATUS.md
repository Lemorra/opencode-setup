# Workflow Status Contract

The manager should maintain a small status file in the target project's `artifacts/status.md` when a workflow spans multiple sessions.

```markdown
# Workflow Status

## State
NEW | STRUCTURED | FEASIBILITY | ROADMAP | MILESTONED | BUILDING | REVIEW | REWORK | DONE

## Current Milestone

## Current Task

## Last Completed Stage

## Blocking Decisions

## Next Action

## Last Review Verdict

## Updated
```

## Rules

- `status.md` is coordination state, not a substitute for the other artifacts.
- Keep it concise.
- Update it whenever the workflow changes state.
- Do not claim `DONE` until the review contract has passed.
