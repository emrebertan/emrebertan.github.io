# Emre Bertan — personal website

A lightweight, static portfolio hosted with GitHub Pages. No server runtime, package manager, build step, analytics, or third-party JavaScript is required.

## Project layout

```text
.
├── index.html                 # semantic page structure and metadata
├── 404.html                   # GitHub Pages not-found page
├── robots.txt                 # crawler policy
├── manifest.webmanifest       # browser install/theme metadata
├── .nojekyll                  # publish files beginning with underscores as-is
├── .github/workflows/static.yml
└── assets/
    ├── favicon.svg
    ├── css/site.css           # design tokens, layout, responsive rules
    └── js/
        ├── translations.js    # Turkish, English, German copy
        └── app.js             # theme, language, command palette
```

## Local preview

Open `index.html` directly for layout review. ES modules can be restricted on `file://` by some browsers; for full behavior, serve this folder with any static file server, for example `npx serve .` (Node.js required only for local preview). The deployed GitHub Pages site runs over HTTPS.

## Publish

The workflow in `.github/workflows/static.yml` publishes the repository root to GitHub Pages after pushes to `main`. In repository Settings → Pages, select **GitHub Actions** as the build and deployment source.

## Security and privacy

- The Content Security Policy in `index.html` limits scripts to this site, blocks plugins and network connections from page scripts, and permits Google Fonts CSS/font files for the existing typography.
- No user-provided content is interpreted as HTML in the command palette. Saved theme/language values are allowlisted before use.
- External links opened in new tabs use `rel="noopener noreferrer"`.
- There are no forms, API keys, server endpoints, analytics, or personal data collection in this static project. Never commit credentials or private data.
- GitHub Pages serves static files. It cannot enforce response security headers, authenticate visitors, or keep secrets. For stronger response headers or server-side protections, put a suitable hosting/proxy layer in front later.
- Protect the `main` branch in GitHub repository Settings → Branches (require pull requests/status checks as appropriate). That protection is a repository setting, not a file in this project.

## Change content

Edit page structure in `index.html`, visual rules in `assets/css/site.css`, and translated text in `assets/js/translations.js`. Keep translation keys aligned across `tr`, `en`, and `de`.
