# PRD: UTX Freight Docs Migration — DeveloperHub to MkDocs Material

**Date:** 2026-03-30
**Owner:** Rafal
**Target domain:** docs.utxfreight.ca
**Source:** `source-developerhub/` (copied from `utxfreight/doc/developerhub.io`)

---

## Goal

Replace the paid DeveloperHub.io docs with a free, self-hosted MkDocs Material site deployed via GitHub Pages at `docs.utxfreight.ca`. Push markdown, it goes live.

---

## Project Structure

```
utxfreight-docs/
├── docs/
│   ├── index.md                    ← landing page (DONE)
│   ├── images/                     ← all screenshots go here
│   └── freight/
│       ├── getting-started.md
│       ├── dispatch.md
│       ├── equipment.md
│       ├── order-tagging.md
│       ├── order-duplication.md
│       ├── managing-customers.md
│       ├── fuel-surcharge.md
│       ├── container-tracking.md
│       ├── automatic-statements.md
│       ├── aged-receivables.md
│       ├── application-settings.md
│       ├── user-roles.md
│       └── changelog.md
├── source-developerhub/            ← original files for reference (delete after migration)
├── mkdocs.yml                      ← site config (DONE)
├── .github/workflows/deploy.yml    ← auto-deploy on push (DONE)
└── PRD-docs-migration.md           ← this file
```

---

## Tasks

### Phase 1: Setup (local environment)

- [ ] **1.1** Install MkDocs Material locally
  ```bash
  pip install mkdocs-material mkdocs-glightbox
  ```

- [ ] **1.2** Test local preview
  ```bash
  cd /home/utxweb/devzone/utxfreight-docs
  mkdocs serve
  ```
  Open http://127.0.0.1:8000 in browser to verify the skeleton works.

### Phase 2: Download images from DeveloperHub

- [ ] **2.1** Download all images from DeveloperHub CDN before they disappear

  The images are in two formats in the source files:

  **Format A — inline URL (older docs):**
  ```
  "url": "https:\/\/image-archive.developerhub.io\/image\/upload\/..."
  ```

  **Format B — asset reference (newer docs like Fuel Surcharge):**
  ```
  "url": "asset:3n3sd68nph1v"
  ```
  With the real URL mapped at the bottom of the file:
  ```
  <!-- asset:3n3sd68nph1v=https://uploads.developerhub.io/prod/k8VN/xxx.png -->
  ```

  **Download script** — run this from `utxfreight-docs/`:
  ```bash
  cd /home/utxweb/devzone/utxfreight-docs

  # Extract all image URLs from source files (both formats)
  grep -roh 'https://[a-zA-Z0-9./_-]*developerhub\.io[a-zA-Z0-9./_-]*\.\(png\|jpg\)' source-developerhub/ | \
    sed 's/\\//g' | sort -u > /tmp/devhub-image-urls.txt

  # Download each image with a numbered filename
  mkdir -p docs/images
  i=1
  while IFS= read -r url; do
    ext="${url##*.}"
    wget -q "$url" -O "docs/images/devhub-$(printf '%03d' $i).$ext" && echo "OK: $url" || echo "FAIL: $url"
    i=$((i+1))
  done < /tmp/devhub-image-urls.txt
  ```

  After downloading, rename each image to something descriptive based on which doc it belongs to (e.g., `fuel-schedule-overview.png`, `fuel-quick-set-form.png`).

- [ ] **2.2** Alternative: screenshot fresh from the live app
  Some DeveloperHub images may be outdated (the app is on v3.8.x now, some screenshots are from v2.x). Consider taking fresh screenshots for any page that has changed significantly. Use browser DevTools to capture at consistent widths (e.g., 1400px).

### Phase 3: Convert docs to MkDocs Material format

