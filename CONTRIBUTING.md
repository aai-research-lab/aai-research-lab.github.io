# Maintaining the site

Source for [aai-research-lab.github.io](https://aai-research-lab.github.io). Built with [Jekyll](https://jekyllrb.com/) on the [al-folio](https://github.com/alshedivat/al-folio) theme; see [`al-folio_README.md`](al-folio_README.md) for upstream theme documentation.

## Where things live

| To change     | Edit                                                  |
| ------------- | ----------------------------------------------------- |
| Front page    | `_pages/about.md`                                     |
| Team members  | `_pages/profiles.md` + a `_pages/about_<name>.md` bio |
| Publications  | `_bibliography/papers.bib`                            |
| News items    | a new file in `_news/`                                |
| Teaching      | `_pages/teaching.md`                                  |
| Join page     | `_pages/join.md`                                      |
| Site settings | `_config.yml`                                         |

## Adding a team member

1. Put the photo in `assets/img/` — JPEG, max 800px wide, under ~150 KB.
2. Create `_pages/about_<name>.md` with the bio, copying an existing one for format. These files deliberately have **no YAML front matter**, and are excluded from the built site so they aren't published as raw markdown.
3. Add a block to the `profiles:` list in `_pages/profiles.md` pointing at both.

## Adding a news item

Create `_news/announcement_YYMMDDShortName.md`:

```yaml
---
layout: post
date: 2026-01-15 00:00:00-0700
inline: true
related_posts: false
---
Your announcement text here.
```

Use `inline: false` and add a `title:` for longer posts that get their own page.

## Adding a publication

Append a BibTeX entry to `_bibliography/papers.bib`. Useful non-standard fields the theme understands: `pdf` (a file in `assets/pdf/`), `code`, `website`, `selected`, `abbr`, `preview`.

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

The site is then served at `http://localhost:4000` — open that in a browser.

Requires Ruby 3.2.x. macOS ships an ancient system Ruby, so install a modern one first, e.g. `brew install rbenv ruby-build && rbenv install 3.2.2 && rbenv local 3.2.2`.

## Before pushing

CI runs Prettier on every push and fails the build if formatting is off:

```bash
npm install
npx prettier --write .
```

Or install the hook once: `pip install pre-commit && pre-commit install`

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site and publishes to the `gh-pages` branch. **Check the Actions tab after pushing** — if the workflow fails, the live site silently keeps serving the previous build.

Other workflows: `prettier.yml` (formatting), `broken-links.yml` (source links), `broken-links-site.yml` (built site), `axe.yml` (accessibility, manual trigger only).

## Conventions

- The lab name is **AAI Research Lab** throughout.
- JPEG for photographs, PNG only where transparency is needed. Responsive-image generation is disabled, so whatever you commit is what visitors download — resize before committing.
- News timestamps use `-0700`.
