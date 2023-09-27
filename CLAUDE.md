# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Personal site at `pedromellogomes.github.io`. Jekyll blog built with the `github-pages` gem (so versions of Jekyll/plugins are pinned to whatever GitHub Pages currently supports). Theme: `minima`. Deploys automatically when pushed to the default branch of the `<user>.github.io` repo — no build step in CI to maintain.

## Commands

- Install deps: `bundle install`
- Local serve with live reload: `bundle exec jekyll serve` (http://localhost:4000)
- Build only: `bundle exec jekyll build` → outputs to `_site/`
- Drafts preview: `bundle exec jekyll serve --drafts`
- After editing `_config.yml`: restart the server (Jekyll does not auto-reload config).

## Architecture

- `_config.yml` — site-wide settings. Still contains placeholder values from the `jekyll new` scaffold (title, email, url, social handles) — update before treating output as real.
- `_posts/` — blog posts. Filename must be `YYYY-MM-DD-title.markdown` or Jekyll skips them. Front matter sets `layout`, `title`, `date`, `categories`.
- `index.markdown` uses `layout: home` from the `minima` theme (renders post list).
- `about.markdown` uses `layout: page`, served at `/about/` via `permalink`.
- `404.html` — custom 404.
- No local layouts/includes/sass — everything inherits from the installed `minima` gem. To customize, copy the file out of the gem (`bundle show minima`) into `_layouts/`, `_includes/`, or `_sass/` and edit there.

## Conventions

- Posts and pages are Markdown with YAML front matter; `permalink` controls the URL.
- `_site/`, `.jekyll-cache/`, `.sass-cache/`, `vendor/`, `Gemfile.lock` are gitignored — do not commit build artifacts.
- Plugin additions must be allowed by GitHub Pages (see https://pages.github.com/versions/) or the deploy will skip them.
