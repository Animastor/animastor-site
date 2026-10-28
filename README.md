# animastor-site

Static public website for animastor.org (marketing landing, library, downloads).

## Source

Content is copied from `/home/animastor/animastor/frontends/website` (monorepo),
with the `index.html` changes from the `wip/monorepo-uncommitted-20261028` branch
(GitHub links retargeted to `github.com/Animastor/animastor-web`).

## Exclusions

- `downloads/*.apk` — not stored in git (see `.gitignore`). The APK is served
  by nginx from `data/` in production (phase 2).
- `.well-known/` — ACME challenge directory, not part of the site repo.

## version.json

`downloads/version.json` is synced from `animastor-web/frontends/website/downloads/version.json`.

## Deployment

Served by `animastor-proxy` (nginx:alpine) via bind-mount:
- `/usr/share/nginx/frontends/website` → `frontends/website/`

## Links

- `/downloads/animastor-android-latest.apk` — referenced from `index.html` and
  `site.js`; the actual APK file is provided by nginx from `data/` (phase 2),
  not from this repository.
