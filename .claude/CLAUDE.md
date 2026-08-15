# Awesome-Shiksha

A content-only MkDocs documentation site — not a software application. It's a personal, open-content
initiative proposing an informal, modular education curriculum. Content is community-contributed via
GitHub issues (requesting topics) and PRs (submitting content). There is no application code.

## Repo structure

- `docs/` — source Markdown content. Edit here.
  - `docs/README.md` — homepage / mission statement (rendered as the site's "Home" nav entry)
  - `docs/<age-group>/` — content organized by age group: `3-5-years`, `6-9-years`, `10-13-years`,
    `14-15-years`. Each has a `README.md` (subject index) and one Markdown file per subject
    (`maths.md`, `science.md`, `english.md`, `ethics.md`, ...). Topics are `##` sections within a
    subject file — don't create a new file per topic.
  - `docs/tags.md` — the material `tags` plugin renders the filterable tag index here
  - `docs/contribution/README.md` — contribution guideline, content template, directory/tag
    conventions, and contributor setup steps
- `site/` — generated static build output (git-ignored). Never hand-edit; regenerate with `mkdocs build`.
- `mkdocs.yaml` — MkDocs config: site metadata, theme (`material`), `tags` plugin, and the `nav:` list.
- `requirements.txt` — pins `mkdocs-material` (installs `mkdocs` as a dependency)
- `gh-pages` branch — deployed output, published via `mkdocs gh-deploy`; not touched on `main`.

## Working conventions

- Only edit files under `docs/`. `site/` is build output.
- New subject pages follow the existing pattern: add `<age-group>/<subject>.md` with a `tags:`
  frontmatter block (subject + age-group tags at minimum), link it from that age group's
  `README.md`, and add it to `mkdocs.yaml`'s `nav:` — it's manual, not auto-generated.
- Every subject page must start with YAML frontmatter listing tags, e.g.:
  ```yaml
  ---
  tags:
    - maths
    - 6-9-years
  ---
  ```
  Reuse existing tags where they fit (check `docs/tags.md` after building) instead of inventing
  near-duplicates.
- The project lives at `github.com/EkPratishat/Awesome-Shiksha` (matches the `origin` remote) — keep
  `repo_url`/`site_url` in `mkdocs.yaml` and any GitHub links in docs pointed at this org.

## Content template for topic pages

Per `docs/contribution/README.md`, each topic should fit within a ~1-hour session and include:

1. **Objective** — why the topic matters, expected learning outcome
2. **Methodology** — how it's taught (video, blog, book chapter, etc.)
3. **Exercise** (optional) — quality over quantity
4. **Evaluation Criteria** — can be qualitative, be creative and relevant
5. **Contributor** (optional) — name/contact

## Build / preview

```bash
pip install -r requirements.txt
mkdocs serve      # local preview
mkdocs build      # produces site/
mkdocs gh-deploy  # publishes to gh-pages
```
