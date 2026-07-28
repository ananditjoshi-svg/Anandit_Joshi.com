# ananditjoshi.com

Personal site and research register. Built as a Jekyll site so GitHub Pages
builds it automatically — no local tooling required.

## 1. Deploy to GitHub Pages

1. Create a new GitHub repository (e.g. `ananditjoshi.com`). Public repos get
   free Pages hosting.
2. Upload everything in this folder to the repo root (drag-and-drop on
   github.com works, or `git push`).
3. In the repo: **Settings → Pages → Source: Deploy from a branch**, select
   `main` / root, and save.
4. Within a minute or two the site is live at
   `https://<your-username>.github.io/<repo-name>/`.

## 2. Point ananditjoshi.com (GoDaddy DNS)

1. In the repo's **Settings → Pages → Custom domain**, enter
   `ananditjoshi.com` and save. (The `CNAME` file in this repo keeps that
   setting from being wiped on future deploys.)
2. In GoDaddy: **My Products → your domain → DNS**. Remove any existing
   A / AAAA records for `@` (these point to your old GoDaddy site, which will
   go offline — intended), then add:

   | Type  | Name | Value                     |
   |-------|------|---------------------------|
   | A     | @    | 185.199.108.153           |
   | A     | @    | 185.199.109.153           |
   | A     | @    | 185.199.110.153           |
   | A     | @    | 185.199.111.153           |
   | CNAME | www  | `<your-username>.github.io` |

3. Back in GitHub Pages settings, wait for the DNS check to pass, then tick
   **Enforce HTTPS**. Propagation can take up to a day but is usually minutes.

## 3. Publishing a new article

Add a markdown file to `_posts/` named `YYYY-MM-DD-your-slug.md`:

```markdown
---
title: "Your title here"
tag: "Study"        # or "Note" — shown as the badge in the register
summary: "One-sentence summary shown under the title."
---

Your article, in plain markdown.
```

Commit it (or drag it into `_posts/` on github.com) — the site rebuilds and
the article appears on the homepage and the research register automatically.
You can also edit posts directly in the GitHub web editor.

## Customizing

- **Email / LinkedIn** — edit the footer links in `_layouts/default.html`.
- **Bio copy** — edit the About section in `index.html`.
- **Colors & type** — everything derives from the CSS variables at the top of
  `assets/css/main.css`.
