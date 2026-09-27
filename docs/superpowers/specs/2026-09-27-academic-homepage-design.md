# Design: Guocong Zhai Academic Homepage (gzhai001.github.io)

Date: 2026-09-27
Status: Approved by user (design direction: Style A — Classic Academic)

## Goal

A personal academic homepage for Guocong Zhai (Assistant Professor, School of
Transportation and Logistics, Southwest Jiaotong University), hosted on GitHub
Pages at https://gzhai001.github.io, built from the content of his CV (LaTeX
resume) and SWJTU faculty page.

## Decisions (from brainstorming)

- **Tech stack:** hand-crafted single-page static HTML — no build step, no Jekyll.
- **Language:** English only.
- **Visual direction:** Style A "Classic Academic" — left sidebar (photo, name,
  affiliation, contact links) + right content column; navy accent `#0b3d6e`;
  responsive (sidebar stacks above content on narrow screens).
- **Sections (standard academic set):** About, News, Education & Appointments,
  Publications (two themes), Research Funding, Awards & Honors +
  Professional Service.

## Architecture

New local folder `~/gzhai001.github.io/`, pushed to a new public GitHub repo
`gzhai001/gzhai001.github.io`. GitHub Pages serves `username.github.io` repos
automatically from the default branch root — no Actions workflow or Pages
configuration needed.

```
gzhai001.github.io/
├── index.html      # all content, semantic sections with anchor ids
├── style.css       # all styling (sidebar layout, navy accent, responsive)
├── assets/
│   ├── photo.jpg   # headshot; GitHub avatar used as initial placeholder
│   └── cv.pdf      # user supplies later; link present in sidebar
├── README.md       # one-paragraph description + how to update
└── docs/superpowers/specs/2026-09-27-academic-homepage-design.md  # this file
```

- No JavaScript required. No external CSS frameworks; system font stack.
- Navigation: sidebar link list + in-page anchors; no top nav bar.

## Content

Source of truth: user's LaTeX CV (verbatim content) + faculty page
(https://faculty.swjtu.edu.cn/gzhai/zh_CN/index/869245/list/index.htm).

1. **Sidebar:** photo, name, title/affiliation (office room omitted),
   email gzhai@swjtu.edu.cn, Google Scholar
   (https://scholar.google.com/citations?user=YJHjwT8AAAAJ&hl=en),
   GitHub (https://github.com/gzhai001), CV (PDF), ORCID/faculty page link.
2. **About:** 1 paragraph — Assistant Professor at SWJTU; research on causal
   inference, statistical modeling, and AI-driven behavioral analytics for
   transportation safety and sustainable shared mobility; PhD Old Dominion
   University (advisor Kun Xie); Research Fellow at NUS (mentor Prateek Bansal).
   Brief recruitment line: prospective students welcome to email.
3. **News** (derived from CV dates):
   - 2026.06 — "Causal inference in conjoint analysis" forthcoming at *Journal of Choice Modelling*.
   - 2026.01 — Awarded NSFC Young Scientists Fund (PI, ¥300,000).
   - 2025.05 — Joined Southwest Jiaotong University as Assistant Professor.
   - 2025 — Guest Editor, *Transportation Research Part D* special issue.
4. **Education & Appointments:** condensed timeline from CV (3 degrees,
   4 appointments).
5. **Publications:** two themed ordered lists exactly as in CV —
   Theme I "Causal Inference for Transportation Safety" ([S1]–[S9]) and
   Theme II "AI-Driven Behavioral Analytics for Sustainable Shared Mobility"
   ([M1]–[M11]); under-review/forthcoming items marked in italic venue text.
6. **Research Funding:** 8 entries from CV with role (PI / Co-PI / Research
   Fellow / Research Assistant), years, and amounts where listed.
7. **Awards & Honors** and **Professional Service** (editorial service,
   peer review summary) as compact sections at the bottom.
8. **Footer:** "Last updated" date, link back to GitHub repo.

## Styling

- Max content width ~1080px, grid `260px 1fr`, gap ~44px; collapses to single
  column below 800px.
- Accent `#0b3d6e` (navy) for headings, rules, links; body text `#222`;
  font stack `-apple-system, "Helvetica Neue", Arial, sans-serif`; base 14.5–15px.
- Section headings: 19px navy with 2px bottom rule (matches approved mockup).
- Print-friendly by default (no dark backgrounds).

## Deployment & auth

- `gh` CLI is not installed; macOS keychain already holds a GitHub HTTPS
  credential for account `gzhai001`.
- Repo creation: GitHub REST API `POST /user/repos` using the keychain token
  (read via `git credential-osxkeychain get`, never echoed or committed).
- Push: HTTPS remote with repo-local `credential.helper=osxkeychain`.
- After push, verify https://gzhai001.github.io returns 200 and renders.

## Verification

1. Serve locally (`python3 -m http.server`) and screenshot via the Kimi
   browser extension; visually confirm layout matches Style A direction.
2. Check all internal anchors and external links resolve.
3. Validate responsiveness by screenshotting a narrow viewport.
4. After deployment, load the live URL in the browser and confirm content.

## Out of scope (YAGNI)

- Blog, talks/teaching pages, multi-page structure, Jekyll, JavaScript widgets,
  analytics, bilingual toggle, dark mode.
