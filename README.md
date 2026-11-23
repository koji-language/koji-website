# The website of Koji

The site of [Koji](https://github.com/koji-language/koji): its home page, its download page, and the
documentation of its last release, made from the `doc/` directory of the repository of Koji. The
generator is written in Koji.

## Building it

With `kojic` on your `PATH` and a checkout of the repository of Koji:

```sh
git clone https://github.com/koji-language/koji ../koji
kojic test src                         # the tests of the generator
kojic run src/site.kj ../koji site     # writes the site to site/
python3 -m http.server -d site         # to look at it, on http://localhost:8000
```

The generator stops with an error if a link of the site leads to a page or a heading that is not
there.

## What is where

| Path | What it is |
| --- | --- |
| `src/site.kj` | The generator: reads the documentation, writes the pages, checks the links. |
| `src/markdown.kj` | Markdown to HTML, as much of it as the documentation uses. |
| `src/highlight.kj` | The colors of the code of Koji. |
| `templates/` | The HTML of the pages: `page.html` for the documentation and the other pages, `home.html` for the home page. |
| `pages/` | The pages of the site in Markdown (`{{version}}` is the version of Koji), and the example of the home page. |
| `static/` | The files copied as they are: the style and the icon. |

The documentation itself is in the repository of Koji: to change it, change `doc/` there. The navigation
of the documentation is that of `doc/README.md`.

## Publishing

`.github/workflows/pages.yml` builds the site with the last release of Koji and publishes it with
GitHub Pages, at each push to `main`. After a release of Koji, run it by hand (Actions, Pages, Run
workflow) to publish the documentation of the new version.
