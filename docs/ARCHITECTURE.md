# Architecture

## Project Summary

`yunchiayu.github.io` is an existing academic website built with Jekyll on top of the `al-folio` theme.

This document should help agents answer:

- Where is the content that powers a page or collection?
- Which directories control layout, shared components, or styling?
- Which files control local Docker behavior versus GitHub Pages deployment?
- Which paths are safe to edit and which should usually be treated as generated or reference-only?

## Top-Level Map

| Path | Purpose | Edit policy |
|---|---|---|
| `./` | Main editable codebase and site source. | Editable when the task targets it. |
| `docs/` | Stable repository documentation for coding agents. | Editable for durable docs. |
| `reports/` | Task-specific reports, plans, and verification notes. | Write generated artifacts here. |
| `chats/` | Reusable staged prompts for future Codex sessions. | Editable when improving workflow. |
| `readme_preview/`, `lighthouse_results/` | Preview images and benchmark outputs. | Usually reference-only. |
| `.jekyll-cache/`, `.tweet-cache/`, `_site/` | Generated local caches and build output. | Usually read-only or disposable. |

## Main Editable Codebase

| Path | Role | Notes |
|---|---|---|
| `_config.yml` | Primary Jekyll and site configuration. | High-leverage file for metadata, collections, plugins, exclusions, and site-wide behavior. |
| `_pages/` | Top-level site pages. | Usually the first place to inspect for page content and routing. |
| `_posts/` | Blog post collection. | Uses Jekyll post naming and front matter conventions. |
| `_projects/` | Project collection pages. | Project-specific content exposed as a Jekyll collection. |
| `_news/` | News and announcement entries. | Used by the announcements section. |
| `_includes/` | Reusable Liquid partials. | Shared snippets for headers, cards, scripts, CV blocks, and other components. |
| `_layouts/` | Page and post layouts. | Controls structure around content and includes. |
| `_sass/` | Theme styling sources. | Changes here affect global styling and component presentation. |
| `assets/` | Static assets and front-end support files. | Includes CSS, JS, images, PDFs, notebooks, JSON, audio, and video. |
| `_plugins/` | Custom Jekyll plugins. | Important when behavior cannot be explained by config, layouts, or includes alone. |
| `_data/` | Structured data consumed by templates. | Useful for menus, CV/resume content, and other reusable data-driven sections. |
| `_bibliography/` | Bibliography sources for scholarly pages. | Relevant for `jekyll-scholar` behavior and citation rendering. |
| `Gemfile`, `Gemfile.lock` | Ruby dependency definition and lockfile. | Critical for local builds, Docker, and plugin compatibility. |
| `docker-compose.yml`, `docker-compose-slim.yml`, `Dockerfile` | Local containerized development stack. | Main debugging surface for Docker-only startup or dependency issues. |
| `bin/` | Helper scripts for local build, deploy, and container startup. | `entry_point.sh` is the Docker runtime entrypoint. |
| `.github/workflows/deploy.yml` | GitHub Pages deployment workflow. | Uses Ruby `3.2.2`, which may differ from local Docker runtime behavior. |
| `package.json` | Front-end formatting dependencies. | Only small dev tooling surface here. |

## Main Entrypoints

- Local Docker development: `docker compose up` -> `bin/entry_point.sh` -> `jekyll serve --port 8080`
- Local direct build: `bundle exec jekyll build` or `bin/cibuild`
- GitHub Pages deployment: `.github/workflows/deploy.yml`

## Invariants

- Preserve site content and routing unless the user asks for behavior changes.
- Treat `_config.yml`, `Gemfile`, `Gemfile.lock`, Docker files, and workflows as high-impact files.
- Keep reports under `reports/`, not inside theme or content directories.
- Expect local Docker and GitHub Actions to differ if Ruby or base images drift.
- Update this document when directory roles or edit boundaries change.
