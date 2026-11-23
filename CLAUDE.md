# akhilbhartiya.github.io

Personal academic website, built with Jekyll on GitHub Pages using the
`minima` theme. GitHub Pages builds from `main` automatically.

## Layout
- `_config.yml`: site settings (title, author, url, theme).
- `index.md`: the whole home page, with bio, links, posts list and Works.
- `_posts/`: blog posts, named `YYYY-MM-DD-title.md`.
- `assets/main.scss`: imports minima and holds our custom styles.
- `profile.jpg`: profile photo, kept at about 300 px wide with metadata stripped.

## Conventions
- Works entries: the title, then the author list (Akhil Bhartiya unlinked and
  not bold, co-authors linked to their ORCID), then a dated DOI/arXiv link.
  Newest first.
- Make changes on a branch and merge to `main` through a pull request.

## Plan
Postponed items, to decide later:
- [ ] **Placeholder post:** `_posts/2026-07-30-welcome-to-my-blog.md` is sample
  text. Replace it with a real first post, or hide the Posts section until
  there is one.
- [ ] **Profile links:** consider moving the ORCID and Google Scholar links from
  the Works intro up into the links list beside Email, LinkedIn and GitHub.

Done:
- [x] Shrink profile photo and strip metadata, fix `author` key, fix greeting typo (PR #1).
- [x] Responsive profile photo, add site `url` (PR #2).
