# Garage Parts Inventory & Job Templates

Keep a catalogue of the parts your shop uses, with cost, charge price and stock levels, import or export it as CSV, and save common jobs as **Job Templates** that fill in parts and labor on a work order in one click.

## :fontawesome-solid-gear: Overview

- :fontawesome-solid-boxes-stacked: **Parts** (Garage sidebar) opens **Parts Inventory**: every part of your current office with its **SKU**, **Category**, **Cost**, **Charge**, **Margin** and **Qty**, 25 per page.
- :fontawesome-solid-filter: Three tabs: **Active**, **Low Stock** and **Disabled**. A part is low on stock when it has a **Reorder Point** above 0 and its quantity on hand is at or below that reorder point.
- :fontawesome-solid-ban: There is no delete for parts. Disable a part you no longer use; you can enable it again at any time.
- :fontawesome-solid-file-csv: **Import CSV** adds parts in bulk, with a preview before anything is saved. **Export** downloads the active parts of your office as a CSV file.
- :fontawesome-solid-clipboard-list: **Templates** (Garage sidebar) opens **Job Templates**: named jobs (for example *Oil Change*) with a list of parts and labor lines. On the work order form, **Apply Template** adds a template's lines to the work order.
- :fontawesome-solid-boxes-stacked: Stock goes down automatically when a work order with catalogue parts moves to **In progress**. See [Parts inventory](garage-work-orders.md#parts-inventory).
- :fontawesome-solid-building: Parts and templates belong to the **office** you are working in. Each office has its own catalogue and its own templates.

<!-- TODO: Screenshot — Parts Inventory page: Import CSV / Export / New Part buttons, Active / Low Stock / Disabled tabs, search box, parts table with coloured Margin and a red Qty badge -->

---

## :fontawesome-solid-bolt: Quick Start

**Add a part:**

1. In the Garage sidebar, click **Parts**, then **New Part**.
2. Enter the **Name** (required), and optionally the **SKU**, **Category** and **Description**.
3. Enter the **Purchase Price** (your cost), the **Charge Price** (what the customer pays), the **Qty on Hand** and a **Reorder Point**.
4. Click **Create Part**.

**Create a job template:**

1. In the Garage sidebar, click **Templates**, then **New Template**.
2. Enter the **Template Name** (required) and a **Description**.
3. Under **Parts**, search for a catalogue part (or type a description) and set **Qty**, **Cost** and **Charge**. Click **Add Part** for more lines.
4. Under **Labor**, enter a **Description**, **Hours** and **Rate**. Click **Add Labor** for more lines.
5. Click **Create Template**.
6. On a new or existing work order, pick the template under **Apply Template** and click **Apply**.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Parts and Templates |
|------|--------------------|
| :fontawesome-solid-user-tie: **Admin** | Full access: create, edit, disable/enable, import, export |
| :fontawesome-solid-user-tie: **Manager** | Full access, for the offices they belong to |
| :fontawesome-solid-screwdriver-wrench: **Garage** | Full access, for the first office on their user account (they cannot switch office) |
| :fontawesome-solid-headset: **Dispatch**, **Customer Service**, **Accountant**, **Customer**, **Warehouse**, drivers and yard workers | No access (the **Garage** menu item is hidden) |

- The **Garage** add-on must be turned on. See [Garage Module Overview](garage-overview.md).
- There are no finer permissions inside the Garage: anyone who can open it can manage parts and templates.

**Where to find it:**

- :fontawesome-solid-arrow-right: Main menu **Garage** :fontawesome-solid-arrow-right: sidebar **Parts** — page **Parts Inventory**
- :fontawesome-solid-arrow-right: Main menu **Garage** :fontawesome-solid-arrow-right: sidebar **Templates** — page **Job Templates**

---

## :fontawesome-solid-boxes-stacked: The Parts Inventory Page

The page header shows **Parts Inventory** (*Manage parts, pricing, and stock levels*) with three buttons:

| Button | What it does |
|--------|-------------|
| :fontawesome-solid-file-import: **Import CSV** | Opens **Import Parts** (see [Importing parts from CSV](#importing-parts-from-csv)) |
| :fontawesome-solid-file-export: **Export** | Downloads the active parts as CSV (see [Exporting parts](#exporting-parts)) |
| :fontawesome-solid-plus: **New Part** | Opens the **New Part** form |

### Tabs

| Tab | Shows |
|-----|-------|
| **Active** (default) | All active parts |
| **Low Stock** | Active parts whose **Reorder Point** is greater than 0 **and** whose quantity on hand is equal to or lower than the reorder point |
| **Disabled** | Parts you have disabled |

!!! info "Parts with a Reorder Point of 0 are never low on stock"
    A part with **Reorder Point** 0 never appears on the **Low Stock** tab and never gets the red quantity badge, even when its quantity on hand is 0. Set a reorder point on every part you want to monitor.

### Search

Type in **Search parts...** and press Enter (or click :fontawesome-solid-magnifying-glass:). The search matches part of the **Name** or the **SKU**, is not case-sensitive, and stays within the tab you are on.

### Columns

The list is sorted by name, 25 parts per page.

| Column | What it shows |
|--------|--------------|
| **Name** | Part name |
| **SKU** | Part number, or **-** if empty |
| **Category** | Category, or **-** if empty |
| **Cost** | **Purchase Price** |
| **Charge** | **Charge Price** |
| **Margin** | Margin as a percentage of the charge price (see below) |
| **Qty** | Quantity on hand. Shown in a **red badge** when the part is low on stock |
| **Actions** | :fontawesome-solid-pen-to-square: edit, and :fontawesome-solid-ban: disable (active parts) or :fontawesome-solid-check: enable (disabled parts) |

### Margin colours

**Margin** = (Charge Price − Purchase Price) ÷ Charge Price × 100, rounded to one decimal. A part with a charge price of 0 shows **0%**.

| Colour | Margin |
|--------|--------|
| **Green** | 50% or more |
| **Yellow** | 30% to under 50% |
| **Red** | Under 30% (including negative margins, when the cost is higher than the charge) |

### Empty list

When the tab has no parts, you see **No parts yet** — *Add parts to your inventory to use them in work orders.* — and a **New Part** button.

---

## :fontawesome-solid-pen-to-square: Adding and Editing a Part

Click **New Part**, or the :fontawesome-solid-pen-to-square: edit icon on a row (page **Edit Part: <name>**).

| Field | Required | Notes |
|-------|----------|-------|
| **Name** | Yes | Shown in part searches on work orders and templates |
| **SKU** | No | Part number. Must be unique across all offices (see below). Searchable |
| **Category** | No | Pick from the list, or leave **Select category...** |
| **Description** | No | Free text |
| **Purchase Price** | No (defaults to 0) | Your cost. 0 or more, up to 2 decimals |
| **Charge Price** | No (defaults to 0) | Price charged to the customer. 0 or more, up to 2 decimals |
| **Qty on Hand** | No (defaults to 0) | Whole number, 0 or more |
| **Reorder Point** | No (defaults to 0) | Whole number, 0 or more. Above 0, it turns on the low stock warning |

Click **Create Part** (new) or **Update Part** (edit). You return to the list with *Part created successfully.* or *Part updated successfully.* **Cancel** returns to the list without saving. If something is wrong, the form shows the errors in a red box at the top (for example *Name can't be blank*).

### Categories

The **Category** list is fixed:

**Brakes**, **Engine**, **Tires**, **Electrical**, **Suspension**, **Transmission**, **Cooling**, **HVAC**, **Exhaust**, **Filters**, **Fluids**, **Body**, **Lighting**, **Other**.

You cannot add your own categories. Use **Other** for anything that does not fit.

!!! warning "SKUs are unique across all offices"
    When you save a part, its **SKU** must not be used by **any** other part, in **any** office, including disabled parts. The comparison is exact (`ABC-1` and `abc-1` count as different SKUs). If the SKU is taken, you see *Sku has already been taken*. Use a different SKU.

!!! info "Changing a part's price"
    Work order and template lines keep the cost and charge they had when the part was added. Changing the price in the catalogue does not change existing work orders or templates.

### Disabling and enabling a part

- Click :fontawesome-solid-ban: on an active part and confirm with **Yes, proceed** in the **Are you sure?** pop-up (*Disable <part name>?*). The part moves to the **Disabled** tab with the message *<part name> disabled.*
- On the **Disabled** tab, click :fontawesome-solid-check: to enable it again (no confirmation). Message: *<part name> enabled.*

A disabled part:

- no longer appears in the part search on the work order form and the template form,
- is left out of **Export**,
- stays on the work orders and templates that already use it.

### Adjusting stock

There is no separate stock-adjustment or receiving screen. To record parts you received or to correct a count, edit the part and change **Qty on Hand**.

Stock is taken out automatically when a work order moves to **In progress** (only for lines picked from the catalogue), and put back when such a line is removed from a work order that is **In progress**, **Completed** or on a draft invoice. Details: [Parts inventory](garage-work-orders.md#parts-inventory).

---

## :fontawesome-solid-file-import: Importing Parts from CSV

Use **Import CSV** to add many parts at once. The import only **adds** new parts. It never updates or disables parts that already exist.

### Step by step

1. On **Parts Inventory**, click **Import CSV**. The **Import Parts from CSV** page opens.
2. Optional: click **Download Current Catalog as CSV Template** to get a file with the right headers (it contains your current active parts).
3. Prepare your CSV file (see [CSV columns](#csv-columns)).
4. Choose the file in the upload area and click **Preview Import**.
5. Check the **Import Preview** page (see [The preview page](#the-preview-page)).
6. Click **Import N Parts** (N is the number of rows ready to import), or **Cancel** to go back.
7. You return to **Parts Inventory** with *Import complete: X parts imported, Y skipped.*

<!-- TODO: Screenshot — Import Preview page with the three summary boxes (Ready to import / Duplicate SKUs (will skip) / Invalid rows (will skip)), the Parts to Import table and the Skipped Rows table -->

### CSV columns

The first row must contain these column headers:

```text
name, sku, category, description, purchase_price, charge_price, quantity_on_hand, reorder_point
```

| Column | Required | How it is imported |
|--------|----------|-------------------|
| `name` | Yes | Rows without a name are not imported |
| `sku` | No | Rows whose SKU already exists in your office (ignoring capitals) are skipped. SKUs must be unique across all offices |
| `category` | No | Must be **exactly** one of the [categories](#categories), with the same spelling and capitals (for example `Brakes`, `HVAC`), or left empty |
| `description` | No | Free text |
| `purchase_price` | No | Plain number such as `12.50`, 0 or more. Empty or not a number becomes 0. Do not use `$` or thousands separators: `$12.50` becomes 0 and `1,250.00` becomes 1 |
| `charge_price` | No | Same rules as `purchase_price` |
| `quantity_on_hand` | No | Whole number. Empty, not a number or negative becomes 0; decimals are dropped |
| `reorder_point` | No | Whole number. Empty, not a number or negative becomes 0; decimals are dropped |

- Header names are not case-sensitive, and spaces are read as underscores (`Purchase Price` works like `purchase_price`). Columns can be in any order; other columns are ignored.
- Spaces at the start and end of each value are removed.
- Every imported part is **active**.

### File rules and messages

| Message | Cause |
|---------|-------|
| *Please select a CSV file.* | You clicked **Preview Import** without choosing a file |
| *Please upload a CSV file (.csv).* | The file is not a CSV |
| *File too large. Maximum size is 1 MB.* | The file is larger than 1 MB |
| *Invalid CSV file: ...* | The file could not be read as CSV (for example a broken quote). The message gives the technical reason |
| *No CSV data found. Please upload again.* | The uploaded file was no longer available when you clicked **Import N Parts** (for example you clicked it a second time, or reloaded the page). Upload the file again |

### The preview page

**Import Preview** shows three counters:

| Counter | Meaning |
|---------|---------|
| **Ready to import** | Rows that passed the preview checks |
| **Duplicate SKUs (will skip)** | Rows whose SKU already exists in your current office |
| **Invalid rows (will skip)** | Rows with a problem (see below) |

Below the counters:

- **Parts to Import (N)** lists the rows ready to import, with **Row** (the line number in your file, the header being line 1), **Name**, **SKU**, **Category**, **Cost**, **Charge** and **Qty**. Only the first 20 rows are listed, followed by *...and N more rows*.
- **Skipped Rows** lists the duplicate and invalid rows, with **Row**, **Name** (or *(blank)*), **SKU** and **Issue**.
- If no row is ready, you see *No valid rows found. Please check your CSV and try again.* and a **Try Again** link.

Nothing is saved until you click **Import N Parts**.

### What the preview checks

| Issue shown | Rule |
|-------------|------|
| *SKU already exists* | The SKU matches a part of your **current office** (active or disabled), ignoring capitals |
| *Name is required* | The `name` column is empty |
| *Purchase price must be >= 0* | `purchase_price` is negative |
| *Charge price must be >= 0* | `charge_price` is negative |

A row with a duplicate SKU is listed only as a duplicate, even if it also has other problems.

!!! info "Parts without a SKU are never treated as duplicates"
    The duplicate check only works on SKUs. If you import the same file twice, or re-import the **Download Current Catalog as CSV Template** file, every row **without** a SKU is added again as a new part. Give your parts a SKU, or remove rows you have already imported.

---

## :fontawesome-solid-file-export: Exporting Parts

Click **Export** on **Parts Inventory** (or **Download Current Catalog as CSV Template** on the import page). The browser downloads `parts_catalog_YYYYMMDD.csv` (today's date, for example `parts_catalog_20261010.csv`).

- It contains the **active** parts of your current office, sorted by name. Disabled parts are not exported.
- It ignores the tab and search you are on: it always exports all active parts.
- Columns: `name`, `sku`, `category`, `description`, `purchase_price`, `charge_price`, `quantity_on_hand`, `reorder_point` — the same headers the import expects.

---

## :fontawesome-solid-clipboard-list: Job Templates

A job template is a reusable job: a name, a description, and lists of parts and labor lines with their quantities, hours and prices. Templates are only used to fill in work orders; changing a template later does not change work orders it was applied to.

### The Job Templates page

Click **Templates** in the Garage sidebar. The page **Job Templates** (*Pre-defined jobs to quickly populate work orders*) has a **New Template** button and two tabs:

| Tab | Shows |
|-----|-------|
| **Active** (default) | Templates you can apply to work orders |
| **Disabled** | Templates you have disabled |

The list is sorted by name, 20 per page, and has no search box.

| Column | What it shows |
|--------|--------------|
| **Name** | Template name |
| **Description** | The description, shortened to 60 characters (ending with *...*) when longer |
| **Parts** | Number of part lines |
| **Labor** | Number of labor lines |
| **Actions** | :fontawesome-solid-eye: view, :fontawesome-solid-pen-to-square: edit, and :fontawesome-solid-ban: disable (active) or :fontawesome-solid-check: enable (disabled) |

When the tab is empty, you see **No templates yet** — *Create reusable job templates to speed up work order creation.* — and a **Create Your First Template** button.

<!-- TODO: Screenshot — Job Templates page with Active / Disabled tabs and a list of templates showing Parts and Labor counts -->

### Creating and editing a template

Click **New Template**, or :fontawesome-solid-pen-to-square: on a row (page **Edit Template**).

| Field | Required | Notes |
|-------|----------|-------|
| **Template Name** | Yes | For example *Oil Change*, *Brake Service*. Shown in the **Apply Template** list on work orders |
| **Description** | No | Short description of the job |

**Parts** section (one row per part, **Add Part** adds a row, :fontawesome-solid-xmark: removes one):

| Column | Notes |
|--------|-------|
| **Part / Description** | Type at least 2 characters to search active catalogue parts by name or SKU (up to 15 results, shown as *Name (SKU)*). Picking a part links the line to the catalogue and fills in **Cost** and **Charge** from the catalogue. You can also type a free description without picking a part |
| **Qty** | Whole number, at least 1. Defaults to 1 |
| **Cost** | Purchase price for the line. 0 or more |
| **Charge** | Price charged to the customer. 0 or more |

When a line is newly linked to a catalogue part and you leave **Cost** or **Charge** at 0, or leave the description empty, the template takes the part's catalogue values when you save.

**Labor** section (one row per labor line, **Add Labor** adds a row, :fontawesome-solid-xmark: removes one):

| Column | Required | Notes |
|--------|----------|-------|
| **Description** | Yes | For example *Replace front pads* |
| **Hours** | Yes | 0 or more, in steps of 0.25 |
| **Rate** | Yes | Hourly rate, **greater than 0**. It is not taken from **Garage Settings**; enter it on each line |

Click **Create Template** or **Update Template**. You return to the list with *Template created successfully.* or *Template updated successfully.* **Cancel** returns without saving. If something is wrong, a red box lists the errors (*N errors prevented this template from being saved:*).

!!! tip "Remove empty rows you don't need"
    A new template starts with one empty part row and one empty labor row (a template being edited with no parts or no labor also shows one). If the template has no labor, remove the empty labor row with :fontawesome-solid-xmark: before saving, since every labor line needs a **Description** and a **Rate**. Likewise, remove an unused empty part row so the template only lists the parts you need.

### Viewing a template

Click :fontawesome-solid-eye: on a row. The page shows the template name and description, an **Edit** button, and two tables:

- **Parts**: **Description**, **Qty**, **Cost**, **Charge** (or *No parts in this template*).
- **Labor**: **Description**, **Hours**, **Rate** (or *No labor in this template*).

**Back to Templates** returns to the list.

### Disabling and enabling a template

- Click :fontawesome-solid-ban: on an active template and confirm with **Yes, proceed** (*Disable this template?*). Message: *<template name> disabled.*
- On the **Disabled** tab, click :fontawesome-solid-check: to enable it again (no confirmation). Message: *<template name> enabled.*

Only **active** templates are offered under **Apply Template** on the work order form. Work orders that a template was already applied to are not affected.

!!! info "Templates cannot be deleted"
    There is no delete button for templates. Disable the ones you no longer use; they stay on the **Disabled** tab and can be enabled again.

### Applying a template to a work order

1. Open a new or existing work order (**Work Orders** :fontawesome-solid-arrow-right: **New Work Order**, or edit one).
2. In the purple **Apply Template** box at the top of the form, pick a template in **-- Select a template --**.
3. Click **Apply**. A **Template Applied** message confirms *"<template name>" has been applied.*

What happens:

- Empty part and labor rows on the form are removed, then the template's lines are **added after** the existing ones. Nothing you already entered is replaced, so applying a template twice adds its lines twice.
- Part lines get the template's catalogue part link, description, quantity, cost and charge. Labor lines get the description, hours and rate. The prices are the ones saved in the template, not the current catalogue prices. Exception: on a template line linked to a catalogue part whose **Cost** or **Charge** is 0, the work order takes the part's current catalogue price for that value when you save it.
- Every added line has its **Tax** checkbox ticked (taxable). Untick it on lines that should not be taxed.
- You can still change or remove any line before saving the work order.
- Catalogue parts added by a template are taken out of stock like any other catalogue line when the work order moves to **In progress**.

The **Apply Template** box only appears when your current office has at least one active template. Details: [Garage Work Orders](garage-work-orders.md#apply-template).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-triangle-exclamation: "Sku has already been taken" but I can't find the part

!!! info "Solution"
    SKUs must be unique across **all offices**, including disabled parts. Check the **Disabled** tab, and ask someone in your other offices (or an Admin who can switch office) whether the SKU is used there. Otherwise use a different SKU.

### :fontawesome-solid-copy: I imported the same file twice and now have duplicate parts

!!! info "Solution"
    Duplicates are only detected by SKU. Parts without a SKU are added again on every import. Disable the extra copies (parts cannot be deleted), and give your parts a SKU to avoid this in the future.

### :fontawesome-solid-pen: How do I update prices for many parts at once?

!!! info "Solution"
    The import only adds new parts; it never updates existing ones. Change prices one by one with :fontawesome-solid-pen-to-square: edit on **Parts Inventory**.

### :fontawesome-solid-boxes-stacked: A part is out of stock but not on the Low Stock tab

!!! info "Solution"
    The part's **Reorder Point** is 0. Only parts with a reorder point above 0 can be low on stock. Edit the part and set a reorder point.

### :fontawesome-solid-magnifying-glass: I can't find a part when adding it to a work order or template

!!! info "Solution"
    The search only lists **active** parts of your current office, and needs at least 2 characters of the name or SKU. Check the **Disabled** tab on **Parts Inventory** and enable the part if needed.

### :fontawesome-solid-clipboard-list: My template doesn't appear under Apply Template

!!! info "Solution"
    Only **active** templates of your current office are listed. Check the **Disabled** tab on **Job Templates** and click :fontawesome-solid-check: to enable it.

### :fontawesome-solid-trash: How do I delete a template or a part?

!!! info "Solution"
    Neither can be deleted from the screen. Disable them instead: they disappear from searches and from **Apply Template**, but stay available on the **Disabled** tab.

### :fontawesome-solid-dollar-sign: I changed a part's price but my template still uses the old price

!!! info "Solution"
    Templates keep the prices they were saved with. Edit the template and update **Cost** and **Charge** on the line (or pick the part again from the search to reload the catalogue prices), then click **Update Template**.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Keeping your catalogue and templates useful"
    - Give every part a **SKU** and a **Category**. SKUs make searches faster and protect you from duplicate imports.
    - Set a **Reorder Point** on parts you keep in stock, and check the **Low Stock** tab regularly.
    - Watch the **Margin** colours: red means less than 30% of the charge price is profit, or you even sell at a loss.
    - Copy category names exactly from the list on this page when you prepare a CSV import.
    - Use **Export** as a quick backup of your active catalogue before a large import.
    - Build templates for your most common jobs (oil changes, brake jobs, inspections), and review their prices when your catalogue prices change.
    - Disable seasonal or outdated templates instead of letting the **Apply Template** list grow.
