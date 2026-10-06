# Oshmita Sarkar — Personal Website

Source for my personal website, published at
[oshmita26.github.io](https://oshmita26.github.io).

It's a [Jekyll](https://jekyllrb.com/) site built on the
[al-folio](https://github.com/alshedivat/al-folio) theme and hosted on
GitHub Pages.

## Content

- **Projects** — `_projects/`
- **CV** — `_data/cv.yml` (rendered to the `/cv/` page and a PDF via RenderCV)
- **Bookshelf** — `_books/` with cover images in `assets/img/book_covers/`
- **Organizations** — `_pages/organizations.md`
- **Pages & navigation** — `_pages/`
- **Site configuration** — `_config.yml`

## Running locally

From the repo root:

```bash
bundle install
npm ci
bundle exec jekyll serve
```

The site is then available at <http://localhost:4000/oshmita.github.io/>.

> **Note:** this site's `baseurl` is `/oshmita.github.io` (set in `_config.yml`),
> so the dev server serves under that subpath — not the root.

### Useful checks

```bash
npx prettier . --write          # format Markdown, YAML, and Liquid
npm run lint:style-contract     # enforce the al-folio thin-starter boundary
bundle exec jekyll build        # production build into _site/
```

## Credits

Built with the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme,
which is based on the [\*folio](https://github.com/bogoli/-folio) design.

## License

Released under the [MIT License](LICENSE).
