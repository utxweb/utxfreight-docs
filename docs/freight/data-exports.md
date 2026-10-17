# Data Exports

Every file you can download from UTX Freight in one place: where the button is, who can use it, which filters it follows, what columns it contains and what the file is called.

## :fontawesome-solid-file-export: Overview

UTX Freight has three kinds of downloads:

- :fontawesome-solid-list: **List exports (CSV)**: **Customers**, **Shipper / Receiver**, **Equipments** and open **Orders**. These are **Admin only** and **ignore the filters and search** on the page. Each one exports a fixed set of records.
- :fontawesome-solid-file-invoice-dollar: **Accounting exports**: the **Invoices** export (QuickBooks columns or AR aging detail, Excel or CSV), the per-invoice **EDI 210** file, the **Income by Customer** CSV, customer **statements** (Excel download, PDF or Excel by email), the **Standard Aged Receivables** Excel and the saved **AR Export** Excel files. The **Invoices** export **follows every active filter** and is capped at **20,000 invoices**.
- :fontawesome-solid-screwdriver-wrench: **Garage**: the **Parts Inventory** CSV.

!!! info "What this page does not cover"
    Order documents and POD files are covered in [Order Documents & POD](order-documents-and-pod.md). There is no data export for people (contacts), drivers, users, checks, expenses or warehouse records.

<!-- TODO: Screenshot — Customers page with the green Export button at the top right -->

---

## :fontawesome-solid-bolt: Quick Start

**To export a list (Admin):**

1. Open **Customers**, **Shipper / Receiver**, **Equipments** or **Orders** from the left menu.
2. Click the green :fontawesome-solid-file-csv: **Export** button. On **Orders** it is in the **ACTION & ORDERS** panel.
3. The CSV downloads. It is the same file whatever filter or search is on screen.

**To export invoices:**

1. Go to **Invoices** and filter the list (status tab, search, **INVOICE DATE** range, **AR AGING** option).
2. Read the caption under **EXPORT**, for example *Exports the 1,002 invoices currently listed (All unpaid) — not the whole database.*
3. Pick **QuickBooks columns** or **AR aging detail**, then **Excel** or **CSV**, and click **Export**.

---

## :fontawesome-solid-table-list: All Exports at a Glance

