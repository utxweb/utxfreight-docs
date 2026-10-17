# Changelog

All notable changes to UTX Freight are documented here. Releases are listed newest first. Each release starts with its main features, followed by the smaller patch releases that shipped after it.

!!! info "Current version: 3.12.19 (released 2026-09-17)"
    The version number has three parts: **major.minor.patch**. A new minor release (for example 3.12.0) brings new features. Patch releases (3.12.1, 3.12.2, ...) bring fixes and smaller improvements. Some patch releases contain only internal maintenance and have no visible change; they are grouped as **Maintenance** below. Release numbers and dates are those recorded in the application when each change shipped; releases 3.0 to 3.10 were re-checked against them, and entries that were filed under the wrong release or described features that do not exist are marked **Corrected entry**.

---

## Version 3.x

### Release 3.12 — Invoice Filtering & Consignee Visibility

**Released:** 2026-08-20 (3.12.0) · **Latest patch:** 3.12.19 (2026-09-17)

#### Invoices

- **Exports now match your filters** — the **Export** button downloads exactly the invoices currently listed. Previously the export ignored the status tab and search on screen and only used a year drop-down, so, for example, exporting while on **Paid** still returned every invoice of that year
- **See what you are exporting before you click** — the **EXPORT** panel states the count and the active filter, for example *"Exports the 1,002 invoices currently listed (All unpaid) — not the whole database."*
- **Two export layouts** — choose **QuickBooks columns** for accounting import, or the new **AR aging detail** layout for collections and month-end review. Both download as **Excel** or **CSV**
- **Invoice date range** — the **INVOICE DATE** card filters the list to a **from/to** range, with one-click presets: **This Month**, **Last Month**, **This Year**, the previous calendar year (labelled with the year number, for example **2025**), and **Last 12 Months**
- **AR AGING card** — the **AR AGING (DAYS PAST DUE)** card filters by how late an invoice is, using open-ended rollups (**Past due**, **30+ days**, **60+ days**) or exact bands (**Not Due**, **0-30**, **31-60**, **61-90**, **91+**). The bands split the unpaid ledger the same way the [Aged Receivables](aged-receivables.md) report does. Invoices marked Paid carry no aging
- **Past-due tabs replaced** — the old **Past Due**, **Past Due (30+ days)** and **Past Due (60+ days)** status tabs are gone. The status tabs are now only **All**, **All Unpaid**, **New**, **Invoiced**, **Paid** and **Partially Paid**; everything about how old an invoice is lives in the **AR AGING** card
- **Days past due and Balance in the list** — the **Due date** column now shows a colour-coded aging badge (**Not Due**, **0-30**, **31-60**, **61-90**, **91+**) under the due date, and a new **Balance** column shows the outstanding amount with the total paid below it, so you no longer have to open the invoice
- **Filters combine instead of replacing each other** — status, search, invoice date, and aging all narrow the same list. Each active filter appears as a removable chip in the search bar, with **Clear All** to reset
- **A cleaner invoice table** — folded from 15 columns to 8 by pairing each value with its closely related detail (invoice with its date, balance with total paid, status with sent date). Nothing was removed
- **Consistent sorting** — past-due views now sort newest-first like every other tab, instead of oldest-first
- **Large export guard** — an export of more than 20,000 invoices is refused with a message asking you to narrow it with the invoice date range, rather than timing out
- Fixed an error when exporting an invoice that had no company assigned, and a company drill-down that led to an empty list

See [Invoices](invoices.md) for how to use the filters and export.

!!! info "Your saved links still work"
    Bookmarked links to the old **Past Due**, **Past Due (30+ days)** and **Past Due (60+ days)** tabs continue to work — they now open the matching **AR AGING** rollup (**Past due**, **30+ days**, **60+ days**) and return the same invoices they always did.

#### 3.12.x patch releases

