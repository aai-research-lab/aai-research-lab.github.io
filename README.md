# A:Ai Research Lab

**Laboratory for Computational Science**
Department of Physics · California State University, Dominguez Hills

[aai-research-lab.github.io](https://aai-research-lab.github.io)

We work at the intersection of physics, chemistry, and biology, using mathematical and computational tools to address hard questions in biophysics and protein design, with applications in biomedicine and biotechnology.

## Research

**Biophysics.** We study the physical principles governing biomolecular interactions, and develop computational and machine learning methods to understand protein dynamics.

**Protein design.** We combine AI with biophysical understanding to design and engineer novel proteins with new structural and functional properties.

**Drug discovery.** We apply protein design to immunogen and antibody engineering, targeting practical problems in therapeutics for neurodegenerative diseases.

Our aim is that this work does not stay in the lab: the methods we build are meant to produce real therapeutic proteins that improve people's lives.

## Software

Open-source tools developed by the lab:

| Project                                                              | Description                                                                                                                                                                                                                                        |
| -------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FastMDAnalysis](https://github.com/aai-research-lab/FastMDAnalysis) | Automated, reproducible end-to-end analysis of molecular dynamics trajectories. One command replaces a scripting session. [`pip install fastmdanalysis`](https://pypi.org/project/fastmdanalysis/) · [docs](https://fastmdanalysis.readthedocs.io) |

## Selected publications

Aina, A. and Kwan, D. FastMDAnalysis: Software for Automated Analysis of Molecular Dynamics Trajectories. _Journal of Computational Chemistry_ **47**, e70350 (2026). [doi:10.1002/jcc.70350](https://doi.org/10.1002/jcc.70350)

Aina, A., Hsueh, S. C. C. and Plotkin, S. S. PROTHON: A Local Order Parameter-Based Method for Efficient Comparison of Protein Ensembles. _Journal of Chemical Information and Modeling_ (2023). [doi:10.1021/acs.jcim.3c00145](https://doi.org/10.1021/acs.jcim.3c00145)

Aina, A. _et al._ De Novo Design of a β-Helix Tau Protein Scaffold: An Oligomer-Selective Vaccine Immunogen Candidate for Alzheimer's Disease. _ACS Chemical Neuroscience_ (2023). [doi:10.1021/acschemneuro.3c00007](https://doi.org/10.1021/acschemneuro.3c00007)

The [full list](https://aai-research-lab.github.io/publications/) is on the site.

## Join us

We look for curious, motivated students and researchers with a foundation in mathematics, physics, chemistry, biology, or computer science. If you are interested in biological problems and want to build research expertise in an interdisciplinary setting, [get in touch](https://aai-research-lab.github.io/join/).

---

## About this repository

Source for the lab website. Built with [Jekyll](https://jekyllrb.com/) on the [al-folio](https://github.com/alshedivat/al-folio) theme; see [`al-folio_README.md`](al-folio_README.md) for upstream theme documentation.

### Editing content

| To change     | Edit                                                  |
| ------------- | ----------------------------------------------------- |
| Front page    | `_pages/about.md`                                     |
| Team members  | `_pages/profiles.md` + a `_pages/about_<name>.md` bio |
| Publications  | `_bibliography/papers.bib`                            |
| News items    | a new file in `_news/`                                |
| Teaching      | `_pages/teaching.md`                                  |
| Join page     | `_pages/join.md`                                      |
| Site settings | `_config.yml`                                         |

**Adding a team member.** Put the photo in `assets/img/` as JPEG, max 800px wide, under ~150 KB. Create `_pages/about_<name>.md` with the bio, copying an existing one for format — these files deliberately have no YAML front matter, and are excluded from the built site so they aren't published as raw markdown. Then add a block to the `profiles:` list in `_pages/profiles.md`.

**Adding a news item.** Create `_news/announcement_YYMMDDShortName.md`:

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

### Local preview

```bash
bundle install
bundle exec jekyll serve
```

The site is then served at `http://localhost:4000` — open that in a browser.

### Before pushing

CI runs Prettier on every push and fails the build if formatting is off:

```bash
npm install
npx prettier --write .
```

Or install the hook once: `pip install pre-commit && pre-commit install`

### Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site and publishes to the `gh-pages` branch. **Check the Actions tab after pushing** — if the workflow fails, the live site silently keeps serving the previous build.

### Conventions

- The lab name is styled **A:Ai Research Lab** — colon after the first A, singular "Lab".
- JPEG for photographs, PNG only where transparency is needed. Responsive-image generation is disabled, so whatever you commit is what visitors download.
