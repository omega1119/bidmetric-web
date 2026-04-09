# BidMetric™

Website for [bidmetric.ai](https://bidmetric.ai)

BidMetric™ is a registered trademark in the United Kingdom, owned by [Greenwood IT Consultancy](https://gitc.digital).

## Structure

```
bidmetric-web/
├── CNAME                    # Domain configuration
├── README.md
└── docs/                    # GitHub Pages root
    ├── index.html           # Redirect page (language detection)
    ├── CNAME                # Domain (duplicated for Pages)
    ├── assets/
    │   ├── css/
    │   │   └── styles.css   # Main stylesheet
    │   └── js/
    │       ├── main.js      # Theme toggle & utilities
    │       └── redirect.js  # Language redirect logic
    └── en/                  # English locale
        ├── index.html       # Coming soon landing page
        ├── privacy.html     # Privacy policy
        └── terms.html       # Terms of service
```

## Localization

The site is structured to support multiple languages in the future. To add a new language:

1. Create a new folder under `docs/` (e.g., `docs/de/` for German)
2. Copy the English files and translate content
3. Update `docs/index.html` to add the new language redirect
4. Update language selectors in all HTML files

## Local Development

See [LOCAL_DEV.md](LOCAL_DEV.md) for detailed instructions.

Quick start:

```bash
cd docs && python3 -m http.server 8080
```

Then visit `http://localhost:8080/en/`

## Deployment

The site is deployed via GitHub Pages from the `docs/` folder.