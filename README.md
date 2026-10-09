# zioniyes.github.io

This repo hosts my portfolio's front page (zioniyes.me). It is a plain Jekyll site with no external theme.

## Where things live

| To change | Edit |
| --- | --- |
| Site title, description, URL | `_config.yml` |
| Navigation links | `_data/nav.yml` |
| Page skeleton (head, header, footer) | `_layouts/default.html` and `_includes/` |
| Colors and small layout tweaks | `assets/css/main.css` (palette in the `:root` block) |
| Base styling | Pico CSS, loaded from a pinned version in `_includes/head.html` |
| Page content | `index.md`, `services.md`, `contact.md` |

Every page starts with front matter (`layout`, `title`, `permalink`). Pages without it are not wrapped in the layout.

## Preview locally

You need Ruby and Bundler.

```sh
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000. Changes reload when you save, except `_config.yml`, which needs a restart.

## Adding a page or a blog post

- New page: create a `.md` file with front matter `layout: default`, a `title`, and a `permalink`. Add it to `_data/nav.yml` if it should appear in the menu.
- Blog post with its own look: create `_layouts/post.html` that starts with `layout: default` in its own front matter, then overrides only the part it needs. Use it from a post's front matter with `layout: post`.

## Deploying

Pushes to `main` deploy the live site through `.github/workflows/pages.yml`. Work on other branches is only previewed locally. Merge to `main` when a change is ready to go live.

The photo gallery at `/gallery` is a separate ThumbsUp-generated site that also deploys through GitHub Pages. It is not built from this repo.
