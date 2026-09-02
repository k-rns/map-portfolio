# map-portfolio

30 Day Map Challenge repo that doubles as a cartographic portfolio, built as a Jekyll site and published to GitHub Pages at [k-rns.github.io/map-portfolio](https://k-rns.github.io/map-portfolio).

## Folder structure

```
.github/workflows/   GitHub Actions workflow that builds and deploys the site
_layouts/            HTML templates used by pages and map posts
_maps/               One Markdown file per challenge day (the "maps" collection)
assets/maps/         Map image files referenced by the day pages
index.md             Homepage: intro text + grid of all 30 day cards
about.md             About page
resources.md         Data Resources page (datasets and tools used)
style.css            Site-wide styles
_config.yml          Jekyll site configuration
LICENSE              Repo license
```

### `.github/workflows/`
- `jekyll-gh-pages.yml` — builds the Jekyll site and deploys it to GitHub Pages on every push to `main` (or manually via the Actions tab).

### `_layouts/`
- `default.html` — base layout shared by `index.md`, `about.md`, and `resources.md`. Provides the header/nav (CHALLENGE, RESOURCES, ABOUT), footer, and page `<title>`.
- `map.html` — layout used by each file in `_maps/`. Renders the day number, title, map image, and optional Challenge/Data/How it was made/Tools sections from front matter, followed by the page's own Markdown content.

### `_maps/`
- `day-01.md` through `day-30.md` — one entry per challenge day. Each file's front matter sets `title`, `day`, and `image` (path to the map image), plus optional `challenge`, `data`, `methods`, and `tools` fields; the Markdown body has "About this map," "Data," "How it was made," and "Tools" sections to fill in. `index.md` loops over these by `day` number to build the homepage grid, showing a placeholder box for any day that doesn't have a file yet.

### `assets/maps/`
- Map image files (e.g. `2026-day-01.png`) referenced by the `image` front-matter field in the corresponding `_maps/day-XX.md` file. Contains a `.gitkeep` so the folder is tracked even when empty.

### Top-level pages
- `index.md` — homepage: challenge intro text plus a 30-card grid (one per day) linking to each map page.
- `about.md` — About page (`/about/`), a short bio.
- `resources.md` — Data Resources page (`/resources/`), a list of datasets and tools used across the challenge, grouped by category.

### Other files
- `style.css` — all site styling (header/nav, map grid, map page layout, footer).
- `_config.yml` — Jekyll config: site title, description, base URL, and the `maps` collection definition (outputs each `_maps/*.md` file to `/maps/:name/`).
- `LICENSE` — repository license.
