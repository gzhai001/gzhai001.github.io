# Academic Homepage Revival Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Finish, clean up, and deploy the existing AcademicPages site in `/Users/gzhai/gzhai001.github.io` to GitHub Pages at https://gzhai001.github.io.

**Architecture:** AcademicPages (Jekyll) static site, already ~95% written. Remaining work: add a News section to the homepage, gitignore local build dirs, delete template placeholder assets, recreate the GitHub repo, push, and verify the live site. GitHub Pages builds `username.github.io` repos automatically with the github-pages gem.

**Tech Stack:** Jekyll (AcademicPages template), Markdown, git over HTTPS using the existing macOS keychain GitHub credential (account `gzhai001`), GitHub REST API via curl, Kimi browser extension for visual verification.

**Working directory for all tasks:** `/Users/gzhai/gzhai001.github.io`

**Spec:** `docs/superpowers/specs/2026-09-27-academic-homepage-design.md`

---

### Task 1: Add News section to homepage

**Files:**
- Modify: `/Users/gzhai/gzhai001.github.io/_pages/about.md` (insert after line 17, before the `Education` heading)

- [ ] **Step 1: Insert the News section**

Edit `_pages/about.md`: after the line `Please feel free to contact me at [gzhai@swjtu.edu.cn](mailto:gzhai@swjtu.edu.cn).` and before `Education`, insert:

```markdown

News
======
* **2026** — Our paper "Causal inference in conjoint analysis: Logit models vs. potential outcomes" is published in the *Journal of Choice Modelling*.
* **2026** — I was awarded the National Natural Science Foundation of China (NSFC) Young Scientists Fund as Principal Investigator.
* **2025** — I joined the School of Transportation and Logistics at Southwest Jiaotong University as an Assistant Professor.
* **2025** — I am serving as Guest Editor for the *Transportation Research Part D* special issue on "AI-Driven Behavioral Analytics for Sustainable Shared Mobility".

```

- [ ] **Step 2: Verify the edit**

Run: `grep -n "News" /Users/gzhai/gzhai001.github.io/_pages/about.md`
Expected: one match line for the `News` heading; file still ends with the `Contact` section.

- [ ] **Step 3: Commit**

```bash
cd /Users/gzhai/gzhai001.github.io
git add _pages/about.md
git commit -m "Add News section to homepage"
```

---

### Task 2: Ignore local build artifacts

**Files:**
- Modify: `/Users/gzhai/gzhai001.github.io/.gitignore`

- [ ] **Step 1: Append entries**

The file currently ends with `node_modules` / `package-lock.json` (no trailing newline). Append:

```
.bundle/
vendor/
.jekyll-cache/
```

- [ ] **Step 2: Verify**

Run: `cd /Users/gzhai/gzhai001.github.io && git status --short | head`
Expected: `.bundle/` and `vendor/` no longer appear as untracked; only intended modified files listed.

- [ ] **Step 3: Commit**

```bash
cd /Users/gzhai/gzhai001.github.io
git add .gitignore
git commit -m "Ignore bundler and jekyll cache directories"
```

---

### Task 3: Delete AcademicPages template placeholder assets

**Files (all deletions):**
- `/Users/gzhai/gzhai001.github.io/files/paper1.pdf`, `paper2.pdf`, `paper3.pdf`, `slides1.pdf`, `slides2.pdf`, `slides3.pdf`
- `/Users/gzhai/gzhai001.github.io/_drafts/post-draft.md`
- `/Users/gzhai/gzhai001.github.io/images/`: `3953273590_704e3899d5_m.jpg`, `500x300.png`, `bio-photo.jpg`, `bio-photo-2.jpg`, `editing-talk.png`, `foo-bar-identity-th.jpg`, `foo-bar-identity.jpg`, `homepage.png`, `image-alignment-1200x4002.jpg`, `image-alignment-150x150.jpg`, `image-alignment-300x200.jpg`, `image-alignment-580x300.jpg`, `paragraph-indent.png`, `paragraph-no-indent.png`, `site-logo.png`

Keep (referenced by template head/favicons or config): `images/profile.png` (avatar, referenced in `_config.yml` line 24), `favicon.ico`, `manifest.json`, `browserconfig.xml`, `safari-pinned-tab.svg`, `mstile-*.png`.

- [ ] **Step 1: Confirm none of the deletion targets are referenced**

Run:
```bash
cd /Users/gzhai/gzhai001.github.io
grep -rn "bio-photo\|site-logo\|foo-bar\|image-alignment\|paragraph-indent\|paragraph-no-indent\|editing-talk\|homepage.png\|500x300\|3953273590\|paper1\|slides1\|post-draft" _config.yml _data _includes _layouts _pages 2>/dev/null
```
Expected: no output. If anything matches, remove that file from the deletion list.

- [ ] **Step 2: Delete the files**

```bash
cd /Users/gzhai/gzhai001.github.io
git rm -q files/paper1.pdf files/paper2.pdf files/paper3.pdf files/slides1.pdf files/slides2.pdf files/slides3.pdf _drafts/post-draft.md
git rm -q images/3953273590_704e3899d5_m.jpg images/500x300.png images/bio-photo.jpg images/bio-photo-2.jpg images/editing-talk.png images/foo-bar-identity-th.jpg images/foo-bar-identity.jpg images/homepage.png images/image-alignment-1200x4002.jpg images/image-alignment-150x150.jpg images/image-alignment-300x200.jpg images/image-alignment-580x300.jpg images/paragraph-indent.png images/paragraph-no-indent.png images/site-logo.png
```

