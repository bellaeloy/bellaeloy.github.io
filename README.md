# bellaeloy.github.io

Personal site of Isabella Eloy Cavalcanti. It uses [Hugo](https://gohugo.io/)
with the [Coder](https://github.com/luizdepra/hugo-coder) theme, and it deploys
to GitHub Pages.

## Run it locally

You need the **extended** build of Hugo (the theme compiles SCSS).

```sh
# Arch Linux
sudo pacman -S hugo

# macOS
brew install hugo

# Or download the binary: https://github.com/gohugoio/hugo/releases
# Pick the file named hugo_extended_<version>_<platform>
```

Clone the repository with its theme submodule, then start the server:

```sh
git clone --recurse-submodules https://github.com/bellaeloy/bellaeloy.github.io.git
cd bellaeloy.github.io
hugo server -D
```

Open <http://localhost:1313>. The server reloads the page when you save a file.

If you cloned without `--recurse-submodules`, run this once:

```sh
git submodule update --init --recursive
```

To build the static files into `public/`:

```sh
hugo --gc --minify
```

## Deploy

Push to `main`. The workflow in `.github/workflows/hugo.yaml` builds the site
and publishes it. Set **Settings → Pages → Source** to **GitHub Actions** one
time, before the first push.

## Add a project

```sh
hugo new content projects/my-new-project.md
```

That command uses `archetypes/projects.md`, so the new file already has every
field. The fields are:

| Field | What it does |
| --- | --- |
| `title` | Project name. |
| `date` | Position on the timeline. The timeline groups by year, newest first. |
| `year`, `role`, `location` | The small label on the card and the fact list. |
| `summary` | The text on the card and on the timeline. Keep it to two sentences. |
| `cover` | Path under `static/`. Use 1200×750 px. |
| `tools` | List of software. It shows in the fact list. |
| `tags` | List of tags. Each tag gets its own page. |
| `featured` | `true` makes the card span the full width of the grid. Use it for one project. |
| `links` | Repeat the `[[links]]` block for each link. A `url` of `"#"` renders as a grey placeholder. |

The Projects page and the Timeline page both read this same folder. You add a
project one time, and it appears on both.

## Add an artwork

The Artwork page reads one file: `content/artwork.md`. Add a `[[pieces]]` block
to its front matter for each drawing.

```toml
[[pieces]]
title = "Axonometric Study"
year = "2025"
medium = "Ink on paper, 42 x 59 cm"
image = "/images/artwork/axonometric-study.svg"
ratio = "9 / 11"
```

`ratio` sets the shape of the frame, so the gallery keeps its columns tidy
before the image loads. Use the real proportion of the piece.

## Light and dark artwork

Every generated drawing exists twice: `name.svg` and `name-dark.svg`. The dark
file carries the dark page background, so a drawing joins the card instead of
sitting on it as a bright rectangle. The site picks the file with a CSS custom
property, which keeps the manual light/dark toggle working.

If you drop in a photo with no dark twin, the site uses the one file for both
schemes. To give any image an explicit dark version, add `coverDark` to a
project, or `imageDark` to an artwork piece.

## Colors

The four brand colors live in `assets/scss/_palette.scss`:

| Color | Hex | Use |
| --- | --- | --- |
| Blue | `#0000ff` | Links, markers, accents. |
| Gold | `#ffd966` | Tags, timeline rail, cover art. |
| Cream | `#fff2cc` | Page background. |
| Ink | `#595959` | Body text. |

`assets/scss/_variables.scss` maps those four onto the theme, for the light
scheme and the dark scheme. `assets/scss/custom.scss` styles the cards and the
timeline. Change a hex in `_palette.scss`, and the whole site follows.

## What is still a placeholder

Replace these before you share the site.

- **Five projects.** Each one has `placeholder = true` in its front matter and
  an HTML comment at the top of the body: `transit-corridor-density-model`,
  `riverfront-commons`, `urban-void-atlas`, `social-housing-typologies`,
  `parametric-facade-study`.
- **All six artworks** in `content/artwork.md`.
- **Three projects are real** and need no change: `ghz-network`,
  `ghz-glossario`, `civic-innovation-python`.
- **`content/about.md`.** Rewrite it in your own words.
- **Cover images.** `static/images/projects/*.svg` and
  `static/images/artwork/*.svg` are generated geometric drawings. Swap in
  photos, plans or renders.
- **Social links.** `config.toml` has GitHub live. LinkedIn, Instagram and email
  are commented out. Fill in the URL and uncomment each block you want.
- **Resume.** Drop a PDF at `static/resume.pdf`, then uncomment the `Resume/CV`
  menu block in `config.toml`.
- **`baseURL`.** It is set to `https://bellaeloy.github.io/`. Change it if you
  use a custom domain, and add a `static/CNAME` file with that domain.

To find every placeholder in one command:

```sh
grep -rn "PLACEHOLDER\|placeholder = true" content/
```