| Version | Date | Change |
|---------|------|--------|
| **3.12.1** | 2026-08-21 | **Consignee order visibility (Customer Portal).** A shipper/receiver record can be linked to a customer account so that account's users get **read-only** visibility of orders delivered to that location, including orders placed by a different customer (for example another freight forwarder). Link it from **Shipper / Receiver** :fontawesome-solid-arrow-right: edit form :fontawesome-solid-arrow-right: **Portal Access — Consignee Link** :fontawesome-solid-arrow-right: **Linked Customer Account**. Only users with the **Customer** role on the linked account get this access; they can view the orders and open their documents, but not edit them. Consignee users see a **Consignee view:** banner on the Orders page, which also states that pricing details are not shown. The **Shipper / Receiver** list gains a **Linked** filter and a **Linked Account** column. See [Shippers & Receivers](shippers-receivers.md) and [Customer Portal](customer-portal.md). |
| **3.12.1** | 2026-08-21 | **Orders header total.** The **Total** figure in the Orders header now sums only the three badges beside it (**New Orders**, **App. Made**, **Dispatched**). It previously also counted Completed orders. |
| **3.12.2** | 2026-08-23 | **Garage: edit work orders until the invoice leaves the shop.** Work orders can now be edited at every stage, including **In Progress** and **Completed** (you no longer need **Reopen Work Order** just to fix a line). A work order attached to a **Draft** invoice can still be edited; the Draft invoice is recalculated after you save and the new total is shown. Editing locks only once the invoice is no longer a Draft (for example **Sent** or **Paid**); a Sent invoice with no payments can be returned to Draft with **Reopen to Edit**. The customer of an invoiced work order cannot be changed. Removing a part from a work order on a Draft invoice returns it to stock. See [Garage Work Orders](garage-work-orders.md). |
| **3.12.3** | 2026-09-04 | **Garage: better work order search.** The work order search now also matches the attached equipment (unit / chassis number, VIN, plate, make, model, type) and the customer's company name. When nothing matches, the page says which term found nothing and offers **Clear search**. |
| **3.12.4** | 2026-09-11 | **Customer page shows the country.** Opening a customer (company) page directly no longer shows an error; the page shows the company's country. |
| **3.12.5** | 2026-09-11 | Maintenance. |
| **3.12.6** | 2026-09-11 | **Statement send and refresh fixed.** Sending a statement or refreshing a customer row from the customer list no longer shows an error; the row repaints with the correct invoice counts. |
| **3.12.7** | 2026-09-11 | **Container tracking run no longer aborts on concurrent edits.** If a dispatcher saves an order while the Port of Montreal (Termont) tracking update is filling in that order's fields, the update now retries that order instead of skipping every remaining container in the run. Values the dispatcher just saved are kept. |
| **3.12.8** | 2026-09-11 | **Tracking popup direct links.** Opening the container tracking popup's address directly (new tab, pasted link, bookmark) now sends you back with the message *"Container status opens in a popup. Click the container number in the list to see it."* instead of an error page. |
| **3.12.9** | 2026-09-11 | **Mobile password reset.** Resetting a password on a phone now shows the reset form (with any error message) instead of an error page. |
| **3.12.10** | 2026-09-12 | **Stability fixes.** Fixed several pages that showed an error page to signed-out visitors. |
| **3.12.11 – 3.12.13** | 2026-09-12 to 2026-09-15 | Maintenance. |
| **3.12.14** | 2026-09-15 | **Broken icons fixed.** The inline-edit loading spinner, the icons in the container number search, and the admin header background image now load correctly. |
| **3.12.15** | 2026-09-15 | **Zone rates fixed.** Editing a zone rate and enabling or disabling a zone on the Zones page work again (they showed an error). See [Zones & Cities](zones-and-cities.md). |
| **3.12.16** | 2026-09-15 | Maintenance. |
| **3.12.17** | 2026-09-16 | **Getting Started checklist.** Admins and Managers get a setup checklist that checks the system and shows, step by step, what is still missing before you can raise a correct first invoice (zone prices, cities in zones, terminal fees, tax numbers, fuel surcharge, and so on). Exactly one step is marked **Do this next**. For Admins and Managers the side menu shows a **Getting started** item (**Setup check** on an account that already invoices, **Setup complete** when every step is done). Also in this release: users allowed to change rates can edit a terminal's default rate in place on the **Terminals** list, and the **Cities** list has a **Shipping** filter for cities where at least one order has been delivered. See [Setup Checklist](setup-checklist.md). |
| **3.12.18** | 2026-09-16 | Maintenance. |
| **3.12.19** | 2026-09-17 | Current version. Maintenance. |

