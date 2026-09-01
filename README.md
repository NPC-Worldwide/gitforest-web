# gitforest-web

Source for [gitforest.net](https://gitforest.net) — the GitForest landing page, binary downloads, and documentation.

## Contents

- `index.html` — landing page
- `downloads.html` — binary downloads (served from `gs://gitforest-executables`)
- `docs/` — user documentation & guidance
- `assets/` — images, favicon
- `.github/workflows/deploy.yml` — CI/CD: GitHub Actions (Workload Identity Federation) → `gs://gitforest-website`

## Deploy

Pushes to `main` auto-deploy to Google Cloud Storage via GitHub Actions (no secrets — WIF only):

```
gs://gitforest-website  (public bucket, index.html suffix)
```

Served via Cloudflare → `https://gitforest.net` and `https://www.gitforest.net`.

## Binaries

Built and published by the [git-forest](https://github.com/NPC-Worldwide/git-forest) repo's release pipeline to:

```
gs://gitforest-executables/  →  https://storage.googleapis.com/gitforest-executables/
```
