# User Roles & Permissions

Every UTX Freight user has exactly one role. The role decides which menus you see, which pages you can open and what you can change on them.

## :fontawesome-solid-users-gear: Overview

- There are two kinds of users:
    - **Web users** sign in with an email and password. Their roles are **Admin**, **Manager**, **Dispatch**, **Customer Service**, **Accountant**, **Customer**, **Warehouse** and **Garage**. They are people under a company on the **Customers** page.
    - **Mobile users** sign in on a phone with an **Access Code** or a login link. Their roles are **Driver**, **Broker** and **Yard Worker**. They are set up under **Mobile Users**, not on the Customers page. See [Mobile Users](mobile-users.md).
- **Admin** can do everything. **Manager** is close, but it is **not** the same as Admin, even on an account with a single office. See [What a Manager cannot do](#what-a-manager-cannot-do).
- **Customer Service** has exactly the same permissions as **Dispatch**. The only visible difference is one column on the Orders list.
- A **Customer** becomes a **consignee** when their company is linked to one or more shipper/receiver records. They then also see, read-only, deliveries addressed to those records.
- Some permissions depend on **edition options** that UTX sets for your account (for example, whether Managers can see Reports). You can't change these in the app. See [Edition options](#edition-options-set-by-utx).
- Dispatchers have one per-user option, **Can manage rates?**, which is on by default.
- Orders, invoices and checks always belong to an **office**. Most users only work with the offices they are assigned to. See [Offices and permissions](#offices-and-permissions).
- If you open a page your role can't use, nothing is changed and you are sent back. See [When access is denied](#when-access-is-denied).

---

## :fontawesome-solid-bolt: Quick Start

To give a staff member a role (Admin only):

1. Go to **Customers** and select your own company (the default filter).
2. In the **Your Company: <name>** box, click **Add Person** and invite the person. Every new person starts with the **Customer** role.
3. Click **Edit Person** on the new row.
4. Pick the **Role** and check the **Offices** the person works in.
5. Click **Save Changes**.
6. For a **Dispatch** or **Customer Service** user, open **Edit Person** again and check or uncheck **Can manage rates?**, then **Save Changes**.

For drivers, brokers and yard workers, use :fontawesome-solid-user: **Mobile Users** :fontawesome-solid-arrow-right: **Drivers, Brokers & Yard** instead. See [Mobile Users](mobile-users.md).

---

## :fontawesome-solid-shield-halved: Access & Permissions

Who can change roles and user settings:

| Role | What they can do with users |
|------|-----------------------------|
| :fontawesome-solid-user-shield: **Admin** | Only role that can set or change a **Role**, **Company**, **Offices** and **Can manage rates?**. Adds, edits and deletes any person |
| :fontawesome-solid-user-tie: **Manager** | Adds (invites) and edits customer people of the offices they belong to. Can delete people. **Cannot** change anyone's **Role**, **Company** or **Offices** |
| :fontawesome-solid-headset: **Dispatch** / :fontawesome-solid-phone: **Customer Service** | Adds and edits customer people only when your account has dispatch customer management turned on (an edition option set by UTX, off by default). Cannot delete people or change roles |
| :fontawesome-solid-file-invoice-dollar: **Accountant**, :fontawesome-solid-user: **Customer** | Edit their own details only, with **Edit Profile** |
| :fontawesome-solid-warehouse: **Warehouse**, :fontawesome-solid-screwdriver-wrench: **Garage** | No access to people, including their own profile. An Admin updates their details |
| Admin, Manager, Dispatch, Customer Service | Add, edit, enable and disable **mobile users** (drivers, brokers, yard workers) and pick their role |

If someone who is not an Admin sends a role, company or office change anyway, UTX Freight ignores it.

**How to get there:**

- :fontawesome-solid-arrow-right: **Customers** > company box > **Edit Person** (staff and customer people)
- :fontawesome-solid-arrow-right: Your name in the top bar > **Edit Profile** (your own details, for users who are not Admin or Manager)
- :fontawesome-solid-arrow-right: **Mobile Users** > **Drivers, Brokers & Yard** (mobile users)

See [People & Invitations](people-and-invitations.md) for the full person form.

---

## :fontawesome-solid-id-badge: The Roles at a Glance

| Role | Kind | In one sentence |
|------|------|-----------------|
| :fontawesome-solid-user-shield: **Admin** | Web | Full access to everything, including **Settings**, website content, offices and exports |
| :fontawesome-solid-user-tie: **Manager** | Web | Runs the offices they belong to: orders, dispatch, invoices, customers, rates and most lists. No Settings, content, offices or exports |
| :fontawesome-solid-headset: **Dispatch** | Web | Day-to-day operations: orders, dispatch board, drivers, equipment, shippers/receivers. Rates and some lists depend on options |
| :fontawesome-solid-phone: **Customer Service** | Web | Same permissions as Dispatch |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Web | Invoices, checks, taxes, charge and expense types, and (by default) full order management, in their offices |
| :fontawesome-solid-user: **Customer** | Web | Sees their company's orders. Creates and edits new orders only when the edition allows it |
| :fontawesome-solid-eye: **Customer (consignee)** | Web | A Customer whose company is linked to shipper/receiver records. Also sees deliveries addressed to them, read-only |
| :fontawesome-solid-warehouse: **Warehouse** | Web | The Warehouse module only (Warehouse add-on) |
| :fontawesome-solid-screwdriver-wrench: **Garage** | Web | The Garage module only (Garage add-on) |
| :fontawesome-solid-truck: **Driver** | Mobile | Sees and completes only the orders assigned to them |
| :fontawesome-solid-handshake: **Broker** | Mobile | Same mobile rights as a Driver |
| :fontawesome-solid-boxes-stacked: **Yard Worker** | Mobile | Container search and the yard buttons on a phone |

---

## :fontawesome-solid-user-shield: Admin

- Can open every page and do every action in the app.
- Only Admins open **Settings**, **Manage Content** and **Manage Offices**, manage **Alert Email Subscriptions**, mark container alerts read, and use the CSV **Export** buttons.
- Only Admins assign roles, offices and **Can manage rates?**.
- On **Manage Content** and **Manage Offices**, Admins edit what exists. New website pages and new offices are added by UTX.
- An Admin still works in one office at a time. The Orders, Invoices and Checks lists show the office you are currently in. See [Multi-Office](multi-office.md).

## :fontawesome-solid-user-tie: Manager

A Manager has full access to orders, the dispatch board, invoices, customers and most lists for the offices they belong to.

What a Manager **can** do, in their offices:

- Create, edit, dispatch, complete, reset, duplicate, delete and transfer orders, view order history, and edit rates, charges, expenses and legs on orders.
- Use the **Dispatch** board, including **Email POD** and driver login links.
- Manage **Invoices**, **Customers** (including deleting customers and people), **Shipper / Receiver**, **Mobile Users** and **Equipments**.
- Manage **Charge Types**, **Expense Types**, **Manage Taxes**, **Manage Brokers**, **Manage Cities**, **Manage Zones**, **Manage Terminals**, **Manage Container Statuses**, **Manage Document Types**, **Manage Equipment Types** and **Manage Move Locations**.
- Use **Auto Orders** (add-on) and the setup checklist (**Getting started**).
- Open the **Garage** when the Garage add-on is on.
- Receive the **New Order** email (as CC) for orders of their office, and the **Invoicing Reminder** (Monday, Wednesday and Friday).

### What a Manager cannot do

These are Admin-only, whatever the number of offices:

| Not available to Managers | Notes |
|---------------------------|-------|
| **Settings** | See [Application Settings](application-settings.md) |
| **Manage Content** (website content) | Not in the Manager's menu. See [Website Content](website-content.md) |
| **Manage Offices** | Not in the Manager's menu |
| **Manage Steamship Lines**, **Manage Container Sizes** | Not in the Manager's menu. See [Lookup Lists](lookup-lists.md) |
| **Export** buttons (Orders, Customers, Shipper / Receiver, Equipments) | Hidden. See [Data Exports](data-exports.md) |
| **Alert Email Subscriptions** and marking container alerts read or unread | Managers can view the alerts page but not change read status. See [Container Alerts](container-alerts.md) |
| Changing a person's **Role**, **Company** or **Offices**, or **Can manage rates?** | Only Admins see those fields |
| **Expenses** page (left menu) | Admin only. Managers still add expenses on orders |
| **Warehouse** module | Only Admin and Warehouse users. See [Warehouse Overview](warehouse-overview.md) |

Two more Manager permissions depend on edition options:

- **Reports** (including **Aged Receivables (AR)** and **AR Export**): only when manager access to Reports is turned on for your account (on by default).
- **Checks**: only when manager access to Checks is turned on for your account (on by default).

## :fontawesome-solid-headset: Dispatch and :fontawesome-solid-phone: Customer Service

**Dispatch** and **Customer Service** have the same permissions. Use whichever name fits the person's job.

What they can do, in their offices:

- Create, edit, dispatch, complete, reset, duplicate, delete and transfer orders, and place orders on behalf of any customer.
- Use the **Dispatch** board, **Email POD** and driver login links.
- Manage **Shipper / Receiver**, **Mobile Users** (drivers, brokers, yard workers), **Equipments**, **Manage Equipment Types** and **Manage Move Locations**.
- View (not change) **Manage Container Statuses**.
- Use **Auto Orders** (add-on).

What depends on **Can manage rates?** (per user, on by default):

| With **Can manage rates?** on | With it off |
|-------------------------------|-------------|
| Rate, charge and expense sections on orders | Hidden |
| **Order Legs** on the full **Edit Order** form | Hidden (the **Order Legs** section of **Quick Edit** is still shown) |
| **Charge Types**, **Expense Types**, **Manage Cities** (and **Fuel Schedule** with the add-on) | Not available |
| **View History** (order audit) | Not available |

What depends on edition options:

- **Customers** (and adding/editing customer people): only when dispatch customer management is turned on for your account (off by default). Even then, Dispatch can't delete customers or people.
- **Manage Terminals**: only when dispatch terminal management is turned on for your account (off by default).

Never available to Dispatch or Customer Service: **Invoices**, **Checks**, **Expenses** page, **Manage Taxes**, **Manage Zones**, **Manage Brokers**, **Manage Document Types**, **Manage Steamship Lines**, **Manage Container Sizes**, **Reports**, **Settings**, the setup checklist, **Garage** and **Warehouse**.

!!! info "The one difference: the Invoiced / Rate column"
    On the **Orders** list, **Customer Service** users see the **Invoiced / Rate** column (the order total), but without the button that opens the order's invoice. **Dispatch** users don't see that column at all. Everything else is identical.

## :fontawesome-solid-file-invoice-dollar: Accountant

Accountants work only with the offices they belong to.

- **Invoices**: full access.
- **Checks**: only when accountant access to Checks is turned on for your account (on by default).
- **Charge Types**, **Expense Types** and **Manage Taxes**: full access. **Fuel Schedule** with the Fuel Surcharge add-on.
- **Orders**, with accountant order management on (the default): full order management. Create, edit, change status, reset, go back one step, duplicate, delete, transfer between offices, open the scanned and signed POD files and **View History**.
- **Orders**, with accountant order management off: view orders, plus edit and **Complete** orders that are **Dispatched**. They can't open the scanned or signed POD files.

Accountants do **not** have:

- The rate, charge and expense sections of the order form (for Admin, Manager and Dispatch with **Can manage rates?**), the **Order Legs** section, or the **Administrative information** and **Appointment Information** sections of **Edit Order** (Admin, Manager, Dispatch). See [Order Rates, Charges & Expenses](order-charges-and-expenses.md).
- **Place the order on behalf of**. An order an Accountant creates is placed under their own name.
- **Dispatch** board, **Email POD**, the **View** POD link in the order menu, **Customers**, **Shipper / Receiver**, **Equipments**, **Mobile Users**, **Expenses** page, **Reports** (including AR), **Settings** or the setup checklist.

!!! info "Accountants and aged receivables"
    Accountants can't open **Reports**, but they can use the **AR Aging** filter and **AR aging detail** export on the Invoices page. See [Aged Receivables](aged-receivables.md).

## :fontawesome-solid-user: Customer

A Customer is a person under one of your customer companies. They see the customer portal. See [Customer Portal](customer-portal.md).

- Sees **all orders placed by anyone in their company**, in the office(s) they belong to. Not only their own.
- Opens **View Details** and the scanned or signed POD documents of those orders.
- Creates orders **only** when your account has customer order entry turned on (an edition option set by UTX, off by default). Even then, they can only edit an order while its status is **New**. Once you make an appointment or dispatch it, the order becomes read-only for them.
- Can't change order status, duplicate, transfer, view history, or see rates, totals, invoices or drivers.
- Uses the shipper/receiver search while filling the order form, but has no **Shipper / Receiver** page.
- Edits their own details with **Edit Profile**.

!!! warning "Customer people and offices"
    A customer person gets the office you are working in when you invite them. **Edit Person** doesn't show the **Offices** field for people of customer companies, so invite customer people from the office whose orders they should see. A customer only sees orders of the offices they belong to.

### :fontawesome-solid-eye: Consignee behaviour

A Customer is treated as a **consignee** when their company is linked to one or more shipper/receiver records. On top of their company's orders, they see, read-only, every order whose delivery is addressed to a linked record, **even when the order was placed by another customer**. The Orders page shows a **Consignee view:** banner and pricing is not shown. Linking is done on the shipper/receiver, with the **Linked Customer Account** field. See [Shippers & Receivers](shippers-receivers.md) and [Customer Portal](customer-portal.md).

## :fontawesome-solid-warehouse: Warehouse

- Only offered in the **Role** list when the Warehouse add-on is on.
- Full access to the Warehouse module: **Orders**, **Product**, **Location**, **Charges**, **Unit of Measure** and **Building**. Also **Charge Types** (and **Fuel Schedule** with the add-on).
- No freight **Orders**, **Dispatch**, **Invoices**, **Customers** or other freight pages.
- Can't open their own **Edit Profile**.

See [Warehouse Overview](warehouse-overview.md).

## :fontawesome-solid-screwdriver-wrench: Garage

- Only offered in the **Role** list when the Garage add-on is on, and only has permissions while the add-on is on.
- Full access to every Garage page (**Work Orders**, **Invoices** and payments, **Equipment**, **Parts**, **Templates**, **Customers**, **Taxes**, **Settings** and **Reports**) for the offices they belong to.
- No freight pages and no **Edit Profile**.

See [Garage Overview](garage-overview.md).

## :fontawesome-solid-truck: Driver and :fontawesome-solid-handshake: Broker

Drivers and Brokers are **mobile users**, not web users. They don't have an email and password and are not people on the Customers page.

- They sign in on a phone with their **Access Code** (5 to 16 characters, set on the mobile user), or with a login link copied by dispatch (Driver Login Links add-on). See [Mobile Users](mobile-users.md) and [Driver Login Links](driver-login-links.md).
- They see **only the orders assigned to them** (as delivery or return driver) that are **Dispatched**. Orders marked **Returned to terminal** drop off their list.
- On those orders they can open the details, collect the delivery and pickup signatures (POD) and mark the container returned. They can't change which driver is assigned.
- A Broker has exactly the same mobile rights as a Driver.
- Only **active** mobile users can sign in with an **Access Code**.

See [Driver Workflow](driver-workflow.md).

## :fontawesome-solid-boxes-stacked: Yard Worker

- A mobile user with the **Yard Worker** role, signed in with an **Access Code**.
- Only has the container search and the yard buttons (**Ground Container**, **Full at yard**, **Empty at yard**). No order list and no POD signatures.
- Not offered in the order driver lists.

See [Yard Management](yard-management.md).

---

## :fontawesome-solid-user-gear: How Roles Are Assigned

### Web users

- Every new person, invited by anyone, is created with the **Customer** role.
- Only an **Admin** can change it, from **Customers** > **Edit Person**. The **Role** and **Offices** fields only appear for people under **your own company**, and never for the account **Owner**.
- The **Role** list contains **Admin**, **Customer**, **Accountant**, **Dispatch**, **Manager** and **Customer Service**, plus **Warehouse** with the Warehouse add-on and **Garage** with the Garage add-on.
- To turn a customer contact into a staff member, an Admin first changes the person's **Company** to your own company and saves, then opens **Edit Person** again to set the **Role** and **Offices**.
- **Can manage rates?** appears only after the role has been saved as **Dispatch** or **Customer Service**. Its note reads *Specifies if this Dispatch can manage rates and charges across the app*.

See [Assigning Staff Roles and Offices](people-and-invitations.md#assigning-staff-roles-and-offices).

### Mobile users

Admin, Manager, Dispatch and Customer Service users pick **Driver**, **Broker** or **Yard Worker** in the **Role** field of the mobile user form. A mobile user belongs to one office. See [Mobile Users](mobile-users.md).

---

## :fontawesome-solid-sliders: Edition Options (Set by UTX)

These options are set by UTX in your account's configuration. They apply to **all** users of that role at once. They are not in **Settings** and can't be changed from the app. Contact UTX support to change one.

| Option | Default | What it changes |
|--------|---------|-----------------|
| Accountant order management | On | **On**: Accountants have full order management in their offices. **Off**: view only, plus edit and **Complete** on **Dispatched** orders |
| Accountant access to Checks | On | Accountants see **Checks** and manage the checks of their offices |
| Manager access to Checks | On | Managers see **Checks** and manage the checks of their offices |
| Manager access to Reports | On | Managers see the **Reports** menu (all reports, including AR) |
| Dispatch customer management | Off | Dispatch and Customer Service see **Customers** and can add and edit customers and customer people (not delete) |
| Dispatch terminal management | Off | Dispatch and Customer Service see **Manage Terminals** with full access |
| Customer order entry | Off | Customers can **Create a new order** and edit orders still **New** |

The defaults above are the standard values. Your account may have been set up differently.

Add-ons also change what roles see: **Garage**, **Warehouse**, **Fuel Surcharge** (Fuel Schedule), **Driver Login Links**, Container Tracking (container alerts), Auto Orders and multi-office. See [Add-ons & Options](add-ons-and-options.md).

The only per-user option is **Can manage rates?** for Dispatch and Customer Service users. It is **on by default** and only an Admin can change it.

---

## :fontawesome-solid-building: Offices and Permissions

- **Orders, invoices and checks are always office-scoped.** Managers, Dispatch, Customer Service and Accountants only see and change those of the offices they belong to. The lists show the office you are currently working in.
- **Customers** see orders of the office(s) they belong to.
- **Shared lists** (customers, shippers/receivers, cities, zones, terminals, brokers, document types, mobile users, equipment, equipment types, charge types, expense types, move locations):
    - **Without multi-office**: a user can manage the records of the offices they belong to.
    - **With multi-office**: these records are shared, and users who can manage them can manage records of every office.
- Permission to manage **Taxes** and **container statuses** is not limited by office.
- **Garage** records stay office-scoped for Managers and Garage users. **Warehouse orders** are not office-scoped.
- **Transfer to Office** (multi-office only) moves an order to another office **you belong to**. An invoiced order can't be transferred.
- With multi-office, users who belong to more than one office switch office from the top bar. Admins only switch between the offices they are assigned to.

See [Multi-Office](multi-office.md).

---

## :fontawesome-solid-table-cells: Roles & Permissions Matrix

How to read the tables:

- **Yes**: always allowed. **No** (or —): not allowed. The menu item or button is hidden unless the cell says otherwise.
- **R**: Dispatch / Customer Service with **Can manage rates?** on (the default).
- Edition options are named in full. Add-ons are noted in the first column.
- "Own offices" means the offices the user belongs to.
- Drivers, Brokers and Yard Workers have no access to any of these web pages. See [Mobile users](#mobile-users-matrix) below.

### Orders

| Feature | Admin | Manager | Dispatch / Customer Service | Accountant | Customer | Warehouse | Garage |
|---------|-------|---------|-----------------------------|------------|----------|-----------|--------|
| See orders | Yes | Own offices | Own offices | Own offices | Their company's orders, own offices (+ consignee deliveries) | No | No |
| **Create a new order** | Yes | Yes | Yes | With accountant order management (placed under their own name) | With customer order entry | No | No |
| **Place the order on behalf of** a customer | Yes | Yes | Yes | No | No | No | No |
| **Edit Order** / **Quick Edit** | Yes | Yes | Yes | Yes with accountant order management; otherwise Dispatched orders only | With customer order entry, status **New** only | No | No |
| Rates, charges and expenses on the order | Yes | Yes | R | No | No | No | No |
| **Order Legs** on the order | Yes | Yes | **Quick Edit**: Yes. **Edit Order**: R | No | No | No | No |
| Status actions (**Make App.**, **Dispatch**, **Complete**) | Yes | Yes | Yes | Yes with accountant order management; otherwise **Complete** on Dispatched orders | No | No | No |
| **Reset Order to New**, **Go Back 1 Step** | Yes | Yes | Yes | With accountant order management | No | No | No |
| **Delete Order** (not invoiced) | Yes | Yes | Yes | With accountant order management | No | No | No |
| **Duplicate** | Yes | Yes | Yes | With accountant order management | No | No | No |
| **View History** (order audit, when enabled for your account) | Yes | Yes | R | With accountant order management | No | No | No |
| Sign POD / **Remove Signature** | Yes | Yes | Yes | With accountant order management | No | No | No |
| **View** POD (order menu) | Yes | Yes | Yes | No | No | No | No |
| Open scanned / signed POD documents | Yes | Yes | Yes | With accountant order management | Yes | No | No |
| **Email POD** to client | Yes | Yes | Yes | No | No | No | No |
| **Invoiced / Rate** column on Orders | Yes | Yes | Customer Service only (no invoice button) | Yes | No | No | No |
| **Not Invoiced** / **Late Invoicing** tabs | Yes | Yes | No | No | No | No | No |
| **Transfer to Office** (multi-office) | Yes | Yes | Yes | With accountant order management | No | No | No |
| **Auto Orders** (add-on) | Yes | Yes (see [Auto Orders](auto-orders.md)) | Yes (see [Auto Orders](auto-orders.md)) | No | No | No | No |
| Copy driver Login Link (add-on) | Yes | Yes | Yes | Orders page only, with accountant order management | No | No | No |
| **Dispatch** board | Yes | Yes | Yes | No | No | No | No |
| View container alerts (tracking add-on) | Yes | Yes | Yes | No menu link | No menu link | No menu link | No menu link |
| Mark container alerts read / **Mark All Read** | Yes | No | No | No | No | No | No |

### Billing and accounting

| Feature | Admin | Manager | Dispatch / Customer Service | Accountant | Customer | Warehouse | Garage |
|---------|-------|---------|-----------------------------|------------|----------|-----------|--------|
| **Invoices** | Yes | Own offices | No | Own offices | No | No | No |
| **Checks** | Yes | Own offices, with manager checks | No | Own offices, with accountant checks | No | No | No |
| **Expenses** page (all expense lines, left menu) | Yes | No menu item | No menu item | No menu item | No menu item | No menu item | No menu item |
| **Charge Types** (order charge / rate types) | Yes | Yes | R | Yes | No | Yes | No |
| **Expense Types** | Yes | Yes | R | Yes | No | No | No |
| **Manage Taxes** | Yes | Yes | No | Yes | No | No | Via **Garage** > **Taxes** |
| **Fuel Schedule** (Fuel Surcharge add-on) | Yes | Yes | R | Yes | No | Yes | No |
| **Reports** (all reports) | Yes | With manager reports | No | No | No | No | No |
| **Aged Receivables (AR)** / **AR Export** | Yes | With manager reports | No | No | No | No | No |

!!! info "Expenses vs Expense Types"
    **Expense Types** (user menu) is the list of expense categories you pick from on an order, such as fuel or tolls. The **Expenses** page (left menu, Admin only) lists the actual expense lines recorded on orders across all offices. Expense lines are added on orders by users who can manage rates. See [Expenses & Checks](expenses-and-checks.md) and [Charge Types & Taxes](charge-types-and-taxes.md).

!!! info "What \"manage rates\" covers"
    Rates are managed in several places. **Charge Types** holds the order charge (rate) types. Zone rates are edited in **Manage Zones**, terminal rates in **Manage Terminals**, and city zones in **Manage Cities**, each with its own rules below.

### Customers, people and contacts

| Feature | Admin | Manager | Dispatch / Customer Service | Accountant | Customer | Warehouse | Garage |
|---------|-------|---------|-----------------------------|------------|----------|-----------|--------|
| **Customers** (create, edit) | Yes | Yes | With dispatch customer management | No | No | No | No |
| Delete a customer (only shown when it has no people and no invoices) | Yes | Yes | No | No | No | No | No |
| Add / edit customer people | Yes | Own offices | With dispatch customer management, own offices | No | No | No | No |
| Change **Role**, **Company**, **Offices**, **Can manage rates?** | Yes | No | No | No | No | No | No |
| Delete a person | Yes | Yes | No | No | No | No | No |
| **Edit Profile** (own details) | Via **Customers** | Via **Customers** | Yes | Yes | Yes | No | No |
| **Shipper / Receiver** | Yes | Yes | Yes | No | Search only, in the order form | No | No |
| **Manage Brokers** | Yes | Yes | No | No | No | No | No |
| **Mobile Users** (Drivers, Brokers & Yard) | Yes | Yes | Yes | No | No | No | No |

### Lists and setup

| Feature | Admin | Manager | Dispatch / Customer Service | Accountant | Customer | Warehouse | Garage |
|---------|-------|---------|-----------------------------|------------|----------|-----------|--------|
| **Manage Cities** | Yes | Yes | R | No | No | No | No |
| **Manage Zones** (incl. zone rates) | Yes | Yes | No | No | No | No | No |
| **Manage Terminals** (intermodal, incl. terminal rates) | Yes | Yes | With dispatch terminal management | No | No | No | No |
| **Manage Container Statuses** (intermodal) | Yes | Yes | View only | No | No | No | No |
| **Manage Container Sizes** (intermodal) | Yes | No | No | No | No | No | No |
| **Manage Steamship Lines** (intermodal) | Yes | No | No | No | No | No | No |
| **Manage Document Types** | Yes | Yes | No | No | No | No | No |
| **Manage Move Locations** | Yes | Yes | Yes | No | No | No | No |
| **Equipments** and **Manage Equipment Types** | Yes | Yes | Yes | No | No | No | No |
| **Getting started** (setup checklist) | Yes | Yes | No | No | No | No | No |

### Administration and add-ons

| Feature | Admin | Manager | Dispatch / Customer Service | Accountant | Customer | Warehouse | Garage |
|---------|-------|---------|-----------------------------|------------|----------|-----------|--------|
| **Settings** | Yes | No | No | No | No | No | No |
| **Manage Content** (website content) | Yes (edit existing pages) | No | No | No | No | No | No |
| **Manage Offices** | Yes (new offices are added by UTX) | No | No | No | No | No | No |
| **Alert Email Subscriptions** (tracking add-on, in Settings) | Yes | No | No | No | No | No | No |
| CSV **Export** (Orders, Customers, Shipper / Receiver, Equipments) | Yes | No | No | No | No | No | No |
| **Garage** (Garage add-on) | Yes | Own offices | No | No | No | No | Own offices |
| **Warehouse** (Warehouse add-on) | Yes | No | No | No | No | Yes | No |

### Mobile users matrix

| Feature | Driver | Broker | Yard Worker |
|---------|--------|--------|-------------|
| Sign in with **Access Code** | Yes | Yes | Yes |
| Sign in with a Login Link (add-on) | Yes | Yes | Not offered (links are copied from the order driver columns) |
| See orders | Only Dispatched orders assigned to them | Same as Driver | No order list |
| Delivery / pickup signatures (POD) | On assigned orders | On assigned orders | No |
| Mark container returned | On assigned orders | On assigned orders | No |
| Change the assigned driver | No | No | No |
| Container search, **Ground Container**, **Full at yard**, **Empty at yard** | No | No | Yes |
| Web pages (Dispatch, Invoices, lists, Settings) | No | No | No |

---

## :fontawesome-solid-bars: Menus by Role

### Left sidebar

| Sidebar item | Admin | Manager | Dispatch / CS | Accountant | Customer | Warehouse | Garage |
|--------------|-------|---------|---------------|------------|----------|-----------|--------|
| **Getting started** / **Setup check** / **Setup complete** | Yes | Yes | — | — | — | — | — |
| **Orders** | Yes | Yes | Yes | Yes | Yes | — | — |
| **Dispatch** | Yes | Yes | Yes | — | — | — | — |
| **Warehouse** (add-on) | Yes | — | — | — | — | Yes | — |
| **Garage** (add-on) | Yes | Yes | — | — | — | — | Yes |
| **Invoices** | Yes | Yes | — | Yes | — | — | — |
| **Fuel Schedule** (add-on) | Yes | Yes | R | Yes | — | Yes | — |
| **Expenses** | Yes | — | — | — | — | — | — |
| **Checks** | Yes | With option | — | With option | — | — | — |
| **Customers** | Yes | Yes | With option | — | — | — | — |
| **Shipper / Receiver** | Yes | Yes | Yes | — | — | — | — |
| **Equipments** | Yes | Yes | Yes | — | — | — | — |
| **Mobile Users** | Yes | Yes | Yes | — | — | — | — |
| **Reports** | Yes | With option | — | — | — | — | — |

### User menu (your name, top bar)

| Role | Items shown |
|------|-------------|
| **Admin** | **Settings**, all **Manage …** lists, **Charge Types**, **Expense Types**, **Manage Taxes**, **Manage Content**, **Manage Offices**, **Logout** |
| **Manager** | **Manage Brokers**, **Manage Cities**, **Manage Clients**, **Manage Container Statuses**, **Manage Document Types**, **Manage Drivers**, **Manage Equipment Types**, **Manage Move Locations**, **Manage Terminals**, **Manage Zones**, **Charge Types**, **Expense Types**, **Manage Taxes**, **Logout** |
| **Dispatch / Customer Service** | **Edit Profile**, **Manage Clients**, **Manage Container Statuses** (view only), **Manage Drivers**, **Manage Equipment Types**, **Manage Move Locations**, **Logout**. With **Can manage rates?**: **Manage Cities**, **Charge Types**, **Expense Types**. With dispatch terminal management: **Manage Terminals** |
| **Accountant** | **Edit Profile**, **Charge Types**, **Expense Types**, **Manage Taxes**, **Logout** |
| **Customer** | **Edit Profile**, **Logout** |
| **Warehouse** | **Charge Types**, **Logout** |
| **Garage** | **Logout**. Garage pages have their own left menu (**Work Orders**, **Invoices**, **Equipment**, **Parts**, **Templates**, **Customers**, **Taxes**, **Settings**, **Reports**, **Back to TMS**) and no user menu |

**Manage Container Sizes**, **Manage Container Statuses**, **Manage Steamship Lines** and **Manage Terminals** only appear on intermodal (container) accounts. See [Navigation & Account](navigation-and-account.md).

---

## :fontawesome-solid-house: Where Each Role Lands After Sign-In

| Role | Starting page |
|------|---------------|
| Admin, Manager, Dispatch, Customer Service, Accountant, Customer | **Orders** |
| Warehouse | **Warehouse** > **Orders** (with the Warehouse add-on; otherwise the home page) |
| Driver, Broker | Their list of assigned Dispatched orders on the phone. See [Driver Workflow](driver-workflow.md) |
| Yard Worker | The container search (phone layout). See [Yard Management](yard-management.md) |

---

## :fontawesome-solid-envelope: Emails by Role

| Email | Who receives it |
|-------|-----------------|
| **New Order #<number> from <company>** | **To:** Admins who have **Email Notifications** and **Active for orders** on. **CC:** Managers of the order's office with **Email Notifications** on |
| **Order #<number> is now dispatched** / **Order Completed for order #<number>** | The person the order is placed for, if their **Email Notifications** is on |
| **Invoicing Reminder** (Monday, Wednesday and Friday, only when orders are waiting to be invoiced) | Admin, Manager and Accountant users with **Active for orders** on, in every office (not affected by **Email Notifications**) |
| Container tracking alert digest (tracking add-on) | Users of your own company that an Admin subscribed under **Alert Email Subscriptions** in **Settings** |
| Invitation and password reset | The person concerned, whatever their role |

See [Notifications & Emails](notifications-and-emails.md) and [Email Notifications](people-and-invitations.md#email-notifications).

---

## :fontawesome-solid-trash: Deleting Users

- Only **Admin** and **Manager** can delete a person, from **Customers** > **Delete** on the person's row. Anyone else gets **Access Denied.**
- Deleting is permanent from the app. It turns off the person's notifications and changes their stored email, so they can't sign in any more. Their orders keep their history. See [Deleting a Person](people-and-invitations.md#deleting-a-person).
- **Active for orders** off does **not** block sign-in. To remove someone's access, delete the person.
- Mobile users are not deleted this way. Disable them under **Mobile Users** so they can't sign in. See [Mobile Users](mobile-users.md).

---

## :fontawesome-solid-ban: When Access Is Denied

- Menu items and buttons you can't use are hidden.
- If you open a page your role doesn't allow (for example from a bookmark or a typed address), UTX Freight cancels the action and sends you back to your starting page with an alert. Nothing is saved.
- Some pages redirect instead: opening **Dispatch** without access sends you to **Orders**, and opening the setup checklist shows **You do not have access to the setup checklist.**
- Pages of an add-on that is off redirect you, whatever your role (for example **Container tracking is not enabled.**).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-user-tie: We have one office. Isn't a Manager the same as an Admin?

!!! info "Solution"
    No. Even with one office, Managers can't open **Settings**, **Manage Content**, **Manage Offices**, **Manage Steamship Lines** or **Manage Container Sizes**, can't use the **Export** buttons, can't manage alert subscriptions or mark alerts read, and can't change roles. **Reports** and **Checks** depend on edition options. Give the **Admin** role to whoever needs those.

### :fontawesome-solid-user-lock: My new dispatcher only sees customer screens

!!! info "Solution"
    Every new person starts as **Customer**. An Admin must open **Edit Person**, set the **Role** to **Dispatch** (or **Customer Service**) and check the **Offices**, then save. The person must be under your own company for the **Role** field to appear.

### :fontawesome-solid-dollar-sign: A dispatcher can't see rates, charge types or View History

!!! info "Solution"
    **Can manage rates?** is off on their profile. An Admin opens **Customers** > **Edit Person** for that dispatcher, checks **Can manage rates?** and saves.

### :fontawesome-solid-building: A dispatcher can't see Customers or Manage Terminals

!!! info "Solution"
    These are edition options set by UTX (dispatch customer management and dispatch terminal management), off by default. They apply to all Dispatch and Customer Service users at once. **Manage Terminals** also only exists on intermodal (container) accounts. Contact UTX support to turn them on.

### :fontawesome-solid-chart-bar: A Manager doesn't see Reports or Checks

!!! info "Solution"
    Manager access to Reports or Checks is turned off for your account. These are edition options set by UTX. Contact UTX support.

### :fontawesome-solid-file-invoice-dollar: An accountant can only view orders

!!! info "Solution"
    Accountant order management is turned off for your account. With it off, Accountants can only view orders, and edit and complete **Dispatched** orders. Contact UTX support to turn it on.

### :fontawesome-solid-file-invoice-dollar: An accountant can't change the rate on an order

!!! info "Solution"
    That is expected. The rate, charge and expense sections of the order form are for Admin, Manager and Dispatch with **Can manage rates?**. Ask one of them to change the order's rate.

### :fontawesome-solid-user: A customer can't create orders

!!! info "Solution"
    Customer order entry is turned off for your account (the default). Contact UTX support if your customers should create orders. When it is on, customers can only edit an order while it is **New**.

### :fontawesome-solid-eye: A customer sees orders they didn't place

!!! info "Solution"
    Customers see every order placed by anyone in their company. If their company is linked to shipper/receiver records, they also see deliveries addressed to those records (consignee view), read-only.

### :fontawesome-solid-truck: Where do I set a driver's password?

!!! info "Solution"
    Drivers, Brokers and Yard Workers don't have passwords. Give them their **Access Code**, or copy them a login link. See [Mobile Users](mobile-users.md).

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Roles"
    - Keep the number of **Admins** small. Use **Manager** for office leads and **Dispatch** or **Customer Service** for operations staff.
    - Turn off **Can manage rates?** for dispatchers who shouldn't see or change pricing.
    - Give customer contacts a single office.
    - Set up drivers, brokers and yard workers as **Mobile Users**, never as people with an email and password.
    - Delete people who leave. Unchecking **Active for orders** doesn't stop them from signing in.