- [ ] **3.1** Convert each source file from DeveloperHub syntax to standard Markdown

  **Conversion rules — tell the agent these:**

  | DeveloperHub syntax | MkDocs Material equivalent |
  |---|---|
  | `$inline[icon,fas fa-truck]` | `:fontawesome-solid-truck:` |
  | `$inline[icon,fas fa-check-circle text-success]` | `:fontawesome-solid-circle-check:` |
  | `$plugin[{"type":"image","data":{"url":"asset:xxx",...,"caption":"..."}}]$` | `![caption](../images/filename.png)` |
  | `$plugin[{"type":"image","data":{"url":"https://...","caption":"..."}}]$` | `![caption](../images/filename.png)` |
  | `$plugin[{"type":"callout","data":{"text":"...","type":"success","title":"Tip"}}]$` | `!!! tip "Tip"\n    text here` |
  | `$plugin[{"type":"callout","data":{"type":"warning",...}}]$` | `!!! warning "Title"\n    text here` |
  | `$plugin[{"type":"callout","data":{"type":"error",...}}]$` | `!!! danger "Title"\n    text here` |
  | `$plugin[{"type":"callout","data":{"type":"info",...}}]$` | `!!! info "Title"\n    text here` |
  | `$plugin[{"type":"code-block",...}}]$` | Standard markdown fenced code blocks |
  | `## $inline[icon,...] Title` | `## :icon: Title` (or just `## Title` if icon is decorative) |

  **Callout type mapping:**
  - `success` → `!!! tip`
  - `warning` → `!!! warning`
  - `error` → `!!! danger`
  - `info` → `!!! info`

  **FontAwesome icon mapping** (common ones in these docs):
  - `fas fa-truck` → `:fontawesome-solid-truck:`
  - `fas fa-gas-pump` → `:fontawesome-solid-gas-pump:`
  - `fas fa-calendar-alt` → `:fontawesome-solid-calendar-days:`
  - `fas fa-building` → `:fontawesome-solid-building:`
  - `fas fa-percent` → `:fontawesome-solid-percent:`
  - `fas fa-sync-alt` → `:fontawesome-solid-arrows-rotate:`
  - `fas fa-ban` → `:fontawesome-solid-ban:`
  - `fas fa-check-circle` → `:fontawesome-solid-circle-check:`
  - `fas fa-pencil-alt` → `:fontawesome-solid-pencil:`
  - `fas fa-shield-alt` → `:fontawesome-solid-shield-halved:`
  - `fas fa-table` → `:fontawesome-solid-table:`
  - `fas fa-question-circle` → `:fontawesome-solid-circle-question:`
  - `fas fa-exclamation-triangle` → `:fontawesome-solid-triangle-exclamation:`
  - `fas fa-exclamation-circle` → `:fontawesome-solid-circle-exclamation:`
  - `fas fa-arrow-right` → `:fontawesome-solid-arrow-right:`
  - `fas fa-copy` → `:fontawesome-solid-copy:`
  - `fas fa-history` → `:fontawesome-solid-clock-rotate-left:`
  - `fas fa-list-alt` → `:fontawesome-solid-rectangle-list:`
  - `fas fa-list-ol` → `:fontawesome-solid-list-ol:`
  - `fas fa-search` → `:fontawesome-solid-magnifying-glass:`
  - `fas fa-user-tie` → `:fontawesome-solid-user-tie:`
  - `fas fa-headset` → `:fontawesome-solid-headset:`
  - `fas fa-file-invoice-dollar` → `:fontawesome-solid-file-invoice-dollar:`
  - `fas fa-eye` → `:fontawesome-solid-eye:`
  - `fas fa-eye-slash` → `:fontawesome-solid-eye-slash:`
  - `fas fa-bolt` → `:fontawesome-solid-bolt:`
  - `fas fa-lightbulb` → `:fontawesome-solid-lightbulb:`
  - `fas fa-lock` → `:fontawesome-solid-lock:`
  - `fas fa-calculator` → `:fontawesome-solid-calculator:`
  - `fas fa-palette` → `:fontawesome-solid-palette:`
  - `fas fa-hashtag` → `:fontawesome-solid-hashtag:`
  - `fas fa-info-circle` → `:fontawesome-solid-circle-info:`
  - `fas fa-grip-lines` → `:fontawesome-solid-grip-lines:`
  - `fas fa-tag` → `:fontawesome-solid-tag:`
  - `fas fa-trash` → `:fontawesome-solid-trash:`
  - `fas fa-check-square` → `:fontawesome-solid-square-check:`

