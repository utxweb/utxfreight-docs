# UTX Freight Documentation — Agent Instructions

You are working on the **UTX Freight product documentation** site.

## Repository Location

- **Docs repo:** `/home/utxweb/devzone/utxfreight-docs/`
- **Docs content:** `/home/utxweb/devzone/utxfreight-docs/docs/`
- **Feature docs:** `/home/utxweb/devzone/utxfreight-docs/docs/freight/`
- **Images:** `/home/utxweb/devzone/utxfreight-docs/docs/images/`
- **Site config:** `/home/utxweb/devzone/utxfreight-docs/mkdocs.yml`
- **Original DeveloperHub source (reference):** `/home/utxweb/devzone/utxfreight-docs/source-developerhub/`
- **Migration PRD:** `/home/utxweb/devzone/utxfreight-docs/PRD-docs-migration.md`

## Technology Stack

- **MkDocs Material** — static site generator
- **Deployed to:** GitHub Pages at `docs.utxfreight.ca`
- **Auto-deploys** on push to `main` via `.github/workflows/deploy.yml`
- **Local preview:** `cd /home/utxweb/devzone/utxfreight-docs && mkdocs serve`

## Writing Docs — Format and Style

All docs are **standard Markdown** with MkDocs Material extensions. Follow the patterns established in the existing converted docs.

### File Structure

Each feature doc goes in `docs/freight/<slug>.md` and must be registered in `mkdocs.yml` under the `nav:` section.

### Heading Style

Use standard `##` headings. Icons in headings are optional but follow this pattern:

```markdown
## :fontawesome-solid-gas-pump: Overview
```

### Admonitions (Callout Boxes)

Use MkDocs Material admonition syntax. These are the four types used in this project:

```markdown
!!! tip "Title"
    Content here. Use for tips, best practices, time-saving advice.

!!! info "Title"
    Content here. Use for general information, solutions, notes.

!!! warning "Title"
    Content here. Use for gotchas, things to watch out for.

!!! danger "Title"
    Content here. Use for critical warnings, data loss risks, actions that can't be undone.
```

### Icons

Use MkDocs Material emoji syntax with FontAwesome Solid icons:

```markdown
:fontawesome-solid-truck:
:fontawesome-solid-gas-pump:
:fontawesome-solid-building:
:fontawesome-solid-calendar-days:
:fontawesome-solid-arrow-right:
:fontawesome-solid-circle-check:
```

Full icon reference: https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/

### Images

Place all images in `docs/images/` with descriptive filenames:

```markdown
![The Fuel Schedule page showing monthly rates](../images/fuel-schedule-overview.png)
```

For captions and sizing:

```markdown
<figure markdown>
  ![Description](../images/fuel-schedule-overview.png){ width="80%" }
  <figcaption>The Fuel Schedule page showing monthly rates</figcaption>
</figure>
```

Images use the `glightbox` plugin — users can click any image to zoom.

### Tables

Standard Markdown tables with header row:

```markdown
| Role | Access Level |
|------|-------------|
| :fontawesome-solid-user-tie: **Manager** | Full access |
| :fontawesome-solid-headset: **Dispatch** | Requires `manage_rates` permission |
```

### Step-by-Step Instructions

Use numbered lists with icons:

```markdown
1. Navigate to :fontawesome-solid-arrow-right: **Charges** :fontawesome-solid-arrow-right: **Fuel Schedule**.
2. Enter the **Rate (%)**.
3. Click **Save Rate**.
```

### FAQ / Troubleshooting Sections

End each feature doc with an FAQ section. Each question is an `###` heading, with the answer in an `!!! info "Solution"` admonition:

```markdown
## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-ban: Customer was exempted but still has fuel charges

!!! info "Solution"
    Exempting a customer does not automatically remove existing charges.
    Go to **Charges > Fuel Schedule**, find the affected month, and click **Recalculate**.
```

## Doc Structure Pattern

Every feature doc follows this structure:

1. **Title + one-line summary** — what the feature does in one sentence
2. **Overview** — how it works at a glance (bullet points)
3. **Quick Start** — fastest path for users who already know the feature
4. **Access & Permissions** — which roles can use it, how to navigate to it
5. **Core sections** — the meat of the feature (setting rates, checking containers, etc.)
6. **Color Guide** (if applicable) — what the colors mean in the UI
7. **FAQ / Troubleshooting** — common questions and solutions
8. **Best Practices** — tips admonition at the end

## Taking Screenshots

Screenshots come from the live UTX Freight app. To get screenshots:

1. **From the live app:** Log into UTX Freight, navigate to the feature, and use browser DevTools or a screenshot tool. Capture at **1400px width** for consistency.
2. **From existing DeveloperHub images:** If the source-developerhub files still exist, extract image URLs from the `<!-- asset:xxx=https://... -->` comments at the bottom of each file and download them:
   ```bash
   # URLs are in comments at the bottom of each source file
   grep -h 'uploads.developerhub.io\|image-archive.developerhub.io' source-developerhub/*.md | \
     sed 's/.*https/https/;s/ .*//' | sort -u
   ```
   Download with `wget` and save to `docs/images/` with descriptive names.
3. **Naming convention:** `<feature>-<description>.png` — e.g., `fuel-schedule-overview.png`, `fuel-quick-set-form.png`, `container-tracking-cn-modal.png`

## Tone

- Second person ("you"), active voice
- Direct, concise — like explaining to a coworker
- No marketing language — this is a user manual
- Bold for UI elements: **Save Rate**, **Fuel Schedule**, **Recalculate**
- Use `>` navigation breadcrumbs: **Charges** > **Fuel Schedule**

## Adding a New Doc

1. Create `docs/freight/<slug>.md` following the structure pattern above
2. Add it to `mkdocs.yml` under the appropriate `nav:` section
3. Add screenshots to `docs/images/`
4. Test locally with `mkdocs serve`
5. Commit and push — deploys automatically

## Converting from DeveloperHub

If converting remaining source-developerhub files, see the full conversion table in `PRD-docs-migration.md` task 3.1. Key rules:

- `$plugin[{"type":"callout",...}]$` → `!!! type "Title"`
- `$plugin[{"type":"image",...}]$` → `![caption](../images/filename.png)`
- `$inline[icon,fas fa-xxx]` → `:fontawesome-solid-xxx:`
- Strip DeveloperHub frontmatter (`---type: page...---published`)
- Remove asset mapping comments (`<!-- asset:xxx=... -->`)
- Use the highest-numbered version of duplicate files (e.g., `6 User Roles.md` over `5 User Roles.md`)
