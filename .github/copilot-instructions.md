# Copilot Instructions for SeonHoYoo.github.io

## 1) What this project is
- Static personal site built with Jekyll, served as GitHub Pages for repository `SeonHoYoo/SeonHoYoo.github.io`.
- Primary content in `_config.yml`, `index.md`, `undergrad-activities.md`, and `assets/main.scss`.
- Remote theme: `sproogen/resume-theme`; customizations are minimal and done via YAML front matter + content arrays.

## 2) Architecture and key files
- `_config.yml`: main site settings (profile, social links, sections, and theme/plugin config).
- `index.md`: homepage scaffold; theme is controlled by remote theme layouts.
- `undergrad-activities.md`: example content page with `layout: default` and markdown content.
- `assets/main.scss`: imports `modern-resume-theme` and is the only custom SCSS.
- `images/`: static assets referenced from config fields (favicons, profile image).

## 3) Workflow commands
- Local development (Ruby environment required):
  - `bundle install`
  - `bundle exec jekyll serve --livereload`
  - open `http://127.0.0.1:4000`
- Build output:
  - `bundle exec jekyll build` into `_site`.
- GitHub Pages is expected to use Jekyll default workflow, no CI scripts present.

## 4) Project conventions
- Content is managed through YAML `content` sections in `_config.yml`, not through a lot of discrete page files.
- Use markdown when adding sections and bullet lists in `about_content` and each `content` block.
- No `.jekyll-cache` or site build outputs tracked in repo.

## 5) Integration points + dependencies
- Remote theme (`sproogen/resume-theme`) + plugin `jekyll-seo-tag`.
- Keep theme-specific structures: `content: - title: ... layout: list` with nested `content` arrays.
- Assets are served from `assets/` and image paths are relative to repo root.

## 6) What AI agents should do first
1. Validate that `_config.yml` is consistent with theme schema (section keys: `about_profile_image`, `content`, etc.).
2. Keep changes minimal: adjust YAML content to avoid breaking no-code theme assumptions.
3. For style changes, target `assets/main.scss` and avoid editing remote theme internals.

## 7) Example edits
- Add new career bullet in `_config.yml` under `content: - title: Career`.
- Update profile image reference: `about_profile_image: images/profile.jpg`.
- Add project page by creating `.md` file with front matter `layout: default` and reference in nav.

---

> Feedback request: is any part of the site flow unclear (example: how sections map to components), or should I add a short checklist for staging/preview in GitHub Pages after commit?