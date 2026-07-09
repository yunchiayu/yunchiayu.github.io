# Refactor Plan Guide

## Purpose

A refactor plan should make the intended change safe, scoped, and reviewable. It should distinguish behavior-preserving cleanup from behavior changes.

## Required Inputs

Before writing a plan, inspect:

- `AGENTS.md`,
- `docs/ARCHITECTURE.md`,
- relevant code and content,
- relevant build scripts and configs,
- code-explanation reports if they exist,
- prior reports for the same area.

## Plan Contents

Include:

- current behavior,
- target behavior,
- files or directories to change,
- public URL or content compatibility expectations,
- build, migration, or compatibility notes,
- test plan,
- smoke-check plan,
- risks and assumptions.

## QA Before Planning

If ambiguity remains, write QA under:

```text
reports/<TASK_NAME>/
```

Each question should include:

- exact uncertainty,
- why it matters,
- recommended default,
- implementation consequence.

## Refactor Safety Rules

- Preserve behavior unless behavior change is explicitly requested.
- Keep changes scoped to the target subsystem.
- Avoid unrelated cleanup.
- Update affected docs and code-explanation reports.
- Re-check local build or deployment paths when editing high-impact files such as `_config.yml`, `Gemfile`, Docker files, or workflows.

## Plan Output

Write the plan under:

```text
reports/<TASK_NAME>/
```

Use a numbered filename such as:

```text
04_Refactor_Plan.md
```

Stop after writing the plan if user confirmation is required.
