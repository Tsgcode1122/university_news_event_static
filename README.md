# University News & Events Hub — static export

This directory is a generated, public-only snapshot of the rendered Drupal website. It is intended to be copied into a separate GitHub repository and connected to Netlify with the publish directory set to `.`.

The export preserves Drupal's rendered HTML, CSS, JavaScript, images, fonts, and other public assets. It deliberately excludes Drupal administration, login and user pages, private files, and other non-public routes.

## Regenerate after Drupal content changes

Run these commands from the Drupal project root:

```bash
open -a Docker
ddev start
node scripts/export-static.mjs
node scripts/validate-static.mjs
```

The exporter reads the live local site at `http://university-news-hub.ddev.site` by default. Override it when needed:

```bash
DRUPAL_URL="https://your-local-or-staging-drupal.example" node scripts/export-static.mjs
```

If DDEV reports an alternate host port, include that port in `DRUPAL_URL`.

To review the generated snapshot locally:

```bash
python3 -m http.server 4173 --directory static-export
```

Then open `http://localhost:4173/`. The export writes `export-manifest.json`, which lists pages, assets, and any fetch failures. Do not commit the Drupal repository, database dumps, `.env` files, credentials, or private files to the static repository.

## Netlify / GitHub

Create a separate repository whose root is the contents of this directory. Netlify will read `netlify.toml` and publish the repository root. No build command is required.

The static site contains only the public snapshot at export time. Drupal search/filter forms retain their public layout and destination, but server-side Drupal behavior is not available in a static deployment; regenerate the snapshot whenever the public content changes.

## Current route scope

The default export starts from the homepage, `/news`, and `/events`, then follows public internal links to individual public content pages, taxonomy pages, and their referenced assets. The current local Drupal instance returns 404 for `/archive` and `/glossary`, so those routes are not fabricated into the export. It does not crawl Drupal admin, login, account, editing, private-file, or feed routes.
