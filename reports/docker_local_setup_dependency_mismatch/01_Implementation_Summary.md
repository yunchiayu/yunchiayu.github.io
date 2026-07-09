# Docker Local Setup Dependency Mismatch

## Summary

`docker compose up` started the container and published port `8080`, but Jekyll did not finish booting, so `http://localhost:8080` was unreachable.

## Root Cause

The failure was caused by a dependency mismatch between the current local Docker runtime and the repo's Ruby dependency assumptions:

- the Docker image `amirpourmand/al-folio:latest` booted with Ruby `4.0.5`,
- Ruby `4.0` no longer ships some standard-library components as default gems,
- `jekyll-scholar` pulled `citeproc-ruby`, which required `observer`,
- `jekyll-twitter-plugin` required `ostruct`.

Because those gems were missing, Jekyll crashed during startup with `LoadError` before it could bind to port `8080`.

## Files Changed

- `Gemfile`
- `Gemfile.lock`

## Fix Applied

1. Confirmed the Docker container was running and port `8080` was published.
2. Read `docker compose logs` and found startup failures for `observer`, then `ostruct`.
3. Added `observer` and `ostruct` to `Gemfile`.
4. Updated `Gemfile.lock` so the new gems were recorded for the repo.
5. Recreated the container and allowed the initial Jekyll dependency install and site build to complete.

## Behavior Preserved

- Site content, layouts, and routing were not intentionally changed.
- GitHub Pages workflow structure remained unchanged.

## Behavior Changed

- Local Docker startup now succeeds under the current Ruby `4.0.x` image.

## Verification

Verified with local smoke checks:

- container logs reached `Server address: http://0.0.0.0:8080`
- logs showed `WEBrick::HTTPServer#start ... port=8080`
- the running container had `jekyll serve` active
- browser confirmation from the user showed the site loaded successfully

## Remaining Limitations

- Local Docker currently runs a newer Ruby than GitHub Actions, which still uses Ruby `3.2.2`.
- Future plugin or dependency updates may expose more local-only incompatibilities if the Docker image and CI runtime continue to diverge.
