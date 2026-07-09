# Code Explanation Guide

## Purpose

Code-explanation reports help future agents understand an existing implementation before review, modification, or debugging. They explain execution flow, configuration flow, data sources, runtime behavior, output artifacts, and directory responsibilities.

Code explanations are task artifacts. Write them under `reports/`, not inside source directories.

## Output Location

Use a task-specific explanation root:

```text
reports/<TASK_NAME>/code_explanation/
```

At the explanation root:

- keep `overview.md` for the end-to-end explanation,
- keep `questions_for_user.md` only when unresolved ambiguity exists,
- place per-file reports under directories that mirror the source tree.

## Directory Structure

Per-file reports should mirror the source structure. Avoid flat report directories when explaining multiple files.

Example:

```text
source:
  _includes/header.liquid

report:
  reports/<TASK_NAME>/code_explanation/_includes/header.md
```

Strip the repository root prefix when it makes the report tree clearer.

## What Usually Matters In This Repo

Focus explanations on high-leverage files such as:

- `_config.yml`
- `_layouts/`
- `_includes/`
- `_plugins/`
- `assets/js/` and `assets/css/`
- `Gemfile` and `Gemfile.lock`
- `docker-compose*.yml`, `Dockerfile`, and `bin/entry_point.sh`
- `.github/workflows/deploy.yml`

Only create per-file reports for files that matter to the main flow.

## `overview.md` Template

Include:

- high-level summary,
- primary entrypoints,
- configuration sources,
- build or render flow,
- important runtime objects or plugins,
- output artifacts,
- comparison of local Docker, local Jekyll, and CI behavior when relevant,
- links to important per-file reports.

Prefer concrete file names, commands, config keys, and plugin names.

## Per-File Report Template

```text
File:
Role:
Read by:
Calls or includes:
Important classes/functions/blocks:
Input objects:
Output objects:
Main logic:
Relationship to other files:
```

## Maintenance After Code Changes

After code review or implementation changes, update affected code-explanation reports in the same workstream.

Always check whether `overview.md` needs updates when changes affect:

- local or deployed entrypoints,
- config or input flow,
- render or layout flow,
- plugin behavior,
- output artifacts,
- Docker or CI compatibility behavior.
