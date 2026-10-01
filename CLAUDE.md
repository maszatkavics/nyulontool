# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Tiny static site, hosted by GitHub Pages at https://maszatkavics.github.io/nyulontool/ (served straight from the repo, branch root). There is no build, lint, or test tooling: plain HTML + inline CSS, no JS framework. To preview, open `index.html` in a browser or run `python3 -m http.server`.

## Product direction (from the owner)

- A modern, "blog-like" site: a front page with a grid of articles, where each article is a **cover image that is clickable** and leads to the article subpage.
- Design is "geek": black background, monospace font, wheat-colored text. Keep CSS inline in each HTML file (as the original did).
- **Super mobile friendly** is a hard requirement (viewport meta, single column on phones, large tap targets). The owner checks changes on a phone via the live URL, so commit and push to the designated branch/main when work is done, then wait for feedback.
- The site title `-= nyúl-ON-tool =-` stays.

## Structure

- `index.html` – blog front page; each article is an `<a class="card">` in `.feed` with a cover image + title. Add new articles by adding another card.
- `nyul/index.html` – first article (URL `/nyulontool/nyul/`). Header is a 3-column grid (`←` back link | centered `-= nyúl-ON-tool =-` | empty spacer) at the same size as the front page; below it a left-aligned `> NYÚL` article title, then the full-width cover-fit GIF.
- `nyul.gif` (~8.7 MB, article content) and `nyul-orig.jpeg` (~125 KB, used as the lightweight card cover so the front page loads fast on mobile). Subpages reference shared assets with `../`.

## Conventions

- Each article lives in its own folder with an `index.html`, so URLs have no `.html` suffix.
- Keep covers small/optimized; avoid putting the big GIF on the front page.
- Every page ends with a small `© kavics` footer. Every article page should follow the subpage layout: back-arrow header, then `> TITLE` on its own line, then content, then footer.
- Workflow: owner prefers pushing straight to `main` (no PRs) for this hobby project.
