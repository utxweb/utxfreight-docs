# Dispatch Board

Run daily operations from one screen: filter open orders by status, date and container status, edit key fields in place, assign drivers and equipment, and move orders through the workflow.

## :fontawesome-solid-road: Overview

The **Dispatch** page (header: **Dispatch** — *Dispatched Orders Management*) is the daily operations board for dispatchers and managers. It lists every open order in your current office that is active or coming up, one row per order.

- :fontawesome-solid-list: **Open orders only** — Completed orders never appear; everything else that is dispatched, dated from yesterday onward, or waiting at a tracked container status is loaded
- :fontawesome-solid-circle: **Status buttons** — show only **New Orders**, **App Made** or **Dispatched** orders
- :fontawesome-solid-calendar-days: **Day tabs** — Yesterday, Today, Tomorrow and the next six days, plus **Any Date** and **No Date**, on the date you choose (**Delivery**, **ETA**, **LFD**, **CUT**, or **Pickup** / **Delivery** for ground)
- :fontawesome-solid-filter: **More tabs** — container status, order type, terminal and tag
- :fontawesome-solid-pen: **Inline editing** — change dates, container number, container status, drivers, return terminal and more without opening the order
- :fontawesome-solid-forward: **Workflow buttons** — **Make App.**, **Dispatch** and **Complete** on each row
- :fontawesome-solid-truck: **Header buttons** — **Chassis**, **Legs**, **Details**, **CN Tracking**, **Port Tracking** and **Alerts**
- :fontawesome-solid-envelope: **Email POD** — send the signed POD to the customer from the row

!!! warning "The board does not refresh by itself"
    The Dispatch page loads its orders once, when you open it. Rows you change yourself update straight away, but changes made by other users, drivers or automatic tracking only show after you reload the page.

<!-- TODO: Screenshot — The Dispatch board showing the quick filter, status buttons, header buttons, day tabs and order rows -->

---

## :fontawesome-solid-bolt: Quick Start

1. Click :fontawesome-solid-road: **Dispatch** in the left menu.
2. The board opens with **Remove Filters** active — every loaded order is shown.
3. Click **Today** (or another day tab) to see the orders delivering that day.
4. Click a status button — :fontawesome-solid-star: **New Orders**, :fontawesome-solid-clock: **App Made** or :fontawesome-solid-road: **Dispatched** — to narrow the list. Click it again to turn it off.
5. Click a driver name (or the empty driver cell) to pick a driver, then click the row's green **Dispatch** button when the order is ready.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-tie: **Admin** | Full access |
| :fontawesome-solid-user-tie: **Manager** | Full access |
| :fontawesome-solid-headset: **Dispatch** | Full access. **View History** in the row menu needs **Can manage rates?** |
| :fontawesome-solid-headset: **Customer Service** | Same as Dispatch |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | **No access** — the menu item is hidden and opening the page redirects to **Orders** |
| :fontawesome-solid-user: **Customer**, **Driver**, other roles | No access — redirected to **Orders** |

**How to get there:**

- :fontawesome-solid-arrow-right: From the left menu, click :fontawesome-solid-road: **Dispatch**

!!! info "Current office only"
    With [multiple offices](multi-office.md), the board shows the orders of the office you are currently working in. Switch office to see another office's board.

See [User Roles](user-roles.md) for what each role can do elsewhere.

---

## :fontawesome-solid-list: Which Orders Appear

When the page opens, **no filter is applied** — the black **Remove Filters** button is active and every loaded order is visible. The board is **not** limited to the current week.

An order is loaded when **all** of these are true:

1. Its status is **not Completed**.
2. It belongs to your **current office**.
3. **At least one** of these is true:
    - Its status is **Dispatched** (whatever its dates)
    - Its **Delivery Date**, **ETA**, **Last Free Day** or **Pickup Date** is **yesterday or later**
    - Its status is **New** and its container status is one of **Pre-Pull**, **Dropped at customer**, **Empty at customer**, **Full at customer**, **Empty at yard**, **Full at yard**, **Empty at Eco**, **Full at Eco** or **Inbound**

### Sort order

Rows are sorted by:

1. Status — **New** first, then **App. Taken**, then **Dispatched**
2. Delivery date (earliest first)
3. Appointment time
4. Storage date
5. ETA date

!!! info "The date toggle does not sort"
    The **Delivery** / **ETA** / **LFD** / **CUT** (or **Pickup** / **Delivery**) buttons only change which date the day tabs filter on. The row order never changes.

