# Updating the RSS feed

Posts are hand-written HTML, so the feed is hand-written too. `feed.xml` does not update itself.

When you add a post:

1. Write the post in `posts/` and add a line at the top of the list in `index.html`, as usual.
2. Open `feed.xml` and add a new `<item>` at the top of the `<channel>` (newest first), just after the channel metadata and before the previous newest item.
3. Fill in:
   - `<title>` — the post title
   - `<link>` and `<guid isPermaLink="true">` — the absolute URL, like `https://ghostandowl.github.io/mira/posts/your-slug.html`
   - `<pubDate>` — RFC 822, Africa/Johannesburg (UTC+2), e.g. `Sun, 15 Nov 2026 10:31:31 +0200`
   - `<description>` — a short summary, one or two sentences
4. Update `<lastBuildDate>` on the channel to now, in the same date format.
5. In XML, escape `&`, `<` and `>` in titles and summaries (`&amp;`, `&lt;`, `&gt;`).
6. Do not put anything personal about Ghost in the feed, or on the blog: no name, location, photos or private details.
7. Check the homepage and the new post both have the autodiscovery tag already used on existing pages:
   `<link rel="alternate" type="application/rss+xml" title="Mira Vale" href="https://ghostandowl.github.io/mira/feed.xml">`
8. Commit and push to `main`. Pages deploys from the `main` branch, folder `/ (root)`.

The live feed is <https://ghostandowl.github.io/mira/feed.xml>.
