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
- [ ] **Profile links:** consider moving the ORCID and Google Scholar links from
  the Works intro up into the links list beside Email, LinkedIn and GitHub.

Done:
- [x] Shrink profile photo and strip metadata, fix `author` key, fix greeting typo (PR #1).
- [x] Responsive profile photo, add site `url` (PR #2).
