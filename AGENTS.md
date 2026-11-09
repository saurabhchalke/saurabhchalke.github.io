# AGENTS.md

Guidance for AI agents working in this repository.

## What this is

The personal blog and homepage of Saurabh Chalke (co-founder of [Thinking Balloon](https://thinkingballoon.com)), served at **https://saurabhchalke.com**.

- Static site built with **Jekyll**, hosted on **GitHub Pages** from the `main` branch. Pushing to `origin/main` deploys; GitHub rebuilds the site in a minute or two.
- No Gemfile, no CI, no build scripts. GitHub Pages builds with its own Jekyll (from the `github-pages` gem) and only the plugins listed in `_config.yml`: `jekyll-seo-tag`, `jekyll-paginate`, `jekyll-sitemap`.
- Custom domain comes from `CNAME`. The look is a terminal-style theme derived from "hacker-blog"; `README.md` is mostly that theme's original README.

## Ground rules

1. **The writing belongs to the author.** Posts are personal essays. When asked to publish text, use it verbatim. Do not rephrase, tighten, "improve", change tone, or add sentences. Purely mechanical fixes (a stray double space, broken Markdown) are fine, but list every one of them when you report back.
2. **Never commit or push without explicit approval.** The author reviews every change first.
3. **Keep it dependency-free.** Don't add a Gemfile, new plugins (GitHub Pages only allows its whitelisted set), JS frameworks, or build tooling unless asked.
4. **Leave sensitive or identity files alone unless asked:** `CNAME`, `google_analytics` in `_config.yml`, `pgp.md`, `assets/pgp/`, `license.md`.

## Repository map

| Path | Purpose |
| --- | --- |
| `_config.yml` | Site settings: title, author, `permalink: /:title`, `paginate: 5`, `future: true`, plugins. Restart `jekyll serve` after editing it. |
| `_posts/` | Blog posts, `YYYY-MM-DD-slug.md`. |
| `_layouts/default.html` | Page shell, pagination, footer, analytics include. |
| `_layouts/post.html` | Renders the post title as `<h2>`, then the date, then the content. |
| `_layouts/page.html` | Static pages (about, archive, pgp). |
| `_includes/head.html` | `<title>`, stylesheet, feed link, `{% seo %}`. |
| `_includes/header.html` | Terminal-style site header (`SaurabhChalke@home:~$`). |
| `_includes/links.html` | Nav links: whoami, blog, pgp, rss. |
| `_includes/footer.html` | Owner name and current year. |
| `_includes/analytics.html` | GA4 snippet, only included when `google_analytics` is set. |
| `_sass/base.scss` | All site styles (one mobile breakpoint at 768px). |
| `_sass/_default_colors.scss` | Color palette. |
| `_sass/rouge-base16-dark.scss` | Code highlighting theme. |
| `css/main.scss` | Sass entry point; imports `base`. |
| `index.html` | Home page: paginated post list with a 50-word teaser per post. |
| `archive.md` | `/archive`: all posts grouped by year. |
| `about.md` | `/about` ("whoami"). |
| `pgp.md`, `assets/pgp/` | `/pgp/` and the public key. |
| `atom.xml` | Feed of the 10 latest posts (RSS 2.0 despite the name), linked as "rss". |
| `assets/images/<post-slug>/` | Images for each post. |
| `404.md`, `robots.txt`, `CNAME`, `license.md` | Error page, crawler rules, custom domain, CC0 license. |

## Adding a post

1. **Filename:** `_posts/YYYY-MM-DD-slug.md`. The `.md` extension is required; Jekyll silently skips files without one.
2. **URL:** with `permalink: /:title`, the post lives at `/<slug>` (the date is not in the URL). Pick the slug carefully, since renaming it later breaks inbound links.
3. **Front matter** (match the recent posts):

   ```yaml
   ---
   title: "Short, Evocative Title"
   layout: post
   date: 2026-11-09
   categories: [Aerospace, Innovation]
   published: true
   ---
   ```

   - The front matter `date` controls the displayed date and ordering, and overrides the filename date. Keep the two in sync for new posts.
   - `future: true` is set, so a future-dated post goes live as soon as it is pushed. Use `published: false` to hold a draft.
   - Categories are Title Case, usually three or four, reusing existing ones where they fit (Aerospace, Defense, Stratosphere, Innovation, Air Pollution, Weather, Energy, Sustainability, Game Theory, Musings, Aerostats, Civil Liberties). They are metadata only; no layout renders them.
4. **Title style:** short, idiomatic or metaphorical, always quoted in YAML. Examples: "SpaceX for the Stratosphere", "A New Sensory Organ for Civilization", "Catching Lightning in a Bottle", "Lighter Than Air, Heavier Than It Looks".
5. **Body:** the layout already prints the title, so don't repeat it as a heading. Use `##` for sections. The first paragraph doubles as the home page teaser (first 50 words, HTML stripped).

## Writing and formatting conventions

- Markdown is Kramdown (GitHub Pages default). Footnotes use `[^1]` in text and `[^1]: ...` at the end of the post.
- Link generously and inline to primary sources and Wikipedia.
- Recent posts use curly quotes and apostrophes (’ “ ”), but the author sometimes types straight ones. Leave the author's characters as written.
- Recent posts contain no em dashes. Don't introduce any.
- Anything inside `{{ }}` or `{% %}` in a post is processed as Liquid. Wrap code samples that contain those sequences in `{% raw %}...{% endraw %}`.
- Raw HTML (styled `<p>`, `<div>`, `<iframe>`) renders on the site but not in GitHub's Markdown file viewer. That's expected.

### Images

Store them in `assets/images/<post-slug>/`. Use JPEG for photos and PNG for diagrams and logos, and keep files reasonably small (compress large photos; existing ones are roughly 100 KB to 1 MB). Embed with `relative_url` and real alt text:

```html
<p style="text-align:center">
  <img src="{{ '/assets/images/<post-slug>/photo.jpeg' | relative_url }}" alt="Describe the image" style="width:80%; height:auto;">
</p>
```

Older posts use bare `/assets/...` paths. Those work because `baseurl` is `/`, but prefer `relative_url` in new content.

### Videos

A plain YouTube link shows no preview. Embed a responsive player instead, using YouTube's privacy-enhanced domain (in keeping with the site's privacy stance):

```html
<div style="position:relative; width:100%; aspect-ratio:16/9; margin: 1rem 0;">
  <iframe src="https://www.youtube-nocookie.com/embed/VIDEO_ID" title="Describe the video" style="position:absolute; inset:0; width:100%; height:100%; border:0;" allow="accelerometer; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>
```

## Previewing locally

```bash
gem install jekyll jekyll-seo-tag jekyll-paginate jekyll-sitemap
jekyll serve --watch --port 8000   # then open http://localhost:8000
```

For closer parity with production, `gem install github-pages` and run `jekyll serve`. Build output goes to `_site/`, which is gitignored. If no Ruby toolchain is available, say so rather than claiming the build was verified.

## Git conventions

- Single branch: `main`. Remote: `origin` (`git@github.com:saurabhchalke/saurabhchalke.github.io.git`).
- Commit messages follow a lowercase conventional-commit style:
  - `docs: add <post title>` for a new post or new page content
  - `fix: ...` for corrections and edits to existing posts
  - `style: ...` for CSS and visual changes
  - `chore: ...` for assets, config, and housekeeping
- Commit a post and its images together. `.DS_Store` files are gitignored; never add them.

## Known quirks

Flag these if relevant, but fix them only when asked:

- `_posts/2024-07-31-speech-to-text-meta-quest` has no `.md` extension, so it has never been published. Renaming it would publish it at `/speech-to-text-meta-quest`. Its image alt text was also copied from the MPC post.
- `atom.xml` has small issues: its self link points to `/feed.xml` (the feed is served at `/atom.xml`), item links contain a double slash, and each item has a duplicate `<link>` element.
- `_includes/footer.html` links to `saurabhchalke.github.io` rather than the custom domain (it redirects, so it's harmless).
- `README.md` is the upstream theme's generic README (for example, it says to push to `master`; this repo uses `main`).
