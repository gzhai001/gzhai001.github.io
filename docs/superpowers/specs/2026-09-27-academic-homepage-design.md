# Design: Guocong Zhai Academic Homepage (gzhai001.github.io)

Date: 2026-09-27 (revised same day after discovering existing AcademicPages site)
Status: Direction approved by user — **revive the existing AcademicPages site**

## Background

Initial plan was a hand-crafted single-page static HTML site (Style A mockup
approved). During setup we discovered `~/gzhai001.github.io` already contains a
partially configured **AcademicPages (Jekyll)** site from Jan–Apr 2025 with most
content already written. User chose to revive it instead. The remote repo
`gzhai001/gzhai001.github.io` no longer exists on GitHub (site returns 404), so
it must be recreated and pushed.

## Current state of the local site (verified)

- `_config.yml`: title, description, URL, repository set; author sidebar filled
  (avatar `profile.png` — exists in `images/`, bio, location, email, Google
  Scholar, ResearchGate, GitHub).
- `_pages/about.md` (homepage): bio, two research themes, education,
  Prospective Students, Contact.
- `_pages/research.md`: two-theme research overview + selected funding list.
- `_pages/publications.md`: full publication list (journal + working papers),
  already includes 2026 updates (e.g., JCM paper now published: 59, 100610).
- `_pages/cv.md`: education, appointments, funding.
- `_data/navigation.yml`: Publications / Research / CV.
- Untracked: `.bundle/`, `vendor/` (must not be committed).
- Template placeholder files still present: `files/paper*.pdf`,
  `files/slides*.pdf`, stock images in `images/`, `_drafts/`.

## Work to complete the revival

1. **Content polish**
   - Add a short **News** section to `_pages/about.md` (from CV dates):
     JCM paper published (2026), NSFC Young Scientists Fund (2026),
     joined SWJTU (2025), TRD guest editorship (2025).
   - Verify `about.md` / `cv.md` / `research.md` / `publications.md` match the
     CV; fix discrepancies (CV is source of truth; note publications.md has
     newer data than CV for JCM — keep the newer published info).
   - Add Awards & Honors and Professional Service to `_pages/cv.md`
     (from CV: ODU awards, outstanding reviewer, editorial board roles,
     guest editorship, 60+ peer reviews).
2. **Cleanup**
   - Delete template placeholder files: `files/paper1-3.pdf`,
     `files/slides1-3.pdf`, stock images (`foo-bar-identity*`,
     `image-alignment*`, `paragraph-indent*`, `500x300.png`,
     `3953273590_704e3899d5_m.jpg`, `homepage.png`, `editing-talk.png`),
     `_drafts/` contents.
   - Confirm `.gitignore` covers `.bundle/`, `vendor/`, `.sass-cache/`,
     `.jekyll-cache/`.
   - Keep `images/profile.png` (avatar), favicon set, `site-logo.png` if used.
3. **Deployment**
   - Create public repo `gzhai001/gzhai001.github.io` via GitHub REST API
     using the existing macOS keychain credential (never echoed/committed).
   - Push `main` over HTTPS (repo-local `credential.helper=osxkeychain`).
   - GitHub Pages builds `username.github.io` repos automatically (Jekyll via
     github-pages gem — AcademicPages' standard deployment path); enable Pages
     via API if not auto-enabled.

## Verification

1. After push, poll the Pages build status via API until built.
2. Load https://gzhai001.github.io in the browser (via Kimi extension),
   screenshot, and confirm: homepage bio renders with sidebar avatar,
   Publications/Research/CV pages load, links (Scholar, GitHub, email) work.
3. Confirm no template placeholder content is reachable.

## Out of scope (YAGNI)

- Blog, talks, teaching, portfolio collections; comments; analytics;
  local Ruby/Jekyll preview setup (site is verified via the deployed build).
