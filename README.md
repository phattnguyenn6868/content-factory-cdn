# content-factory-cdn

Public static asset host for **Xưởng Content** (content-factory). This repo has no
purpose on its own — it exists only to be served through [jsDelivr](https://www.jsdelivr.com/)'s
GitHub origin as a free CDN.

## How consumers should use this

Never link to a branch (e.g. `@main`). Branch URLs are mutable and jsDelivr may
cache stale or inconsistent content across files. Always pin to an immutable
**commit SHA**:

```
https://cdn.jsdelivr.net/gh/phattnguyenn6868/content-factory-cdn@<commit-sha>/<path>
```

Example:

```
https://cdn.jsdelivr.net/gh/phattnguyenn6868/content-factory-cdn@<sha>/brand/logo-mark.svg
```

To get the current SHA after pushing:

```bash
git rev-parse HEAD
```

Update the pinned SHA in the consuming app (see `web/src/lib/cdn.ts` in the main
`content-factory` repo) whenever new assets are added here.

## Layout

- `blog/` — article images (hero/inline images for blog posts)
- `brand/` — logo and brand assets
- `video/` — hero/demo video files offloaded from the app

## Rules for anyone committing here

- **No Git LFS.** jsDelivr does not resolve LFS pointer files — it will serve
  the pointer text itself, not the binary. Commit real files directly.
- **No secrets.** This repo is public. Never commit `.env` files, API keys, or
  database dumps.
- Keep filenames stable once published — anything already linked via a pinned
  SHA continues to work even if you later rename/delete the file on `main`,
  but avoid churn for clarity.
