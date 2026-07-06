# burdick.dev

Personal consulting site for [Shaun Burdick](https://burdick.dev) — engineering leadership, software architecture, and agile delivery.

## Tech

- Static HTML + CSS (no framework, no build step)
- [Fira Code](https://github.com/tonsky/FiraCode) via Google Fonts
- Terminal aesthetic (green-on-black, monospace)
- Deployed via GitHub Pages (artifact-based Actions workflow)

## Quick start

```bash
# Serve locally
python3 -m http.server 8000
# Or
npx serve .
```

Open `http://localhost:8000` in a browser. No build step needed.

## Project structure

```
├── index.html           # Main landing page
├── 404.html             # Custom error page
├── calendar.html        # Redirects to zcal.co/shaunburdick
├── CNAME                # Custom domain: burdick.dev
├── robots.txt
├── sitemap.xml
├── assets/
│   ├── terminal.css     # Shared design tokens & styles
│   └── favicon.svg      # Terminal-prompt favicon
└── .github/workflows/
    └── deploy.yml       # Pages deployment
```

## License

MIT
