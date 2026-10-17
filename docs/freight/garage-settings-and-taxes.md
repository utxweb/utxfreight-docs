# Garage Settings & Tax Rates

Set the defaults your garage uses for each office (labor rate, payment terms, invoice numbering and the company details printed on documents) and manage the GST/QST tax rates applied to garage invoices.

## :fontawesome-solid-sliders: Overview

The Garage sidebar has two setup pages: **Settings** (page title **Garage Settings**) and **Taxes** (page title **Tax Rates**).

- :fontawesome-solid-building: **Garage Settings are per office.** Each office has its own labor rate, payment terms, invoice prefix, invoice number sequence and company details. The page always shows the settings of the office you are currently working in (see [Multi-Office](multi-office.md)).
- :fontawesome-solid-wrench: **Default Labor Rate ($/hour)** pre-fills the **Rate** of each new labor line on a work order.
- :fontawesome-solid-calendar-days: **Default Payment Terms** pre-fills the **Terms** of new garage invoices.
- :fontawesome-solid-hashtag: **Invoice Prefix** and the office's invoice sequence build garage invoice numbers such as `GRG-00001`. The page shows the number the next invoice will get.
- :fontawesome-solid-address-card: **Company Information** (address, phone, GST and QST numbers) is printed on garage invoices, work order estimates, statements and summaries.
- :fontawesome-solid-percent: **Tax Rates are shared with freight.** **Garage** > **Taxes** shows and edits the **same** tax records as **Manage Taxes** in the main application, from **all** offices. See [Charge Types, Expense Types & Taxes](charge-types-and-taxes.md).

<!-- TODO: Screenshot — The Garage Settings page with Default Labor Rate, Shop Supplies, Default Payment Terms, Invoice Prefix (with the "Next invoice:" preview) and the Company Information section -->

---

## :fontawesome-solid-bolt: Quick Start

**To set up a new office's garage:**

1. In the Garage sidebar, click **Settings**.
2. Enter the **Default Labor Rate ($/hour)**, pick the **Default Payment Terms** and set the **Invoice Prefix**.
3. Under **Company Information (shown on invoices)**, fill in **Company Address**, **Phone**, **GST Number** and **QST Number**.
4. Click **Save Settings**.
5. Click **Taxes** in the sidebar and check that your office has an **Active** tax rate. If not, click **New Tax Rate**, enter the **Name**, **GST (Federal Tax %)** and **QST (Provincial Tax %)**, tick **Active** and click **Create Tax Rate**.

!!! tip "Do this before the first invoice"
    Invoice numbers are assigned the moment an invoice is created, and new invoices take their terms and tax from these pages. Set them up first so your numbering, terms and taxes are right from the start.

---

## :fontawesome-solid-shield-halved: Access & Permissions

Both pages are part of the Garage area, which is only available when the Garage add-on is enabled for your company (see [Add-ons & Options](add-ons-and-options.md)).

| Role | Garage Settings | Tax Rates |
|------|-----------------|-----------|
| :fontawesome-solid-user-shield: **Admin** | View and edit | View, create, edit and delete |
| :fontawesome-solid-user-tie: **Manager** | View and edit | View, create, edit and delete |
| :fontawesome-solid-screwdriver-wrench: **Garage** | View and edit | View, create, edit and delete |
| :fontawesome-solid-file-invoice-dollar: **Accountant**, :fontawesome-solid-headset: **Dispatch**, **Warehouse**, **Customer**, drivers | No access to the Garage area | No access to the Garage area |

