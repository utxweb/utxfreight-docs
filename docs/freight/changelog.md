# Changelog

All notable changes to UTX Freight are documented here. Releases are listed newest first.

---

## Version 3.x

### Release 3.10 — Multi-Office Shared Resources <small>Mar 2026</small>

#### Multi-Office Addon (Pro Module)

- Share **customers, equipment, drivers, terminals, and shippers** across offices while keeping **orders and invoices** segregated per office
- Office-specific customer and equipment management

#### Orders

- Clear appointment fields automatically when resetting an order back to **New**

---

### Release 3.9 — Monthly Fuel Surcharges <small>Mar 2026</small>

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

### Release 3.8 — Order Archival & Housekeeping <small>Mar 2026</small>

#### Orders

- **Stale order detection** — automatically identify orders that have been open longer than the configured threshold
- **Bulk archive** stale orders to keep the Orders and Dispatch pages clean
- **Safe archive UX** — archived orders moved to a separate view with visual indicators
- **Type-to-confirm delete** — orders can only be deleted from the archived view with a confirmation step
- **Restore** archived orders back to active status

#### Email

- Add **Postmark** as an alternative email delivery method alongside SMTP
- Configure Postmark per-edition via API settings
- Route authentication emails (password resets, invitations) through Postmark

---

### Release 3.7 — Container Tracking & Alerts <small>Mar 2026</small>

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

### Release 3.6 — Garage Module <small>Mar 2026</small>

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

### Release 3.5 — Order Duplication Enhancements <small>May 2025</small>

#### Orders

- Enhanced **order duplication** with selectable fields — choose which fields to copy (pickup number, drivers, equipment, container status)
- **Quantity selector** for bulk duplication (1-100 copies)
- Duplication modal shows which fields will and will not be copied
- Automatic redirect to filtered view after duplication

---

### Release 3.4 — Audit Trail System <small>May 2025</small>

#### Audit

- **Reusable audit trail** for all major modules — view history for orders, equipment, container sizes, checks, and more
- **History modal** accessible from listing pages with a single click
- Enhanced tag handling in audit history

---

### Release 3.3 — Container Status Management <small>May 2025</small>

#### Dispatch

- New **container status management** interface
- Custom container statuses for **container transfers**
- Modernized layout for container status configuration

---

### Release 3.2 — Reports & Invoicing <small>2024–2025</small>

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

### Release 3.1 — User Feedback & Quality of Life <small>2024–2025</small>

#### General

- **User feedback modal** — submit feedback directly from the app with automatic browser metadata capture
- Equipment **re-enable restriction** — only the person who disabled equipment can re-enable it
- Auto-login **user picker** on the login page

---

### Release 3.0 — Platform Upgrade <small>May 2025</small>

#### Platform

- Upgrade to **Ruby 3.2** and **Rails 7.1**
- Modernized application framework for improved performance and security
- Enhanced error tracking with **Airbrake** integration

---

## Version 2.x

??? note "Release 2.26 — Jun 2023"

    ### Orders

    - Optimize the Orders page by adding a configurable **archive cutoff date** to reduce query time
    - Add missing database indexes for improved query performance

??? note "Release 2.25 — Jun 2023"

    ### Orders

    - Add **last free day** to the listing for Imports for customers view

    ### Tagging

    - Add the ability to make the tagging mandatory for all orders

??? note "Release 2.11 — Apr 2021"

    ### Dispatch

    - Add Port of Montreal bulk update modal

??? note "Release 2.10 — Apr 2021"

    ### Invoices

    - Automatically include the PO# in the invoice email subject

??? note "Release 2.9 — Mar 2021"

    ### Dispatch

    - Include all the Orders in progress with a Last Free Date
    - Add the **Last Free Date (LFD)** filter for the date range
    - Add the **No Date** and **Any Date** filters

    ### Track and Trace

    - Hide **new** Orders when there is no information available from CN
    - Limit the history changes to the last few relevant items

??? note "Release 2.8 — Mar 2021"

    ### Customers

    - Standardize Customer address book with all Canada / US provinces and states

    ### Dispatch

    - Make the container filter exclusive
    - Add the pickup number to searchable fields

    ### Invoices

    - Highlight active companies when creating **Invoices**

    ### Reports

    - Highlight active companies in the selection menu

    ### Statement

    - Remove disabled companies from reporting

    ### Track and Trace

    - Add **Port of Montreal** container tracking
    - Add **Container** information for Termont 68 and Viau 52
    - Add **Last Free Date** for CN tracking

??? note "Release 2.7 — Feb 2021"

    ### Reports

    - Add **Income by Shipper**
    - Add totals to **Income by Customer**

    ### Orders

    - Add **pickup number** to the listing for Imports

??? note "Release 2.6 — Feb 2021"

    ### Orders

    - Inline edit for **Purchase Order, Container Size, Steamship Line** and **Terminal**
    - Normalize the **container number**

    ### Tagging

    - Add the ability to set a **default tag** for each customer

    ### Track and Trace

    - Add **Container** movement history
    - Track container **Destination ETA** updates

??? note "Release 2.5 — Feb 2021"

    ### Dispatch

    - Enable **Dispatch** filter toggling to improve user experience
    - Add the Order **Pickup Number** to the Dispatch page

    ### Warehouse Addon (Pro Module)

    - Documentation coming soon

??? note "Release 2.4 — Feb 2021"

    ### Dispatch

    - Improve the **Dispatch** filtering to support combined filters, **ETA** and **Delivery** date filtering, **Terminal** filtering and container status combined with text search.

    ### Orders

    - Add the ability to export **open** orders to **CSV**

??? note "Release 2.3 — Feb 2021"

    ### Track and Trace

    - Add **CN** Track'n Trace scheduler
    - Add **CN** Track'n Trace modal on the **Dispatch** page
    - Add **CN Terminal** filter on the **Order** and **Dispatch page**

??? note "Release 2.2 — Feb 2021"

    ### Dispatch

    - Enhance the **driver link** to display the driver name when copying the link

    ### Invoices

    - New **clean** invoice template optimized to fit more information on a single page

    ### Orders

    - Add **confirmation** messages before performing assertive actions such as delete or reset orders

??? note "Release 2.1 — Jan 2021"

    ### Equipments

    - Add a sub type to the Equipments Type in order to categorize the Equipment into **Chassis, Trailers and Trucks**
    - Add a **search box, pagination** and multiple **filters** on the Equipment list page
    - Add an **Export to CSV** button to the Equipment list page
    - Add the ability to **Enable / Disable** the equipment directly from the Equipment list page
    - Add clear codes (green, orange and red) for the different Equipment attributes such as **Inspection Status, Mechanical Status, Order Assignment and Active Status**
    - Add a quick view of the Equipment list on the **Orders** page
    - Improve the **Equipment Selection** on the Orders and Dispatch page to display **only active** equipment

    ### Orders

    - Add a **Magic Link** that can be sent to drivers which allows them to auto-login to the application and see their assigned **Work Orders**
    - Make the Order history modal scrollable

    ### SMS Addon (Pro Module)

    - Add an **SMS module** which allows to send SMS messages to Drivers with the **Magic Link** to auto login to the mobile application
