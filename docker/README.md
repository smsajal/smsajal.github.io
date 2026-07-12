# Local Docker preview

Self-contained Docker setup for previewing this site locally. The compose
files live here; they reuse the repo-root `Dockerfile` and
`bin/entry_point.sh` via build `context: ..`.

Run all commands **from the repo root**.

## Build & serve

```bash
docker compose -f docker/docker-compose.yml up -d --build
```

First run takes a few minutes (it installs the v1 gems). Then open:

- <http://localhost:8080/>  ← the site (baseurl is blank, so it's the root path, **not** `/al-folio/`)
- `/experience/`, `/education/`, `/skills/`, `/publications/`, `/cv/`

## Troubleshoot / stop

```bash
docker compose -f docker/docker-compose.yml logs --tail=80   # view build/serve logs
docker compose -f docker/docker-compose.yml down             # stop and remove
```

## Notes

- The container builds to its own `/tmp/_site` (not the bind-mounted `_site`)
  to avoid host bind-mount write deadlocks; it watches `_config.yml` and
  restarts Jekyll on config changes.
- **Slim variant** (no local build, pulls a prebuilt image):
  `docker compose -f docker/docker-compose-slim.yml up -d`.
- **Permission error** (`.jekyll-cache/.gitignore … Permission denied`): uncomment
  the `USER` / `GROUPID` / `USERID` args in the root `Dockerfile` and the matching
  `build.args` in `docker-compose.yml`, filling them from `id -g`, `id -gn`,
  `id -u`, `echo $USER`, then rebuild with `--build`.
- Requires a running Docker **engine** (Docker Desktop, Colima, Rancher, etc.) —
  the `docker` CLI alone is not enough.