- [ ] **Step 3: Commit**

```bash
cd /Users/gzhai/gzhai001.github.io
git commit -q -m "Remove AcademicPages template placeholder assets"
```

---

### Task 4: Create the GitHub repo and push

**Files:** none (git/GitHub operations only)

- [ ] **Step 1: Create the public repo via the GitHub API**

The macOS keychain already holds a GitHub HTTPS credential for `gzhai001`. Retrieve it into a shell variable without printing it, and create the repo:

```bash
TOKEN=$(printf 'protocol=https\nhost=github.com\n' | git credential-osxkeychain get | awk -F= '/^password=/{print $2}')
curl -s -H "Authorization: Bearer $TOKEN" -H "Accept: application/vnd.github+json" \
  -X POST https://api.github.com/user/repos \
  -d '{"name":"gzhai001.github.io","description":"Personal academic homepage of Guocong Zhai","private":false,"has_issues":false,"has_wiki":false}' \
  | python3 -c "import json,sys; d=json.load(sys.stdin); print(d.get('full_name') or d)"
```
Expected output: `gzhai001/gzhai001.github.io`

If the output is an error JSON with `Resource not accessible` / 403 (token lacks `repo` scope) or `name already exists`, STOP and ask the user: either create the public repo `gzhai001.github.io` manually at https://github.com/new, or install GitHub CLI (`brew install gh && gh auth login`). Do not retry with the same token.

- [ ] **Step 2: Set repo-local credential helper and push**

```bash
cd /Users/gzhai/gzhai001.github.io
git config credential.helper osxkeychain
git branch -M main
git push -u origin main
```
Expected: objects pushed, `branch 'main' set up to track 'origin/main'`. The remote `origin` already points to `https://github.com/gzhai001/gzhai001.github.io.git` — verify with `git remote -v` first; if missing, run `git remote add origin https://github.com/gzhai001/gzhai001.github.io.git`.

- [ ] **Step 3: Confirm Pages is building**

```bash
TOKEN=$(printf 'protocol=https\nhost=github.com\n' | git credential-osxkeychain get | awk -F= '/^password=/{print $2}')
curl -s -H "Authorization: Bearer $TOKEN" https://api.github.com/repos/gzhai001/gzhai001.github.io/pages \
  | python3 -c "import json,sys; d=json.load(sys.stdin); print(d.get('status'), d.get('html_url'))"
```
Expected: `building https://gzhai001.github.io/` or `built https://gzhai001.github.io/`. If the response is 404 (Pages not auto-enabled), enable it:
```bash
curl -s -H "Authorization: Bearer $TOKEN" -X POST https://api.github.com/repos/gzhai001/gzhai001.github.io/pages -d '{"source":{"branch":"main","path":"/"}}'
```
If the token lacks permission, tell the user to enable it at repo Settings → Pages (source: main, root).

---

### Task 5: Verify the live site

**Files:** none (verification only)

- [ ] **Step 1: Wait for the build, then confirm HTTP 200**

```bash
for i in $(seq 1 20); do code=$(curl -s -o /dev/null -w "%{http_code}" https://gzhai001.github.io/); echo "$code"; [ "$code" = "200" ] && break; sleep 15; done
```
Expected: final output `200` (first builds typically take 1–5 minutes).

- [ ] **Step 2: Visual check via the Kimi browser extension**

Navigate the user's browser (daemon at `http://127.0.0.1:10086`, session `homepage-verify`, group_title "主页上线检查") to `https://gzhai001.github.io/`, take a screenshot, and read it. Confirm: sidebar shows avatar photo, name, bio, email/Scholar/GitHub links; main column shows bio, News, Education, Prospective Students, Contact.

- [ ] **Step 3: Check subpages and links**

In the same browser session, open in new tabs and screenshot each:
- `https://gzhai001.github.io/publications/` — two themes + working papers render
- `https://gzhai001.github.io/research/` — themes + funding render
- `https://gzhai001.github.io/cv/` — education through skills render
Confirm the Google Scholar link points to `https://scholar.google.com/citations?user=YJHjwT8AAAAJ&hl=en` and GitHub link to `https://github.com/gzhai001`.

- [ ] **Step 4: Confirm placeholders are gone**

Run: `curl -s -o /dev/null -w "%{http_code}\n" https://gzhai001.github.io/files/paper1.pdf`
Expected: `404`.

- [ ] **Step 5: Report to user**

Tell the user the site is live, summarize what each page contains, and note how to update it (edit `_pages/*.md`, push). Leave the browser tabs open unless the user asks to close them.

---

## Self-Review Notes

- Spec coverage: News section (Task 1) ✓; CV cross-check — done during planning, cv.md already complete ✓; cleanup (Task 3) ✓; gitignore for `.bundle/`/`vendor/` (Task 2) ✓; repo creation + push + Pages (Task 4) ✓; verification incl. placeholders-unreachable check (Task 5) ✓.
- No placeholders: every content edit includes the exact Markdown; every command is literal.
- Consistency: repo name `gzhai001.github.io`, branch `main`, paths absolute under `/Users/gzhai/gzhai001.github.io` throughout.
