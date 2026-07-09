# Chat Prompt: Code Review

We are working in:

```text
/Users/yunchiayu/MyGitHub/yunchiayu.github.io
```

## Read First

- `AGENTS.md`
- `docs/CODE_REVIEW_GUIDE.md`
- refactor plan and implementation summary under `reports/<TASK_NAME>/`
- changed source files and verification steps
- affected docs and code-explanation reports

## Task

Review the refactor for `<TASK_NAME>`.

Prioritize:

- bugs,
- behavior regressions,
- compatibility breaks,
- missing tests or smoke checks,
- stale code-explanation reports,
- unrelated cleanup or scope drift.

## Constraints

- Do not modify files during review unless explicitly asked.

## Output

Lead with findings ordered by severity. Include file and line references where possible. If no issues are found, say so clearly and list remaining test gaps or residual risks.