---

### Release 3.11 — Compound Search & Filtering

**Released:** 2026-04-12 (3.11.0) · **Latest patch:** 3.11.31 (2026-08-18)

#### Orders

- **Compound search and filters** — combine any mix of status tab, order type, container status, terminal, search text, and tags in a single view. Filters chain independently rather than overriding each other
- **New filter interface** — full-width search bar with inline filter chips, a 3-column card grid for **ORDER TYPE** / **CONTAINER STATUS** / **TERMINAL**, and a **Clear All** button
- **Filter chips** — each active filter appears as a removable badge; click the × to drop one dimension while keeping the rest
- **Order Type filter** — filter orders by type (Import, Export, Transfer, etc.) as a distinct dimension from container status
- **N/A (not set)** option in the **CONTAINER STATUS** card for orders where a container status has not been set
- Shareable, bookmarkable filter URLs — the address bar reflects the exact filter state

See [Orders](orders.md).

#### 3.11.x patch releases

**Freight**

| Version | Date | Change |
|---------|------|--------|
| **3.11.1 – 3.11.5** | 2026-04-12 to 2026-04-13 | **Search fixes.** Removing a filter chip while a search is active now does what you expect (the × no longer appears to do nothing, and removing a status chip no longer jumps back to the in-progress list). |
| **3.11.6** | 2026-04-15 | **Search links and sorting.** Links that open a search on the Orders page (after duplicating or creating an order, and from container tracking and alert pages) open the matching search result again instead of the default list. Freshly duplicated orders appear at the top. |
| **3.11.8** | 2026-05-08 | **Dispatch shows all container status buttons' orders.** The Dispatch page now includes **New** orders that have any of the container statuses on its filter buttons (Pre-Pull, Dropped / Empty / Full at customer, Empty / Full at yard, Empty / Full at Eco, Inbound), even when they have no dates yet. Previously only Pre-Pull, Empty at yard and Full at yard were included. See [Dispatch](dispatch.md). |
| **3.11.9** | 2026-05-08 | **Cleaner order history.** The order **History** no longer shows internal system entries. |
| **3.11.10** | 2026-05-12 | Changes to website pages and document types now show immediately, instead of only after the next update of the app. |
| **3.11.17** | 2026-05-21 | **List page sizes.** Lists whose page size is set above 30 rows now actually use it; for example **Shipper / Receiver** now shows 50 rows per page instead of 30. **Orders** and **Customers** stay at 30 per page. |
| **3.11.18** | 2026-05-21 | **Copy container number.** A copy icon (:fontawesome-solid-copy:) beside the container number on the Dispatch and Orders rows copies the plain number to the clipboard, so it pastes as text (not as a link) into chat apps and email. |
| **3.11.19** | 2026-05-26 | **Invoice search fixed.** Searching invoices (by container number or company name) no longer shows an error. |
| **3.11.20** | 2026-06-16 | **Equipment notes and new statuses.** Equipment has a new **Notes** field, shown as a column on the Equipment list, editable inline and on the edit form, and included in the CSV export. Two new equipment statuses: **Parked at SAAQ** and **Expired**; both count as out of service. The note of a chassis is shown in the **Assign Equipment** window so dispatchers see it when picking a chassis. See [Equipment](equipment.md). |
| **3.11.21 – 3.11.22** | 2026-06-19 | **Standard Aged Receivables fixes.** The Standard Aged Receivables report (**Reports** :fontawesome-solid-arrow-right: **Aged Receivables (AR)**) now correctly reconstructs what was outstanding on a past as-of date (it previously showed nothing for invoices that were open then but have since been paid), and loads quickly for offices with very large invoice histories. See [Aged Receivables](aged-receivables.md). |
| **3.11.27** | 2026-08-04 | **Select All in the invoice order picker.** On the new and edit invoice forms, a **Select All** / **Deselect All** button above the order list selects the orders the current filter shows, with a counter of how many are selected. On the edit form, **Deselect All** asks for confirmation before clearing orders already on the invoice. See [Creating Invoices](creating-invoices.md). |
| **3.11.28** | 2026-08-17 | **Invoice save no longer fails silently.** Saving an invoice that includes an order with incomplete data (for example a blank container number) used to do nothing, with no error. The invoice now saves. **Select All** is now disabled, with an explanation, until a company is chosen, so it can no longer put several companies' orders on one invoice. |
| **3.11.29** | 2026-08-18 | **Invoice counters restored.** The invoice list again shows each invoice's total and order count, and moving an order off an invoice correctly lowers that invoice's total. |
| **3.11.30** | 2026-08-18 | **Order row actions report rejected saves.** Reset, go back one step, remove signature and change equipment on the Orders and Dispatch rows now show a red **Order not updated!** message with the reason when the order cannot be saved, and the row keeps its real status. Previously they showed success while nothing was saved. |

