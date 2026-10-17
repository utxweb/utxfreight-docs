# Garage Module Overview

The **Garage** add-on is a repair shop module inside UTX Freight: you keep garage customers and their vehicles, write work orders for repairs and service, turn finished work into invoices, and record payments, all separately from your freight orders and invoices.

## :fontawesome-solid-screwdriver-wrench: Overview

- :fontawesome-solid-puzzle-piece: **Garage** is an add-on. It only appears when it is turned on for your installation. See [Add-ons & Options](add-ons-and-options.md).
- :fontawesome-solid-door-open: You open it from the **Garage** item in the main (left) menu of UTX Freight. It always opens on **Work Orders**.
- :fontawesome-solid-table-columns: The Garage has its own screen layout with a dark sidebar: **Work Orders**, **Invoices**, **Equipment**, **Parts**, **Templates**, **Customers**, **Taxes**, **Settings**, **Reports**, and **Back to TMS** at the bottom.
- :fontawesome-solid-people-arrows: Garage customers, garage equipment, garage invoices and garage statements are **separate** from their freight counterparts. Nothing is shared between the two except the tax rates (see [How Garage data differs from Freight](#how-garage-data-differs-from-freight)).
- :fontawesome-solid-building: Everything in the Garage belongs to the **office** you are working in. You only see the work orders, invoices, customers, equipment, parts, templates and settings of your current office.
- :fontawesome-solid-route: The typical flow is: **Customer** :fontawesome-solid-arrow-right: **Equipment** :fontawesome-solid-arrow-right: **Work Order** (Estimate :fontawesome-solid-arrow-right: Approved :fontawesome-solid-arrow-right: In Progress :fontawesome-solid-arrow-right: Completed) :fontawesome-solid-arrow-right: **Invoice** (Draft :fontawesome-solid-arrow-right: Sent) :fontawesome-solid-arrow-right: **Payment** (Partially paid / Paid).
- :fontawesome-solid-user-gear: **Admin**, **Manager** and **Garage** users can use it.

!!! info "What the Garage does not do"
    The Garage is built around work orders and invoicing. It does **not** schedule preventive maintenance or track service due dates, and it has no vehicle import: the only CSV import in the Garage is for **Parts**. Earlier versions of the release notes described these features; they are not part of the current module.

<!-- TODO: Screenshot — The Garage layout: dark sidebar on the left (Work Orders highlighted), top bar with page title, user name and office name, Work Orders list in the main area -->

---

## :fontawesome-solid-bolt: Quick Start

1. In the main menu, click :fontawesome-solid-screwdriver-wrench: **Garage**. The **Work Orders** page opens.
2. Go to **Settings** and fill in **Garage Settings** (labor rate, shop supplies, payment terms, invoice prefix, company details). See [Garage Settings & Taxes](garage-settings-and-taxes.md).
3. Go to **Taxes** and make sure an active tax rate exists for your office.
4. Go to **Customers** :fontawesome-solid-arrow-right: **New Customer**, then **Equipment** :fontawesome-solid-arrow-right: **New Equipment** for the customer's vehicle. (You can also create both on the fly from the work order form.)
5. Go to **Work Orders** :fontawesome-solid-arrow-right: **New Work Order**, pick the **Customer** and **Equipment**, add parts and labor, and click **Create Work Order**. It starts as an **Estimate**.
6. Move it through **Approved**, **In Progress** and **Completed** with the **Mark ...** buttons on the work order page (**Mark Approved**, **Mark In progress**, **Mark Completed**) or the **Move to** section of the row's actions menu (:fontawesome-solid-ellipsis-vertical:).
7. On the completed work order, click **Generate Single Invoice** (**Generate invoice** in the row's actions menu). The invoice opens as a **Draft**.
8. Click **Email Invoice** (or **Mark Sent** if you deliver it another way), then use **Record Payment** when the customer pays.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Garage access |
|------|--------------|
| :fontawesome-solid-user-tie: **Admin** | Full access to every Garage page |
| :fontawesome-solid-user-tie: **Manager** | Full access to every Garage page, for the offices they belong to |
| :fontawesome-solid-screwdriver-wrench: **Garage** | Full access to every Garage page, for the first office on their user account (they cannot switch office). No access to freight pages |
| :fontawesome-solid-headset: **Dispatch**, **Customer Service**, **Accountant**, **Customer**, **Warehouse**, drivers and yard workers | No access. The **Garage** menu item is hidden |

- The add-on must be turned on. If it is off, the **Garage** menu item is hidden for everyone, and opening a Garage page sends you back to the main application.
- The **Garage** role is only offered in the role list when the Garage add-on is on. See [User Roles](user-roles.md) and [People & Invitations](people-and-invitations.md).
- Inside the Garage there are no finer permissions: anyone who can open the Garage can create, edit, invoice, void, record payments and change settings.

**Where to find it:**

- :fontawesome-solid-arrow-right: Main menu :fontawesome-solid-screwdriver-wrench: **Garage** — opens **Work Orders**
- :fontawesome-solid-arrow-right: Garage sidebar :fontawesome-solid-arrow-left: **Back to TMS** — returns to the main UTX Freight application

---

## :fontawesome-solid-table-columns: The Garage Screen

### :fontawesome-solid-bars: The sidebar

The sidebar shows **Garage** with your company name at the top, then these items, in this order:

| Sidebar item | What it opens | Details |
|------|------|------|
| :fontawesome-solid-wrench: **Work Orders** | The work order list with status tabs (**All**, **Estimates**, **Approved**, **In Progress**, **Completed**, **Invoiced**) and **New Work Order** | [Garage Work Orders](garage-work-orders.md) |
| :fontawesome-solid-file-invoice: **Invoices** | The garage invoice list with tabs (**All**, **Draft**, **Sent**, **Unpaid**, **Paid**, **Void**) and **New Invoice** | [Garage Invoices](garage-invoices.md) |
| :fontawesome-solid-truck: **Equipment** | Vehicles and units serviced by the shop (truck, trailer or chassis), with **New Equipment** and a VIN **Decode** button on the form | [Garage Customers & Equipment](garage-customers-and-equipment.md) |
| :fontawesome-solid-gear: **Parts** | **Parts Inventory**, with **Import CSV**, **Export** and **New Part** | [Garage Parts & Templates](garage-parts-and-templates.md) |
| :fontawesome-solid-clipboard-list: **Templates** | **Job Templates** (pre-filled parts and labor you can apply to a work order), with **New Template** | [Garage Parts & Templates](garage-parts-and-templates.md) |
| :fontawesome-solid-users: **Customers** | Garage customers, with **New Customer** | [Garage Customers & Equipment](garage-customers-and-equipment.md) |
| :fontawesome-solid-percent: **Taxes** | **Tax Rates** (GST/QST), with **New Tax Rate** | [Garage Settings & Taxes](garage-settings-and-taxes.md) |
| :fontawesome-solid-sliders: **Settings** | **Garage Settings** for the current office | [Garage Settings & Taxes](garage-settings-and-taxes.md) |
| :fontawesome-solid-chart-bar: **Reports** | A **Dashboard** plus **Profit Report**, **Customer Work Summary** and **Customer Statement** | [Garage Reports](garage-reports.md) |

At the bottom of the sidebar:

- :fontawesome-solid-arrow-left: **Back to TMS** — returns to the main UTX Freight application.
- **Release** — the UTX Freight version number.

The current page is highlighted in blue in the sidebar.

### :fontawesome-solid-window-maximize: The top bar

The top bar shows the page title on the left, and your **name** and the **office** you are working in on the right.

### :fontawesome-solid-mobile-screen: On a phone or small screen

On screens narrower than 1024 pixels the sidebar is hidden:

1. Tap the :fontawesome-solid-bars: menu button at the top left to slide the sidebar in.
2. Tap a sidebar item, or tap :fontawesome-solid-xmark: (or the dimmed area beside the sidebar) to close it.

When you print a Garage page, the sidebar and top bar are left out.

### :fontawesome-solid-circle-question: Confirmation pop-ups

Actions that change a status or remove something (for example **Mark Sent**, **Void**, **Delete**, **Reopen**, removing a payment, or moving a work order to **In Progress**) ask for confirmation in an **Are you sure?** pop-up window. Read the message (it explains what will happen) and click **Yes, proceed** to continue, or **Cancel** to stop.

### :fontawesome-solid-comment-slash: No Feedback button

The **Feedback** button you see in the main UTX Freight application is not available inside the Garage. To send feedback, click **Back to TMS** first (Admins and Managers), or contact your administrator.

---

## :fontawesome-solid-building: Office Scoping

Every Garage record belongs to one office: customers, equipment, parts, job templates, work orders, invoices (and their payments) and Garage settings. The Garage always works in your **current office**, shown in the top bar.

- Lists, searches, reports and statements only include the current office's records.
- New records are created in the current office.
- **Garage Settings** (labor rate, payment terms, invoice prefix and numbering, company details) are kept per office, so each office has its own invoice number sequence.
- **Admins** and **Managers** can change office from the office selector in the main application (with the Multi-Office add-on and more than one office), then click **Garage** again. See [Multi-Office](multi-office.md).
- **Garage** users cannot switch offices. They always work in the first office on their user account. If a Garage user needs to work for another office, ask your administrator to change the offices on their account.

!!! info "Tax rates are the exception"
    The **Taxes** page lists the same tax rates as the main application, from all offices. New tax rates are created in your current office, and a new invoice picks the current office's active tax rate by default. See [Garage Settings & Taxes](garage-settings-and-taxes.md).

---

## :fontawesome-solid-route: Typical Workflow

### :fontawesome-solid-1: Customer and equipment

1. Go to **Customers** :fontawesome-solid-arrow-right: **New Customer**. A garage customer needs at least a first and last name. Add an email address if you want to email invoices and statements.
2. Go to **Equipment** :fontawesome-solid-arrow-right: **New Equipment** and link the unit to the customer. Use **Decode** next to the VIN to fill in vehicle details automatically.

!!! tip "Create them from the work order"
    On the work order form, the green buttons next to **Customer** and **Equipment** open **Quick Create Customer** and **Quick Create Equipment**. Fill in the short form and click **Create & Select**. On the customer list, the work order button on a row starts a new work order for that customer.

### :fontawesome-solid-2: Work order

1. Go to **Work Orders** :fontawesome-solid-arrow-right: **New Work Order**.
2. Search and select the **Customer** (required) and the **Equipment**. Optionally use **Apply Template** to load parts and labor from a job template.
3. Fill in the details (**Description**, **P/O Number**, **Date In**, **Est. Completion**, **Odometer In**, **Assigned Technician**), the parts and labor lines, **Shop Supplies Fee** and **Internal Notes (not shown on invoice)**.
4. Click **Create Work Order**. It starts in **Estimate**. You can print it with **Print Estimate** on the work order page (**Print estimate** in the row's actions menu).

Then move it forward:

| Status | How it gets there | Notes |
|--------|------------------|-------|
| **Estimate** | New work order | Can move to **Approved** or straight to **In Progress** |
| **Approved** | Customer agreed to the estimate | Can move to **In Progress** |
| **In Progress** | Work has started | Moving here **decrements parts inventory** (quantity on hand) for the work order's parts that were picked from **Parts** inventory. Stock never goes below zero |
| **Completed** | Work is finished | The **Date Out** is set to today if it is empty. You can now invoice it, or reopen it with **Reopen Work Order** (**Reopen** in the row's actions menu), which sends it back to **Approved** |
| **Invoiced** | The work order was put on an invoice | Set when the work order is added to an invoice. Still editable while the invoice is a **Draft**; locked once the invoice is sent |

On the work order page the status buttons read **Mark Approved**, **Mark In progress** and **Mark Completed**, and the status badge shows the status in sentence case (for example **In progress**). Each move asks for confirmation first. Statuses only move forward; the only way back is **Reopen Work Order** (Completed to Approved) or taking the work order off its invoice (Invoiced to Completed), which happens when you remove it from a draft invoice, delete the draft invoice or void the invoice.

!!! tip "Billing a completed work order"
    To bill a completed work order, use **Generate Single Invoice** or **Bundle with Other Work Orders**. These create the invoice and set the work order to **Invoiced** for you.

Details: [Garage Work Orders](garage-work-orders.md).

### :fontawesome-solid-3: Invoice

From a **Completed** work order:

- **Generate Single Invoice** (**Generate invoice** in the row's actions menu) creates a draft invoice for this work order only.
- **Bundle with Other Work Orders** (**Bundle with others** in the row's actions menu) opens **New Invoice** for the same customer so you can put several completed work orders on one invoice.

You can also start from **Invoices** :fontawesome-solid-arrow-right: **New Invoice**. Invoice numbers come from the office's **Invoice Prefix** and sequence in **Garage Settings**.

| Invoice status | Meaning |
|----------------|---------|
| **Draft** | Not sent yet. You can **Edit** or **Delete** it, and still edit its work orders |
| **Sent** | Sent to the customer, by **Email Invoice** (which marks a draft as sent) or **Mark Sent**. While no payment is recorded, **Reopen to Edit** returns it to **Draft** |
| **Partially paid** | At least one payment is recorded, but a balance remains |
| **Paid** | Payments cover the full total |
| **Void** | Cancelled. Its work orders go back to **Completed** so you can invoice them again. Voided invoices are excluded from reports |

Details: [Garage Invoices](garage-invoices.md).

### :fontawesome-solid-4: Payment

On a **Sent** or **Partially paid** invoice with a balance due, fill in **Record Payment** (**Amount**, **Method**, **Reference #**, **Date**) and click **Record Payment**. The invoice status updates automatically. A payment cannot be larger than the balance due. **Method** is one of Cash, Check, Credit card, E transfer or Debit. Remove a payment with the :fontawesome-solid-xmark: on its row; this is refused once the invoice is **Paid** (*Cannot remove payments from a fully paid invoice.*).

### :fontawesome-solid-5: Follow-up

Use **Reports** for the profit report, per-customer work summaries and customer statements, including scheduled emails. See [Garage Reports](garage-reports.md).

---

## :fontawesome-solid-code-compare: How Garage Data Differs from Freight

| | Freight (main application) | Garage |
|---|---|---|
| **Customers** | Customer companies on the **Customers** page ([Managing Customers](managing-customers.md)) | Garage customers on the Garage **Customers** page: a person (first and last name) with an optional company name. Not linked to freight customers |
| **Equipment** | Chassis, trailers and trucks you assign to orders ([Equipment](equipment.md)) | Units belonging to garage customers, used on work orders. Not visible on the freight **Equipments** page and cannot be assigned to freight orders |
| **Work** | Orders ([Orders](orders.md)) | Work orders |
| **Invoices** | Freight invoices ([Invoices](invoices.md)) | Garage invoices with their own numbering (**Invoice Prefix**). Never shown on the freight **Invoices** page or in [Aged Receivables](aged-receivables.md) |
| **Payments** | [Invoice Email & Payments](invoice-email-and-payments.md) | **Record Payment** on the garage invoice |
| **Statements** | [Customer Statements](customer-statements.md) and [Automatic Statements](automatic-statements.md) | **Customer Statement** and its own schedule in Garage **Reports** ([Garage Reports](garage-reports.md)) |
| **Taxes** | Tax rates | The same tax rates (shared) |

!!! warning "Tax rates used by garage invoices cannot be deleted"
    Because tax rates are shared, a tax rate that is used by any garage invoice cannot be deleted from the main application either. You see *Cannot delete — used by N garage invoices.* (for example *used by 1 garage invoice.*). On the Garage **Taxes** page, the delete button only appears for rates that no garage invoice uses, and deleting is also refused if a freight invoice uses the rate. Make the rate inactive instead.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see Garage in the menu

!!! info "Solution"
    The Garage add-on must be turned on for your installation, and your role must be **Admin**, **Manager** or **Garage**. Dispatch, Customer Service and Accountant users do not get the Garage. Ask your administrator.

### :fontawesome-solid-users-slash: I can't find a customer, work order or invoice

!!! info "Solution"
    Garage data is per office. Check the office name in the top bar. Admins and Managers can switch office in the main application and reopen the Garage. Also check that you are not looking for a freight customer: freight customers do not appear in the Garage.

### :fontawesome-solid-file-circle-question: My garage invoices are not on the Invoices page or in Aged Receivables

!!! info "Solution"
    That is by design. Garage invoices only appear under **Garage** :fontawesome-solid-arrow-right: **Invoices** and in Garage **Reports**.

### :fontawesome-solid-calendar-xmark: Where do I schedule preventive maintenance or import my vehicles?

!!! info "Solution"
    The Garage does not have maintenance scheduling or a vehicle import. Add equipment one by one (the VIN **Decode** button helps), or create it from the work order with **Quick Create Equipment**. Parts can be imported with **Import CSV** on the **Parts** page.

### :fontawesome-solid-comment: Where is the Feedback button?

!!! info "Solution"
    It is not shown in the Garage. Admins and Managers can click **Back to TMS** and use **Feedback** there.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Getting the most out of the Garage"
    - Fill in **Garage Settings** and an active tax rate for each office **before** creating the first invoice, so invoice numbers, terms and taxes are right from the start.
    - Add an email address to garage customers so you can use **Email Invoice** and emailed statements.
    - Move work orders to **In Progress** only when work actually starts, since that is when parts are taken out of inventory.
    - Use **Bundle with Other Work Orders** to send one invoice for several completed jobs for the same customer.
    - Fix a mistake on a sent invoice with **Reopen to Edit** (only when no payment is recorded) or **Void**, rather than creating a duplicate.
