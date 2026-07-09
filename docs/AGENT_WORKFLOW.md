# Agent Workflow

## Required Pre-Work

Before editing:

1. Read `AGENTS.md`.
2. Read `docs/ARCHITECTURE.md`.
3. Read `docs/REPORTING_CONVENTIONS.md`.
4. Inspect relevant pages, layouts, includes, assets, configs, scripts, and prior reports.
5. Search the repo before asking questions when the answer can be discovered locally.

## Repository-Specific Workflow

For this codebase:

1. Identify whether the task is about content, layout/theme, build tooling, or deployment.
2. Read the relevant high-leverage files first:
   - content: `_pages/`, `_posts/`, `_projects/`, `_news/`
   - presentation: `_layouts/`, `_includes/`, `_sass/`, `assets/`
   - config/build: `_config.yml`, `Gemfile`, `Gemfile.lock`, `docker-compose*.yml`, `Dockerfile`, `bin/`
   - deployment: `.github/workflows/deploy.yml`
3. Write code-explanation or audit reports when they will help future work.
4. Distinguish behavior-preserving cleanup from user-visible behavior changes.
5. Ask QA questions for high-impact ambiguity.
6. Write a refactor plan before broad changes.
7. Implement narrowly.
8. Run the most relevant smoke checks and update affected docs or reports.

## Build and Verification Paths

Use one or more of these checks depending on the task:

- Docker local serve: `docker compose up`
- Docker rebuild: `docker compose up --build`
- Inspect running server: `docker compose logs`, `docker compose ps`
- Local Jekyll build: `bundle exec jekyll build`
- CI-equivalent helper: `bin/cibuild`
- Deployment flow reference: `.github/workflows/deploy.yml`

If local Docker behavior differs from GitHub Pages deployment, compare:

- local Docker image and Ruby version,
- `Gemfile` and `Gemfile.lock`,
- GitHub Actions Ruby version and build steps.

## Coding Rules

- Read before editing.
- Keep changes scoped to the requested task.
- Preserve site structure, collection conventions, and front matter behavior unless the user asks otherwise.
- Do not treat caches or generated output as authoritative source files.
- Match the existing style and content patterns unless the task is a deliberate redesign or refactor.
- Do not delete unrelated theme or content files during focused fixes.

## Stop Gates

Stop and wait for confirmation when:

- documentation-only planning was requested,
- QA is needed before implementation,
- a refactor plan was requested before code edits,
- a proposed change affects broad site behavior or deployment behavior,
- a task would require editing generated preview artifacts without explicit request.