**Garage add-on**

| Version | Date | Change |
|---------|------|--------|
| **3.11.7** | 2026-04-30 | **Customer-aware equipment selector and quick create.** On the work order form, the equipment search lists the selected customer's equipment as soon as you click in it, and each result shows its owner. The **+** button opens **Quick Create Equipment** so you can add a vehicle without leaving the form; it is linked to the work order's customer. The chosen equipment shows as a chip with a **Change** button. |
| **3.11.11** | 2026-05-16 | **One invoice for several work orders.** Use **Bundle with Other Work Orders** (or **Bundle with others** in the row menu) to put several work orders of the same customer on one invoice; each work order's completion date appears on the invoice. Also: an optional **Accountant Email** on garage customers, CC'd on invoice and work summary emails, and a grouped row-actions menu (**View**, **Move to**, **Actions**) on the Work Orders list. See [Garage Invoices](garage-invoices.md). |
| **3.11.12** | 2026-05-16 | Garage invoice and work summary emails are sent from your company's accountant email address, which fixes delivery failures on some mail servers. |
| **3.11.13 – 3.11.14** | 2026-05-16 to 2026-05-18 | **Email confirmations list all recipients.** The confirmation before sending an invoice or work summary, and the message after sending, list every recipient, including the accountant CC. |
| **3.11.23** | 2026-06-20 | **Customer statement of account.** **Reports** :fontawesome-solid-arrow-right: **Customer Statement** shows a customer's unpaid invoices split into **Overdue** and **Not Yet Due**, with **Print / PDF**, an **Email to** button, **Send Test Email**, and **Automatic Statement Emails** (weekly or monthly). The confirmation dialogs on statement and work summary emails now appear before sending, and a failed send is reported. See [Garage Reports](garage-reports.md). |
| **3.11.24** | 2026-07-24 | **Pre-tax discount and Reopen.** An invoice can carry one **Discount**, a percentage or a dollar amount, applied before taxes. A **Sent** invoice with no payments can be returned to Draft with **Reopen to Edit**, so you no longer have to void it to fix it. |
| **3.11.25** | 2026-07-24 | **P/O number on work orders.** Work orders have a **P/O Number** field. It shows on the work order, the estimate print, and in each work order's header on the invoice (page, print and email). |

!!! info "Not listed"
    Patch releases not listed above (3.11.15, 3.11.16, 3.11.26 and 3.11.31) contain internal or maintenance changes only.

---

### Release 3.10 — Multi-Office Shared Resources

**Released:** 2026-03-29 (3.10.0) · **Latest patch:** 3.10.15 (2026-04-11)

#### Multi-Office Addon (Pro Module)

- Share **customers, shippers / receivers, drivers, equipment, terminals** and the other lists across offices, while **orders, invoices and checks** stay separate per office
- **Transfer to Office** — move an order that is not invoiced to another office from the order's caret menu; the order shows a **Transferred** badge in the receiving office
- The current office is shown in the top bar, page headers and on mobile, and the office switcher shows which office you are in
- Reports and the container tracking digest are calculated per office

See [Multi-Office](multi-office.md).

#### Garage Addon (Pro Module)

- **Reopen completed work orders** — **Reopen Work Order** moves a completed work order back to **Approved**. (Since 3.12.2 you can edit a completed work order directly; reopening is only needed for work that is not actually finished.)
- **Customer work summary reports** — service history per customer, with email
- **Void and delete invoices** — void an invoice to reverse it (its work orders are detached from it) or delete it, with confirmation prompts
- Clearer **confirmation dialogs** before destructive actions (void, delete, reopen)
- Layout fixes to **PDF invoices and estimates**, due date recalculated when payment terms change, and all taxes shown in the Garage as in Freight

