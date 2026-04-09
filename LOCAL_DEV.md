# Local Development (Python Static Server)

This site is a static HTML/CSS/JS site under the `docs/` folder. The fastest way to preview locally is to serve the `docs/` directory with Python's built‑in HTTP server.

## Prerequisites
- macOS with Python 3 installed (`python3 --version`)
- Default shell: zsh

## Start the server
```zsh
cd "/repos/bidmetric-web/docs"
python3 -m http.server 8080
```

Alternative (serve the repo root):
```zsh
cd "/repos/bidmetric-web"
python3 -m http.server 8080
```

## Open in the browser
- If you served the `docs/` folder (recommended):
  - Visit: `http://localhost:8080/`
  - English landing: `http://localhost:8080/en/`
  - Privacy: `http://localhost:8080/en/privacy.html`
  - Terms: `http://localhost:8080/en/terms.html`

- If you served the repo root instead:
  - Visit: `http://localhost:8080/docs/`
  - English landing: `http://localhost:8080/docs/en/`
  - Privacy: `http://localhost:8080/docs/en/privacy.html`
  - Terms: `http://localhost:8080/docs/en/terms.html`

## Stop the server
- Press `Ctrl+C` in the terminal.

## Troubleshooting
- Clear cache/hard refresh if assets look stale.
- If port 8080 is in use, pick another port:
```zsh
python3 -m http.server 9000
```

## Optional: Node http-server
```zsh
npm install -g http-server
cd "/repos/bidmetric-web/docs"
http-server -p 8080
```

## Future Localization
When adding new languages, create folders under `docs/` (e.g., `docs/de/`, `docs/fr/`) and update:
1. `docs/index.html` — add redirect mapping
2. Language selector dropdowns in all HTML files
