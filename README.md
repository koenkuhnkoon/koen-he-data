# Higher Education Dashboards

Public-facing analyses and interactive dashboards on tertiary education systems, financing, and outcomes.

Maintained by Koen Geven and collaborators.

## Live dashboards

GitHub Pages is enabled on this repo and serves the `docs/` folder. Live URLs:

- **Landing page:** https://koenkuhnkoon.github.io/koen-he-data/
- Individual dashboards are linked from the landing page once published.

(Replace `koen-he-data` with the actual repo name once created — see Setup below.)

## What lives here

- `docs/` — static HTML dashboards. Each is a single self-contained file with charts (Plotly, with `plotly.js` loaded from a CDN) and inline styling. No build step.
- `docs/index.html` — landing page that lists available dashboards.
- `README.md` — this file.
- `LICENSE` — MIT for code; data within charts retains its source license (UNESCO UIS, PROPHE, PIAAC, etc.).

## What does NOT live here

This repo is the public-facing layer. The data pipeline, raw data, draft material, and internal notes live in a separate private repo. Only the rendered HTML output is published here.

## Setup (one-time)

```bash
# Create the public repo on GitHub
gh repo create koenkuhnkoon/<repo-name> --public --source=. --remote=origin --push

# Enable GitHub Pages from the docs/ folder
gh api repos/koenkuhnkoon/<repo-name>/pages \
  -X POST -f 'source[branch]=main' -f 'source[path]=/docs'
```

After that, every push to `main` updates the live site within a minute or two.

## Adding a new dashboard

1. Drop the self-contained HTML into `docs/`.
2. Add a card to `docs/index.html`.
3. Commit and push to `main`. GitHub Pages rebuilds automatically.

## Sources used

- [UNESCO UIS](https://uis.unesco.org/) — global education statistics.
- [PROPHE](https://prophe.albany.edu/) — Program for Research on Private Higher Education, SUNY Albany.
- [OECD PIAAC](https://www.oecd.org/skills/piaac/) — Programme for the International Assessment of Adult Competencies.