#### Orders

- Resetting an order back to **New**, or going back one step to **New**, now clears the appointment fields

#### Email & Notifications

- Restored **multiple recipients** — emails can again be sent with several To, CC and BCC addresses
- **Feedback notifications** — new feedback submitted from the app is emailed to UTX support
- **Notification preferences respected** — the invoicing reminder emails sent to admins, accountants and managers now go only to users whose **Email Notifications** box is checked on their person record. Container tracking alert digests still go to everyone subscribed to them

#### General

- **File upload limit** — documents, PODs and signatures are limited to 20 MB per file
- Email addresses are validated on the POD and invoice email forms (a display-name format such as *Name &lt;email&gt;* is accepted)

!!! info "Corrected entry"
    Earlier versions of this changelog listed "office-specific customer and equipment management" and an "improved archive experience" in this release. Customers and equipment are shared between offices, and no archive feature is available in the current version.

---

### Release 3.9 — Monthly Fuel Surcharges

**Released:** 2026-03-27 (3.9.0) · **Latest patch:** 3.9.5 (2026-03-28)

#### Fuel Surcharge

- Replace the weekly fuel surcharge system with a **monthly system** — set one rate per month instead of per week
- **Quick Set** form to create or update rates for any month, with a **Copy Fwd** option to copy the rate forward
- **Custom company rates** — pick a customer in the Quick Set form to override the general rate for that customer
- **Exempt customers** from fuel surcharges with the **Exempt from Fuel Surcharge** checkbox on the customer profile
- **Recalculate** button that opens a preview of how each open order's fuel charge will change before you apply it
- **Stale charge detection** — red indicators when exempt customers still have fuel charges
- **Missing rates warning** banner for months without a defined rate
- Legacy weekly rates preserved for historical orders

See [Fuel Surcharge](fuel-surcharge.md).

---

### Release 3.8 — Tracking Health, Alert Emails & Garage

**Released:** 2026-03-18 (3.8.0) · **Latest patch:** 3.8.16 (2026-03-27)

#### Garage Addon (Pro Module) — first release (2026-03-26)

- A **repair-shop module** for work orders and invoicing: keep garage customers and their equipment, write work orders for repairs and service, and turn finished work into invoices
- **Work orders** with parts and labor lines, moving through **Estimate**, **Approved**, **In Progress**, **Completed** and **Invoiced**
- **Templates** (canned jobs) — pre-defined lists of parts and labor for common jobs
- **CSV import** for the **Parts** catalogue (the only CSV import in the Garage)
- **VIN decoder** — the **Decode** button on the equipment form fills in vehicle details from the VIN
- **Invoice email** with PDF attachment and company logo
- **Tax management** with per-line taxable toggles
- Equipment search by unit number, make, model, VIN or license plate

See [Garage Overview](garage-overview.md).

!!! info "Corrected entry"
    Earlier versions of this changelog placed the Garage in release 3.6 and said it tracks upcoming maintenance and imports vehicle data from CSV. It shipped in 3.8 and does neither.

#### Container Tracking & Alerts

- **Integration Health** cards show, for each tracking source, how many containers were submitted, how many the source found, and how many orders were updated, so a low hit rate is visible (3.8.0)
- Blank, **N/A** and duplicate container numbers are no longer sent to the tracking sources, and spaces around container numbers are removed first
- **Stale alerts suppressed** — the Alerts dashboard shows the last 90 days by default (**Show all time** shows everything), hides alerts for orders that are no longer in progress, and containers that have already left are not alerted again
- **Alert email subscriptions** — choose which alert types you receive by email; the digest email gains an *Action Required* section, order references and a link to the dashboard
- The **LFD Approaching** count now matches the **Upcoming Last Free Days** table

See [Container Alerts](container-alerts.md).

#### Orders

