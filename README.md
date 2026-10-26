# rad1092.github.io

The source of [rad1092.github.io](https://rad1092.github.io), a developer portfolio. It is a plain Jekyll site
that GitHub Pages builds from `main`; there is no theme and no JavaScript framework.

English lives at `/` and Korean at `/ko/`. A Korean browser opening an English page is sent to the same page in
Korean, and a language picked with the EN / 한국어 switch is remembered and wins after that.

| Path | What |
|---|---|
| `_data/home.yml` | Home page copy in both languages, and which projects are featured |
| `_data/projects.yml` | The featured projects: links, media, summary and facts |
| `_data/t.yml` | Interface strings |
| `projects/`, `ko/projects/` | Case study pages |
| `_layouts/`, `_includes/` | Page templates |
| `assets/css/site.css` | All styles |
| `assets/media/` | Screenshots, GIFs and short videos |

To preview locally:

```sh
jekyll serve
```