!!! warning "Garage Taxes also apply to freight"
    The Garage **Taxes** page edits the same tax records as **Manage Taxes** in the main application. A change made there by anyone with Garage access also applies to **freight** invoices. See [Tax Rates are shared with freight](#tax-rates-are-shared-with-freight).

**How to get there:**

- :fontawesome-solid-arrow-right: Garage sidebar :fontawesome-solid-arrow-right: **Settings** opens **Garage Settings**.
- :fontawesome-solid-arrow-right: Garage sidebar :fontawesome-solid-arrow-right: **Taxes** opens **Tax Rates**.

See [Garage Overview](garage-overview.md) for how to open the Garage area.

---

## :fontawesome-solid-sliders: Garage Settings

The **Garage Settings** page is a single form for the current office. An office's settings are created automatically the first time they are needed (for example when someone opens **Settings**, or creates a work order or invoice in that office), with these starting values:

| Setting | Starting value |
|---------|----------------|
| **Default Labor Rate ($/hour)** | 95.00 |
| **Shop Supplies (% of subtotal)** | 5.00 |
| **Default Payment Terms** | Net 30 |
| **Invoice Prefix** | GRG |
| Next invoice number | 1 (shown as `GRG-00001`) |
| Company Information fields | Empty |

### :fontawesome-solid-pen: Editing the settings

1. Make sure you are working in the right office (see [Multi-Office](multi-office.md)).
2. In the Garage sidebar, click **Settings**.
3. Change the fields you need (see the table below).
4. Click **Save Settings**. The page reloads with the message **Settings updated successfully.**

### :fontawesome-solid-table-list: Fields

| Field | Hint shown on the page | What it does |
|-------|------------------------|--------------|
| **Default Labor Rate ($/hour)** | *Applied to new labor line items* | Pre-fills the **Rate** of each new labor line on a work order. You can change the rate on any line. Existing labor lines keep their rate when you change this setting. Must be 0 or more. |
| **Shop Supplies (% of subtotal)** | *Suggested percentage for shop supplies fee* | Your office's suggested shop supplies percentage, for reference. The fee itself is entered as a dollar amount on the work order or invoice. See [How shop supplies are charged](#how-shop-supplies-are-charged). Must be between 0 and 100. |
| **Default Payment Terms** | — | Pre-fills **Terms** on new garage invoices. Choices: **Due on Receipt**, **Net 15**, **Net 30**, **Net 45**, **Net 60**. |
| **Invoice Prefix** | *Next invoice:* followed by the next number, for example **GRG-00042** | The text placed before the number on new garage invoices. See [Invoice numbering](#invoice-numbering). |
| **Company Address** | Placeholder *123 Main St\nCity, Province  Postal Code* | Multi-line address printed on garage documents. Press Enter to start a new line. Printed documents keep your line breaks; emails show the lines joined with ` \| `. |
| **Phone** | — | Phone number printed on garage documents. |
| **GST Number** | — | Your GST registration number, printed next to the **GST** line on invoices and work order estimates. |
| **QST Number** | — | Your QST registration number, printed next to the **QST** line on invoices and work order estimates. |

!!! info "Garage company details are separate from freight"
    **Company Address**, **Phone**, **GST Number** and **QST Number** here are used only by Garage documents. Freight invoices use the GST and QST numbers in the main application settings (see [Application Settings](application-settings.md)). If you use both, fill in both places.

!!! note "Allowed values"
    The labor rate must be 0 or more and the shop supplies percentage must be between 0 and 100. Settings outside these ranges are not saved.

### Invoice numbering

Every garage invoice gets its number when it is created (drafts included). The number is built as:

`<Invoice Prefix>-<next number padded to 5 digits>`

For example, prefix `GRG` and next number 42 give `GRG-00042`. After each new invoice, the office's next number goes up by one.

- The **Next invoice:** line under **Invoice Prefix** shows the number the next invoice will get. It reflects the **saved** prefix, so it updates after you click **Save Settings**.
- The **next number cannot be edited** on this page. It only moves forward as invoices are created. It is never reset and numbers are never reused, even if an invoice is voided.
- Changing the **Invoice Prefix** only affects invoices created afterwards. Existing invoices keep their numbers, and the sequence continues from where it was (for example `GRG-00042` is followed by `SHOP-00043`).
- Each office has its **own** sequence, but invoice numbers must be unique across **all** offices. If you use the Garage in more than one office, give each office a **different** prefix so their invoice numbers never overlap.

!!! tip "Always set a prefix"
    `GRG` is only the starting value. Keep a prefix in the **Invoice Prefix** field so your invoice numbers stay easy to recognise.

See [Garage Invoices & Payments](garage-invoices.md) for how invoices are created.

### :fontawesome-solid-print: Where the company information appears

| Document | Company Address and Phone | GST Number and QST Number |
|----------|:-------------------------:|:-------------------------:|
| Printed / PDF garage invoice | :fontawesome-solid-circle-check: | :fontawesome-solid-circle-check: |
| Printed work order (estimate) | :fontawesome-solid-circle-check: | :fontawesome-solid-circle-check: |
| Invoice email (body) | :fontawesome-solid-circle-check: | — (they are on the attached PDF invoice) |
| Work summary email (body and attached PDF) | :fontawesome-solid-circle-check: | — |
| Customer statement (print and email) | :fontawesome-solid-circle-check: | — |
| Customer summary (print) | :fontawesome-solid-circle-check: | — |

Each item is only printed when it is filled in. The GST and QST numbers appear in brackets next to the **GST** and **QST** lines, and only when the document has a GST or QST amount above 0. See [Garage Work Orders](garage-work-orders.md), [Garage Invoices & Payments](garage-invoices.md) and [Garage Reports](garage-reports.md).

### How shop supplies are charged

Shop supplies are charged as a dollar amount:

- On a work order, enter the amount in **Shop Supplies Fee**.
- On an invoice, the shop supplies amount is the sum of the work orders' fees, unless you enter a different amount on the invoice.

Shop supplies are taxable: GST and QST are calculated on them along with the taxable parts and labor. See [Garage Work Orders](garage-work-orders.md) and [Garage Invoices & Payments](garage-invoices.md).

---

## :fontawesome-solid-percent: Tax Rates

The **Tax Rates** page (subtitle *Manage GST/QST rates for invoices*) lists tax rates in alphabetical order by name.

<!-- TODO: Screenshot — The Tax Rates page with Name, GST %, QST %, Active, Invoices and Actions columns -->

### :fontawesome-solid-table-columns: Columns

| Column | Shows |
|--------|-------|
| **Name** | The tax rate name. This is what appears in the **Tax Rate** dropdown on garage invoices. |
| **GST %** | The federal tax percentage. |
| **QST %** | The provincial tax percentage. |
| **Active** | An **Active** (green) or **Inactive** (grey) badge. |
| **Invoices** | How many **garage** invoices use this tax rate. |
| **Actions** | :fontawesome-solid-pen-to-square: **Edit**, and :fontawesome-solid-trash: **Delete** when no garage invoice uses the tax rate. |

!!! info "The list shows all offices"
    The page lists every tax rate in the application, from **all** offices, and does not show which office each one belongs to. Use names that make the office clear (for example *QC GST/QST 2025*) if you have several offices.

If there are no tax rates at all, the page shows **No tax rates yet** with a **Create Tax Rate** button.

### :fontawesome-solid-plus: Adding a tax rate

1. Click **New Tax Rate**.
2. Fill in the form (see below).
3. Click **Create Tax Rate**. You return to the list with the message **Tax rate created successfully.**

The new tax rate belongs to the office you are currently working in. There is no office field on this form.

### :fontawesome-solid-pen-to-square: Editing a tax rate

1. Click the :fontawesome-solid-pen-to-square: **Edit** icon on the row. The page **Edit Tax Rate:** *name* opens.
2. Change the fields.
3. Click **Update Tax Rate** (or **Cancel** to go back). You return to the list with the message **Tax rate updated successfully.**

Editing does not change which office the tax rate belongs to.

### :fontawesome-solid-table-list: Form fields

| Field | Hint shown on the page | Notes |
|-------|------------------------|-------|
| **Name \*** | Placeholder *e.g. GST/QST 2025* | The name shown in the **Tax Rate** dropdown on garage invoices and wherever freight lists taxes. |
| **Active** | *Available for use on invoices* | Only active tax rates of your current office are offered on garage invoices. New tax rates are active by default. |
| **GST (Federal Tax %)** | *Federal Goods & Services Tax percentage* (placeholder 5.0) | Enter `5` for 5%. The browser accepts 0 to 100 in steps of 0.001. |
| **QST (Provincial Tax %)** | *Quebec Sales Tax percentage* (placeholder 9.975) | Enter `9.975` for 9.975%. Enter `0` if you do not charge a provincial tax. The browser accepts 0 to 100 in steps of 0.001. |

### :fontawesome-solid-calculator: How garage documents use tax rates

- **New invoice:** the **Tax Rate** dropdown lists only the **active** tax rates of your current office, plus **No tax**. The first active tax rate of the office is pre-selected.
- **Invoice from a work order** (**Generate Single Invoice**): the office's first active tax rate is used.
- **Work order totals and printed estimate:** use the office's first active tax rate. With no active tax rate, no tax is shown.
- GST and QST are calculated on the taxable parts and labor plus shop supplies, after any discount. The amounts are saved on the garage invoice and recalculated when a draft invoice is saved again.

!!! tip "Keep one active tax rate per office"
    Work orders and one-click invoices pick "the first active tax rate" of the office. If an office has several active tax rates, you cannot be sure which one is picked. Keep only one active per office and set the others to inactive.

### :fontawesome-solid-trash: Deleting a tax rate

1. Click the :fontawesome-solid-trash: **Delete** icon on the row.
2. Confirm the **Delete** *name***?** prompt.
3. The tax rate is removed and the message **Tax rate deleted.** appears.

A tax rate can only be deleted when no invoice uses it, garage **or** freight. If invoices use it, the tax rate is kept and the message below appears:

> **Cannot delete tax rate — N invoice(s) use it.**

where N is the number of garage and freight invoices using it. Set the tax rate to inactive instead.

!!! danger "Deleting cannot be undone"
    A deleted tax rate cannot be restored. If you only want to stop offering it on new garage invoices, untick **Active** instead.

---

## Tax Rates are shared with freight

Garage **Taxes** and **Manage Taxes** in the main application show and edit the **same** tax records. A change on either page applies to both freight and garage invoices.

| | Garage > Taxes | Manage Taxes (freight) |
|---|---|---|
| Who can open it | Anyone with Garage access (Admin, Manager, Garage) | See [Charge Types, Expense Types & Taxes](charge-types-and-taxes.md) |
| Which tax rates are listed | All offices | See [Charge Types, Expense Types & Taxes](charge-types-and-taxes.md) |
| New tax rates belong to | Your current office | The office chosen on the form |
| **Invoices** column counts | Garage invoices | Freight invoices |
| Delete is allowed when | No garage invoice and no freight invoice uses it | See [Charge Types, Expense Types & Taxes](charge-types-and-taxes.md) |

!!! warning "Changing a rate affects freight invoices"
    Freight invoices store which tax they use, not the amount. If you edit the GST % or QST % of a tax rate that freight invoices use, those freight invoices are recalculated with the new percentage. When a rate changes, create a **new** tax rate, make it active, set the old one to inactive and leave its percentages unchanged.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-hashtag: How do I change the next invoice number?

!!! info "Solution"
    You cannot. The **Next invoice:** line is a preview only, and the number moves forward by one each time a garage invoice is created. You can change the **Invoice Prefix**, which applies to invoices created afterwards.

### :fontawesome-solid-box-open: How do I charge shop supplies?

!!! info "Solution"
    Enter the fee as an amount in **Shop Supplies Fee** on the work order, or enter it on the invoice. See [How shop supplies are charged](#how-shop-supplies-are-charged).

### :fontawesome-solid-wrench: I changed the labor rate but my work order still shows the old rate

!!! info "Solution"
    **Default Labor Rate ($/hour)** only pre-fills **new** labor lines. Existing lines keep the rate they were created with. Edit the **Rate** on those lines if needed.

### :fontawesome-solid-building: The settings look different from what I saved

!!! info "Solution"
    Garage Settings are per office. Check which office you are working in (see [Multi-Office](multi-office.md)). Each office has its own labor rate, terms, prefix, invoice sequence and company details.

### :fontawesome-solid-eye-slash: My tax rate is not in the invoice's Tax Rate dropdown

!!! info "Solution"
    The garage invoice dropdown only lists **active** tax rates of your **current office**. Check that the tax rate is ticked **Active** and that it was created in the office you are working in. The Tax Rates page lists all offices, so a tax rate can appear there but belong to another office.

### :fontawesome-solid-ban: Why can't I delete a tax rate?

!!! info "Solution"
    A tax rate used by any garage or freight invoice cannot be deleted. The **Invoices** column on this page counts garage invoices only, while the message **Cannot delete tax rate — N invoice(s) use it.** counts garage and freight invoices together. To stop offering the tax rate, untick **Active** instead.

### :fontawesome-solid-print: My address or GST number is missing from the invoice

!!! info "Solution"
    Fill in **Company Address**, **Phone**, **GST Number** and **QST Number** under **Company Information (shown on invoices)** in Garage **Settings** for the office that owns the invoice. GST and QST numbers only print next to a GST or QST line above 0, and they are not shown in the invoice email body.

---

## :fontawesome-solid-star: Best Practices

!!! tip "Best Practices"
    - Fill in **Garage Settings** and create an active tax rate for each office **before** creating the first garage invoice.
    - Give each office a **distinct Invoice Prefix** so invoice numbers never collide.
    - Keep **one active tax rate per office** so work orders and invoices always pick the right one.
    - When tax rates change, create a new tax rate and deactivate the old one instead of editing its percentages.
    - Remember that tax rates are shared with freight: agree with your accounting team before editing or deleting one.
