# Container Statuses

Manage the list of **container statuses** (such as *Arrived - Awaiting delivery*, *Full at yard* or *Returned to terminal*) that you set on intermodal orders to track where each container is.

## :fontawesome-solid-boxes-stacked: Overview

A container status is a short label that says where the container on an order is right now. It is separate from the **order status** (*New*, *App. Made*, *Dispatched*, *Completed*).

- :fontawesome-solid-list: The **Container Statuses** page (*Manage and reference all container statuses.*) lists every status available in your account.
- :fontawesome-solid-lock: **Built-in** statuses come with UTX Freight. They cannot be edited or deleted.
- :fontawesome-solid-pen: **Custom** statuses are the ones your company adds. You choose the name, the colour and which order types they apply to. You can edit or delete them at any time.
- :fontawesome-solid-palette: Each status has a **colour**. Orders and Dispatch show the status (and the chassis number) in that colour, so you can scan the list at a glance.
- :fontawesome-solid-table-columns: **Job Type Configuration** records which order types (Import, Export, Transfer and so on) a status is meant for, with a short description for each.
- :fontawesome-solid-gears: Some statuses are set **automatically** by the driver app and the yard app, for example **Dropped at customer** when a driver captures a delivery signature on an import.
- :fontawesome-solid-clock-rotate-left: Every change to a custom status is recorded and can be viewed with **View History**.

!!! info "Intermodal only"
    Container statuses are part of the intermodal (container) workflow. The **Manage Container Statuses** menu item, the **C.Status** column and the yard counters only appear when your account runs in intermodal mode.

!!! info "Statuses are shared by all offices"
    The list of container statuses is the same for the whole account. With the Multi-Office add-on, a status created in one office is available in every office.

---

## :fontawesome-solid-bolt: Quick Start

1. Click your **name** in the top menu :fontawesome-solid-arrow-right: **Manage Container Statuses**.
2. Click **New Status** at the top right.
3. Enter the **Status Name**.
4. Pick a **Color** with the colour picker, type a hex code (for example `#28a745`), or click one of the **Quick Color Selection** swatches.
5. Under **Job Type Configuration**, tick the order types the status applies to and optionally write a description for each.
6. Click **Save**.

The status is added to the **Custom** section of the list. Reload the **Orders** or **Dispatch** page and it appears in the container status dropdowns.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access Level |
|------|-------------|
| :fontawesome-solid-user-shield: **Admin** | Full access: view, create, edit and delete custom statuses, view history |
| :fontawesome-solid-user-tie: **Manager** | Full access: view, create, edit and delete custom statuses, view history |
| :fontawesome-solid-headset: **Dispatch** | **View only.** Sees the list, colours and job type configuration. There is no **New Status** button and no **Actions** column |
| :fontawesome-solid-headset: **Customer Service** | **View only** (same access as Dispatch) |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access to the page |
| :fontawesome-solid-user: **All other roles** (Customer, Driver, Yard Worker, Warehouse, Garage) | No access to the page |

