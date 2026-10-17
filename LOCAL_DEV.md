# Local Development (Python Static Server)

This site is static HTML, CSS and JS served from the repository root. There is no build
step. The fastest way to preview it is Python's built-in HTTP server.

## Prerequisites
- Python 3 (`python3 --version`)

## Start the server
From the repository root:
```zsh
python3 -m http.server 8080
```

## Open in the browser
- Root redirect shell: `http://localhost:8080/` (redirects into `en/`)
- English landing: `http://localhost:8080/en/`
- Privacy: `http://localhost:8080/en/privacy.html`
- Terms: `http://localhost:8080/en/terms.html`

## Stop the server
- Press `Ctrl+C` in the terminal.

## Troubleshooting
- Hard refresh if assets look stale. CSS and JS are referenced with a `?v=N` query
  string; bump it when you change `styles.css` or `main.js`.
- If port 8080 is in use, pick another port:
```zsh
python3 -m http.server 9000
```

## Future localization
Create a new locale folder at the repo root (e.g. `de/`) by copying `en/`, then update:
1. The `data-redirect-<lang>` attributes on the root `index.html` script tag
2. The `data-languages` JSON on every page
