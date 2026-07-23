# davidsmts.github.io

Personal research site — [davidsmts.github.io](https://davidsmts.github.io).

Plain Jekyll on GitHub Pages, no gem theme, no build step. Push to `main` and
Pages rebuilds it.

```
_config.yml              site title, description, email
_data/publications.yml   the publication list — edit this, not the HTML
_layouts/default.html    page shell: meta tags, nav, theme toggle, footer
index.html               the single page
assets/main.css          all styles (light + dark)
papers/                  self-hosted PDFs
```

## Adding a paper

Add an entry at the top of `_data/publications.yml`:

```yaml
- title: "Paper Title"
  authors: "First Author, David Schmotz, Last Author"   # your name is bolded automatically
  year: 2026
  venue: "Preprint"
  status: "Under review"        # optional badge
  summary: >-
    Two or three sentences on what the paper shows.
  note: >-
    Optional single-line highlight.
  tags: [Topic, Topic]
  links:
    - name: arXiv
      url: https://arxiv.org/abs/XXXX.XXXXX
```

The first entry in `links` also becomes the paper's title link. To host the PDF
here, drop it in `papers/` and link it as `url: /papers/name.pdf`.

Every field except `title` and `authors` is optional — omit what you don't have
and the layout adapts. Use `*` in the author string for equal contribution; the
footnote under the list already explains it.

## Local preview

Requires Ruby and the `github-pages` gem:

```sh
bundle exec jekyll serve   # http://localhost:4000
```
