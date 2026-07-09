# Code Review Guide

## Review Stance

When asked for a review, prioritize bugs, build regressions, content/render regressions, missing tests or smoke checks, stale docs, and maintainability risks. Findings should lead the response.

## Review Inputs

Inspect:

- changed files,
- related content, layouts, includes, and configs,
- relevant build or deploy scripts,
- refactor plan,
- implementation summary,
- code-explanation reports if they exist,
- relevant architecture docs.

## Output Format

Use this order:

1. Findings, ordered by severity, with file/line references when available.
2. Open questions or assumptions.
3. Brief change summary.
4. Test gaps or residual risk.

If there are no findings, say so clearly and mention remaining test gaps or risk.

## What To Check

- Does the change match the plan?
- Did site behavior or rendered output change unexpectedly?
- Are layout, include, or front matter assumptions still valid?
- Are local Docker and GitHub Actions behavior still aligned where they need to be?
- Are public URLs, collections, and config defaults preserved where expected?
- Are tests or smoke checks sufficient for the risk level?
- Are docs and code-explanation reports still accurate?
- Were unrelated files changed?

## After Review

If review feedback leads to code or docs modifications, update affected reports under `reports/`, especially code-explanation reports for changed important files.
