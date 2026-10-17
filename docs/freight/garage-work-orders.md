# Garage Work Orders

Create, price and track repair and service jobs in the Garage add-on, from the first estimate through to the invoice.

## :fontawesome-solid-wrench: Overview

- :fontawesome-solid-list: The **Work Orders** page is the first page of the Garage. It lists every work order of your current office, newest first, 20 per page, with status tabs, a search box and an **Actions** menu on each row.
- :fontawesome-solid-file-pen: A work order has a **Customer** (required), optional **Equipment**, a description, dates, an odometer reading, an assigned technician, **Parts** lines, **Labor** lines, a **Shop Supplies Fee** and **Internal Notes**.
- :fontawesome-solid-arrow-right: Every work order moves through five statuses: **Estimate** :fontawesome-solid-arrow-right: **Approved** :fontawesome-solid-arrow-right: **In progress** :fontawesome-solid-arrow-right: **Completed** :fontawesome-solid-arrow-right: **Invoiced**. An estimate can also go straight to **In progress**. A completed work order can be **Reopened** back to **Approved**. A completed work order becomes **Invoiced** when you generate an invoice for it.
- :fontawesome-solid-boxes-stacked: When a work order moves to **In progress**, the quantities of its catalogue parts are taken out of parts inventory.
- :fontawesome-solid-pen: You can edit a work order at any status, including **Invoiced** while its invoice is still a **draft**. Saving then recalculates the draft invoice. Only a work order billed on an invoice that has left draft (sent, partially paid, paid) is locked.
- :fontawesome-solid-print: **Print Estimate** opens a printable estimate for the customer. Internal notes are never printed.
- :fontawesome-solid-gauge: The **Odometer In** you enter updates the equipment's odometer, but only when the new reading is higher.

<!-- TODO: Screenshot — Work Orders list with status tabs, search box and an open row Actions menu -->

---

## :fontawesome-solid-bolt: Quick Start

1. Click **Garage** in the left menu of UTX Freight. The Garage opens on :fontawesome-solid-arrow-right: **Work Orders**.
2. Click **New Work Order**.
3. Type at least two letters in **Customer** and pick the customer from the list (or click the green **+** to create one).
4. Click in **Equipment** to see that customer's units and pick one (or click **+** to create one).
5. Optional: pick a template under **Apply Template** and click **Apply** to fill in parts and labor.
6. Add or adjust **Parts** and **Labor** lines, then click **Create Work Order**. It is saved as an **Estimate**.
7. Click **Print Estimate** to give the customer a copy. When they agree, click **Mark Approved**.
8. When work starts, click **Mark In progress** (parts are taken out of inventory). When it is done, click **Mark Completed**.
9. Click **Generate Single Invoice** to bill it, or **Bundle with Other Work Orders** to put several completed work orders on one invoice. See [Garage Invoices](garage-invoices.md).

---

## :fontawesome-solid-shield-halved: Access & Permissions

The Garage is an add-on. When it is not turned on for your company, the **Garage** menu item does not appear and Garage pages send you back to the dashboard. See [Add-ons and Options](add-ons-and-options.md).

| Role | Work Orders (view, create, edit, change status, print, invoice) |
|------|------|
| :fontawesome-solid-user-tie: **Admin** | Yes |
| :fontawesome-solid-user-tie: **Manager** | Yes, for the offices they belong to |
| :fontawesome-solid-screwdriver-wrench: **Garage** | Yes, for the offices they belong to |
| :fontawesome-solid-headset: **Dispatch**, **Accountant**, **Customer**, **Driver**, **Warehouse** and other roles | No — the **Garage** menu item is hidden |

**Where to find it:**

- :fontawesome-solid-arrow-right: Left menu :fontawesome-solid-screwdriver-wrench: **Garage** — opens the Work Orders list
- :fontawesome-solid-arrow-right: Garage sidebar :fontawesome-solid-arrow-right: **Work Orders**
- :fontawesome-solid-arrow-right: Garage sidebar :fontawesome-solid-arrow-right: **Customers** :fontawesome-solid-arrow-right: the work order button on a customer row — opens **New Work Order** with that customer already filled in

