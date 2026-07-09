# Chat Prompt: Start Refactor

We are working in:

```text
/Users/yunchiayu/MyGitHub/yunchiayu.github.io
```

## Read First

- `AGENTS.md`
- `docs/AGENT_WORKFLOW.md`
- `docs/REFACTOR_PLAN_GUIDE.md`
- approved refactor plan under `reports/<TASK_NAME>/`
- existing code-explanation reports if the plan names them

## Task

Implement the approved refactor plan for `<TASK_NAME>`.

## Constraints

- Keep edits scoped to the approved plan.
- Preserve site behavior where the plan requires compatibility.
- Do not perform unrelated cleanup.
- Update affected docs and code-explanation reports.

## Verification

Run the tests and smoke checks named in the plan. If a check cannot run, document why.

## Final Output

Write an implementation summary to:

```text
reports/<TASK_NAME>/05_Implementation_Summary.md
```

The summary must include:

- files changed,
- behavior changed or preserved,
- tests or checks run,
- docs or code-explanation reports updated,
- remaining limitations.