| File | Where | Who can download | Follows on-screen filters? | Format | File name |
|------|-------|------------------|---------------------------|--------|-----------|
| [Customers](#customers-csv) | **Customers** > **Export** | Admin | No | CSV | `<account>-companies-YYYY-MM-DD.csv` |
| [Shippers / Receivers](#shippers-receivers-csv) | **Shipper / Receiver** > **Export** | Admin | No | CSV | `<account>-shippers-receivers-YYYY-MM-DD.csv` |
| [Equipment](#equipment-csv) | **Equipments** > **Export** | Admin | No | CSV | `<account>-equipments-YYYY-MM-DD.csv` |
| [Open orders](#open-orders-csv) | **Orders** > **ACTION & ORDERS** > **Export** | Admin | No | CSV | `<account>-orders-open-YYYY-MM-DD.csv` |
| [Invoices](#invoices-export) | **Invoices** > **EXPORT** panel | Admin, Manager, Accountant | **Yes** (status, search, date range, aging) | Excel or CSV | `<account>-invoices-<status>[-<from>-to-<to>]-on-DDMMYY.xlsx` / `.csv` |
| [EDI 210](#edi-210) | **Invoices** > row :fontawesome-solid-gear: menu > **EDI 210** | Admin, Manager, Accountant (only when EDI invoicing is enabled) | One invoice | CSV | `EDI210_<invoice number>_YYYYMMDD.csv` |
| [Income by Customer](#income-by-customer-csv) | **Reports** > **Income by Customer** > **Export Report** | Users with the **Reports** menu | **Yes** (customer, start and end date) | CSV | `<account>-income_by_customer-<start>-<end>.csv` |
| [Statement (Excel)](#customer-statements) | **Reports** > **Customer Reports** > green Excel button | Users with the **Reports** menu | One customer | Excel | `<Customer name> Statement of Account as of YYYY-MM-DD.xlsx` |
| [Statement (email)](#customer-statements) | **Reports** > **Customer Reports** > **Email** | Users with the **Reports** menu | One customer | PDF or Excel attachment | `Statement of account as of YYYY-MM-DD.pdf` / `.xlsx` |
| [Standard AR Excel](#standard-aged-receivables-excel) | **Reports** > **Aged Receivables (AR)** > **Download Excel** | Users with the **Reports** menu | **Yes** (**As of Date:**) | Excel | `Standard_Aged_Receivables_YYYY-MM-DD.xlsx` |
| [AR Export Excel](#ar-export-excel) | **Reports** > **AR Export** > **Generated Reports** > Download | Users with the **Reports** menu | **Yes** (**Report Period**) | Excel | Starts with `ar-report-`, includes year and month |
| [Garage parts](#garage-parts-csv) | **Garage** > **Parts** > **Export** | Admin, Manager, Garage (Garage add-on on) | No | CSV | `parts_catalog_YYYYMMDD.csv` |

`<account>` is the short account name UTX set up for your company. It is the same at the start of every list export file name. In invoice export file names it is written in lower case with hyphens.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | List CSVs (Customers, Shipper / Receiver, Equipments, Orders) | Invoices export and EDI 210 | Reports downloads (Income by Customer, statements, Standard AR, AR Export) | Garage parts CSV |
|------|------|------|------|------|
| :fontawesome-solid-user-shield: **Admin** | Yes | Yes | Yes | Yes, when the Garage add-on is on |
| :fontawesome-solid-user-tie: **Manager** | No | Yes, for the offices they belong to | Only if UTX has turned on report access for managers on your account (ask UTX support) | Yes, when the Garage add-on is on |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No | Yes, for the offices they belong to | No (no **Reports** menu) | No |
| :fontawesome-solid-headset: **Dispatch** | No | No (no **Invoices** menu) | No | No |
| :fontawesome-solid-screwdriver-wrench: **Garage** | No | No | No | Yes, when the Garage add-on is on |
| :fontawesome-solid-user: **Customer**, **Warehouse**, drivers | No | No | No | No |

!!! warning "List exports are Admin only"
    The **Export** button on **Customers**, **Shipper / Receiver**, **Equipments** and **Orders** is only shown to Admins. If another role opens an export link directly (for example from a link an Admin shared), the download is refused and they are sent back to the dashboard with an access denied message. Ask an Admin to export the file.

See [User Roles](user-roles.md) for the full permission list.

---

## :fontawesome-solid-list: List Exports (CSV)

All four list exports work the same way:

- **Admin only.** The green :fontawesome-solid-file-csv: **Export** button is shown to Admins only.
- **Filters and search are ignored.** The tab, filter buttons and search box on the page do not change the file. Each export always contains the same fixed selection, described below.
- **Not limited to your current office.** None of the four list exports filters by office.
- **CSV only**, comma separated, with a header row. Column headers are written as they appear in the file, for example *Address one* or *Equipment type display name*. They are listed exactly below.
- **File name** ends with today's date as `YYYY-MM-DD`.

### Customers CSV

**Where:** **Customers** > green **Export** button at the top right.
**File:** `<account>-companies-YYYY-MM-DD.csv`
**Contains:** every company in the system: your own company, and active, disabled and deleted customers. Active companies come first (your own company after the other active ones), then by name.

| Column | Content |
|--------|---------|
| **Id** | Company ID number |
| **Name** | Company name |
| **Address one** | Address 1 |
| **City** | City |
| **State** | State/province |
| **Zip** | ZIP/postal code |
| **Country** | Country |
| **Active** | `true` or `false` |

!!! info "No contacts in the customer export"
    The file lists companies only. It has no people, no email addresses and no phone numbers. See [Managing Customers](managing-customers.md).

### Shippers / Receivers CSV

**Where:** **Shipper / Receiver** > green **Export** button at the top right.
**File:** `<account>-shippers-receivers-YYYY-MM-DD.csv`
**Contains:** only shippers/receivers used as the **delivery** location on at least one order **created in the last 12 months**, sorted by company name. Records used only as a pickup location, or not used on an order in the last 12 months, are left out.

| Column | Content |
|--------|---------|
| **Id** | Record ID number |
| **Company name** | Company name |
| **Zone name** | Zone of the linked city, or `N/A` |
| **Address** | Street address |
| **Zip** | Postal code |
| **City name** | Linked city name, or the old free-text city if there is no linked city |
| **Country name** | Country of the linked city, or the old free-text country |
| **Contact info** | The record's contact info text |
| **Active** | `true` or `false` |

See [Shippers & Receivers](shippers-receivers.md).

### Equipment CSV

**Where:** **Equipments** > green **Export** button.
**File:** `<account>-equipments-YYYY-MM-DD.csv`
**Contains:** every equipment record, enabled and disabled, sorted by name, including the equipment of other offices if you have [multiple offices](multi-office.md).

| Column | Content |
|--------|---------|
| **Id** | Equipment ID number |
| **Name** | **Name/Number** |
| **Equipment type display name** | Equipment type, for example *Chassis: 40' - 2 AXLES* |
| **Inspection date** | **Next Inspection Date** |
| **Serial number** | Serial number |
| **Model** | Model |
| **Year** | Year |
| **Plate number** | Plate number |
| **Lessor** | **Lessor or Morgagee** |
| **Status** | **Equipment Status** (for example *Available*, *In garage*, *Flat tire*) |
| **Notes** | Notes |
| **Weight** | **Tare weight** |
| **Weight unit** | Weight unit |
| **Active** | `true` (enabled) or `false` (disabled) |

See [Equipment](equipment.md).

### Open Orders CSV

**Where:** **Orders** > **ACTION & ORDERS** panel > green **Export** button.
**File:** `<account>-orders-open-YYYY-MM-DD.csv`
**Contains:** every order whose status is **new**, **App. Taken** (the **App. Made** tab) or **Dispatched**, the same statuses as the **In Progress** tab, created on or after the **Order Archive Cutoff Date** in [Application Settings](application-settings.md). Completed and cancelled orders are never in this file. Orders of every office are included.

| Column | Content |
|--------|---------|
| **Reference** | Order number |
| **Description** | Order type: *Container Import*, *Container Export*, *Container Transfer*, *Dry Van Move* or *International Export* |
| **Status** | Order status: `new`, `App. Taken` or `Dispatched` |
| **Container number** | Container number |
| **Customer name** | Company of the customer user the order is placed for (**Place the order on behalf of**) |
| **Delivery company name** | Delivery location. For **Container Transfer** orders, the customer's company name |
| **Container status with customer name** | Container status. *Empty at customer*, *Dropped at customer* and *Full at customer* are written with the delivery location name instead of "customer" (for example *Empty at <delivery location>*) |
| **Delivery date** | Delivery date |
| **App info** | Appointment date and time, as `<date> @ <hh:mm AM/PM>` (the time part is empty when no appointment time is set) |
| **Pickup terminal name** | Pickup terminal |
| **Container size name** | Container size |
| **Steamship line name** | Steamship line |
| **Display hazardous** | `HAZMAT` for hazardous orders, otherwise empty |
| **Display equipment name** | Equipment. For **Borrowed** equipment, the chassis number |
| **Return date display** | Return date. For dry van and transfer orders, the closing date |
| **Creation date** | Date the order was created, `YYYY-MM-DD` |
| **Last update** | Date the order was last changed, `YYYY-MM-DD` |

!!! warning "The order export ignores the tabs"
    Picking **Completed**, **New**, any other tab or a search on the Orders page does not change the file. It always contains all In Progress orders. See [Orders](orders.md).

---

## :fontawesome-solid-file-invoice-dollar: Invoices Export

**Where:** **Invoices** > **EXPORT** panel (in the filter bar).
**Who:** Admin, Manager and Accountant. Managers and Accountants only see invoices of the offices they belong to.

Unlike the list exports, the invoice export contains **exactly the invoices currently listed**, across all pages. Every active filter is applied:

- the status tab: **All**, **All Unpaid** (default), **New**, **Invoiced**, **Paid**, **Partially Paid**
- the search text (**Invoice #, Container # or company name**)
- the **INVOICE DATE** range (or a preset: **This Month**, **Last Month**, **This Year**, the previous year shown as its number (for example **2025**), **Last 12 Months**)
- the **AR AGING (DAYS PAST DUE)** option (**Past due**, **30+ days**, **60+ days**, **Not Due**, **0-30**, **31-60**, **61-90**, **91+**)

Only invoices of the **office you are currently working in** are exported. The caption under the **Export** button states the count and filters before you click, for example *Exports the 1,002 invoices currently listed (All unpaid, past due) — not the whole database.*

**To export:**

1. Filter the list until it shows what you want.
2. In **EXPORT**, pick the layout: **QuickBooks columns** or **AR aging detail**.
3. Pick the format: **Excel** (default) or **CSV**.
4. Click **Export**.

!!! warning "20,000 invoice cap"
    The file is built in one go, so an export is capped at **20,000 invoices**. If your filters match more, you are sent back to the list with: *That export covers N invoices, which is more than the 20,000 this can build at once. Narrow it with the invoice date range, then export again.* Use **INVOICE DATE** presets such as **This Year** or **Last 12 Months** and export in batches.

### QuickBooks columns layout

One row per invoice, sorted by invoice date (oldest first).

| Column | Content |
|--------|---------|
| **Invoice** | Invoice number |
| **Invoice Date** | `YYYY-MM-DD` |
| **Customer** | Company name, or `Unknown` |
| **Details** | One entry per order, `<type> - <container>`, separated by commas. Types: **CI** import, **EX** export, **DV** dry van, **TF** transfer, **IX** international export |
| **Amount before sales taxes** | Subtotal |
| **GST Charged** | GST (`0.00` if the invoice has no tax) |
| **QST Charged** | QST (`0.00` if the invoice has no tax) |
| **Amount after sales taxes** | Invoice total with taxes |

### AR aging detail layout

One row per invoice, sorted by due date (oldest first), followed by a **TOTALS** row that adds up every money column. Aging is calculated as of **today**.

| Column | Content |
|--------|---------|
| **Invoice** | Invoice number |
| **Invoice Date** | `YYYY-MM-DD` |
| **Customer** | Company name |
| **Status** | Invoice status |
| **Terms** | Invoice terms |
| **Due Date** | `YYYY-MM-DD` |
| **Days Overdue** | Days past the due date (or the invoice date if there is no due date) as of today. Negative for invoices that are not due yet. Empty for Paid invoices |
| **Aging Bucket** | **Not Due**, **0-30**, **31-60**, **61-90**, **91+**, or **Settled** for Paid invoices |
| **Invoice Total** | Total with taxes |
| **Amount Paid** | Invoice total minus balance |
| **Balance** | Amount still owed |
| **Last Payment** | Paid date of the first payment line recorded on the invoice, or the invoice's paid date if it has no payment lines |
| **Not Due** · **0-30** · **31-60** · **61-90** · **91+** | The balance in the one column matching the invoice's bucket. The others show 0 |

### Invoice export file names

`<account>-<layout>-<status>[-<YYYYMMDD>-to-<YYYYMMDD>]-on-DDMMYY.<xlsx|csv>`

- `<layout>` is `invoices` (QuickBooks columns) or `invoice-aging` (AR aging detail).
- `<status>` is `all-invoices`, `all-unpaid`, `new`, `invoiced`, `paid` or `partially-paid`.
- The date range part is added only when both a start and an end invoice date are set.
- `on-DDMMYY` is today's date.

Example: `acme-invoice-aging-all-unpaid-20260101-to-20261231-on-101026.xlsx`.

In Excel files the worksheet is named after the status tab (for example *All unpaid*). The search text and aging option are not in the file name; check the caption under **Export** before you download.

See [Invoices](invoices.md#exporting-invoices) for the full invoice list.

### EDI 210

**Where:** **Invoices** > a row's :fontawesome-solid-gear: **Actions** menu > :fontawesome-solid-download: **EDI 210**. Only shown when EDI invoicing is enabled on your account (contact UTX support).
**Who:** users who can manage the invoice (Admin, and Managers and Accountants of the invoice's office).
**File:** `EDI210_<invoice number>_YYYYMMDD.csv` (today's date).
**Contains:** one invoice, one row per order on it, with a header row. Dates are `dd/mm/yyyy` and amounts have two decimals and no thousands separator.

| Column | Content |
|--------|---------|
| **DOC TYPE** | Always `INV` |
| **INVOICE-NUMBER** | Invoice number |
| **ITEM NUMBER** | 1, 2, 3… one per order |
| **MSC PO** | The order's **Purchase Order (P.O.)** |
| **TERMS** | Terms in days (`0` for *Due on Receipt*) |
| **INVOICE-DATE** | Invoice date |
| **INVOICE-DUE DATE** | Due date |
| **CURRENCY** | Customer's default currency |
| **BASE RATE** | Order base rate |
| **PRE-PULL**, **STORAGE**, **FUEL** | Always `0.00` |
| **OTHER** | Total of all the order's charges |
| **INVOICE TOTAL** | Invoice total with taxes (repeated on every row) |
| **WAYBILL-NUMBER** | Order reference number |
| **WAYBILL-DATE** | Order waybill date |
| **VESSEL** | Vessel |
| **VOYAGE NUMBER** | Voyage |
| **UNIQUE-SHIPMENT-ID** | Container number |
| **EQUIP-INITIAL** | First four characters of the container number |
| **DESTINATION  - UNLOC** | UN/LOCODE of the delivery location |
| **NOTES** | Always `*` |

These columns are in the file but always empty: **BOND CHARGES**, **CHASSIS DETENTION**, **DROP CHARGES**, **GENSET COST**, **OVERWEIGHT**, **SPECIAL PERMIT**, **WAITING TIME COST**, **DEAD RUN**, **OVERDIMENTION**, **SCALING**, **HAZMAT**, **RESERVATION FEE**, **EQUIP-NUMBER**, **ORIGIN-UNLOC**, **ORIGIN-PROV**, **DESTINATION-PROV**, **WEIGHT**, **UOM**, **EQUIP-SIZE**, **EQUIP-TYPE**.

!!! warning "Fuel is in OTHER"
    The EDI file does not split charges by type. All of an order's charges, including fuel surcharge, are added together in **OTHER**, and **FUEL** stays at `0.00`.

---

## :fontawesome-solid-chart-bar: Report Exports

These downloads are on the **Reports** menu, which Admins have. Managers have it only when UTX has turned on report access for managers on your account (ask UTX support). Accountants and Dispatch do not. All of them work on the customers of the **office you are currently in**. See [Reports](reports.md).

### Income by Customer CSV

**Where:** **Reports** > **Income by Customer** > **Export Report**.
**File:** `<account>-income_by_customer-<start date>-<end date>.csv`
**Follows:** the **Customer** (or **[ALL CUSTOMERS]**), **Start date** and **End date** in the form. The form opens with last month's first and last day filled in. On multi-office accounts, only invoices of the current office are counted.

| Column | Content |
|--------|---------|
| **Customer** | Customer name in capitals |
| **Invoices** | Number of the customer's invoices dated in the range |
| **Completed Orders** | Number of orders on those invoices |
| **All Income** | Total of those invoices, taxes included |
| **Paid Income** | Amount paid on those invoices |

A **TOTALS** row closes the file. Amounts have two decimals and a comma thousands separator (for example `1,234.56`) and no currency label. Only customers with at least one invoice in the range are listed.

!!! info "Summary only"
    The CSV has one line per customer. The invoice and order drill-down on the page is not exported. Rows are not sorted by **All Income** as they are on screen.

### Customer statements

**Where:** **Reports** > **Customer Reports**, one row per customer.

| Button | What you get |
|--------|--------------|
| Green :fontawesome-solid-file-excel: button | Downloads `<Customer name> Statement of Account as of YYYY-MM-DD.xlsx` (one sheet, **Statement**) |
| **Print** | Opens the statement in a new browser tab. It is a web page, not a file: use your browser's print or *Save as PDF* |
| **Email** | Sends the statement as an attachment: `Statement of account as of YYYY-MM-DD.pdf`, or `.xlsx` when the customer's **Default Statement Format** is **Excel (.xlsx)** |

A **PDF** file is only produced as the email attachment. There is no PDF download button.

Rows, sections and the statement layout are described in [Customer Statements](customer-statements.md#what-the-statement-contains).

### Standard Aged Receivables Excel

**Where:** **Reports** > **Aged Receivables (AR)** > :fontawesome-solid-file-excel: **Download Excel**.
**File:** `Standard_Aged_Receivables_YYYY-MM-DD.xlsx` (the **As of Date:**), one sheet named `Standard AR YYYY-MM`.
**Follows:** the **As of Date:** shown on the page.

| Column | Content |
|--------|---------|
| **Customer** | Customer name |
| **Not Yet Overdue** | Balances due after the as-of date |
| **30 or Less** | 0 to 30 days past due |
| **31 to 60** | 31 to 60 days past due |
| **61 to 90** | 61 to 90 days past due |
| **91 or More** | More than 90 days past due |
| **Total Unpaid** | Sum of the bucket columns |

One row per customer with a balance, then a **TOTALS** row. The invoice counts and *overdue* line shown on screen are not in the file. See [Aged Receivables](aged-receivables.md#standard-aged-receivables).

### AR Export Excel

**Where:** **Reports** > **AR Export** > **Generated Reports** > green :fontawesome-solid-file-excel: button in the **Download** column (only when **Status** is **Ready**).
**File:** name starts with `ar-report-` and includes the report year and month. One sheet named `AR Report YYYY-MM`.
**Follows:** the **Report Period** month you generated. The file covers the 12 months ending on that month's last day.

| Column | Content |
|--------|---------|
| **Customer** | Customer name |
| **Invoices** | Invoices dated in the 12-month window |
| **Completed Orders** | Orders on those invoices |
| **All Income** | Total of those invoices, taxes included |
| **AR As Of YYYY-MM-DD** | Unpaid balance on the as-of date of the invoices dated in the 12-month window (older unpaid invoices are not counted) |
| **30 days** · **60 days** · **90 days** · **90+ days** | That unpaid balance split by days since the **invoice date**: 0 to 30, 31 to 60, 61 to 90, more than 90 |

Every non-deleted customer of the office (active or disabled) gets a row, even with no invoices, followed by a **TOTALS** row. The file is saved, so downloading it again gives the same figures until you **Regenerate**. See [Aged Receivables](aged-receivables.md#performance-report-ar-export).

---

## :fontawesome-solid-screwdriver-wrench: Garage Parts CSV

**Where:** **Garage** > **Parts** > **Parts Inventory** > **Export**, or **Download Current Catalog as CSV Template** on the **Import CSV** page.
**Who:** Admin, Manager and Garage users, when the Garage add-on is on.
**File:** `parts_catalog_YYYYMMDD.csv`
**Contains:** the **active** parts of your **current office**, sorted by name. Disabled parts are left out. The **Active** / **Low Stock** / **Disabled** tab and the search box do not change the file.

Columns (lower case, the same headers the import expects): `name`, `sku`, `category`, `description`, `purchase_price`, `charge_price`, `quantity_on_hand`, `reorder_point`.

See [Garage Parts & Templates](garage-parts-and-templates.md#exporting-parts).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the Export button on Customers, Shipper / Receiver, Equipments or Orders

!!! info "Solution"
    These four exports are Admin only, and the button is hidden for every other role. Ask an Admin to download the file. Opening the export link directly as a non-Admin sends you back to the dashboard with an access denied message.

### :fontawesome-solid-filter: My customer, equipment or order export ignored my filter

!!! info "Solution"
    That is expected. The four list exports always contain the same fixed set of records, whatever tab, filter or search is on screen. Open the CSV in a spreadsheet and filter it there. Only the **Invoices** export follows the filters on the page.

### :fontawesome-solid-user-slash: A shipper/receiver is missing from the export

!!! info "Solution"
    The shipper/receiver export only includes records used as the **delivery** location on an order created in the last 12 months. Pickup-only locations and locations not used recently are left out.

### :fontawesome-solid-box-archive: Completed orders are not in the order export

!!! info "Solution"
    The order export only contains In Progress orders (**new**, **App. Taken**, **Dispatched**) created on or after the **Order Archive Cutoff Date**. For invoiced work, use the **Invoices** export or the [Reports](reports.md).

### :fontawesome-solid-ban: The invoice export says it covers more than 20,000 invoices

!!! info "Solution"
    Narrow the list with an **INVOICE DATE** range (for example **This Year** or **Last 12 Months**) and export in several batches. The status tab, search and aging options also reduce the count shown in the caption under **Export**.

### :fontawesome-solid-file-invoice: My invoice export has more (or fewer) rows than I expected

!!! info "Solution"
    The export uses every active filter and covers all pages, while the screen shows one page at a time. Read the caption under **Export**, it lists the count and filters. Also check you are in the right office: the export only covers the office you are currently working in.

### :fontawesome-solid-download: I don't see EDI 210 in the invoice menu

!!! info "Solution"
    **EDI 210** only appears when EDI invoicing is enabled for your account. Contact UTX support to have it turned on.

### :fontawesome-solid-file-pdf: How do I download a statement as PDF?

!!! info "Solution"
    Click **Print** on **Customer Reports** and use your browser's *Save as PDF*. A PDF file is only generated as the email attachment (manual or [automatic](automatic-statements.md)) for a customer whose **Default Statement Format** is **PDF Format**.

### :fontawesome-solid-chart-bar: I can't find Income by Customer, statements or the AR files

!!! info "Solution"
    These are under the **Reports** menu. Admins have it. Managers have it only if UTX has turned on report access for managers on your account (ask UTX support). Accountants can use the **AR aging detail** layout of the **Invoices** export instead.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Best Practices"
    - Before exporting invoices, set an **INVOICE DATE** range. It keeps you under the 20,000 cap and puts the period in the file name.
    - Use **AR aging detail** with **All Unpaid** for collections work, and **QuickBooks columns** for importing into your accounting software.
    - Keep the downloaded **Standard_Aged_Receivables** file as your record for a closed month. The on-screen report is recalculated every time.
    - List exports are a full snapshot. Filter and sort them in your spreadsheet rather than expecting the page filters to apply.
    - Treat exported files as confidential: they contain customer names, addresses and amounts.
