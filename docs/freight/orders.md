# Orders

Find, filter, and act on every freight order from one list: the **Orders** page.

## :fontawesome-solid-truck: Overview

Orders are the core of UTX Freight. Every move, whether a container import, an export, a transfer or a dry van move, starts as an order. The **Orders** page (header **Listing orders**, subtitle **Orders Management**) is the list where you find and work on them:

- :fontawesome-solid-hashtag: **Counters**: New Orders, App. Made, Dispatched, Total, and the yard counts for intermodal accounts
- :fontawesome-solid-magnifying-glass: **Search**: one box that covers container #, order #, P/O, booking #, customer, and more
- :fontawesome-solid-filter: **Status tabs and filter cards**: narrow by status, order type, container status, terminal, and tag
- :fontawesome-solid-pencil: **Inline editing**: change dates, numbers, drivers, and statuses directly on the row
- :fontawesome-solid-bars: **Row action menu**: Quick Edit, documents, POD, duplicate, reset, transfer, delete, and more
- :fontawesome-solid-file-csv: **Export**: download all In Progress orders to CSV (Admin only)
- :fontawesome-solid-circle-info: **Legend**: a built-in key to every badge, icon, and abbreviation on the page

This page covers the list itself. Related topics have their own pages:

| Topic | Page |
|-------|------|
| Filling in the order form | [Order Form](order-form.md) |
| Status flow: Make App., Dispatch, Complete | [Order Workflow](order-workflow.md) |
| Charges, rates, and expenses | [Order Charges & Expenses](order-charges-and-expenses.md) |
| Documents, POD, and eBoL | [Order Documents & POD](order-documents-and-pod.md) |
| Duplicating orders | [Order Duplication](order-duplication.md) |
| Legs and move locations | [Order Legs & Move Locations](order-legs-and-move-locations.md) |
| Tags | [Order Tagging](order-tagging.md) |

