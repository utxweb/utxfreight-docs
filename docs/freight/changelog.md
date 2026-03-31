# Changelog

All notable changes to UTX Freight are documented here. Releases are listed newest first.

---

## Version 3.x

### Release 3.10 — Multi-Office Shared Resources

#### Multi-Office Addon (Pro Module)

- Share **customers, equipment, drivers, terminals, and shippers** across offices while keeping **orders and invoices** segregated per office
- Office-specific customer and equipment management

#### Orders

- Clear appointment fields automatically when resetting an order back to **New**

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
