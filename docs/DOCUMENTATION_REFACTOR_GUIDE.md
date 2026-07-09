# Documentation Refactor Guide

## Purpose

Use this guide when converting stale, generic, or task-specific repository instructions into durable docs for coding agents.

## Target Structure

Prefer:

```text
AGENTS.md
docs/ARCHITECTURE.md
docs/AGENT_WORKFLOW.md
docs/REPORTING_CONVENTIONS.md
chats/
reports/
```

Add domain-specific guides only when they will remain useful across future tasks.

## What Belongs In `AGENTS.md`

Keep:

- project root,
- short project role,
- first-read checklist,
- routing table for major directories,
- edit boundaries,
- report location pointer.

Avoid:

- long task checklists,
- stale one-off plans,
- large code explanations,
- deployment postmortems that belong in `reports/`.

## What Belongs In `docs/`

Move stable knowledge into `docs/`:

- architecture and directory roles,
- workflow rules,
- reporting conventions,
- domain-specific persistent constraints,
- code review expectations,
- code-explanation conventions.

## What Belongs In `chats/`

Keep staged prompts in `chats/`:

- audit prompts,
- documentation refactor prompts,
- implementation plan prompts,
- implementation start prompts,
- code review prompts.

These should be reusable and procedural.

## What Belongs In `reports/`

Move task history into `reports/`:

- audits,
- QA files,
- implementation plans,
- summaries,
- code explanations,
- verification notes,
- postmortems.

## Refactor Process

1. Read existing docs and the top-level tree.
2. Identify stable guidance versus task-specific history.
3. Write a documentation refactor plan under `reports/<TASK_NAME>/`.
4. Stop for confirmation if requested.
5. Apply the docs refactor.
6. Verify links and paths.
7. Summarize changed docs.
