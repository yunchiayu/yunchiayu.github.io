# Reporting Conventions

## Destination Rules

Stable repository knowledge belongs in `docs/`.

Task-specific artifacts belong under `reports/`, including:

- code explanations,
- audits,
- documentation refactor plans,
- implementation QA,
- refactor plans,
- implementation summaries,
- verification notes,
- postmortems.

Do not place reports in content, theme, or asset directories such as `_pages/`, `_posts/`, `_projects/`, `_includes/`, `_layouts/`, `_sass/`, `assets/`, or `_plugins/`.

## Directory Convention

Use a task-specific directory:

```text
reports/<TASK_NAME>/
```

For code explanations, use:

```text
reports/<TASK_NAME>/code_explanation/
```

## File Naming

Use Markdown. For ordered histories, use numbered filenames such as:

```text
01_Codebase_Audit.md
02_Documentation_Refactor_Plan.md
03_Implementation_QA.md
04_Refactor_Plan.md
05_Implementation_Summary.md
```

Add new numbered files for iterative QA or follow-up rounds when needed.

## Code Explanation Reports

Follow:

```text
docs/CODE_EXPLANATION_GUIDE.md
```

## Stop-And-Wait Rules

If the user asks for an audit, write the audit and stop.

If the user asks for a documentation refactor plan, write the plan and stop.

If the user asks for an implementation or refactor plan, write the plan and stop.

If a plan says to wait for confirmation, do not implement until confirmed.
