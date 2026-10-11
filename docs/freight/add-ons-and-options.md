# Add-ons, Account Options & Account Status

Your UTX Freight system is configured by UTX: which add-ons are on, which order types you use, how invoices are numbered, what some roles are allowed to do, and whether the account is active or suspended. This page lists every add-on and account option, what each one changes in the application, and what happens when the account is suspended.

## :fontawesome-solid-puzzle-piece: Overview

- :fontawesome-solid-screwdriver-wrench: **UTX turns these on.** Add-ons and account options are part of your system's configuration. There is no screen in the application where you can switch them on or off yourself. To change one, contact UTX support.
- :fontawesome-solid-eye-slash: **Off means hidden.** When an add-on is off, its menu items, buttons, columns and form fields are not shown at all. Opening one of its pages directly sends you back elsewhere in the application (for example to the **Orders** page, or to the **Charge Types** list with the message *Fuel surcharge addon is not enabled.*).
- :fontawesome-solid-truck-ramp-box: **Shipment mode** sets the shape of the whole application: **intermodal** (containers, terminals, steamship lines) or **ground** (trailers, pickup and delivery).
- :fontawesome-solid-list: **Order types** decide which kinds of orders you can create (for example **Container Import** and **Container Export**).
- :fontawesome-solid-user-lock: **Permission flags** widen or narrow what the **Manager**, **Dispatch**, **Accountant** and **Customer** roles can do, on top of the normal role rules in [User Roles](user-roles.md).
- :fontawesome-solid-ban: **Account suspension** is set by UTX. While the account is suspended, nobody can create, duplicate or upload new orders, but existing orders stay visible.

## :fontawesome-solid-bolt: Quick Start

1. To find out whether a feature is available to you, look for its menu item or button. If it is not there, the add-on is probably off (or your role does not have access).
2. To turn an add-on or option on or off, contact UTX support. Say which one, using the names on this page.
3. If you see the red **System Notice: Account Suspended** banner, contact the UTX accounting department using the details in the banner. Your existing orders remain available while you sort it out.

## :fontawesome-solid-lock: Access & Permissions

| Who | What they can do |
|-----|------------------|
| :fontawesome-solid-user-shield: **UTX super administrator** | Turns add-ons and options on and off in the system configuration. Sees the **Super User Dashboard** (user menu > **Super User**), which lists the **Enabled Addons** and **Configuration** values, and the **Company Suspension** page where the account is suspended or unsuspended |
| :fontawesome-solid-user-shield: **Admin**, :fontawesome-solid-user-tie: **Manager** and all other roles | Use whatever the add-ons and options switch on. Cannot see or change the configuration. See the suspension banner and the blocked buttons when the account is suspended |

!!! info "The Super User menu is for UTX"
    The **Super User** item in the user menu (click your **name** at the top of the screen) is shown only to UTX super administrators. Admins and managers of your company do not see it. Your own company settings are in **Settings**, in the same user menu. See [Application Settings](application-settings.md).

## :fontawesome-solid-plug: Add-ons

Each add-on is a separate switch. The **Enabled Addons** panel on the Super User Dashboard lists them by these names, each marked **ON** or **OFF**.