<!-- TODO: Screenshot — The Orders list page showing the counters in the header, the search bar, the status tabs, the filter cards, and a few order rows -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Orders** from the left menu. The list opens on the **In Progress** tab.
2. Type a container #, order #, P/O, or customer name in the **Container #, Order # and more** box and click **Search**.
3. Use the status tabs (**All**, **In Progress**, **New**, **App. Made**, **Dispatched**, **Completed**) to change which statuses you see.
4. Click a linked value on a row to edit it in place, or click the **caret** next to the row's action button for the full action menu.
5. To add an order, click **Create a new order** in the header. See [Order Form](order-form.md).

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access to the Orders page |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Full access to all orders, plus **Export** |
| :fontawesome-solid-user-tie: **Manager** | Full access to orders in their offices: create, edit, inline edit, status actions, reset, go back one step, duplicate, transfer, delete |
| :fontawesome-solid-headset: **Dispatch** / **Customer Service** | Same order access as Manager: create, edit, inline edit, status actions, delete, reset, duplicate, transfer. **View History** needs the **Can manage rates?** option on the user's profile |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Full order access by default (account configuration option `accountant_can_manage_orders`, on by default; it is not on the **Settings** page). If the option is off: view only, plus **Complete** and edit on Dispatched orders. Never sees the filter cards, the **Equipment**, **Legend**, or **Export** buttons, or the **Not Invoiced** / **Late Invoicing** tabs |
| :fontawesome-solid-user: **Customer** | Sees all orders placed by anyone in their company, in their offices. View only by default. When the account configuration option `customer_can_manage_orders` is on (off by default), customers can also create orders and edit orders that are still **New**. Customers never get **Delete Order**, inline editing, or the status action buttons |
| :fontawesome-solid-eye: **Customer (consignee)** | Also sees, read-only, the deliveries addressed to their linked shipper/receiver records, from all freight forwarders, in the office they are working in. See [Consignee view](#consignee-view) |
| :fontawesome-solid-id-card: **Driver** | Always sees only **Dispatched** orders assigned to them. Drivers use the mobile view; see [Driver Workflow](driver-workflow.md) |
| :fontawesome-solid-warehouse: **Warehouse** / :fontawesome-solid-wrench: **Garage** | No access to Orders |

**How to get there:**

- :fontawesome-solid-arrow-right: From the left menu, click **Orders**

!!! info "Archive cutoff"
    Orders created before the **Order Archive Cutoff Date** (**Settings**) never appear on this page: not in any status tab and not in search results. See [Application Settings](application-settings.md).

!!! info "Multi-office"
    The list only shows orders of the office you are working in. If a search finds nothing and your account has several offices, the page shows **No orders found for "…" in *office*. Try switching to another office using the menu above.** See [Multi-Office](multi-office.md).

---

## :fontawesome-solid-list: Order Types

Order types are turned on per account (setting `order_type_enabled`). By default only **Import** and **Export** are enabled. The order form and the **Order Type** filter card only offer the enabled types.

Each row starts with a short code badge. Hover the badge to see the order description.

| Code | Full name | What it is |
|------|-----------|------------|
| **CI** | **Container Import** | A full container is picked up at the terminal and delivered to the customer. The empty container is then returned (**Return To**, **Return Date**) by a return driver. |
| **CX** | **Container Export** | An empty container is picked up at the terminal, loaded at the customer, and the full container is returned to the terminal. |
| **TF** | **Container Transfer** | A container move to the **Return To** location. The **Deliver To** column shows that location; there is no return date and no second driver. |
| **DV** | **Dry Van Move** | A ground move from a pickup company to a delivery company. |
| **IX** | **International Export** | An export order that uses an eBill of Lading (**eBoL**) instead of a POD. |
| **WH** | **Warehouse** | Warehouse orders. Listed in the Legend only when warehouse orders are enabled. See [Warehouse Orders](warehouse-orders.md). |

The **Order Type** filter card uses short names: **Import**, **Export**, **Transfer**, **Dry Van**, **International Export**.

---

## :fontawesome-solid-hashtag: Counters

The page header shows counters:

| Counter | Counts |
|---------|--------|
| **New Orders** (red) | Orders with status New |
| **App. Made** (orange) | Orders with status App. Taken |
| **Dispatched** (green) | Orders with status Dispatched |
| **Total** (black) | New Orders + App. Made + Dispatched |
| **Empty at Yard** (blue, intermodal) | Orders not yet Completed whose container status is *Empty at yard* |
| **Full at Yard** (blue, intermodal) | Orders not yet Completed whose container status is *Full at yard* |
| **Pre-Pull** (blue, intermodal) | Orders not yet Completed whose container status is *Pre-Pull*. Shown only when *Pre-Pull* is one of your container statuses |

!!! warning "Counters ignore filters"
    The counters always count every order you can access in the current office. Search, status tabs, and filter cards do not change them, and unlike the list they also count orders created before the **Order Archive Cutoff Date**.

---

## :fontawesome-solid-magnifying-glass: Search

The search bar at the top reads **Container #, Order # and more**. Type a value and click **Search** (or press Enter). The search is not case-sensitive and matches:

| Field | Match |
|-------|-------|
| Order # (type the number only, without any letter prefix your account adds to order numbers) | Exact |
| **P/O** (delivery purchase order #) | Exact |
| Reference number (the order's own reference / waybill number field) | Contains |
| Container # / Trailer # | Contains |
| Booking # | Contains |
| Deliver To company (shipper/receiver) | Contains |
| Pickup company | Contains |
| Customer company (Bill To) | Contains |
| Equipment name | Contains |
| Order type, by its internal name (`import`, `export`, `transfer`, `dry_van`, `international_export`) | Contains |
| Container size | Contains |

**How search interacts with the tabs:**

- If you search **without choosing a status tab**, the search widens to **All** statuses. An **All ✕** chip appears in the search bar; click its **✕** to narrow back to **In Progress**.
- If you chose a tab first (for example **Completed**), the search stays within that tab.
- Your other filters (order type, container status, terminal, tag) are kept when you search.
- Orders created before the archive cutoff date are never found.

---

## :fontawesome-solid-filter: Status Tabs

| Tab | Shows | Who sees it |
|-----|-------|-------------|
| **All** | Every status | Everyone |
| **In Progress** (default) | New + App. Taken + Dispatched | Everyone |
| **New** | Status New | Everyone |
| **App. Made** | Status App. Taken | Everyone |
| **Dispatched** | Status Dispatched | Everyone |
| **Completed** | Status Completed | Everyone |
| **Not Invoiced** | Completed, not on an invoice, with a delivery date on or after the **Order Start Date** (**Settings**, Invoice group) | Admin / Manager |
| **Late Invoicing** | Same as Not Invoiced, but only orders delivered before the end of the week two weeks ago | Admin / Manager |

The active tab is highlighted green. Clicking a tab changes **only the status**; your search text and other filters stay.

!!! info "Drivers"
    Drivers always see the **Dispatched** list, whatever tab they pick. Orders whose container status is *Returned to terminal* are hidden from them.

!!! tip "Use Late Invoicing as a billing check"
    **Late Invoicing** lists completed work that has been waiting to be billed for more than about two weeks. If old completed orders are missing from **Not Invoiced**, check the **Order Start Date** in **Settings**. See [Creating Invoices](creating-invoices.md).

---

## :fontawesome-solid-sliders: Filter Cards

Below the tabs, Admin, Manager, Dispatch, and Customer Service users see filter cards.

### Order Type (intermodal accounts)

One button per enabled order type. Click a button to show only that type; click the active (green) button again to turn it off.

### Container Status (intermodal accounts)

A single dropdown. The list reloads as soon as you pick a value:

- **All Statuses**: no container status filter
- **N/A (not set)**: orders with no container status
- each container status configured for your account (see [Container Statuses](container-statuses.md))

### Terminal

Buttons for **CN**, **CP**, **Racine**, **Cast**, and **Termont**. A button appears only when a matching terminal exists in your account. The filter uses the order's pickup terminal. Click the active button again to turn it off. See [Managing Terminals](managing-terminals.md).

### Tags

When the account is intermodal and the tagging add-on is on, tag buttons appear next to the status tabs (everyone sees them). Click a tag to show only orders with that tag; click the active tag again to turn it off. See [Order Tagging](order-tagging.md).

### Action & Orders

| Button | What it does |
|--------|--------------|
| :fontawesome-solid-truck: **Equipment** | Opens the equipment list. See [Equipment](equipment.md) |
| :fontawesome-solid-circle-info: **Legend** | Opens the **Orders Page Legend** (see [Legend](#legend)) |
| :fontawesome-solid-file-csv: **Export** | Admin only. See [Export](#export) |

When the Auto Orders add-on is on, an **AUTO ORDERS** card adds **Processing**, **Need Review**, and **Completed** views, and an **Upload** button appears in the header. See [Auto Orders](auto-orders.md).

### Filter chips, All, and Clear All

Each active filter shows as a small grey chip inside the search bar (for example **Completed ✕**, **Container Import ✕**, **N/A (not set) ✕**, **CN ✕**, **Tag: … ✕**).

- Click a chip's **✕** to remove just that filter. Your search text and the other filters stay.
- Click **Clear All** (right of the search bar) to reset everything: search text, tab, and all filters. The page returns to **In Progress**.
- The **All** tab is not a reset. It only changes the status; other filters stay on.

<!-- TODO: Screenshot — The search bar with two filter chips, the status tabs, and the Order Type / Container Status / Terminal cards -->

---

## :fontawesome-solid-table-columns: Columns

The list shows **30 orders per page**, with page links at the bottom. Header labels shown as links are sortable: click to sort, click again to reverse.

### Intermodal accounts

| Column | Content | Sortable |
|--------|---------|----------|
| **Status** / **Order#** | Order type code, status badge, **Transferred** label, order #, and on large screens only the **P/O#** and Special Note | Status, Order# |
| **Deliver To** / Bill To | Delivery company (for TF, the return location), then the customer company | Deliver To |
| **ETA** | Estimated time of arrival (CI and CX) | Yes |
| **Storage (STO)** / **Demurrage (DEM)** | Storage and demurrage dates (CI) | Both |
| **Delivery/Pickup** / App. Time | Delivery date and appointment time | Delivery/Pickup |
| Size / Steamship / Weight | Container size, steamship line, weight, **OFF-HIRE** label | No |
| **Container#** / Book#/Seal# / Last Free Day | Container #, icons, **B#** booking and **S#** seal (CX, TF), seal (CI), **LFD** (CI, CX) | Container# |
| Vessel / ERD / Cutoff Date | Vessel, **ERD** and **CUT** dates (CX) | No |
| **Terminal / Pickup From / Pickup #** | Pickup terminal; for DV the pickup company; for IX the shipper; pickup # (CI) | Yes |
| Chassis # | Equipment button and, for *Borrowed*, the chassis #. Users who cannot change equipment see the equipment name as text | No |
| **C.Status** | Container status, in its configured colour | Yes |
| Delivery **Driver** | Delivery driver and the date that leg was signed | Driver |
| **Return To** / **Return Date** | Return location and return date (no date for TF) | Both |
| Return **Driver** | Return driver and the date that leg was signed (none for TF) | Driver |
| Invoiced / **Rate** | Invoice button (when the order is invoiced), order total, zone badge (TF orders show the zone name as plain text) | Rate |
| Email POD | Send-POD button, shown only once the order has a signature, a scanned POD, or a previous POD email | No |
| (actions) | Status action button and caret menu | No |
| POD | Scanned and signed POD icons | No |
| DOC | Documents icon (only for users who can edit the order) | No |

### Ground accounts

| Column | Content | Sortable |
|--------|---------|----------|
| **Status** / **Order#** | Same as intermodal | Status, Order# |
| **Pickup From** | Pickup company | Yes |
| **Pickup Date** | Pickup date (for orders other than DV and TF, the return date) | Yes |
| **Deliver To** / Bill To | Delivery company, then the customer company | Deliver To |
| **Delivery Date** / App. Time | Delivery date and appointment time | Delivery Date |
| **Trailer#** | Trailer number and icons | Yes |
| Equipment # | Equipment button | No |
| Pickup **Driver** | Driver for the pickup | Driver |
| Delivery **Driver** | Driver for the delivery | Driver |
| Invoiced / **Rate**, Email POD, actions, POD, DOC | Same as intermodal | Rate |

### Role-dependent columns

| Column | Visible to |
|--------|-----------|
| Driver columns | Admin, Manager, Dispatch, Customer Service, Accountant (when it can manage orders) |
| **Invoiced** / **Rate** | Admin, Manager, Accountant, Customer Service. Customer Service sees the rate but not the invoice button. Hidden on small screens |
| **Email POD** | Admin, Manager, Accountant, Dispatch, Customer Service |

Customers never see the Special Note.

---

## :fontawesome-solid-tags: Badges and Icons

### Status badges

| Badge | Status |
|-------|--------|
| :fontawesome-solid-star: red | **New Order** |
| :fontawesome-solid-clock: orange | **Appointment Made** (App. Taken) |
| :fontawesome-solid-road: green | **Dispatched** |
| :fontawesome-solid-check: grey | **Completed** |

See [Order Workflow](order-workflow.md) for how an order moves between statuses.

### Row labels and icons

| Item | Where | Meaning |
|------|-------|---------|
| :fontawesome-solid-right-left: **Transferred** | Status column | The order was transferred from another office. Hover to see which one |
| Coloured order # | Status column | The order has a tag; the colour is the tag colour |
| **P/O#:** | Under the order # | The delivery purchase order number, or **N/A** |
| Special Note (bold red text) | Under the P/O# | The order's **Special Note** field, which also shows on the driver's phone. Hidden from customers |
| :fontawesome-solid-fire: (orange) | Container column | HAZMAT. Icon only; hover to see "HAZMAT" |
| :fontawesome-solid-weight-hanging: (blue) | Container column | Scale. Hover to see the scale value |
| :fontawesome-solid-exclamation: (red) | Container column | DAMAGED. Icon only; hover to see "DAMAGED" |
| :fontawesome-solid-copy: | Container column | Copies the container number as plain text. A **Container number copied** message confirms it |
| :fontawesome-solid-train: / :fontawesome-solid-ship: | Container column | Check container status with terminal tracking, when the add-on is on for that terminal. See [Container Tracking](container-tracking.md) |
| **OFF-HIRE** (red) | Size column | Equipment off-hire |
| Driver name in green or red | Driver columns | Green when that leg is ready for the driver's signature; red otherwise |
| :fontawesome-solid-share-from-square: | Driver columns | Copies the driver's magic link (Magic Link add-on), shown when that leg is ready for the driver. See [Driver Login Links](driver-login-links.md) |
| :fontawesome-solid-comment-sms: | Delivery driver column | Send an SMS to the driver (SMS add-on), shown when the leg is ready for signature and a driver is assigned. Green after a delivered SMS, red after a failed one; hover for the last send time |
| Zone badge (blue) | Rate column | The order's zone |
| **Zone Not Set** (red) | Rate column | No zone is assigned. See [Zones & Cities](zones-and-cities.md) |
| :fontawesome-solid-file-invoice: | Invoiced column | Opens the invoice list searched to this order's invoice. Not shown to Customer Service |
| :fontawesome-solid-envelope: | Email POD column | Send the POD to the client. Blue when no POD email was sent yet; after a send, green when the last email was delivered and red otherwise. Hover for the last delivery time |
| :fontawesome-regular-file-pdf: (red) | POD column | Opens the scanned POD |
| :fontawesome-solid-file-signature: (green) | POD column | Opens the signed POD |
| :fontawesome-regular-file-lines: (red) | DOC column | The order has documents; opens them. Only shown to users who can edit the order |

!!! info "When icons do not show"
    The HAZMAT, Scale, and DAMAGED icons, the tracking button, and container # editing only appear for users who can edit orders, and only when the container number is 20 characters or shorter.

### Text colours

| Item | Colour | Meaning |
|------|--------|---------|
| **LFD**, **CUT**, and **STO** dates | Red | Always shown in red when set |
| **ERD** date | Green | Always shown in green when set |
| Container # | Red | Container status is *Arrived - Missing customs* or *Arrived - On hold* |
| Container size | Red | The size name contains 20 or 45, or LCL or DRY. A missing size shows as grey **Empty** |
| Terminal name | Brown | Racine, Termont, Termont 68, or Cast |
| **C.Status** and equipment name | The container status colour | Set per status in [Container Statuses](container-statuses.md); no status shows grey **N/A** |

### Legend

Click **Legend** in the **Action & Orders** card to open the **Orders Page Legend**. It explains:

- **Order Type Badges**: CI, CX, TF, DV, IX (and WH when warehouse is enabled)
- **Order Status Badges**: New Order, Appointment Made, Dispatched, Completed
- **Warning Icons & Badges**: HAZMAT, Scale, DAMAGED, Off-Hire
- **Acronyms & Abbreviations**: ETA, STO, DEM, LFD, ERD, CUT, B#, S#, P/O#
- **Document Icons**: POD Email, Scanned POD, Signed POD, Documents, Invoice
- **Color Coding**: container status colours (set per status) and zone badges (Zone Name, Zone Not Set)

<!-- TODO: Screenshot — The Orders Page Legend modal -->

---

## :fontawesome-solid-pencil: Inline Editing

Values shown as links on a row can be edited in place: click the value, change it in the small popup, and confirm. The row refreshes on its own.

Inline fields need full order rights (Admin, Manager, Dispatch, Customer Service, and Accountant when it can manage orders). Customers cannot edit inline.

| Field | Popup title | Order types | Extra condition |
|-------|-------------|-------------|-----------------|
| **P/O#** | Enter P/O number | All | |
| **ETA** | Enter estimated time of arrival date (ETA) | CI, CX | Intermodal |
| **STO** (storage) | Enter container storage date | CI | Intermodal |
| **DEM** (demurrage) | Enter container demurrage date | CI | Intermodal |
| Container size | Select Size | All | Intermodal |
| Steamship line | Select Steamship Line | All | Intermodal |
| **Container #** | Enter new container number | All | Number of 20 characters or less |
| **LFD** (last free day) | Enter last free date | CI, CX | |
| **ERD** | Enter earliest return date (ERD) | CX | Intermodal |
| **CUT** (cutoff) | Enter cutoff date | CX | Intermodal |
| Pickup terminal | Select Terminal | All except DV and IX | Intermodal |
| Pickup # | Enter new pickup number | CI | Intermodal |
| **Chassis #** | Enter chassis number | All | Only when the equipment is **Borrowed** |
| **C.Status** (container status) | Enter new container status | All | Intermodal. Shown as a link to Admin, Manager, Accountant, Dispatch, and Customer Service; saving needs order edit rights, so an Accountant without full order access is refused |
| Delivery driver (first driver column) | Enter new delivery driver (CI); Enter new return driver (other types) | All | |
| Return driver (second driver column) | Enter new return driver (CI); Enter new delivery driver (other types) | All except TF | |
| **Return To** | Enter new return to | All | Intermodal |
| **Return Date** | Enter new return date | All except TF | Intermodal |

The popup titles of the two driver columns are swapped for every order type except CI; the column you click is the one that changes.

The **equipment** button (truck icon) opens the equipment assignment window. See [Equipment](equipment.md).

!!! warning "Delivery date is not inline-editable"
    The **Delivery/Pickup** (or **Delivery Date**) column is display only. Change it through **Quick Edit**, **Edit Order**, or the status actions (see [Order Workflow](order-workflow.md)).

<!-- TODO: Screenshot — An order row with an inline-edit popup open on the container number -->

---

## :fontawesome-solid-ellipsis-vertical: Row Actions

All actions are in the button group near the end of the row.

### Status action button

The left button moves the order to its next status:

| Order status | Button |
|--------------|--------|
| New | **Make App.** |
| App. Taken | **Dispatch** |
| Dispatched | **Complete** |
| Completed, or no permission | **Actions** (no action) |

See [Order Workflow](order-workflow.md).

### Caret menu

Click the **caret** (:fontawesome-solid-caret-down:) next to the action button. Items appear only when they apply:

| Item | What it does | Shown when | See |
|------|--------------|-----------|-----|
| **Quick Edit** | Opens the order in a popup | You can edit the order | [Order Form](order-form.md) |
| **Documents** | Opens the popup on the documents section | You can edit the order | [Order Documents & POD](order-documents-and-pod.md) |
| **View POD** / **View eBoL** | Opens the POD PDF (eBoL for IX) | Admin, Manager, Dispatch, Customer Service, Driver | [Order Documents & POD](order-documents-and-pod.md) |
| **View Internal POD** | Opens the internal POD | Internal POD enabled; Admin, Manager, Dispatch, Customer Service | [Order Documents & POD](order-documents-and-pod.md) |
| **View Carrier Confirmation** | Opens the carrier confirmation | DV orders; Admin, Manager, Dispatch, Customer Service | [Order Documents & POD](order-documents-and-pod.md) |
| **View Details** | Opens the order details page | You can view the order | |
| **Edit Order** | Opens the full order form | You can edit the order | [Order Form](order-form.md) |
| **Reset Order to New** | Sets the status back to New and clears the appointment date, appointment time, and delivery date, after a **RESET THE STATUS** confirmation | Status is not New; Admin, Manager, Dispatch, Customer Service, or Accountant with full order access | [Order Workflow](order-workflow.md) |
| **Go Back 1 Step** | Moves the status back one step, after a **GO BACK ONE STEP** confirmation. Going back from App. Taken to New also clears the appointment and delivery date | Status is not New; same roles | [Order Workflow](order-workflow.md) |
| **Duplicate** | Opens the duplicate window | You have full order rights (not Customers) | [Order Duplication](order-duplication.md) |
| **Transfer to Office** | Moves the order to another of your offices | Multi-office, and you have another office. Shown greyed as **Transfer (Invoiced)** when the order is invoiced | [Multi-Office](multi-office.md) |
| **View History** | Shows the order's change history | Data audit enabled (on by default); Admin, Manager, Accountant with full order access, or Dispatch / Customer Service with **Can manage rates?** | |
| **Remove Signature** | Clears the delivery signature, after a **CLEAR THE SIGNATURE** confirmation | Order is not Completed, has a delivery signature, and you have full order rights | [Order Documents & POD](order-documents-and-pod.md) |
| **Delete Order** | Deletes the order, after a **DELETE THIS ORDER** confirmation | You have full order rights (never Customers). Greyed out when invoiced | |

!!! danger "Delete and Remove Signature cannot be undone"
    **Delete Order** and **Remove Signature** are permanent. An invoiced order cannot be deleted: clicking the greyed **Delete Order** shows **INVOICED ORDER — This order is invoiced and cannot be deleted. Remove it from the invoice first.**

<!-- TODO: Screenshot — The caret menu open on a Dispatched order -->

---

## :fontawesome-solid-file-csv: Export

Click **Export** in the **Action & Orders** card to download a CSV file.

- **Admin only.** Other roles do not see the button.
- **Filters are ignored.** The file always contains all **In Progress** orders (New, App. Taken, Dispatched) created after the archive cutoff date, from every office, whatever tab, search, filter, or office is active.
- **Fixed columns:** Reference, Description, Status, Container number, Customer name, Delivery company name, Container status with customer name, Delivery date, App info, Pickup terminal name, Container size name, Steamship line name, Display hazardous, Display equipment name, Return date display, Creation date, Last update.
- **Fixed file name:** `<account>-orders-open-<YYYY-MM-DD>.csv`.

For other exports, see [Data Exports](data-exports.md).

---

## :fontawesome-solid-eye: Consignee view

A customer user linked to one or more shipper/receiver records is a **consignee**. A blue banner appears above the list:

> **Consignee view:** you are seeing all delivery orders addressed to *linked companies* — from all freight forwarders. Pricing details are not shown.

Consignees see, read-only, every delivery addressed to those companies in the office they are working in, plus their own company's orders. See [Customer Portal](customer-portal.md).

---

## :fontawesome-solid-ban: Account suspension

If the account is suspended, a red banner **System Notice: Account Suspended** appears above the list, with the suspension level name and number, the message, and the **Reason** when one is set.

While suspended:

- **Create a new order** turns red with a :fontawesome-solid-ban: icon.
- **Upload** (Auto Orders) turns red the same way.
- Clicking either opens **Account Suspended - Action Blocked** (**Order Creation Disabled**) instead of creating anything. Contact your system administrator to lift the suspension.

---

## :fontawesome-solid-mobile-screen: Drivers on mobile

Drivers see a separate mobile view of their dispatched orders. See [Driver Workflow](driver-workflow.md) and [Mobile Users](mobile-users.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-magnifying-glass: Can't find an order in the list

!!! info "Solution"
    1. Check the chips in the search bar: an order type, container status, terminal, or tag filter may still be on. Click **Clear All** to reset everything. The **All** tab alone does not clear filters.
    2. The default tab is **In Progress**, which hides Completed orders. Pick **All** or **Completed**, or search without picking a tab.
    3. If the order is older than the **Order Archive Cutoff Date** in **Settings**, it is hidden from every tab and from search. Move the date back to see it.
    4. In a multi-office account, switch office from the menu at the top.

### :fontawesome-solid-hashtag: The counters don't match the list

!!! info "Solution"
    This is expected. Counters ignore search and filters, count every order you can access in the office (including orders older than the archive cutoff date), and **Total** is New + App. Made + Dispatched only.

### :fontawesome-solid-file-csv: My export doesn't match what I filtered

!!! info "Solution"
    **Export** always downloads all In Progress orders, from every office, with fixed columns. It does not follow your search, tab, filters, or current office.

### :fontawesome-solid-circle-check: Order was signed but is not Completed

!!! info "Solution"
    A driver's signature does not complete an order. An order becomes **Completed** only when someone clicks **Complete** on the row (or in [Dispatch](dispatch.md)). Only Completed orders can be invoiced. See [Order Workflow](order-workflow.md).

### :fontawesome-solid-file-invoice-dollar: Not Invoiced or Late Invoicing tab is missing or empty

!!! info "Solution"
    Both tabs are shown only to Admin and Manager. They list Completed orders with no invoice and a delivery date on or after the **Order Start Date** in **Settings**. Orders delivered before that date never appear.

### :fontawesome-solid-pencil: I can't edit a field on the row

!!! info "Solution"
    Inline editing needs order edit permission. Some fields only exist for certain order types (for example **ERD** and **CUT** are Export only, **STO**/**DEM** are Import only), the chassis # is editable only for *Borrowed* equipment, and the delivery date is never inline-editable; use **Quick Edit**.

### :fontawesome-solid-trash: Delete Order is greyed out

!!! info "Solution"
    The order is on an invoice. Remove it from the invoice first, then delete it.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips"
    - Search without picking a tab first: the search covers every status.
    - Use the **Special Note** for instructions your team must see; customers never see it.
    - Check **Late Invoicing** each week so completed work gets billed.
    - Watch for red **Zone Not Set** badges before invoicing.
    - Use the copy button next to the container # when pasting into chat or email, to avoid pasting a link.