---

## :fontawesome-solid-filter: Filtering the Board

All filters work instantly in your browser on the orders already loaded — nothing is reloaded from the server. Filters from different groups **combine** (an order must match all of them).

### :fontawesome-solid-circle: Status buttons

Four round buttons sit at the top of the page. Hover over one to see its tooltip.

| Button | Icon | Tooltip | Shows |
|--------|------|---------|-------|
| :fontawesome-solid-star:{ .text-danger } | Red star | **New Orders** | Orders with status **New** |
| :fontawesome-solid-clock:{ .text-warning } | Yellow clock | **App Made** | Orders with status **App. Taken** |
| :fontawesome-solid-road:{ .text-success } | Green road | **Dispatched** | Orders with status **Dispatched** |
| :fontawesome-solid-ban: | Black ban | **Remove Filters** | Clears **every** filter (status, all tabs and the quick filter) |

- Only one status can be active at a time.
- **Clicking an active status button turns it off** — the board then shows all statuses again (other filters stay).
- Choosing a status keeps your day tab, type, terminal and tag filters.

### :fontawesome-solid-magnifying-glass: Quick filter

The search box on the left (placeholder **Filter dispatched orders**) filters the board as you type.

- It matches **all loaded rows**, whatever their status.
- It combines with the status button and tabs that are active. Typing turns off the **Remove Filters** highlight.
- It looks in: order number, container number, booking number, P/O number, deliver-to company and address, equipment name, container status, pickup terminal name, order type, pickup and delivery driver names, the drivers on the order's legs, steamship line, container size, pickup number, customer name, and the order's delivery, ETA, pickup, LFD and cutoff dates (as `YYYY-MM-DD`).
- The match is a simple "contains" match and is not case-sensitive.

!!! tip "Searching beyond the board"
    The quick filter only sees orders loaded on the board. To find any order (including Completed ones), use the order search box in the top-right of the page header, or the **Orders** page — see [Orders](orders.md).

### :fontawesome-solid-calendar-days: Date field toggle and day tabs

**Step 1 — pick the date field.** The button group on the left of the day tabs chooses which date the tabs look at:

| Setup | Button | Day tabs filter on |
|-------|--------|--------------------|
| Intermodal | **Delivery** (default) | Delivery date |
| Intermodal | **ETA** | Estimate Time of Arrival |
| Intermodal | **LFD** | Last Free Day |
| Intermodal | **CUT** | Vessel cutoff date |
| Ground | **Pickup** | Pickup date |
| Ground | **Delivery** (default) | Delivery date |

Switching the field while a day tab is active **turns that day tab off** (the board then shows every date again). Click the day tab again to filter on the new date field. **Remove Filters** does not reset this toggle.

**Step 2 — pick a day.** The tabs are a **rolling window** starting from today:

| Tab | Shows orders whose chosen date is… |
|-----|------------------------------------|
| **Yesterday** | Yesterday |
| **Today** | Today |
| **Tomorrow** | Tomorrow |
| Six day names (e.g. **Mon**, **Tue**…) | Each of the next six days after tomorrow (today + 2 to today + 7). The last one is the same weekday as today, one week ahead |
| **Any Date** | Set (any value) |
| **No Date** | Blank |

- Only one day tab can be active. Click the active tab again to turn it off.

### :fontawesome-solid-box: Container status tabs (intermodal only)

| Tab | Shown |
|-----|-------|
| **Pre-Pull** | Only if your company has a **Pre-Pull** container status configured |
| **Dropped @ Customer** | Always |
| **Empty @ Customer** | Always |
| **Full @ Customer** | Always |
| **Empty @ Yard** | Always |
| **Full @ Yard** | Always |
| **Empty @ Eco** | Only if configured |
| **Full @ Eco** | Only if configured |
| **Inbound** | Only if configured |

Each tab shows the orders whose **C.Status** starts with that status name. "Only if configured" means your company has a custom container status with exactly that name. What each status means for your company is set in [Container Statuses](container-statuses.md).

!!! warning "Choosing a container status clears the other filters"
    Selecting a container status tab turns off the status button, day tab, type, terminal and tag filters, and empties the quick filter. You can then add other filters on top.

### :fontawesome-solid-tags: Order type, terminal and tag tabs

