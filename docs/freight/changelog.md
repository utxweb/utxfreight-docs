# Changelog

All notable changes to UTX Freight are documented here. Releases are listed newest first.

---

## Version 3.x

### Release 3.12 — Invoice Filtering & Consignee Visibility

#### Invoices

- **Exports now match your filters** — the Export button downloads exactly the invoices currently listed. Previously the export ignored the filters on screen and returned every invoice regardless of what you had selected
- **See what you are exporting before you click** — the Export panel states the count and the active filter, for example *"Exports the 1,002 invoices currently listed (All unpaid)"*
- **Two export layouts** — choose **QuickBooks columns** for accounting import, or the new **AR aging detail** layout for collections and month-end review
- **Invoice date range** — filter the list to a **from/to** range, with one-click presets for This Month, Last Month, This Year, last year, and Last 12 Months
- **AR aging on the invoice list** — filter by how late an invoice is, using open-ended rollups (**Past due**, **30+ days**, **60+ days**) or exact bands (**Not Due**, **0-30**, **31-60**, **61-90**, **91+**). The bands split the ledger the same way the Aged Receivables report does
- **New Aging and Balance columns** — see days past due and the outstanding amount directly in the list, without opening the invoice
- **Filters combine instead of replacing each other** — status, search, invoice date, and aging all narrow the same list. Each active filter appears as a removable chip in the search bar, with **Clear All** to reset
- **A cleaner invoice table** — folded from 15 columns to 8 by pairing each value with its closely-related detail (invoice with its date, balance with total paid, status with sent date). Nothing was removed
- **Consistent sorting** — past-due views now sort newest-first like every other tab, instead of oldest-first
- **Large export guard** — exports are capped at 20,000 invoices with a clear message to narrow the filter, rather than timing out
- Fixed an error when exporting an invoice that had no company assigned, and a company drill-down that led to an empty list

!!! info "Your saved links still work"
    Bookmarked **Past Due**, **30+** and **60+** invoice links continue to work — they now open the matching AR aging view and return the same invoices they always did.

#### Customer Portal

- **Consignee order visibility** — a consignee can now be linked to a customer account so their users get **read-only** visibility of orders delivered to them, including orders created by a different freight forwarder
- Consignee users see an explanatory banner on the Orders page describing the scope of what they can view
- Link a consignee to a customer account from the **Clients** admin form using the new company selector

#### Orders

- The **Total** figure in the Orders header now sums the operational statuses (New, App. Taken, Dispatched) so it matches the badges beside it — it previously also counted Completed orders

---

### Release 3.11 — Compound Search & Filtering

#### Orders

- **Compound search and filters** — combine any mix of status tab, order type, container status, terminal, search text, and tags in a single view. Filters chain independently rather than overriding each other
- **New filter interface** — full-width search bar with inline filter chips, a 3-column card grid for Order Type / Container Status / Terminal, and a **Clear All** button
- **Filter chips** — each active filter appears as a removable badge; click the × to drop one dimension while keeping the rest
- **Order Type filter** — filter orders by type (Import, Export, Transfer, etc.) as a distinct dimension from container status
- **N/A container status** option for orders where a container status has not been set
- Renamed the **Terminal** card (previously labelled Location) for consistency across the interface
- Shareable, bookmarkable filter URLs — the address bar reflects the exact filter state

---

### Release 3.10 — Multi-Office Shared Resources

#### Multi-Office Addon (Pro Module)

- Share **customers, equipment, drivers, terminals, and shippers** across offices while keeping **orders and invoices** segregated per office
- Office-specific customer and equipment management

#### Garage Addon (Pro Module)

- **Reopen completed work orders** — move a finished work order back to approved status for additional edits
- **Customer work summary reports** — generate service history reports per customer
- **Void and delete invoices** — void an invoice to reverse it or delete it entirely, with confirmation prompts
- Improved **confirmation dialogs** before destructive actions (void, delete)
- Visual and layout improvements to **PDF invoices and estimates**

#### Orders

- Clear appointment fields automatically when resetting an order back to **New**
- Improved **archive experience** with a cleaner interface for managing archived orders

#### Email & Notifications

- Restored **multiple recipients** support — send emails with To, CC, and BCC fields
- **Feedback notifications** — new user feedback submissions are emailed to the support team
- Respect **notification preferences** — only send tracking digests and alerts to users who opted in

#### General

- **File upload limit** — 20 MB maximum per attachment across all upload areas
- Improved **email address validation** throughout the application
- Performance improvements for offices with large order volumes

---

### Release 3.9 — Monthly Fuel Surcharges

#### Fuel Surcharge

