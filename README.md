# A:Ai Research Lab

Source for [aai-research-lab.github.io](https://aai-research-lab.github.io) — the website of the **A:Ai Research Lab**, Department of Physics, California State University, Dominguez Hills.

Built with [Jekyll](https://jekyllrb.com/) on the [al-folio](https://github.com/alshedivat/al-folio) theme. See [`al-folio_README.md`](al-folio_README.md) for upstream theme documentation.

## Editing content

| To change     | Edit                                                  |
| ------------- | ----------------------------------------------------- |
| Front page    | `_pages/about.md`                                     |
| Team members  | `_pages/profiles.md` + a `_pages/about_<name>.md` bio |
| Publications  | `_bibliography/papers.bib`                            |
| News items    | a new file in `_news/`                                |
| Teaching      | `_pages/teaching.md`                                  |
| Join page     | `_pages/join.md`                                      |
| Site settings | `_config.yml`                                         |

### Adding a team member

1. Add the photo to `assets/img/` — **JPEG, max 800px wide, under ~150 KB**.
2. Create `_pages/about_<name>.md` with the bio. Copy an existing one for the format; note these files have no YAML front matter by design, and are excluded from the built site so they aren't published as raw markdown.
3. Add a block to the `profiles:` list in `_pages/profiles.md` pointing at both.

### Adding a news item

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

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000` in a browser.

## Before you push

CI runs Prettier on every push and will fail the build if formatting is off. Run it first:

```bash
npm install
npx prettier --write .
```

Or install the hook once and forget about it:

```bash
pip install pre-commit && pre-commit install
```

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site and publishes it to the `gh-pages` branch. **Check the Actions tab after pushing** — if the workflow fails, the live site silently keeps serving the previous build.

## Conventions

- The lab name is styled **A:Ai Research Lab** (singular "Lab", colon after the first A).
- Images: JPEG for photographs, PNG only where transparency is needed. Responsive-image generation is disabled, so whatever you commit is what visitors download — resize before committing.