| Add-on | What appears when it is on | More |
|--------|----------------------------|------|
| `magic_link` | A :fontawesome-solid-share-from-square: icon (tooltip **Click to copy**) next to the delivery driver once the order is ready for the driver, and next to the return (pickup) driver once the container is ready for return. Clicking it copies the driver's Login Link | [Driver Login Links & SMS](driver-login-links.md) |
| `sms` | Built to add an SMS icon next to the delivery driver to text the order to the driver. **Currently unavailable:** the SMS icon is never shown, even with the add-on on | [Driver Login Links & SMS](driver-login-links.md#sms-notifications-currently-unavailable) |
| `fuel_surcharge` | The **Fuel Schedule** menu item (for users who can manage charge types), a **Fuel Surcharge** section with the **Exempt from Fuel Surcharge** checkbox on the customer form, the **Auto compute fuel surcharges for this order** field on the order form, and automatic fuel charges on import, export and transfer orders that are not yet completed or invoiced and have auto compute on. Fuel surcharge charge types (the monthly rates) are hidden from the **Charge Types** list and managed on the **Fuel Schedule** page instead | [Fuel Surcharge](fuel-surcharge.md) |
| `track_n_trace_cn` | CN Rail container tracking: a red :fontawesome-solid-train: icon (tooltip **Check container status**) on orders picked up at a CN terminal, and the **CN Tracking** button on the **Dispatch** page | [Container Tracking](container-tracking.md) |
| `track_n_trace_port_of_montreal` | Termont (Port of Montreal) container tracking: a blue :fontawesome-solid-ship: icon on orders picked up at a Termont terminal, and the **Port Tracking** button on the **Dispatch** page | [Container Tracking](container-tracking.md) |
| `track_n_trace_mtrtml` | MGT (Racine / Cast) container tracking: an orange :fontawesome-solid-ship: icon on orders picked up at a Racine or Cast terminal, and the **Port Tracking** button on the **Dispatch** page | [Container Tracking](container-tracking.md) |
| `textract` | Auto Orders: an **Upload** button next to **Create a new order** on the **Orders** page, and an **AUTO ORDERS** filter box (**Processing**, **Need Review**, **Completed**) for reviewing orders read from uploaded documents. Shown to users allowed to use Auto Orders (Admin, Manager, Dispatch) | [Auto Orders](auto-orders.md) |
| `warehouse` | The **Warehouse** menu group (**Orders**, **Product**, **Location**, **Charges**, **Unit of Measure**, **Building**), the **Warehouse** user role, the **Warehouse** and **Intermodal & Warehouse** customer services, and **Warehouse** / **Intermodal** filter buttons on the customer list and the **Charge Types** list | [Warehouse Overview](warehouse-overview.md) |
| `garage` | The **Garage** menu item (repair shop work orders, invoices and payments), the **Garage** user role and the **Garage** customer service | [Garage Overview](garage-overview.md) |
| `multi_office` | Several offices in one system. Customers, terminals, equipment and other lists are shared by all offices, while orders, invoices and checks stay with their office. Adds **Transfer to Office** to the order row menu on the **Orders** and **Dispatch** pages (Admin, Manager and Dispatch; not for invoiced orders) | [Multi-Office](multi-office.md) |

With any of the three tracking add-ons on, you also get the **Alerts** button on the **Dispatch** page, the [Container Alerts](container-alerts.md) page, the **Alert Email Subscriptions** box in [Application Settings](application-settings.md) and an **Alerts** column in each customer's people list. If a CN terminal and a Racine/Cast terminal tracking add-on could both apply, the CN icon is shown first.

### :fontawesome-solid-tags: Tags

Tags are not in the add-on list. They are turned on when UTX sets up a list of tag names for your account (the **Tags** line on the Super User Dashboard shows them, or **(none)**). With tags configured you get:

- A **Tag / Group** field on the order form.
- A **Default tag** field on the customer form.
- Tag filter buttons (one per tag, plus **No Tag**) on the **Dispatch** page, and tag buttons on the **Orders** page for intermodal accounts.

Users cannot add, rename or delete tags. See [Order Tags](order-tagging.md).

## :fontawesome-solid-sliders: Account Options

These options are also set by UTX. The **Default** column is the product default; your account may be configured differently.

### :fontawesome-solid-truck-ramp-box: Shipment Mode

| Value | What it changes |
|-------|-----------------|
| `intermodal` (default) | Container-based screens. The **Orders** and **Dispatch** lists show **ETA**, **Storage (STO)** / **Demurrage (DEM)**, **Size** / **Steamship** / **Weight**, **Container#** / **Book#/Seal#** / **Last Free Day**, **Vessel** / **ERD** / **Cutoff Date**, **Terminal** / **Pickup From** / **Pickup #**, **Chassis #**, **C.Status** and **Return To** / **Return Date** columns, plus the **Empty at Yard** and **Full at Yard** counters at the top of the **Orders** page. The driver columns are **Delivery** and **Return**. The **Orders** page has the **ORDER TYPE** and **CONTAINER STATUS** filter boxes, and the **Dispatch** page has container status and terminal filters. The user menu includes **Manage Container Sizes**, **Manage Container Statuses**, **Manage Steamship Lines** and **Manage Terminals**. The **Dispatch** date filter offers **Delivery**, **ETA**, **LFD** and **CUT** |
| `ground` | Trailer-based screens. The **Orders** and **Dispatch** lists show **Pickup From** and **Pickup Date** columns, **Trailer#** instead of **Container#**, **Equipment #** instead of **Chassis #**, and **Delivery Date** instead of **Delivery/Pickup**. The driver columns are **Pickup** and **Delivery**. The container columns, container counters and filters, and container menu items above are hidden. The **Dispatch** date filter offers **Pickup** and **Delivery** |

### :fontawesome-solid-list: Order Types

`order_type_enabled` lists the order types you can choose in the **Job type** list on the New order form. It also sets the buttons in the **ORDER TYPE** filter box on the **Orders** page (intermodal accounts) and the order type filters on the **Dispatch** page. The **Dispatch** page has filters for **Import**, **Export**, **Transfer** and **Dry Van** only; there is no **International Export** filter there. Default: **import** and **export**.

| Value | Shown as |
|-------|----------|
| `import` | **Container Import** |
| `export` | **Container Export** |
| `transfer` | **Container Transfer** |
| `dry_van` | **Dry Van Move** |
| `international_export` | **International Export** |

The **Order Types** line on the Super User Dashboard lists the types turned on for your account. See [Order Form](order-form.md).

### :fontawesome-solid-gears: Order, Invoice and Statement Options

| Option | Default | What it does when on |
|--------|---------|----------------------|
| `tag_is_optional` | On | The **Tag / Group** list has a blank choice, so an order can have no tag. When off, there is no blank choice and every order gets a tag. Only matters if tags are configured |
| `order_id_prefix` / `order_id_start` | No prefix / 781000 | Order numbers are the prefix followed by the order's internal number plus the start value |
| `edi_invoicing_enabled` | Off | Adds a **Waybill date** field to import and export orders (the reference field is labelled **Waybill number(reference)**), and an **EDI 210** download in the invoice row menu |
| `internal_pod_enabled` | Off | Adds **View Internal POD** to the order row menu on the **Orders** page, for Admin, Manager and Dispatch. See [Order Documents & POD](order-documents-and-pod.md) |
| `data_audit_enabled` | On | Shows **View History** in the order row menu on the **Orders** and **Dispatch** pages (for users allowed to audit orders; dispatchers need **Can manage rates?**). When off, **View History** is hidden. See [Order Status Workflow](order-workflow.md) |
| `automated_statement_enabled` | Off | Adds the **Automatic Statement schedule for this customer** section to the customer form and the **Delivery Day / Next Date** column and the statement day counters to **Customer Reports**. See [Automatic Statements](automatic-statements.md) |
| `display_detailed_statement` | Off | Customer statements list the orders under each invoice (container number, reference number and order total), in the on-screen statement and in the export. See [Customer Statements](customer-statements.md) |
| `invoice_id_decorator` | On | Invoice numbers start with the first letter of the customer's name and the two-digit invoice year, for example `A26 - 00123`. When off, the invoice number is just the five-digit number, for example `00123` |
| `invoice_template` | `invoice` | Chooses the layout used for printed and emailed invoices. UTX can switch your account to another layout |
| `check_charges_enabled` | On | Shows the **Check Expenses** section on the check form, so you can attach expenses to a check. See [Expenses & Checks](expenses-and-checks.md) |
| `emails_link_back_to_app` | On | Order **Dispatched** and **Completed** notification emails, POD emails and invoice-with-POD emails include a **View your orders** link back into UTX Freight, and the invoicing reminder includes **View Orders Late for Invoicing**. When off, these links are left out. See [Notifications & Emails](notifications-and-emails.md) |

### :fontawesome-solid-user-lock: Permission Flags

These flags apply to every user with the role. They are separate from the per-user **Can manage rates?** setting for dispatchers described in [User Roles](user-roles.md).

| Flag | Default | Role | When on | When off |
|------|---------|------|---------|----------|
| `accountant_can_manage_orders` | On | :fontawesome-solid-calculator: **Accountant** | Can create, edit and manage orders in their office | Can only view orders (and still complete and edit **Dispatched** orders) |
| `accountant_can_manage_checks` | On | :fontawesome-solid-calculator: **Accountant** | Can manage checks | No access to checks |
| `manager_can_manage_checks` | On | :fontawesome-solid-user-tie: **Manager** | Can manage checks | No access to checks |
| `manager_can_view_reports` | On | :fontawesome-solid-user-tie: **Manager** | Can open the reports (analytics) pages | No access to the reports pages |
| `dispatch_can_manage_customers` | Off | :fontawesome-solid-headset: **Dispatch** | Can manage customers and their people | Cannot manage customers |
| `dispatch_can_manage_terminals` | Off | :fontawesome-solid-headset: **Dispatch** | Can manage terminals | Cannot manage terminals |
| `customer_can_manage_orders` | Off | :fontawesome-solid-user: **Customer** | Can create orders from the customer portal, and edit or delete their company's orders while they are still **New** | Can only view their company's orders. See [Customer Portal](customer-portal.md) |

The **Configuration** panel on the Super User Dashboard shows **Customer Can Manage Orders** and **Dispatch Can Manage Customers** as **Yes** or **No**.

## :fontawesome-solid-ban: Account Suspension

UTX can suspend your company's account, for example for late payment. Suspension affects the whole system, for every user.

### :fontawesome-solid-layer-group: Suspension Levels

| Level | Name | Message shown to users |
|-------|------|------------------------|
| 0 | **Active** | No banner (normal use) |
| 1 | **Level 1 - Late Payment Warning** | *Your account has been temporarily suspended due to late payment.* |
| 2 | **Level 2 - Account Suspended** | *Your account is suspended due to payment issues.* |
| 3 | **Level 3 - Service Restricted** | *Your account services are restricted.* |
| 4 | **Level 4 - Collections** | *Your account is under collections review.* |
| 5 | **Level 5 - Account Terminated** | *Your account has been terminated.* |

Every message is followed by the contact details of the UTX accounting department (email and phone).

!!! info "All levels block the same actions"
    The level changes the name and message shown, not what is blocked. Levels 1 to 5 all block the same actions, listed below.

### :fontawesome-solid-triangle-exclamation: What Users See

- A red, dismissible banner titled **System Notice: Account Suspended** at the top of the **Orders** page (and of the dashboard, for users who land there). It shows the level name with the level number (for example **Level 2 - Account Suspended (Level 2)**), the message, and a **Reason:** line if UTX entered a reason.
- The **Create a new order** button turns red with a :fontawesome-solid-ban: icon. Clicking it opens the **Account Suspended - Action Blocked** window (**Order Creation Disabled**), which repeats the level, message and reason and, under **Why is this blocked?**, explains: *New order creation has been disabled due to the current account suspension. To restore access to order creation, please contact your system administrator to resolve the suspension.* Click **Close** to dismiss it.
- With Auto Orders, the **Upload** button also turns red and opens the same window.

<!-- TODO: Screenshot — Orders page with the "System Notice: Account Suspended" banner and the red "Create a new order" button -->

### :fontawesome-solid-hand: What Is Blocked

| Action | While suspended |
|--------|-----------------|
| **Create a new order** | Blocked. The button opens the **Account Suspended - Action Blocked** window. Opening the new order page directly sends you back to the **Orders** list |
| **Duplicate** an order | Blocked. No copies are created and you are returned to the **Orders** list |
| **Upload** (Auto Orders) | Blocked. The button opens the **Account Suspended - Action Blocked** window |
| Viewing, searching and opening existing orders | Still allowed |
| Editing, dispatching and completing existing orders, invoicing | Not blocked by the suspension |

### :fontawesome-solid-unlock: Lifting a Suspension

Only UTX can suspend or unsuspend the account, from **Super User** > **Company Suspension** (**Suspend Company** / **Unsuspend Company**). When the account is unsuspended, the level goes back to **Active**, the banner disappears and order creation, duplication and upload work again.

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: A feature in these docs is missing from my menu

!!! info "Solution"
    The feature is probably an add-on that is off for your account, or your role does not have access. Check the add-on table above, then ask your admin about your role. To turn an add-on on, contact UTX support.

### :fontawesome-solid-toggle-off: Can I switch an add-on or option myself?

!!! info "Solution"
    No. Add-ons, shipment mode, order types, tags and permission flags are part of the system configuration that UTX manages. Contact UTX support with the name of the option you want changed.

### :fontawesome-solid-ban: The Create a new order button is red

!!! info "Solution"
    Your company's account is suspended. Read the banner at the top of the **Orders** page for the level and reason, then contact the UTX accounting department using the details shown. You can keep viewing existing orders in the meantime.

### :fontawesome-solid-copy: Duplicate does nothing and I'm back on the Orders list

!!! info "Solution"
    Duplicating is blocked while the account is suspended. No copies were created. Once the suspension is lifted, duplicate the order again.

### :fontawesome-solid-comment-sms: The sms add-on is on but there is no SMS icon

!!! info "Solution"
    SMS notifications are currently unavailable; the icon is never shown. Use the driver's Login Link instead. See [Driver Login Links & SMS](driver-login-links.md).

### :fontawesome-solid-headset: A dispatcher cannot edit customers or terminals

!!! info "Solution"
    By default, dispatchers cannot manage customers or terminals. UTX can turn on `dispatch_can_manage_customers` and `dispatch_can_manage_terminals` for your account.

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips"
    - When you ask UTX to change an option, name it exactly as on this page (for example `customer_can_manage_orders`) to avoid confusion.
    - Before turning on `customer_can_manage_orders`, decide who on your team will check the orders customers place from the portal.
    - Changing `invoice_id_decorator` changes how invoice numbers look. Agree on it before you start sending invoices, so numbers stay consistent for your customers.
    - Act on a Level 1 late payment warning quickly: order creation is already blocked at Level 1.