- Replace the weekly fuel surcharge system with a **monthly system** — set one rate per month instead of per week
- **Quick Set** form to create or update rates for any month with copy-forward support
- **Custom company rates** to override the general rate for specific customers
- **Exempt customers** from fuel surcharges with a checkbox on the customer profile
- **Recalculate** button to update all open orders in a month with one click, with a preview modal
- **Stale charge detection** — red indicators when exempt customers still have fuel charges
- **Missing rates warning** banner for months without a defined rate
- Legacy weekly rates preserved for historical orders

---

### Release 3.8 — Order Archival & Housekeeping

#### Orders

- **Stale order detection** — automatically identify orders that have been open longer than the configured threshold
- **Bulk archive** stale orders to keep the Orders and Dispatch pages clean
- **Safe archive UX** — archived orders moved to a separate view with visual indicators
- **Type-to-confirm delete** — orders can only be deleted from the archived view with a confirmation step
- **Restore** archived orders back to active status

#### Email

- Improved **email delivery reliability** with a secondary delivery channel and per-account configuration

---

### Release 3.7 — Container Tracking & Alerts

#### Container Tracking

- **Real-time container tracking** across three terminal sources: CN Rail, Termont (Port of Montreal), and MGT (Racine/Cast)
- Automatic updates **every 10 minutes** from all terminal sources
- **Tracking modal** with color-coded headers — green for ready to pick up, blue for in transit, red for holds
- **Auto-populate order fields** from terminal data — seal number, weight, steamship line, container size, and customs status
- **Container number trimming** — automatically strip whitespace from container numbers
- **Pipeline health dashboard** showing submitted vs. found container counts per terminal

#### Container Alerts

- **Alerts Dashboard** with summary cards for Pickup Ready, Customs Released, LFD Approaching, and Departed
- **Upcoming Last Free Days table** with color-coded urgency rows (red = expired, yellow = 1-2 days)
- **Integration Health cards** — green/red border indicating whether terminal data is fresh or stale
- **Daily digest email** summarizing all new tracking alerts
- **Email subscriptions** — choose which alert types to receive
- Suppress stale container alerts for containers no longer being tracked

#### Dispatch

- Add **inbound container status** filter options
- New container statuses: **Empty at Eco**, **Full at Eco**
- Display **vessel cutoff date** on the Dispatch page

---

### Release 3.6 — Garage Module

#### Garage Addon (Pro Module)

- Complete **fleet and vehicle management** system
- **Dashboard** with vehicle overview, upcoming maintenance, and service history
- **Canned jobs** — pre-defined service templates for common maintenance tasks
- **CSV import** for bulk vehicle data migration
- **VIN decoder** — automatically populate vehicle details from VIN
- **Invoice email** with PDF attachment and company logo
- **Tax management** with per-line taxable toggles
- **License plate search** across the fleet

---

### Release 3.5 — Order Duplication Enhancements

#### Orders

- Enhanced **order duplication** with selectable fields — choose which fields to copy (pickup number, drivers, equipment, container status)
- **Quantity selector** for bulk duplication (1-100 copies)
- Duplication modal shows which fields will and will not be copied
- Automatic redirect to filtered view after duplication

---

### Release 3.4 — Audit Trail System

#### Audit

- **Reusable audit trail** for all major modules — view history for orders, equipment, container sizes, checks, and more
- **History modal** accessible from listing pages with a single click
- Enhanced tag handling in audit history

---

### Release 3.3 — Container Status Management

#### Dispatch

- New **container status management** interface
- Custom container statuses for **container transfers**
- Modernized layout for container status configuration

---

### Release 3.2 — Reports & Invoicing

#### Reports

- **Aged Receivables** report — Performance AR (operational, 12-month view) and Standard AR (GAAP-compliant snapshot)
- **QuickBooks invoice export** for accounting integration

#### Invoices

- **Invoice discrepancies** feature to identify payment mismatches
- Track **appointment and completed dates** on invoices
- **Due on Receipt** invoice term option
- **Recover deleted invoices** via Super User Dashboard

#### Orders

- **"From Email" filter** on the Orders page
- New terminal filters: **CP, Racine, Cast**

---

### Release 3.1 — User Feedback & Quality of Life

#### General

- **User feedback modal** — submit feedback directly from the app with automatic browser metadata capture
- Equipment **re-enable restriction** — only the person who disabled equipment can re-enable it

---

## Version 2.x

??? note "Version 2 — Foundation Releases"

    Version 2 established the core UTX Freight platform with the features below.

    #### Orders

    - **Magic Link** — send drivers a link to auto-login and see their assigned Work Orders
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
    - **Port of Montreal** bulk update modal
    - **Last Free Date (LFD)** filter with date range, No Date, and Any Date options

    #### Track and Trace

    - **CN Rail** Track'n Trace scheduler and modal on the Dispatch page
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

    - **SMS Addon** — send Magic Link via SMS to drivers
    - **Warehouse Addon**
