# Blog

Themeless Hugo site. Markup is in `layouts/`, appearance is in `assets/css/main.css`.

## Local

Hugo 0.165+ (`hugo version`).

```bash
hugo server
```

New dated post:

```bash
hugo new content posts/my-post.md
```

Set `draft: false` (or drop the field) when it should be published. `hugo server --buildDrafts` shows drafts.

## Files to edit

| Path | What it is |
| --- | --- |
| `hugo.toml` | title, menus, pagination, author |
| `assets/css/main.css` | all styling; start with the `:root` variables |
| `layouts/baseof.html` | HTML shell |
| `layouts/home.html` | index (dated post list) |
| `layouts/posts/page.html` | a single post |
| `layouts/page.html` | other pages (about, …) |
| `layouts/section.html` | `/posts/` archive |
| `layouts/taxonomy.html` | `/tags/`, `/categories/` |
| `layouts/term.html` | one tag or category |
| `layouts/_partials/` | header, footer, lists, pagination |
| `content/posts/` | Markdown posts |

## GitHub Pages

1. Create a GitHub repository and add it as `origin`.
2. In the repo: **Settings → Pages → Source: GitHub Actions**.
3. Push `master`. The workflow in `.github/workflows/hugo.yaml` builds with the Pages URL as `baseURL`.

For a user site, name the repo `username.github.io`. For a project site, the site lives at `https://username.github.io/repo/`.

Change `title` and `params.author` in `hugo.toml` before the first public push. `baseURL` there is only for local builds; Actions overrides it.
