# akhilbhartiya.github.io

Personal academic website, built with Jekyll on GitHub Pages using the
`minima` theme. GitHub Pages builds from `main` automatically.

This file is the shared instructions for **every** AI agent working on this
repo (Claude Code, Google Antigravity, Gemini CLI, Codex, Cursor, Copilot and
others). Keep all rules, conventions and the plan in this file and nowhere
else. Do not add tool-specific copies such as `CLAUDE.md` or `GEMINI.md`;
Claude Code and Antigravity read this file directly.

## Layout
- `AGENTS.md`: this file.
- `_config.yml`: site settings (title, author, url, theme) and the `exclude`
  list that keeps agent files off the site.
- `index.md`: home page, with the intro, profile links and the list of posts.
- `works.md`: list of papers at `/works/`, shown in the header menu.
- `_posts/`: published posts, named `YYYY-MM-DD-title.md`.
- `_drafts/`: Obsidian notes, not published on the site but **visible in the
  public GitHub repo**.
- `assets/main.scss`: imports minima and holds our custom styles.
- `assets/images/`: images used in posts.
- `profile.jpg`: profile photo, kept at about 300 px wide with metadata stripped.

## Working with several agents
- Start every task from the latest `main`, on a new branch named
  `<agent>/<short-topic>`, for example `antigravity/new-post` or
  `claude/works-update`. Never commit directly to `main`.
- Never push to another agent's open branch. If two tasks touch the same file,
  finish and merge one PR before starting the other.
- Keep each PR small and focused on one task.
- **The Plan section below is our shared memory.** When you finish, postpone
  or add a task, update the Plan in the same PR.
- In the PR description, say which agent made the change.

## Building locally
GitHub Pages builds the site itself, so the repo has no `Gemfile` (it is
gitignored on purpose; do not commit one). To check a change, build with a
Gemfile kept **outside** the repo:

```ruby
# /some/temp/dir/Gemfile
source "https://rubygems.org"
gem "jekyll", "~> 3.10"
gem "minima", "2.5.1"
gem "kramdown-parser-gfm"
gem "webrick"
gem "csv"
gem "base64"
gem "bigdecimal"
gem "logger"
```

```bash
cd /some/temp/dir
bundle install
bundle exec jekyll build -s /path/to/repo -d /some/temp/dir/site
```

Check the pages at both desktop and phone widths before opening a PR.

## Conventions
- Works entries: the title, then the author list (Akhil Bhartiya unlinked and
  not bold, co-authors linked to their ORCID), then a dated DOI/arXiv link.
  Newest first.
- Make changes on a branch and merge to `main` through a pull request.

## Publishing an Obsidian draft
To turn a note in `_drafts/` into a post:
1. Move it to `_posts/YYYY-MM-DD-slug.md`, where the slug is lowercase with
   hyphens and no spaces.
2. Add front matter with `layout: post`, `title:` and `date:`. Keep any
   existing Obsidian properties that are harmless.
3. Convert Obsidian-only syntax, which Jekyll does not render:
   - `[[Note]]` and `[[Note|text]]` become Markdown links to the published
     post, or plain text if the note is not published;
   - `![[image.png]]` becomes `![alt](/assets/images/image.png)`, with the
     image copied there and its metadata stripped;
   - `> [!note]` callouts become ordinary blockquotes;
   - `%% comments %%` are deleted, because Jekyll would publish them.
4. Build locally and check that the page renders.

## Rules
- **Security check before every pull request.** Before opening a PR, review the
  full diff for security problems, fix any you find, and add a short
  "Security check" section to the PR description saying what was checked. At
  minimum, check for:
  - secrets, tokens, passwords or private data in any file, including old
    commits on the branch;
  - personal metadata in images, such as EXIF location and device data (strip
    it);
  - third-party scripts, iframes or embeds, which should load only from
    trusted sources over `https`, with pinned versions;
  - links using `target="_blank"`, which need `rel="noopener noreferrer"`;
  - raw HTML or Liquid that echoes user-controlled or external content;
  - `_config.yml` changes that publish files meant to stay private (check
    `exclude`).

## Plan
Postponed items, to decide later:
- [ ] **Placeholder post:** `_posts/2026-07-30-welcome-to-my-blog.md` is sample
  text. Replace it with a real first post, or hide the Posts section until
  there is one.

Done:
- [x] Shrink profile photo and strip metadata, fix `author` key, fix greeting typo (PR #1).
- [x] Responsive profile photo, add site `url` (PR #2).
- [x] Security-check rule; Works on its own page; ORCID/Scholar in profile links;
  `_drafts/` for Obsidian notes (PR #3).
- [x] Shared `AGENTS.md` instructions for all agents, with no tool-specific copies (PR #4).