!!! info "Managing statuses vs. setting a status on an order"
    The permissions above are for **managing the list** of statuses. Setting the container status **on an order** is done from the order itself (the **C.Status** column or the order form) and follows the order permissions. See [Where Container Statuses Appear](#where-container-statuses-appear).

**How to get there:**

- :fontawesome-solid-arrow-right: Click your **name** at the top of the screen to open the user menu, then click **Manage Container Statuses**.

**Manage Container Statuses** is in the user menu with the other **Manage …** items. It is **not** inside the **Settings** page. See [Navigation & Account](navigation-and-account.md).

---

## :fontawesome-solid-list: The Container Statuses List

The list shows **custom** statuses first, sorted by name, then a dashed separator line, then the **built-in** statuses, also sorted by name.

<!-- TODO: Screenshot — Container Statuses page showing a custom status at the top, the dashed separator, built-in statuses below, and the Actions dropdown open on a custom row -->

### Columns

| Column | What it shows |
|--------|---------------|
| **Status Name** | The status name in bold. This is the exact text saved on orders. |
| **Type** | A **Custom** badge (green) or a **Built-in** badge (blue). |
| **Color** | A small square in the status colour. |
| One column per order type | One column for each order type enabled in your account, for example **Import**, **Export**, **Transfer**, **Dry van**, **International export** and **Warehouse**. A green :fontawesome-solid-circle-check: with the description underneath means the status is enabled for that order type. A grey :fontawesome-solid-circle-xmark: with **N/A** means it is not. |
| **Actions** | Admin and Manager only. Custom statuses have an **Actions** dropdown. Built-in statuses have no actions. |

Only the order types turned on for your account get a column. If your account does not use Warehouse orders, for example, there is no **Warehouse** column.

The footer shows the totals: **Total: _N_ statuses (_X_ built-in, _Y_ custom)**.

### Row Actions

On a custom status, open the **Actions** dropdown:

| Action | What it does |
|--------|--------------|
| :fontawesome-solid-pencil: **Edit** | Opens the **Edit Container Status** window. See [Editing a Custom Status](#editing-a-custom-status). |
| :fontawesome-solid-trash: **Delete** | Asks **Are you sure?**, then deletes the status. See [Deleting a Custom Status](#deleting-a-custom-status). |
| :fontawesome-solid-clock-rotate-left: **View History** | Shows the change history of the status: who created or changed it and what changed. |

### Panels below the list

Two information panels sit under the list:

- **Color Legend**: a suggested meaning for each common colour (see [Color Guide](#color-guide)).
- **Automatic Status Changes**: the statuses the system can set on its own (see [Automatic Status Changes](#automatic-status-changes)).

---

## :fontawesome-solid-lock: Built-in Statuses

Built-in statuses are created with your account. They cannot be edited, renamed, recoloured or deleted. Several of them drive app behaviour (driver app steps, yard counters, Dispatch tabs), which is why they are locked.

The table shows each built-in status with its default colour and the order types it is enabled for out of the box.

| Status | Colour | Enabled for |
|--------|--------|-------------|
| **Arrived - Awaiting delivery** | Green `#28a745` | Import |
| **Arrived - Missing customs** | Red `#dc3545` | Import |
| **Arrived - On hold** | Red `#dc3545` | Import |
| **At customer** | Muted grey `#6c757d` | None |
| **Driver at terminal** | Light green `#90ee90` | Import, Export, Transfer |
| **Dropped at customer** | Red `#dc3545` | Import, Export, Transfer, Dry Van |
| **Empty at customer** | Yellow `#ffc107` | Import, Export, Dry Van, International Export |
| **Empty at yard** | Blue `#007bff` | Import, Export, Transfer, Dry Van |
| **Export** | Orange `#fd7e14` | Export, International Export |
| **Full at customer** | Orange `#fd7e14` | Export, Dry Van, International Export |
| **Full at yard** | Purple `#6f42c1` | Import, Export, Transfer, Dry Van |
| **Live load** | Red `#dc3545` | Import, Export, Dry Van |
| **On rail** | Pink `#e91e63` | Import, Export, Transfer, International Export |
| **On route to customer** | Yellow `#ffc107` | Import, Transfer, Dry Van |
| **On route to terminal** | Yellow `#ffc107` | Import, Export, Transfer, Dry Van, International Export |
| **On route to yard** | Yellow `#ffc107` | None |
| **On vessel** | Dark blue `#003366` | Import, Export, International Export |
| **Ready for 2nd stop** | Muted grey `#6c757d` | None |
| **Returned to terminal** | Green `#28a745` | Import, Export, Transfer, International Export |
| **Reused for export** | Orange `#fd7e14` | Export |

The descriptions for each order type (for example *Container has arrived at terminal and is ready for pickup* for **Arrived - Awaiting delivery** on Import) are shown in the list on the page.

!!! info "Your list may also contain custom statuses set up by UTX"
    Some accounts already had their own statuses before the status manager existed, for example **Pre-Pull**, **Empty at Eco**, **Full at Eco** or **Inbound**. These were carried over as **Custom** statuses (grey, no order types ticked). You can edit them like any other custom status. Be careful renaming them: some names switch on extra Dispatch tabs and counters (see [Dispatch tabs](#dispatch-tabs)).

---

## :fontawesome-solid-plus: Creating a Custom Status

1. Open **Manage Container Statuses**.
2. Click **New Status**. The **New Container Status** window opens.
3. Fill in the fields (see below).
4. Click **Save**.

The window closes and **Container status '_name_' was created successfully.** is shown. Click **Cancel** to close without saving.

<!-- TODO: Screenshot — New Container Status window with Status Name, Color picker and hex field, Quick Color Selection swatches and the Job Type Configuration section -->

### Fields

| Field | Required | Description |
|-------|----------|-------------|
| **Status Name** | Yes | The name shown everywhere in the app and saved on the order. It must be unique. |
| **Color** | Yes | The colour used to display the status. Use the colour picker on the left, or type a hex code in the format `#RRGGBB` (a `#` followed by six characters 0-9 / A-F, for example `#17a2b8`). The two stay in sync. A new status starts with light grey `#cccccc`. |
| **Quick Color Selection** | — | One-click colour swatches. Hover a swatch to see its name: Green, Light Green, Blue, Yellow/Warning, Red/Danger, Purple, Dark Blue, Orange, Pink, Muted Grey, Dark Grey, Light Grey, Teal/Info, Cyan/Success. Clicking a swatch fills in **Color**. |
| **Job Type Configuration** | No | One checkbox per order type enabled in your account: **Import (CI)**, **Export (CX)**, **Transfer (TF)**, **Dry Van (DV)**, **International Export (IX)**, **Warehouse (WH)**. Tick each order type the status applies to and, optionally, type a description in the box below it (for example *Container waiting at the rail yard*). |

!!! warning "Names must be clearly different"
    Two names that only differ by case, spaces or punctuation, such as *Pre-Pull* and *pre pull*, are treated as the same status, so the second one cannot be saved. Choose a name that is clearly different from every existing status.

!!! info "What Job Type Configuration does"
    The ticks and descriptions are shown in the order type columns of the **Container Statuses** list, so your team knows which statuses to use for which kind of order. They do **not** hide a status from any dropdown: every status, built-in and custom, is offered on every order that has a container status field.

---

## :fontawesome-solid-pen-to-square: Editing a Custom Status

1. On the custom status, open **Actions** :fontawesome-solid-arrow-right: **Edit**.
2. The **Edit Container Status** window opens with the same fields as when creating.
3. Change the name, colour or job types.
4. Click **Update**.

**Container status '_name_' was updated successfully.** is shown.

- Unticking an order type under **Job Type Configuration** clears its description.
- A colour change shows up on the Orders and Dispatch pages the next time they are loaded, on every order that has the status.

!!! warning "Renaming does not update existing orders"
    The status **name** is saved as text on each order. If you rename a status, orders that already had the old name keep the old text. To move them to the new name, change the container status on those orders. Search the Orders page with the **CONTAINER STATUS** filter set to the old name to find them before you rename.

---

## :fontawesome-solid-trash: Deleting a Custom Status

1. On the custom status, open **Actions** :fontawesome-solid-arrow-right: **Delete**.
2. Confirm **Are you sure?**.

The page reloads and the status is gone from the list.

!!! danger "Deleting does not clear the status on orders"
    Orders that already have the deleted status keep its name as text. The status is no longer offered in the dropdowns or in the **CONTAINER STATUS** filter, and its custom colour is no longer applied. Change those orders to another status first.

Built-in statuses cannot be deleted.

---

## :fontawesome-solid-gears: Automatic Status Changes

Most status changes are made by your office team. The following changes are made automatically by the mobile apps.

| Trigger | Order type | Container status becomes |
|---------|------------|--------------------------|
| The driver captures the delivery signature (**Sign DELIVERY**) | Container Import | **Dropped at customer** |
| The driver captures the signature when dropping the empty (**Sign DROP**, step *Export: Drop Empty*) | Container Export (not International Export) | **Dropped at customer** |
| The driver taps **Drop Completed** (step *Import: Return empty*) | Container Import | **Returned to terminal** |
| The driver taps **Transfer Completed** | Transfer | **Returned to terminal** |
| The yard worker taps **Full at yard** in the yard app | Any | **Full at yard** |
| The yard worker taps **Empty at yard** in the yard app | Any | **Empty at yard** |

See [Driver Workflow](driver-workflow.md) and [Yard Management](yard-management.md) for the mobile side.

!!! info "Returned to terminal removes the order from the driver app"
    Drivers never see orders whose container status is **Returned to terminal**. Setting it by hand from the office has the same effect: the order leaves the driver's list. Some other statuses also close individual driver steps, for example **Dropped at customer** on an import closes *Import: Deliver to client*. See [When an Order Leaves Your List](driver-workflow.md#when-an-order-leaves-your-list).

---

## :fontawesome-solid-eye: Where Container Statuses Appear

### On the Orders and Dispatch lists

| Where | What you see |
|-------|--------------|
| **C.Status** column | The order's container status in its colour, or a grey **N/A** when none is set. On the **Orders** page you can sort by this column. Click the status to pick a new one from a dropdown (*Enter new container status*) that lists every status, plus an empty choice that clears the status. The new status is saved at once and the row refreshes. |
| **Chassis #** column | The chassis / equipment number is shown in the colour of the order's container status. |
| Container number | Shown in **red** when the container status is **Arrived - Missing customs** or **Arrived - On hold**, so held containers stand out. |

Admins, Managers, Dispatch and Customer Service users can click the **C.Status** value to change it, on both pages. On the **Orders** page, Accountants can also change it if UTX has turned on order management for accountants on your account (ask UTX support). See [Orders](orders.md) and [Dispatch](dispatch.md).

### On the order form

The **Container status** dropdown on the order form lists every status, sorted by name. It appears on **Import**, **Export**, **Transfer** and **International Export** orders. See [Order Form](order-form.md).

### Orders page filter

In the Orders page filters, the **CONTAINER STATUS** card has a dropdown with **All Statuses**, **N/A (not set)** and every status in the list. Use **N/A (not set)** to find orders that have no container status yet.

### Yard counters

At the top of the **Orders** page, next to the order status counters, intermodal accounts see:

- **Empty at Yard**: number of orders with the status **Empty at yard**.
- **Full at Yard**: number of orders with the status **Full at yard**.
- **Pre-Pull**: only when your account has a status named exactly **Pre-Pull**.

Completed orders are not counted.

### Dispatch tabs

The **Dispatch** page has a row of container status tabs that filter the board:

| Tab | Status filtered | Shown |
|-----|-----------------|-------|
| **Pre-Pull** | Pre-Pull | Only when a custom status named exactly **Pre-Pull** exists |
| **Dropped @ Customer** | Dropped at customer | Always |
| **Empty @ Customer** | Empty at customer | Always |
| **Full @ Customer** | Full at customer | Always |
| **Empty @ Yard** | Empty at yard | Always |
| **Full @ Yard** | Full at yard | Always |
| **Empty @ Eco** | Empty at Eco | Only when a custom status named exactly **Empty at Eco** exists |
| **Full @ Eco** | Full at Eco | Only when a custom status named exactly **Full at Eco** exists |
| **Inbound** | Inbound | Only when a custom status named exactly **Inbound** exists |

Clicking a container status tab clears the other Dispatch filters and shows only orders with that status. Click it again to turn it off.

!!! tip "Turning on the optional tabs"
    To get the **Pre-Pull**, **Empty @ Eco**, **Full @ Eco** or **Inbound** tab, create a custom status with that exact name (same spelling and capitals). Renaming or deleting it removes the tab.

!!! info "New orders on the Dispatch board"
    The Dispatch board normally shows dispatched orders and orders with recent dates. A **New** order also appears there when its container status is **Pre-Pull**, **Dropped at customer**, **Empty at customer**, **Full at customer**, **Empty at yard**, **Full at yard**, **Empty at Eco**, **Full at Eco** or **Inbound**. Completed orders never appear.

### Mobile apps

- **Driver app**: each order shows a **CONTAINER STATUS** line when a status is set. Orders with **Returned to terminal** are hidden. See [Driver Workflow](driver-workflow.md).
- **Yard app**: each search result shows **CONTAINER STATUS**, with **Full at yard** / **Empty at yard** buttons. See [Yard Management](yard-management.md).

### Customer names in the status

In the **Orders** column of the **Equipment** page and in the orders CSV export, the statuses **Dropped at customer**, **Empty at customer** and **Full at customer** are shown with the delivery customer's name instead of the word *customer*, for example **Dropped at _Customer name_**. See [Equipment](equipment.md) and [Data Exports](data-exports.md).

---

## :fontawesome-solid-palette: Color Guide

You can give a custom status any colour. The **Color Legend** panel on the page suggests these meanings, which the built-in statuses follow:

| Colour | Suggested meaning |
|--------|-------------------|
| :fontawesome-solid-circle:{ style="color: #28a745" } **Green (Success)** | Container ready for delivery |
| :fontawesome-solid-circle:{ style="color: #90ee90" } **Light Green** | Driver at terminal |
| :fontawesome-solid-circle:{ style="color: #dc3545" } **Red (Danger)** | Critical status requiring attention |
| :fontawesome-solid-circle:{ style="color: #ffc107" } **Orange (Warning)** | Status in progress, monitoring needed |
| :fontawesome-solid-circle:{ style="color: #007bff" } **Blue (Primary)** | Standard operational status |
| :fontawesome-solid-circle:{ style="color: #6f42c1" } **Purple** | Yard storage status |
| :fontawesome-solid-circle:{ style="color: #003366" } **Dark Blue** | Vessel/ocean transport |
| :fontawesome-solid-circle:{ style="color: #fd7e14" } **Orange (Export)** | Export operations |
| :fontawesome-solid-circle:{ style="color: #e91e63" } **Pink** | Rail transport |

Orders with no container status show **N/A** in grey.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-user-lock: There is no **Manage Container Statuses** item in my menu

!!! info "Solution"
    The item only appears for Admin, Manager, Dispatch and Customer Service users, and only on intermodal accounts. Accountants and other roles do not see it. Ask an Admin or Manager.

### :fontawesome-solid-ban: I can't edit or delete a status

!!! info "Solution"
    Built-in statuses (blue **Built-in** badge) are locked and have no **Actions** menu. Only custom statuses can be edited or deleted, and only by Admins and Managers. Dispatch and Customer Service users have view-only access. If you need a variation of a built-in status, create a new custom status with a different name.

### :fontawesome-solid-eye-slash: My new status doesn't show in the dropdown on the Orders page

!!! info "Solution"
    The list of statuses is loaded when the page opens. Reload the **Orders** or **Dispatch** page after creating the status.

### :fontawesome-solid-filter: I ticked only "Import" but the status still shows on Export orders

!!! info "Solution"
    This is expected. **Job Type Configuration** documents which order types a status is meant for; it does not filter the dropdowns. Every status is offered on every order with a container status field.

### :fontawesome-solid-floppy-disk: The status won't save

!!! info "Solution"
    Check that:

    - **Status Name** is filled in and not already used by another status (including names that only differ by case, spaces or punctuation).
    - **Color** is a full hex code: `#` followed by six characters, for example `#1a2b3c`. Short codes like `#abc` and colour names like `red` are not accepted.
    - You are an Admin or Manager.

### :fontawesome-solid-pen: I renamed a status and some orders still show the old name

!!! info "Solution"
    Renaming only changes the status list. Orders store the status name as text, so existing orders keep the old name. After the rename, the old name is no longer in the **CONTAINER STATUS** filter, so find those orders by searching or sorting the Orders page on the **C.Status** column, then set the new status on each one. Next time, filter by the old name **before** renaming.

### :fontawesome-solid-truck: An order disappeared from the driver's phone

!!! info "Solution"
    Check the container status. Orders with **Returned to terminal** are hidden from drivers. This is set automatically when the driver taps **Drop Completed** or **Transfer Completed**, and also when someone in the office sets it by hand. Change the status back if the move is not finished.

### :fontawesome-solid-triangle-exclamation: Why is the container number red?

!!! info "Solution"
    The container status is **Arrived - Missing customs** or **Arrived - On hold**. Once the hold or customs issue is cleared, change the status (for example to **Arrived - Awaiting delivery**) and the number returns to normal.

### :fontawesome-solid-table-columns: There is no Warehouse (or Dry Van) column in the list

!!! info "Solution"
    The list and the **Job Type Configuration** section only show the order types turned on for your account. Contact UTX support if you need another order type enabled.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Keep the list short and consistent"
    - **Reuse built-in statuses** where you can. They drive driver steps, Dispatch tabs and yard counters. Custom statuses only display, except the names **Pre-Pull**, **Empty at Eco**, **Full at Eco** and **Inbound**, which switch on Dispatch tabs (and, for **Pre-Pull**, an Orders counter).
    - **Pick colours with meaning.** Follow the [Color Guide](#color-guide) so red always means "needs attention" and your team can read the board at a glance.
    - **Fill in Job Type Configuration** with a short description for each order type, so new dispatchers know when to use each status.
    - **Check for orders before renaming or deleting** a custom status: filter the Orders page by that status first.
    - **Use Arrived - Missing customs / Arrived - On hold** for held containers, so the container number turns red on every list.