- [ ] **3.2** Source files to convert (pick the latest numbered version of each):

  | Source file | Target file | Notes |
  |---|---|---|
  | `1 Getting Started 2.md` | `docs/freight/getting-started.md` | Use this one (listed: true) |
  | `2 Dispatch.md` | `docs/freight/dispatch.md` | |
  | `3 Equipment.md` | `docs/freight/equipment.md` | |
  | `4 Order Tagging.md` | `docs/freight/order-tagging.md` | |
  | `5 Automatic Statements.md` | `docs/freight/automatic-statements.md` | |
  | `6 User Roles.md` | `docs/freight/user-roles.md` | Use `6` (latest) |
  | `7 Application Settings.md` | `docs/freight/application-settings.md` | Use `7` (latest) |
  | `9 Managing Customers.md` | `docs/freight/managing-customers.md` | Use `9` (latest) |
  | `8 Reporting - Aged Receivables.md` | `docs/freight/aged-receivables.md` | |
  | `14 Fuel Surcharge.md` | `docs/freight/fuel-surcharge.md` | Most complex, many images |
  | `15 Container Tracking.md` | `docs/freight/container-tracking.md` | |
  | `13 Changelog.md` | `docs/freight/changelog.md` | Use `13` (latest) |
  | `Orders - Duplication.md` | `docs/freight/order-duplication.md` | |

  Skip: `9 ---.md`, `12 ---.md` (separators), older duplicates (`5 User Roles`, `6 Application Settings`, `7 Managing Customers`, `8 Getting Started`, `10 Getting Started`, `10 Changelog`)

- [ ] **3.3** Strip DeveloperHub frontmatter from all files. Replace with a simple `# Title` heading.

- [ ] **3.4** Update all image references to point to local `../images/filename.png`

- [ ] **3.5** Remove asset mapping comments from bottom of files (`<!-- asset:xxx=https://... -->`)

### Phase 4: GitHub repo and deployment

- [ ] **4.1** Create GitHub repo
  ```bash
  cd /home/utxweb/devzone/utxfreight-docs
  gh repo create utxweb/utxfreight-docs --public --source=. --push
  ```

- [ ] **4.2** Enable GitHub Pages
  - Go to repo Settings > Pages
  - Source: Deploy from branch
  - Branch: `gh-pages` (created automatically by the deploy workflow)

- [ ] **4.3** Verify deployment
  Push to `main`, wait for the GitHub Action to run (~60 seconds), then check:
  `https://utxweb.github.io/utxfreight-docs/`

### Phase 5: Custom domain setup

- [ ] **5.1** Add CNAME to repo
  ```bash
  echo "docs.utxfreight.ca" > docs/CNAME
  ```

- [ ] **5.2** DNS: Add CNAME record at your domain registrar
  ```
  Type:  CNAME
  Name:  docs
  Value: utxweb.github.io
  ```
  (Do this wherever utxfreight.ca DNS is managed)

- [ ] **5.3** Enable HTTPS in GitHub Pages settings
  After DNS propagates (~5-30 min), go to repo Settings > Pages and check "Enforce HTTPS"

- [ ] **5.4** Verify `https://docs.utxfreight.ca` loads correctly

### Phase 6: Cleanup

- [ ] **6.1** Delete `source-developerhub/` folder from repo once all content is migrated and verified
- [ ] **6.2** Cancel DeveloperHub.io subscription
- [ ] **6.3** Redirect or update any links pointing to `utxfreight.developerhub.io` to `docs.utxfreight.ca`

---

## How to run the conversion

Tell the agent:

> Convert the DeveloperHub docs in `source-developerhub/` to MkDocs Material format.
> Follow the conversion rules in `PRD-docs-migration.md` task 3.1.
> Use the file mapping in task 3.2.
> Download images first using the script in task 2.1, then rename them descriptively.
> Output converted files to `docs/freight/`.
> Run `mkdocs serve` to verify the result.

---

## Notes

- The `mkdocs.yml`, `docs/index.md`, and `.github/workflows/deploy.yml` are already created and ready
- Some docs have multiple versions (numbered prefixes). Always use the highest number — that's the latest
- Files with `listed: false` in frontmatter were hidden in DeveloperHub — review whether they should be included or dropped
- The DeveloperHub images may go offline after you cancel — download them FIRST