- **Order duplication** no longer offers to copy drivers, equipment or pickup number — they are always reset. **Copy Reference Number** is optional and checked by default; **Copy Container Status** is optional and unchecked by default. See [Order Duplication](order-duplication.md)
- The **Send invoice to customer**, Quick Edit and invoice edit windows no longer close when you click outside them, so you do not lose what you typed

#### Email

- A second email delivery service can be configured per account to improve delivery reliability

!!! info "Corrected entry"
    Earlier versions of this changelog described release 3.8 as "Order Archival & Housekeeping" (stale order detection, bulk archive, type-to-confirm delete, restore). These features are not available in the current version. The only related setting is the order cutoff date that hides old orders from the order lists (see Version 2).

---

### Release 3.7 — Container Tracking, Alerts & User Feedback

**Released:** 2026-02-21 (3.7.0) · **Latest patch:** 3.7.28 (2026-03-18)

#### Container Tracking (2026-03-18)

- **Container tracking** across three terminal sources: CN Rail, Termont (Port of Montreal), and MGT (Racine/Cast). Each source is a separate add-on
- On the Dispatch page, Termont and MGT share one **Port Tracking** button, and the MGT source is named **MGT (Racine/Cast)** everywhere
- **Automatic updates** from each enabled terminal source. How often the update runs is set by UTX, and only the sources whose add-on is turned on are polled
- More reliable updates: timeouts and automatic retries when a terminal source does not answer
- Container numbers in the **Upcoming Last Free Days** table open the tracking window

See [Container Tracking](container-tracking.md).

#### Container Alerts (2026-03-18)

- **Alerts Dashboard** with summary cards for **Pickup Ready**, **Customs Released**, **LFD Approaching**, and **Departed**
- **Upcoming Last Free Days (Next 7 Days)** table with color-coded urgency rows
- **Integration Health** cards — one per enabled source, showing whether its data is fresh
- **Daily digest email** summarizing new tracking alerts from all sources

See [Container Alerts](container-alerts.md).

#### General

- **User feedback** — the **Feedback** button in the top bar opens a form to send feedback from any page, with a category and a description (at least 10 characters). The page address and browser details are captured automatically
- **Recover deleted invoices** — UTX support can restore a deleted invoice together with its orders (contact UTX support) (3.7.0)

#### Fuel Surcharge (weekly system, replaced in 3.9)

- Per-customer weekly rates, customer exemptions with warnings when an exempt customer still has fuel charges, and a help box on the fuel schedule page. These carried over into the monthly system in 3.9

---

### Release 3.6 — Order Duplication & Orders Legend

**Released:** 2026-02-09 (3.6.0)

#### Orders

- The **duplication window** lists the fields that are copied and the fields that are always reset (invoice, status, container number, documents, signatures, manual charges)
- **Legend** button on the Orders page opens a window explaining the icons and badges on order rows

See [Order Duplication](order-duplication.md).

---

### Release 3.5 — Standard Aged Receivables

**Released:** 2026-02-05 (3.5.0) · **Latest patch:** 3.5.2 (2026-02-05)

#### Reports

- **Standard Aged Receivables** — a GAAP-style snapshot of outstanding receivables as of a chosen date, aged on invoice due dates, alongside the existing Performance report (now in the menu as **AR Export**)

See [Aged Receivables](aged-receivables.md).

---

### Release 3.4 — Invoice Payment Audit

**Released:** 2026-02-03 (3.4.0)

#### Invoices

- **Audit Payments** (on the Invoices page) lists invoice discrepancies, such as payment mismatches

---

### Release 3.3 — Aged Receivables Report

**Released:** 2026-01-28 (3.3.0) · **Latest patch:** 3.3.6 (2026-02-01)

#### Reports

- **Aged Receivables** report (the Performance report, now in the menu as **AR Export**: income and sales activity for the 12 months ending on the selected date, with outstanding invoices)
- Faster **Income by Shipper** and Aged Receivables reports

See [Aged Receivables](aged-receivables.md).

---

### Release 3.2 — Container Statuses, QuickBooks Export & Terminal Filters

**Released:** 2025-05-31 (3.2.0) · **Latest patch:** 3.2.9 (2026-01-28)

#### Dispatch

- New **container status management** page (2025-05-31). See [Container Statuses](container-statuses.md)
- **Inbound** container status filter and **vessel cutoff date** on the Dispatch page (2025-07)

