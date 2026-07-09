# AGENTS.md

## Project Role

You are a coding agent working in:

```text
/Users/yunchiayu/MyGitHub/yunchiayu.github.io
```

`yunchiayu.github.io` is an existing Jekyll-based academic website repository built on the `al-folio` theme. Understand the current site structure, build workflow, and deployment path before proposing documentation or code refactors.

## Start Here

Before planning or editing, read:

```text
docs/ARCHITECTURE.md
docs/AGENT_WORKFLOW.md
docs/REPORTING_CONVENTIONS.md
```

For codebase explanation, documentation refactor, implementation refactor, or review tasks, also read the matching guide:

```text
docs/CODE_EXPLANATION_GUIDE.md
docs/DOCUMENTATION_REFACTOR_GUIDE.md
docs/REFACTOR_PLAN_GUIDE.md
docs/CODE_REVIEW_GUIDE.md
```

## Repository Routing

| Path | Role | Edit policy |
|---|---|---|
| `./` | Main editable website codebase, content, theme overrides, and build config. | Editable when the task requires it. |
| `docs/` | Stable repository documentation and agent guidance. | Editable for durable docs. |
| `reports/` | Task reports, QA, plans, summaries, and verification notes. | Write task artifacts here. |
| `chats/` | Reusable staged prompts for future Codex sessions. | Editable when improving agent workflow. |
| `readme_preview/`, `lighthouse_results/` | Reference or generated preview assets. | Treat as reference-only unless the task targets them. |
| `.jekyll-cache/`, `.tweet-cache/`, `_site/` | Local/generated build artifacts and caches. | Do not treat as source of truth. |

## Global Boundaries

- Read before editing.
- Preserve site behavior unless the user explicitly asks for behavior changes.
- Keep edits inside this repository.
- Do not place reports inside content, theme, or asset directories.
- Avoid unrelated cleanup while changing content, theme, or build behavior.
- Verify with Jekyll or Docker smoke checks when the task touches build or deployment flow.
- Watch for environment drift between local Docker and GitHub Actions Ruby versions.

## Reporting

Stable repository knowledge belongs in `docs/`. Task-specific artifacts belong under `reports/`.

Follow:

```text
docs/REPORTING_CONVENTIONS.md
```