| Group | Tabs | Shown when |
|-------|------|------------|
| Order type | **Import**, **Export**, **Transfer**, **Dry Van** | Each type that is enabled for your company |
| Terminal (intermodal) | **CN**, **CP**, **Termont** | **CN**: CN terminals are set up for your company. **CP**: a terminal named exactly "CP" exists. **Termont**: a terminal whose name contains "Termont" or "Viau" exists. Each tab shows orders whose **pickup terminal name starts with** CN, CP or Termont |
| Tag | One tab per tag (tooltip **Tag** *name*), plus **No Tag** | Tags are set up for your company — see [Order Tagging](order-tagging.md) |

One tab per group can be active; click an active tab to turn it off.

---

## :fontawesome-solid-table-columns: Columns

The columns depend on whether your company runs **intermodal** or **ground** dispatch.

=== "Intermodal"

    | Column | Content | Editable in place |
    |--------|---------|-------------------|
    | **Status / Order#** | Type badge, status badge, order number, **P/O#**, status comment | **P/O#** |
    | **Deliver To** | Delivery company and address (the return terminal for Transfers) | — |
    | **ETA** | Estimate Time of Arrival (Import and Export) | Yes |
    | **Storage (STO) / Demurrage (DEM)** | Import only | Both dates |
    | **Delivery/Pickup** / *App. Time* | Delivery date and appointment time | — |
    | **Size / Steamship / Weight** | Container size, steamship line, weight, **OFF-HIRE** badge | Size, Steamship line |
    | **Container# / Book#/Seal# / Last Free Day** | Container number with badges and copy button; booking number (Export, Transfer) or seal number (Import); **LFD** (Import, Export) | Container number, LFD |
    | **Vessel / ERD / Cutoff Date** | Export only | ERD, CUT |
    | **Terminal / Pickup From / Pickup #** | Pickup terminal (pickup company for Dry Van, shipper for International Export); pickup number (Import) | Terminal, Pickup # |
    | **Chassis #** | Equipment button; chassis number when the equipment is **Borrowed** | Via **Assign Equipment**; chassis number |
    | **C.Status** | Container status | Yes |
    | **Delivery Driver** | First driver (see [Driver Assignment](#driver-assignment)) | Yes |
    | **Return To / Return Date** | Return terminal and return date (no return date on Transfers) | Both |
    | **Return Driver** | Second driver | Yes |
    | **Legs** | Numbered leg badges | Toggle active leg |
    | **Email POD** | POD email button | — |
    | *(last)* | Workflow button and row menu | — |

=== "Ground"

    | Column | Content | Editable in place |
    |--------|---------|-------------------|
    | **Status / Order#** | Type badge, status badge, order number, **P/O#**, status comment | **P/O#** |
    | **Pickup From** | Pickup company and address | — |
    | **Pickup Date** | Pickup date | — |
    | **Deliver To** | Delivery company and address | — |
    | **Delivery Date** / *App. Time* | Delivery date and appointment time | — |
    | **Trailer#** | Trailer number with badges and copy button | Trailer number |
    | **Equipment #** | Equipment button; chassis number when **Borrowed** | Via **Assign Equipment**; chassis number |
    | **Pickup Driver** | First driver | Yes |
    | **Delivery Driver** | Second driver | Yes |
    | **Legs** | Numbered leg badges | Toggle active leg |
    | **Email POD** | POD email button | — |
    | *(last)* | Workflow button and row menu | — |

### :fontawesome-solid-pen: Editing a field in place

1. Click the underlined value. A blank value shows as **N/A** (container number, pickup number, chassis number, P/O#) or **Empty** (other fields).
2. A small popup opens — for example **Enter new container status**, **Enter last free date**, **Enter estimated time of arrival date (ETA)**, **Enter container storage date**, **Enter container demurrage date**, **Enter earliest return date (ERD)**, **Enter cutoff date**, **Enter new return date**, **Enter new return to**, **Enter new container number**, **Enter new pickup number**, **Enter chassis number**, **Select Size**, **Select Steamship Line**, **Select Terminal** or **Enter P/O number**.
3. Pick or type the new value and confirm. It is saved straight away and the row is redrawn.

- Container numbers are saved in upper case. Clearing a container number or chassis number saves the text **N/A**; clearing a pickup number leaves it blank.
- On Dry Van orders, editing the **Return Date** changes the order's pickup date.
- Changing the **Return To** terminal also updates the order's legs and recalculates the order total (terminal charges).

### :fontawesome-solid-tag: Row badges and icons

| Badge / icon | Meaning |
|--------------|---------|
| **CI**, **CX**, **TF**, **DV**, **IX**, **WH** | Order type: Container Import, Container Export, Transfer, Dry Van, International Export, Warehouse (hover for the description) |
| :fontawesome-solid-star: / :fontawesome-solid-clock: / :fontawesome-solid-road: | Status: **New Order**, **Appointment Made**, **Order Dispatched** |
| :fontawesome-solid-right-left: **Transferred** | The order was transferred from another office (hover for the office name) |
| Coloured order number | The order's tag colour |
| Red text under the order number | The order's status comment |
| :fontawesome-solid-fire: | **HAZMAT** |
| :fontawesome-solid-weight-hanging: | Scale (hover for the value) |
| :fontawesome-solid-exclamation: (red) | **DAMAGED** (Import orders only) |
| **OFF-HIRE** (red) | Container is off-hire (Import orders only) |
| Red container size | Size names containing 20, 45, LCL or DRY. **Empty** (grey) when no size is set |
| Brown terminal name | Racine, Termont, Termont 68 or CAST |
| Coloured container status / equipment name | The colour set for that container status in [Container Statuses](container-statuses.md) |
| :fontawesome-solid-copy: | Copy the container number as plain text (toast: **Container number copied**) |
| Red container number | Container status is **Arrived - Missing customs** or **Arrived - On hold** |
| Red **LFD**, **CUT**, **STO** dates; green **ERD** date | Date colour coding |
| :fontawesome-solid-train:{ .text-danger } / :fontawesome-solid-ship:{ .text-warning } / :fontawesome-solid-ship:{ .text-primary } | **Check container status** — see [Per-row tracking](#per-row-tracking-icons) |

---

## :fontawesome-solid-user: Driver Assignment

Each row has **two driver columns**. Which driver goes where depends on the order type:

| Order type | First column (**Delivery Driver** intermodal / **Pickup Driver** ground) | Second column (**Return Driver** intermodal / **Delivery Driver** ground) |
|------------|------------------|-------------------|
| **Import** | Delivery driver | Return (pickup) driver |
| **Transfer** | Pickup driver | — (none) |
| **Export**, **Dry Van**, others | Pickup driver | Delivery driver |

To assign a driver:

1. Click the driver name (or the empty cell).
2. Choose a driver from the list. The list contains the active drivers of your current office, plus a blank entry to remove the driver.
3. The driver is saved and the order's legs are updated to match.

!!! warning "Picking a driver does not dispatch"
    Assigning a driver only saves the driver. The order keeps its status (for example **App. Taken**) until you click **Dispatch** — see [Workflow Buttons](#workflow-buttons).

**Name colours:**

- :fontawesome-solid-circle:{ .text-success } **Green** — that driver's signature step is open.
- :fontawesome-solid-circle:{ .text-danger } **Red** — the step is not open.

When a step counts as open:

| Order type | First column green when… | Second column green when… |
|------------|--------------------------|---------------------------|
| **Import** | Order is **Dispatched**, has no delivery signature or scanned signed POD, and the container status is not **Dropped at customer**, **Returned to terminal** or **Empty at yard** | The order is **Dispatched** *or* has a delivery signature or scanned signed POD, and the container status is not **Returned to terminal** |
| **Dry Van** | Order is **Dispatched** and has no delivery signature, pickup signature or scanned signed POD | Order is **Dispatched** and has no delivery signature or scanned signed POD |
| **Transfer** | Order is **Dispatched**, has no delivery signature, pickup signature or scanned signed POD, and the container status is not **Returned to terminal** | — (no second driver) |
| **Export** and other types | Order is **Dispatched**, has no delivery signature, pickup signature or scanned signed POD, and the container status is not **Dropped at customer**, **Returned to terminal** or **Full at yard** | Order is **Dispatched**, has no delivery signature or scanned signed POD, and the container status is not **Live load**, **Returned to terminal** or **Empty at yard** |

The date under a driver name is when that driver signed.

### :fontawesome-solid-share-from-square: Driver Login Link

With the **Driver Login Links** add-on, a :fontawesome-solid-share-from-square: icon (tooltip **Click to copy**) appears next to a driver name:

- Next to the **delivery driver** — when a delivery driver is assigned and the **first** signature step is open.
- Next to the **pickup driver** — when a pickup driver is assigned and the **second** signature step is open.

1. Click the icon. The link is copied to your clipboard.
2. A toast confirms **Login Link copied for** *DRIVER NAME* — "Send this link using your messaging app or by email".
3. Paste the link in a message or email to the driver. The driver opens it to sign in without a password.

![Toast confirming the driver login link was copied](../images/dispatch-magic-driver-link.png)

The link belongs to the driver, not to the order. It stays valid for **24 hours** from the last time it was copied: copying it again while it is still valid keeps the same link and extends it by another 24 hours; once it has expired, copying creates a new link. If the driver was removed from the order in the meantime, the toast says **Login Link failed to copy** — "Please make sure a driver is assigned to the order". See [Driver Login Links](driver-login-links.md) for details.

---

## :fontawesome-solid-forward: Workflow Buttons

The last column shows one coloured button for the next step, plus a caret that opens the row menu.

| Order status | Button | Next status |
|--------------|--------|-------------|
| **New** | **Make App.** (gold) | **App. Taken** |
| **App. Taken** | **Dispatch** (green) | **Dispatched** |
| **Dispatched** | **Complete** (black) | **Completed** (the row stays, with a grey **Actions** button, until you reload the page) |

The **Dispatch** button only appears on orders at **App. Taken**. If you don't have permission for the next step, a grey **Actions** button is shown instead.

Each button opens a modal; dispatching and completing can email the customer. See [Order Status Workflow](order-workflow.md) for the modals, toasts and emails.

### :fontawesome-solid-ellipsis-vertical: Row menu

Click the caret next to the workflow button:

| Item | What it does | Shown when |
|------|--------------|------------|
| **Quick Edit** | Edit the order in a modal | Always (staff roles) |
| **Documents** | Open the order's documents | Always (staff roles) |
| **View POD** (**View eBoL** for International Export) | Opens the POD PDF in a new tab | Always |
| **View Details** | Opens the order page | Always |
| **Edit Order** | Opens the full order form | Always (staff roles) |
| **Reset Order to New** | After a confirmation (**RESET THE STATUS**), sets the status back to **New** and clears the appointment date, appointment time and delivery date | Status is not New |
| **View History** | Shows the order's change history | Order history is turned on for your account (ask UTX support); Dispatch / Customer Service need **Can manage rates?** |
| **Transfer to Office** | Moves the order to another office | Multi-office, and you belong to another office. Shows **Transfer (Invoiced)** (disabled) for invoiced orders |
| **Remove Signature** | After a confirmation (**CLEAR THE SIGNATURE**), clears the delivery signature, signee and signature date — cannot be undone. The pickup signature is not touched | Order is not Completed and has a delivery signature |

See [Order Status Workflow](order-workflow.md) for Reset, Transfer and View History.

---

## :fontawesome-solid-truck: Assigning Equipment

1. Click the :fontawesome-solid-truck: equipment button in the **Chassis #** (intermodal) or **Equipment #** (ground) column. It shows the current equipment name, or **N/A**.
2. The **Assign Equipment** modal opens with the order number (and container size for intermodal).
3. Pick from the **Equipment** list (active chassis and trailers of your current office, with their availability), or **-- No Equipment --** to release it.
4. Click **Update Order**. A toast **Order Updated** confirms "The chassis for Order *#* was updated to *equipment*" or "The chassis was released from the Order *#*". If the order can't be saved, the toast says **Order not updated!** with the reason.

If the equipment is **Borrowed**, an editable chassis number appears under the button — click it to type the chassis number (**Enter chassis number**).

See [Equipment](equipment.md) for equipment setup and availability.

---

## :fontawesome-solid-route: Legs Column

The **Legs** column shows one numbered badge per leg on the order (hover for the leg's title).

- **Blue** badge — the active leg
- **Grey** badge — inactive leg

Click a badge to make that leg the active one; every other leg on the order becomes inactive. Click the active badge again to turn it off. See [Order Legs & Move Locations](order-legs-and-move-locations.md).

---

## :fontawesome-solid-envelope: Email POD

The **Email POD** column shows an :fontawesome-solid-envelope: button once the order has a driver signature (delivery or pickup), a scanned signed POD, or has been emailed before.

| Button colour | Meaning |
|---------------|---------|
| Blue | Not sent yet (tooltip **Send POD to client**) |
| Green | Last email delivered (tooltip **Last email delivered** + date) |
| Red | The last send failed |

To send:

1. Click the button. The **Send POD to client** modal opens.
2. **To** is filled with the order's delivery email and **Subject** with *&lt;your company&gt; Order # &lt;order number&gt; Completed*. Add **CC** / **BCC** if needed. **To** and **Subject** are required. **To**, **CC** and **BCC** accept several addresses separated by commas or semicolons.
3. Click **Send**. A toast shows **POD Sent!**, or **Sending POD Failed!** with the reason.

See [Order Documents & POD](order-documents-and-pod.md) for POD content.

---

## :fontawesome-solid-toolbox: Header Buttons

The buttons to the right of the status buttons:

| Button | Shown when | What it does |
|--------|-----------|--------------|
| :fontawesome-solid-train:{ .text-danger } **CN Tracking** | CN tracking add-on | Opens CN Rail container tracking (shows **Loading** while it runs) |
| :fontawesome-solid-ship:{ .text-primary } **Port Tracking** | Port of Montreal (Termont) or Racine/CAST tracking add-on | Opens port container tracking (shows **Loading** while it runs) |
| :fontawesome-solid-bell: **Alerts** | Any tracking add-on | Opens the **Container Alerts** page (tooltip **Container Alerts**). A red badge shows the number of unread CN and port alerts |
| :fontawesome-solid-truck: **Chassis** | Always | Opens **Available Equipments** (tooltip **Equipment**) — the active chassis and trailers of your office, most available first |
| :fontawesome-solid-user: **Legs** | Always | Opens **Driver Legs for Today** |
| :fontawesome-solid-user: **Details** | Always | Opens **Driver Legs Details for Today** |

See [Container Tracking](container-tracking.md) and [Container Alerts](container-alerts.md).

### Driver Legs for Today

A table of **Driver** and **Legs**: how many legs each driver has on orders whose **delivery date is today** in your current office, sorted by driver name. Orders of **any status** count, including Completed ones. Legs without a driver are not counted.

### Driver Legs Details for Today

A grid with one row per order delivering today that has at least one leg (**Order #**), and one column per leg (**Leg #1**, **Leg #2**, …), showing the driver of each leg. A cell is blank when that leg has no driver.

### Per-row tracking icons

A small button (tooltip **Check container status**) appears before the container number when the order's pickup terminal is covered by a tracking add-on:

| Icon | Pickup terminal | Add-on |
|------|-----------------|--------|
| :fontawesome-solid-train:{ .text-danger } Red train | CN terminal | CN tracking |
| :fontawesome-solid-ship:{ .text-warning } Orange ship | Racine or CAST terminal | Racine/CAST port tracking |
| :fontawesome-solid-ship:{ .text-primary } Blue ship | Termont terminal | Port of Montreal (Termont) tracking |

Click it to check that container's status in a modal.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: An order doesn't appear on the Dispatch board

!!! info "Solution"
    Check the load rule in [Which Orders Appear](#which-orders-appear): the order must not be Completed, must be in your current office, and must be Dispatched, have a delivery, ETA, LFD or pickup date from yesterday onward, or be New at one of the listed container statuses. Then click **Remove Filters** — a status button, tab or quick filter may be hiding it. If it was just created or changed by someone else, reload the page.

### :fontawesome-solid-user: I picked a driver but the order is still App. Taken

!!! info "Solution"
    Assigning a driver doesn't change the status. Click the green **Dispatch** button on the row and confirm the **Dispatch Order** modal.

### :fontawesome-solid-ban: The accountant can't open Dispatch

!!! info "Solution"
    Accountants have no access to the Dispatch board and are sent to **Orders**. Only Admin, Manager, Dispatch and Customer Service can open it.

### :fontawesome-solid-arrows-rotate: A driver signed but the board still shows the old status

!!! info "Solution"
    The board doesn't refresh automatically. Reload the page to see changes made by drivers, other users or tracking.

### :fontawesome-solid-link: The driver link icon doesn't appear

!!! info "Solution"
    The **Driver Login Links** add-on must be on, a driver must be assigned, and the matching signature step must be open: the first step for the delivery driver, the second step for the pickup driver. See [Driver Login Link](#driver-login-link).

---

!!! tip "Best practices"
    - Start the day with **Today** + **App Made** to see what still needs dispatching.
    - Use the **LFD** and **CUT** toggles with the day tabs to catch storage and cutoff deadlines early.
    - Reload the board before big decisions — it does not auto-refresh.
    - Check **Legs** before assigning more work to a driver.