!!! info "Current office"
    Work orders belong to an office. The list, the counts, the customer, equipment and part searches, the technician list and the tax used for totals all follow the office you are currently working in. With [multiple offices](multi-office.md), switch office to see another office's work orders. See [User Roles](user-roles.md) for what each role can do elsewhere.

---

## :fontawesome-solid-list: The Work Orders List

### Status tabs

Above the list is one tab per status, each with a count:

| Tab | Shows |
|-----|-------|
| **All** | Every work order (selected by default) |
| **Estimates** | Status **Estimate** |
| **Approved** | Status **Approved** |
| **In Progress** | Status **In progress** |
| **Completed** | Status **Completed** |
| **Invoiced** | Status **Invoiced** |

The counts follow the search: while a search is active, each tab counts only the work orders that match it.

### Search

Type in the search box and click **Search**. One search term is matched (case-insensitive, anywhere in the text) against:

- the customer's **first name**, **last name** and **company name**
- the work order **description**
- the equipment **unit number**, **VIN**, **license plate**, **make**, **model** and **equipment type** (truck, trailer, chassis)

Work orders with no equipment are still found by customer or description.

The search keeps the tab you are on. Clicking a different tab starts again without the search term.

### Columns

| Column | What it shows |
|--------|---------------|
| **ID** | The work order number, for example *#128*. Click it to open the work order. |
| **Customer** | The customer name, with the company in brackets when there is one |
| **Equipment** | Type, unit number and year/make/model of the equipment, or **-** if none |
| **Status** | A coloured badge (see [Status colours](#status-colours)) |
| **Date In** | The **Date In** of the work order |
| **Technician** | The **Assigned Technician**, or **-** |
| **Total** | Parts + labor + shop supplies fee, **before tax** |
| **Actions** | The :fontawesome-solid-ellipsis-vertical: menu (see below) |

Work orders are sorted by creation date, newest first, 20 per page, with page links at the bottom when there is more than one page.

### Row Actions menu

Click :fontawesome-solid-ellipsis-vertical: on a row. The menu has up to three sections and only shows what applies to that work order:

| Section | Item | Shown when |
|---------|------|------------|
| **View** | **View details** | Always |
| | **Open invoice** (with the invoice number) | The work order is on an invoice that is not void |
| | **Print estimate** | Always (opens in a new tab) |
| **Move to** | **Approved**, **In progress**, **Completed** | The next statuses allowed from the current one (see [Status workflow](#status-workflow)) |
| **Actions** | **Edit** | The work order is not locked. Shows **updates draft** when it is on a draft invoice. |
| | **Generate invoice** | Status is **Completed** and there is no active invoice |
| | **Bundle with others** | Same as **Generate invoice** |
| | **Reopen** | Status is **Completed** |

A status change or reopen started from the list brings you back to the list, on the same tab.

### Empty states

- **No work orders yet** — shown when no search is active and the tab you are on has no work orders (for example the **Invoiced** tab when nothing is invoiced yet). Click **Create Your First Work Order**.
- **No work orders match "…"** — your search found nothing. The message reminds you what the search covers. Click **Clear search** to go back to the tab without the search term.

---

## :fontawesome-solid-file-pen: Creating and Editing a Work Order

Click **New Work Order** on the list, or **Edit** on a work order. New work orders start with **Date In** set to today and one empty part row and one empty labor row.

<!-- TODO: Screenshot — New Work Order form with customer, equipment chip, parts and labor lines -->

### Apply Template

The purple **Apply Template** box appears at the top of the form only when your office has at least one active template (Garage sidebar :fontawesome-solid-arrow-right: **Templates**, see [Garage Parts and Templates](garage-parts-and-templates.md)).

1. Pick a template in **-- Select a template --**.
2. Click **Apply**.

What happens:

- Empty part and labor rows are removed first.
- The template's parts and labor lines are **added after** the lines already on the form. Nothing you already entered is replaced, so applying a template twice adds its lines twice.
- Part lines get the template's part (when it is a catalogue part), description, quantity, cost and charge. Labor lines get the template's description, hours and rate.
- A **Template Applied** message confirms *"<template name>" has been applied.*

| Message | Meaning |
|---------|---------|
| **Please select a template first.** | You clicked **Apply** without picking a template |
| **Failed to load template.** | The template could not be loaded. Try again. |

### Customer

**Customer \*** is required.

- Type at least **2 characters**. The list shows up to 15 active customers of your office whose first name, last name or company name contains what you typed. Pick one.
- Typing a name without picking it from the list does not select a customer. If you save that way, you get **Customer is required. Please search and select a customer.**
- Click the green :fontawesome-solid-plus: button to open **Quick Create Customer**: fill in **First Name \***, **Last Name \***, and optionally **Phone** and **Company**, then click **Create & Select**. The new customer is created and selected. If a name is missing you see **First name and last name are required.**
- While the work order is on a draft invoice, the customer box is greyed out, the green :fontawesome-solid-plus: button is not shown, and the customer cannot be changed (see [Editing a work order on a draft invoice](#editing-a-work-order-on-a-draft-invoice)).

### Equipment

**Equipment** is optional.

- When a customer is selected, clicking in the equipment box immediately lists **that customer's** active equipment. Type to narrow the list.
- With no customer selected, typing searches all active equipment of the office.
- The search matches **unit number**, **make**, **model**, **VIN** and **license plate**, and shows up to 15 results.
- After you pick a unit, it is shown as a blue chip (*equipment — owner*). Click **Change** on the chip to clear it and search again.
- Text you type but never pick from the list is cleared when you leave the box.
- Click the green :fontawesome-solid-plus: button to open **Quick Create Equipment**: pick the **Equipment Type \*** (**Truck**, **Trailer** or **Chassis**) and optionally fill in **Unit Number**, **Year**, **Make**, **Model** and **License Plate**, then click **Create & Select**. If a customer is already selected on the work order, the new equipment is linked to that customer. If no type is picked you see **Equipment type is required.**

Full equipment records (VIN, odometer, service history) are managed under Garage sidebar :fontawesome-solid-arrow-right: **Equipment**. See [Garage Customers and Equipment](garage-customers-and-equipment.md).

### Job details

| Field | Notes |
|-------|-------|
| **Description** | The work to be done. Shown on the work order, the printed estimate, and searchable from the list. |
| **P/O Number** | The customer's purchase order number. Shown on the work order and the printed estimate. |
| **Date In** | Defaults to today on a new work order |
| **Est. Completion** | Expected completion date. Printed on the estimate as **Estimated Completion**. |
| **Odometer In** | Current mileage. Whole number, 0 or more. See [Odometer updates](#odometer-updates). |
| **Assigned Technician** | Pick from the active users of your current office. The field is hidden when there are none. |
| **Shop Supplies Fee** | A dollar amount, 0 or more. Added to the total and always counted as taxable. |
| **Internal Notes (not shown on invoice)** | For your shop only. Shown on the work order page, never on the printed estimate. |

There is no **Date Out** field on the form. **Date Out** is set automatically when the work order is marked **Completed**.

### Parts lines

Each part row has: **Part / Description**, **Qty**, **Cost**, **Charge**, **Line Total**, **Tax** and a red :fontawesome-solid-xmark: to remove the row. Click **Add Part** to add a row.

- **From the parts catalogue:** type at least **2 characters** of a part name or SKU in **Part / Description**. The list shows up to 15 active parts of your office as *Name (SKU)*. Picking one links the line to the catalogue part and fills in the name, **Cost** (purchase price) and **Charge** (selling price). You can change the prices afterwards.
- **Low Stock warning:** if the picked part's quantity on hand is at or below its reorder point, a **Low Stock** message appears for a few seconds: *<part> has only <n> left in stock.* It is a warning only; the line is still added.
- **Free-text line:** type a description without picking from the list. The line is not linked to the catalogue and never affects inventory.
- When a line is first saved with a catalogue part (or switched to a different one) and **Cost** or **Charge** is 0, or the description is empty, they are filled from the catalogue when you save.
- **Qty** must be a whole number greater than 0. **Cost** and **Charge** must be 0 or more.
- **Line Total** (Qty × Charge) updates as you type.

### Labor lines

Each labor row has: **Description**, **Hours**, **Rate**, **Line Total**, **Tax** and :fontawesome-solid-xmark:. Click **Add Labor** to add a row.

- **Rate** is pre-filled with the **Default Labor Rate ($/hour)** from Garage sidebar :fontawesome-solid-arrow-right: **Settings** (see [Garage Settings and Taxes](garage-settings-and-taxes.md)). You can change it per line.
- **Description** is required. **Hours** must be 0 or more (in steps of 0.25). **Rate** must be greater than 0.
- **Line Total** (Hours × Rate) updates as you type.

### Taxable flag

The **Tax** checkbox on each part and labor line is ticked by default, including on lines added by a template. Untick it for lines that should not be taxed. Only ticked lines, plus the shop supplies fee, are taxed in the totals.

### Saving

Click **Create Work Order** (new) or **Update Work Order** (edit). **Cancel** leaves without saving.

| Message | When |
|---------|------|
| **Work order created successfully.** | A new work order was saved. It is always created as **Estimate**. |
| **Work order updated successfully.** | Changes saved |
| **Work order updated. Draft invoice <number> was recalculated to <total>.** | Changes saved on a work order that is on a draft invoice |
| *<n> errors prevented this work order from being saved:* followed by a list | Something is missing or invalid (for example no customer, a part quantity of 0, a labor line with no description). Fix the listed items and save again. |

!!! tip "Remove rows you don't use"
    Every part and labor row on the form is saved and checked as a line. Click :fontawesome-solid-xmark: on any empty part or labor row you do not need before saving.

---

## :fontawesome-solid-arrows-turn-right: Status Workflow

| From | Can move to | Button on the work order page | Confirmation text |
|------|-------------|------------------|-------------------|
| **Estimate** | **Approved** | **Mark Approved** | *Mark as Approved? The customer has agreed to the estimate.* |
| **Estimate** | **In progress** | **Mark In progress** | *Mark as In Progress? Parts inventory will be decremented.* |
| **Approved** | **In progress** | **Mark In progress** | *Mark as In Progress? Parts inventory will be decremented.* |
| **In progress** | **Completed** | **Mark Completed** | *Mark as Completed? You can generate an invoice or reopen the work order from the completed state.* |
| **Completed** | **Invoiced** | **Generate Single Invoice** or **Bundle with Other Work Orders** | See [Garage Invoices](garage-invoices.md) |
| **Completed** | **Approved** (reopen) | **Reopen Work Order** | *Reopen this work order? It goes back to Approved because the work is not actually finished. You do not need this just to edit it — use Edit instead.* |

The same moves are in the row **Actions** menu under **Move to** and **Actions** (the **Completed** confirmation there reads *Mark as Completed? You can generate an invoice or reopen the work order.*, and **Reopen** asks *Reopen this work order? It will return to Approved.*).

After a move you see *Work order #<id>: status changed to <status>.* Reopening shows *Work order #<id>: reopened to Approved.*

**What each move does:**

- **To In progress:** catalogue parts on the work order are taken out of inventory (see [Parts inventory](#parts-inventory)).
- **To Completed:** **Date Out** is set to today, unless it already has a date. **Date Out** is not shown on the work order page or the printed estimate; it appears as **Completed:** on the invoice and in the customer summary report.
- **To Invoiced:** happens when the work order is put on an invoice (**Generate Single Invoice**, **Bundle with Other Work Orders**, or adding it to an invoice).
- **Reopen:** only from **Completed**. The work order goes back to **Approved**. **Date Out** is not cleared.

You cannot move a work order backwards (other than **Reopen**), and there are no moves out of **Invoiced**. To take a work order off an invoice, delete or void the invoice, or remove the work order from it, on the invoice side. See [Garage Invoices](garage-invoices.md).

| Message | Meaning |
|---------|---------|
| **Cannot transition to <status>.** | That move is not allowed from the current status |
| **Cannot modify an invoiced work order.** | The work order is on an invoice that has left draft |
| **Only completed work orders can be reopened.** | **Reopen** was used on a work order that is not **Completed** |
| **Work order must be completed before invoicing.** | An invoice was requested for a work order that is not **Completed** |

!!! tip "Editing does not need Reopen"
    You can edit a completed work order directly with **Edit**. Use **Reopen** only when the work is actually not finished.

### Status colours

| Badge | Status |
|-------|--------|
| :fontawesome-solid-circle:{ style="color: #ca8a04" } Yellow | **Estimate** |
| :fontawesome-solid-circle:{ style="color: #2563eb" } Blue | **Approved** |
| :fontawesome-solid-circle:{ style="color: #9333ea" } Purple | **In progress** |
| :fontawesome-solid-circle:{ style="color: #16a34a" } Green | **Completed** |
| :fontawesome-solid-circle:{ style="color: #64748b" } Grey | **Invoiced** |

### Deleting a work order

Work orders are not deleted from the **Work Orders** list or the work order page. Leave unused estimates in the **Estimates** tab.

---

## :fontawesome-solid-boxes-stacked: Parts Inventory

Inventory is the **quantity on hand** of each part in Garage sidebar :fontawesome-solid-arrow-right: **Parts** (see [Garage Parts and Templates](garage-parts-and-templates.md)). Only lines linked to a catalogue part count; free-text lines never touch inventory.

| Event | Effect on quantity on hand |
|-------|---------------------------|
| Work order moves to **In progress** | Each catalogue part line's **Qty** is subtracted. Stock never goes below 0. |
| A catalogue part line is removed while the work order is **In progress**, **Completed** or **Invoiced** (draft invoice) | The line's **Qty** is added back |
| A catalogue part line is removed while the work order is **Estimate** or **Approved** | Nothing (stock was never taken out) |

!!! tip "Add parts before In progress"
    Stock is taken out when the work order moves to **In progress**. Put all catalogue parts on the work order before that step. To correct a part's stock at any time, adjust its quantity on hand under Garage **Parts**.

---

## :fontawesome-solid-file-invoice-dollar: Editing a Work Order on a Draft Invoice

A work order that is **Invoiced** on an invoice still in **draft** stays editable, so you can fix a line without voiding the invoice.

- The work order page shows an amber banner: *This work order is on <invoice number> which is still a draft — you can still edit it. Saving a change updates the draft invoice totals automatically. No need to void the invoice.* with an **Open draft invoice** link.
- The edit form shows: *This work order is on draft invoice <number>. Your changes will be saved and the draft invoice total will be updated automatically. You do not need to void the invoice. The customer cannot be changed here — remove the work order from the invoice first.*
- The **Customer** box is read-only. To bill a different customer, remove the work order from the invoice first.
- When you save, the draft invoice totals are recalculated. A change to the work order's **Shop Supplies Fee** moves the invoice's shop supplies fee by the same amount, so an amount typed directly on the invoice is kept.
- If you started the edit from the draft invoice page, saving takes you back to the invoice. Otherwise you return to the work order.

### When the work order is locked

Once the invoice is marked sent (or has payments), the work order is locked. **Edit** is greyed out with a :fontawesome-solid-lock: and the tooltip *This work order is billed on a sent invoice. Reopen that invoice to Draft to edit it again.* Trying to edit shows one of these messages:

| Invoice status | Message | Way out |
|----------------|---------|---------|
| Sent | *Cannot edit this work order — it is billed on invoice <number>. Use 'Reopen to Edit' on that invoice first.* | Use **Reopen to Edit** on the invoice, then edit the work order |
| Partially paid | *Cannot edit this work order — it is billed on invoice <number>, which has payments recorded. Remove the payments, then use 'Reopen to Edit' on it.* | Remove the payments on the invoice, then **Reopen to Edit** |
| Paid | Same message as partially paid | See the warning below |

If the invoice was marked sent between opening the form and saving, the save is refused with the same message and nothing is changed.

!!! info "Work orders on paid invoices"
    Payments cannot be removed from a fully paid invoice (*Cannot remove payments from a fully paid invoice.*), and only sent invoices without payments can be reopened. So a work order on a **paid** invoice cannot be edited. Voiding the invoice takes its work orders off it and returns them to **Completed**, but it also voids a paid invoice — check with your accountant first. See [Garage Invoices](garage-invoices.md).

---

## :fontawesome-solid-file-lines: The Work Order Page

Click the work order **ID** or **View details**.

<!-- TODO: Screenshot — Work Order detail page with header buttons, status hint, customer/equipment cards and totals -->

### Header

- **Work Order #<id>**, the total **including tax**, the status badge, **Date In**, the technician and the **P/O** number.
- Buttons, depending on status: **Edit**, **Print Estimate**, **Mark Approved** / **Mark In progress** / **Mark Completed**, and for **Completed** work orders **Generate Single Invoice**, **Bundle with Other Work Orders** and **Reopen Work Order**. **View Invoice** appears when the work order is on an invoice that is not void.

### Status hint

A blue bar under the header tells you the next step:

| Status | Hint |
|--------|------|
| **Estimate** | *This is an estimate. When the customer approves, click 'Mark Approved' to proceed.* |
| **Approved** | *Customer approved. Click 'Mark In Progress' when work begins.* |
| **In progress** | *Work is being performed. Click 'Mark Completed' when the job is done.* |
| **Completed** | *Work is finished. Click 'Generate Invoice' to bill the customer.* |
| **Invoiced** | *This work order has been invoiced.* with a **View Invoice** link |

On a draft invoice, the amber draft banner replaces this bar.

### Cards and tables

| Section | Contents |
|---------|----------|
| **Customer** | Name (with company), phone and email |
| **Equipment** | Equipment name, **VIN**, **Odometer** (the equipment's current reading), **Odometer In** (this work order's reading) and a **View Service History** link to the equipment page. Shows *No equipment assigned* when there is none. |
| **Description** | Shown when filled in |
| **Parts** | **Description**, **Qty**, **Unit Price** (the charge price), **Total**, **Tax** (:fontawesome-solid-check: taxable, :fontawesome-solid-minus: not taxable), and **Parts Subtotal**. *No parts added* when empty. Cost prices are not shown here. |
| **Labor** | **Description**, **Hours**, **Rate**, **Total**, **Tax**, and **Labor Subtotal**. *No labor added* when empty. |
| **Totals** | **Parts**, **Labor**, **Shop Supplies** (when above 0), then, when a tax is set up, **Subtotal**, **GST (x%)**, **QST (x%)**, and **Total** |
| **Internal Notes** | Yellow box, shown when filled in |

**Back to Work Orders** returns to the list.

### How tax is calculated

- The tax rates come from the **first active tax** set up for your current office (Garage sidebar :fontawesome-solid-arrow-right: **Taxes**, see [Garage Settings and Taxes](garage-settings-and-taxes.md)). If there is no active tax, no tax lines are shown and the total has no tax.
- Taxable amount = ticked part lines + ticked labor lines + the **Shop Supplies Fee**.
- **GST** and **QST** are each that taxable amount × their rate, rounded to the cent.
- **Total** = parts + labor + shop supplies + GST + QST.

!!! info "List total vs. page total"
    The **Total** column on the list is **before tax**. The total in the work order header and at the bottom of the page **includes tax**. The final invoice amount can differ again if the invoice has a discount or a different tax. See [Garage Invoices](garage-invoices.md).

---

## :fontawesome-solid-print: Print Estimate

Click **Print Estimate** on the work order page, or **Print estimate** in the row **Actions** menu. The estimate opens in a new browser tab; use your browser's print command to print it or save it as PDF.

The estimate shows:

- A faint **ESTIMATE** watermark, your logo (when one is set up for your installation), company name, *Garage Services*, and the **Company Address** and **Phone** from Garage **Settings** (Company Information), when filled in.
- **ESTIMATE** and **WO #<id>** at the top right.
- **Prepared For**: customer name, phone and email.
- **Vehicle / Equipment** (when equipment is set): equipment name, **VIN** and **Plate**.
- **P/O Number** (when set), **Date In**, **Estimated Completion** (when set) and **Status**.
- **Description** (when set).
- One table with all part lines, then all labor lines: **Description**, **Qty/Hours**, **Rate**, **Amount**, **Tax** (:fontawesome-solid-check: for taxable lines).
- Totals: **Subtotal** (parts + labor), **Shop Supplies** (when above 0), **GST** and **QST** (only when above 0, with your GST/QST numbers from Garage **Settings** when set), and **Estimated Total**.

**Not printed:** internal notes, the assigned technician, odometer readings and part cost prices.

The estimate can be printed at any status; the **Status** line shows where the work order is.

---

## :fontawesome-solid-gauge: Odometer Updates

When you save a work order with an **Odometer In** value and equipment selected:

- If the reading is **higher** than the equipment's current odometer (or the equipment has none), the equipment's odometer is set to it.
- If it is the same or **lower**, the equipment's odometer is left unchanged. The work order still keeps its own **Odometer In**.

This happens when you first enter **Odometer In**, change it, or change the equipment on the work order. The equipment odometer never goes down from a work order.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-user-xmark: "Customer is required" but I typed the customer name

!!! info "Solution"
    Typing is not enough: you must pick the customer from the drop-down list that appears after 2 characters. If the customer does not exist, click the green **+** next to **Customer** and use **Quick Create Customer**.

### :fontawesome-solid-truck: The equipment list is empty when I click in Equipment

!!! info "Solution"
    With a customer selected, the list, and anything you type, only covers that customer's **active** equipment. A unit linked to no customer or to another customer does not appear. Check under Garage **Equipment** that the unit is active and linked to the right customer, or create it with the **+** button (it is linked to the selected customer). Equipment that is not linked to any customer can only be found when no customer is selected yet.

### :fontawesome-solid-boxes-stacked: Inventory did not go down for a part I added

!!! info "Solution"
    Stock is taken out when the work order moves to **In progress**, and only for lines linked to a catalogue part (picked from the list). Free-text lines never change inventory. To correct stock, adjust the part's quantity on hand under Garage **Parts**.

### :fontawesome-solid-lock: I can't edit an invoiced work order

!!! info "Solution"
    If the invoice is a draft, **Edit** works and the invoice total is recalculated. If the invoice was sent, open it and use **Reopen to Edit**. If it has payments, remove them first. A fully paid invoice cannot be reopened (see [When the work order is locked](#when-the-work-order-is-locked)).

### :fontawesome-solid-trash: How do I delete a work order?

!!! info "Solution"
    Work orders are not deleted from the Garage screens. Leave unused estimates in the **Estimates** tab.

### :fontawesome-solid-calculator: The total on the list is different from the total on the work order

!!! info "Solution"
    The list total is before tax. The work order page total includes GST and QST from your office's active tax.

### :fontawesome-solid-clipboard-list: I don't see Apply Template

!!! info "Solution"
    The box only appears when your current office has at least one **active** template. Create or enable one under Garage :fontawesome-solid-arrow-right: **Templates**.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips"
    - Pick parts from the catalogue instead of typing them, so inventory and costs stay accurate.
    - Get all parts on the work order **before** marking it **In progress**, since that is when stock is taken out.
    - Use **Edit**, not **Reopen**, to fix lines on a completed work order.
    - Bill completed work orders with **Generate Single Invoice** or **Bundle with Other Work Orders**.
    - Fix mistakes while the invoice is still a draft. Once it is sent, you have to reopen the invoice; once it is paid, you cannot edit the work order.
    - Enter **Odometer In** on every visit to keep the equipment's mileage and service history up to date.
    - Use **Internal Notes** for shop-only information; it never appears on the printed estimate.
