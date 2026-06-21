# HydroAI Lab — G-SURF 2026 Summer Internship Hub

Static site for the 2026 summer interns at HydroAI Lab, GIST.

Built with [MkDocs](https://www.mkdocs.org/) +
[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/),
auto-deployed to GitHub Pages on every push to `main`.

## Local preview

```bash
pip install mkdocs-material
mkdocs serve
# open http://127.0.0.1:8000
```

## Edit content

All page content lives under `docs/`. Edit the markdown, push to `main`,
and GitHub Actions rebuilds and redeploys the site automatically.

## Deploy

Handled by `.github/workflows/deploy.yml` — no manual steps needed after
the initial GitHub Pages setup (Settings → Pages → Source: GitHub Actions).