#### Invoices

- **Due on Receipt** invoice term option (2025-10)
- **QuickBooks invoice export** for accounting import (2026-01-25)

#### Orders

- New terminal filters on the Orders page: **CP**, **Racine**, **Cast** (2026-01-27). Since 3.11 these are in the **TERMINAL** filter card

#### General

- **Account suspension notice** — when UTX suspends an account, a **System Notice: Account Suspended** banner is shown and creating new orders is blocked

!!! info "Corrected entry"
    Earlier versions of this changelog listed a **From Email** filter on the Orders page and appointment and completed dates on invoices in this release. Neither exists in the current version. Aged Receivables (3.3), invoice discrepancies (3.4) and invoice recovery (3.7) were also listed here; they shipped in the releases shown.

---

### Release 3.1 — Audit Trail & Eco Container Statuses

**Released:** 2025-05-23 (3.1.0) · **Latest patch:** 3.1.3 (2025-05-26)

#### Audit

- **Audit trail** for major modules — view the change history of orders, equipment, container sizes, checks and more
- **History** window opened from listing pages with a single click
- Tag changes shown in the history

#### Dispatch

- New container statuses: **Empty at Eco**, **Full at Eco**

!!! info "Corrected entry"
    Earlier versions of this changelog said that only the person who disabled a piece of equipment can re-enable it. The current version has no such restriction. The user feedback form listed here shipped in 3.7.

---

### Release 3.0 — Platform Upgrade & Bulk Duplication

**Released:** 2025-05-18 (3.0.0) · **Latest patch:** 3.0.2 (2025-05-22)

- Platform upgrade of the application framework
- **Order duplication** with a **Number of copies** field (1 to 100) and a choice of optional fields to copy. (Since 3.8 the optional fields are **Copy Reference Number** and **Copy Container Status**.) See [Order Duplication](order-duplication.md)

---

## Version 2.x

??? note "Version 2 — Foundation Releases"

    Version 2 established the core UTX Freight platform with the features below.

    #### Orders

    - **Driver Login Links** — send drivers a link to auto-login and open the order assigned to them
    - **Order duplication** with P/O grouping
    - **Confirmation dialogs** before destructive actions (delete, reset)
    - **CSV export** for open orders
    - **Inline edit** for Purchase Order, Container Size, Steamship Line, and Terminal
    - Normalize and validate **container numbers**
    - Add **last free day** and **pickup number** to the Import orders listing
    - Configurable **archive cutoff date** to improve page performance

    #### Dispatch

    - **Combined filters** — ETA, Delivery date, Terminal, container status, and text search
    - **Driver link** displays the driver name when copying
    - **Pickup Number** on the Dispatch page
    - **Port of Montreal** bulk update window
    - **Last Free Date (LFD)** filter with date range, No Date, and Any Date options

    #### Track and Trace

    - **CN Rail** Track'n Trace automatic updates and tracking window on the Dispatch page
    - **Port of Montreal** container tracking (Termont 68 and Viau 52)
    - **Container movement history** and **Destination ETA** tracking
    - **Last Free Date** for CN tracking
    - CN Terminal filter on the Order and Dispatch pages

    #### Invoices

    - **Clean invoice template** optimized to fit more information on a single page
    - Automatically include the **PO#** in the invoice email subject
    - Highlight active companies when creating invoices

    #### Equipment

    - Sub types: **Chassis, Trailers, and Trucks**
    - **Search, pagination, and filters** — Inspection Due, Past Due, by type
    - **Export to CSV** and **Enable/Disable** from the listing page
    - Color-coded **availability status** (Inspection, Mechanical, Assignment, Active)
    - Quick view of Equipment list on the **Orders** page
    - Show **only active** equipment when assigning to orders

    #### Tagging

    - **Default tags** per customer — automatically applied to new orders
    - **Mandatory tagging** option for all orders

    #### Reports

    - **Income by Shipper** and **Income by Customer** with totals

    #### Customers

    - Standardized address book with all **Canada/US provinces and states**

    #### Statements

    - Remove disabled companies from reporting

    #### Pro Modules

    - **Warehouse Addon**
