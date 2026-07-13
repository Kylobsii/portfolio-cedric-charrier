# my-portfolio

Source for my portfolio site, built with [MkDocs](https://www.mkdocs.org/) +
[Material theme](https://squidfunk.github.io/mkdocs-material/).

## Setup (one time)

```bash
python -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Preview locally

```bash
mkdocs serve
```

Then open http://127.0.0.1:8000 — it live-reloads as you edit files.

## Deploy to GitHub Pages

First time only: create a GitHub repo named `my-portfolio` (or update
`site_url` / `repo_url` in `mkdocs.yml` to match whatever name you use),
then:

```bash
git init
git add .
git commit -m "Initial portfolio scaffold"
git branch -M main
git remote add origin https://github.com/yourusername/my-portfolio.git
git push -u origin main
```

Then, to build and publish the site itself:

```bash
mkdocs gh-deploy
```

This builds the site and pushes it to a `gh-pages` branch. Go to your repo's
**Settings → Pages** and make sure the source is set to the `gh-pages` branch
(mkdocs gh-deploy usually configures this automatically on first run).

Your site will be live at `https://yourusername.github.io/my-portfolio/`.

Every time you update content, just run `mkdocs gh-deploy` again.

## Adding a new project or experience page

1. Add a new `.md` file under `docs/projects/` or `docs/experiences/`
2. Add one line for it under `nav:` in `mkdocs.yml`
3. `mkdocs serve` to preview, `mkdocs gh-deploy` to publish

## To-do before this is portfolio-ready

- [ ] Replace all placeholder text (`Your Name`, `yourusername`, bracketed hints)
- [ ] Fill in real project/experience content
- [ ] Add screenshots to `docs/assets/images/`
- [ ] Add a resume PDF at `docs/assets/resume.pdf` (or delete that button in resume.md)
- [ ] Update `site_url` / `repo_url` / social links in `mkdocs.yml`
- [ ] Delete `docs/projects/_TEMPLATE_NOTES.md` (it's just a note for you)
