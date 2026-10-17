<!-- BEGIN GENERATED (web-common/agents/copilot-instructions.md -- edits here are overwritten by tools/sync-agent-config.sh) -->

# Agent instructions

This is a static site: hand-written HTML, CSS, and vanilla JS, deployed to GitHub
Pages from the `main` branch. There is no build step, no npm, no bundler, and no
framework (React, Vue, a static site generator's templating, etc.). Edit the HTML
files directly: do not introduce a build pipeline to "improve" this.

## Never change these without explicit approval

These are load-bearing. Changing them silently breaks live URLs, analytics history,
or JS that reads them by exact string:

- **URL slugs and file paths** (e.g. `en/products/metric.html`). Renaming or moving
  a page breaks bookmarks, search rankings, and inbound links from the App Store or
  other sites.
- **Anchor IDs** (`id="..."` targeted by in-page links or external deep links).
- **The Google Analytics measurement ID** (`G-XXXXXXXXXX` in the `gtag.js` snippet).
  Changing it silently orphans historical analytics data.
- **`data-*` attribute contracts** read by `assets/js/main.js` and
  `assets/js/redirect.js`, e.g. `data-languages`, `data-active-lang`,
  `data-footer-type`, `data-store` / `data-store-product`, `data-redirect-<lang>`,
  `data-theme` on `<source>` elements. These scripts parse specific attribute names
  and values; renaming or restructuring one without updating the JS (and every HTML
  file that uses it) breaks the feature with no error.

## General conventions

- No external `<script src>` beyond Google's `gtag.js`: do not add other
  third-party scripts without asking first.
- Fonts are self-hosted (`assets/fonts/*.woff2` + `@font-face` in `styles.css`), not
  loaded from Google Fonts or any other external stylesheet host. Every repo used to
  load its body font (usually Inter) from `fonts.googleapis.com`; all were migrated
  to self-hosted `@font-face` declarations in Sep 2026. Don't reintroduce an external
  font `<link>`: add a new self-hosted woff2 instead.
- When adding a page, copy an existing locale's page as the template rather than
  writing one from scratch, to keep markup structure consistent across locales.

<!-- END GENERATED -->

<!-- Per-repo notes go below this line. Never touched by the sync script. -->

## bidmetric-web specifics

- Domain `bidmetric.ai`. BidMetric is a UK registered trademark owned by Greenwood IT
  Consultancy. Keep the "BidMetric™" form in visible copy and titles where it is
  already used.
- The product is not launched: `en/index.html` is a "Coming Soon" page. Do not
  invent features, pricing or store links.
- No Google Analytics tag is wired into any HTML head, so analytics is inactive here.
  `main.js` contains the cookie consent banner only. Do not add a measurement ID
  without approval.
- English only today (`en`). The root `index.html` is a redirect shell
  (`assets/js/redirect.js`, `data-redirect-en`) into `en/`. Pages: `en/index.html`,
  `en/privacy.html`, `en/terms.html`.
- `assets/images/og-image.png` is a generated placeholder share image (brand name on
  the dark background). Replace it with a designed one when available, keeping the
  filename, so no page needs editing.
- The README and `LOCAL_DEV.md` still describe an old `docs/` folder layout. It is
  stale: the site files live at the repo root. Trust the file tree.
- Cache-busting: CSS and JS are referenced with a `?v=N` query string. Bump it when
  you change `styles.css` or `main.js`.
