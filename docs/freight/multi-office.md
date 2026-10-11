# Multi-Office

Run several offices (branches) in one UTX Freight account: each office keeps its own orders, invoices and checks, while customers, drivers, equipment and other master data are shared.

## :fontawesome-solid-building: Overview

**Multi-Office** is an add-on (Pro Module). UTX turns it on for your account; it is not a toggle in **Settings**. See [Add-ons & Options](add-ons-and-options.md).

- :fontawesome-solid-building: **Offices are set up by UTX.** Admins can see the list of offices under **Manage Offices**, but cannot create, rename or delete an office.
- :fontawesome-solid-user-shield: **Admins are added automatically** to every new office when UTX creates it. Other staff are given offices by an Admin on their person record.
- :fontawesome-solid-right-left: **The office switcher** in the top bar lets you move between the offices you belong to. You always work "in" one office at a time.
- :fontawesome-solid-lock: **Orders, invoices and checks belong to one office.** You only see the ones of the office you are currently working in.
- :fontawesome-solid-share-nodes: **Master data is shared.** Customers, shippers / receivers, drivers, equipment, terminals, zones, charge types and the other lists are the same in every office.
- :fontawesome-solid-truck-arrow-right: **Transfer to Office** moves an order that is not invoiced to another office.
- :fontawesome-solid-chart-bar: **Reports, statements and the invoicing reminder** are calculated per office. The container tracking digest email is split by office.

---

## :fontawesome-solid-bolt: Quick Start

1. Check the office name in the top bar. That is the office you are working in.
2. To change office, click the office name and pick another one. The page reloads with **Switched to the &lt;office name&gt; office**.
3. Create orders, invoices and checks while you are in the office they belong to.
4. To move an order to another office, open its caret menu and click **Transfer to Office**. See [Transferring an order](#transferring-an-order-to-another-office).

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Manage Offices (view list) | Office switcher | Transfer to Office |
|------|----------------------------|-----------------|--------------------|
| :fontawesome-solid-user-shield: **Admin** | Yes (view only) | Yes, between the offices on their user | Yes, to offices on their user |
| :fontawesome-solid-user-tie: **Manager** | No | Yes, between their offices | Yes, for orders of their offices, to their other offices |
| :fontawesome-solid-headset: **Dispatch** / **Customer Service** | No | Yes, between their offices | Yes, for orders of their offices, to their other offices |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No | Yes, between their offices | Only when order management is turned on for Accountants (`accountant_can_manage_orders`, on by default). See [User Roles](user-roles.md) |
| :fontawesome-solid-user: **Customer** | No | Yes, between their offices (see [Customer Portal](customer-portal.md)) | No |
| :fontawesome-solid-warehouse: **Warehouse**, :fontawesome-solid-screwdriver-wrench: **Garage** | No | No | No |

!!! info "The switcher needs two offices"
    The office switcher only appears when the Multi-Office add-on is on **and** your user belongs to more than one office. With a single office on your user, you always work in that office and there is nothing to switch.

**How to get there:**

- :fontawesome-solid-arrow-right: **Office switcher**: the office name with the :fontawesome-solid-building: icon in the top bar, to the left of **Feedback**.
- :fontawesome-solid-arrow-right: **Manage Offices**: click your **name** at the top of the screen to open the user menu, then click **Manage Offices** (Admins only). See [Navigation & Account](navigation-and-account.md).
- :fontawesome-solid-arrow-right: **Transfer to Office**: the caret menu next to an order's status button, on the **Orders** list and the **Dispatch** board.

---

## :fontawesome-solid-list: Manage Offices (Admin)

**Manage Offices** shows one row per office in your account. The page is **read-only**: there are no add, edit or delete buttons.

<!-- TODO: Screenshot — Manage Offices table with Name, Orders, Invoices, Companies and Users columns -->

| Column | What it shows |
|--------|---------------|
| **Name** | The office name, as shown in the office switcher |
| **Orders** | Number of orders that belong to the office |
| **Invoices** | Number of invoices issued by the office |
| **Companies** | Number of customer companies. With Multi-Office on, customers are shared, so every office shows the **same total** |
| **Users** | Number of people (staff and customer contacts) assigned to the office |

!!! info "New offices are created by UTX"
    To open a new office or rename one, contact UTX support. When UTX creates an office, every Admin user is added to it automatically. Offices cannot be deleted, to protect the orders and invoices linked to them.

!!! warning "Admins added later are not in older offices"
    The automatic assignment happens only when the office is created. An Admin user created afterwards must have the offices checked on their person record, like any other staff member.

### Giving people access to offices

An Admin assigns offices on the person record:

1. Open the person under their company and click **Edit Person**.
2. Check the **Offices** the person works in.
3. Click **Save Changes**.

Only Admins see the **Offices** field, and only for people of your own company (staff), not for the account owner. When you invite a person (staff or customer contact), they are added to the office you are working in. Customer contacts cannot be moved to another office from **Edit Person**. The field hint reads **Do NOT assign more than one office to customers.** See [People & Invitations](people-and-invitations.md#assigning-staff-roles-and-offices).

---

## :fontawesome-solid-right-left: Switching Offices

1. Click the office name in the top bar.
2. The list shows your offices. The current one is in bold with a green :fontawesome-solid-check: check mark.
3. Click another office.

You return to the page you were on, now showing the new office's data, with the message **Switched to the &lt;office name&gt; office**. If you pick an office you do not belong to, the message is **Request failed** and you stay where you were.

<!-- TODO: Screenshot — Office switcher dropdown in the top bar with the current office checked -->

**Which office am I in?**

- The office name is always shown in the top bar switcher, and next to your company name at the top left (*Company* | *Office*).
- The top bar has a **different color per office**: the first office keeps the standard dark bar, the next ones get dark blue, dark green, dark burgundy, dark amber and dark teal, in the order the offices were created. With more than six offices, the colors repeat.
- On the mobile layout, the header shows your company name followed by the office name.
- The **Edit Order** (Quick Edit), **Dispatch Order**, **Complete Order** and appointment modals show the order's office next to the title, and the full order form shows a read-only **Office** line.
- The **Duplicate** dialog says **New order(s) will be created in: &lt;office&gt;**. Duplicates are always created in the office you are in. See [Order Duplication](order-duplication.md).
- The **Container Alerts** page shows the current office name next to its subtitle.

!!! info "Your choice is kept for the session"
    The office you pick stays selected while you are signed in. If you are removed from that office, UTX Freight puts you back in your first office.

---

## :fontawesome-solid-share-nodes: What Is Shared and What Is Per Office

### Per office

These records belong to **one** office. Lists, counters and searches only show the current office's records, and new records are created in the current office.

| Record | Notes |
|--------|-------|
| **Orders** | The **Orders** list, its counters and the **Dispatch** board show only the current office. See [Orders](orders.md) and [Dispatch](dispatch.md) |
| **Invoices** | A new invoice belongs to the office you are in. See [Creating Invoices](creating-invoices.md) |
| **Checks** | A new check belongs to the office you are in. See [Expenses & Checks](expenses-and-checks.md) |
| **Saved AR Export reports** | The **Generated Reports** list is kept per office. See [Aged Receivables](aged-receivables.md) |
| **Garage data and settings** | Garage customers, equipment, parts, job templates, work orders, invoices and garage settings are kept per office. See [Garage Overview](garage-overview.md) and [Garage Settings & Taxes](garage-settings-and-taxes.md) |

!!! warning "Searching from the wrong office"
    An order search only looks in the current office. If a container search finds nothing, the **Orders** page shows **No orders found for "…" in &lt;office&gt;.** with the hint *Try switching to another office using the menu above.*

### Shared by all offices

With Multi-Office on, these lists are the **same in every office**. A record created in one office is immediately available in the others, and users manage them regardless of which office they are in (within the limits of their role).

- **Customers** (companies) — see [Managing Customers](managing-customers.md)
- **Shippers / Receivers** — see [Shippers & Receivers](shippers-receivers.md)
- **Brokers** — see [Lookup Lists](lookup-lists.md)
- **Drivers** — see [Mobile Users](mobile-users.md)
- **Equipment** and **Equipment Types** — see [Equipment](equipment.md)
- **Terminals** — see [Managing Terminals](managing-terminals.md)
- **Cities** and **Zones** — see [Zones & Cities](zones-and-cities.md)
- **Container Sizes** and **Steamship Lines** — see [Lookup Lists](lookup-lists.md)
- **Document Types** — see [Order Documents & POD](order-documents-and-pod.md)
- **Expense Types** and **Charge Types** — see [Charge Types & Taxes](charge-types-and-taxes.md)
- **Move Locations** — see [Order Legs & Move Locations](order-legs-and-move-locations.md)
- **Units of Measure**, warehouse **Buildings**, **Locations** and **Products** — see [Warehouse Setup](warehouse-setup.md)
- **Taxes** (the **Manage Taxes** list) — see [Charge Types & Taxes](charge-types-and-taxes.md). Exception: on a garage invoice, the tax list only offers taxes that were created in the current office
- **Container statuses** — see [Container Statuses](container-statuses.md)

**Place the order on behalf of**: on the full order form (new order and **Edit Order** page), the list shows the active people of every customer, whatever office they belong to. In the **Edit Order** (Quick Edit) and **Dispatch Order** modals, the list only shows people assigned to the office you are in.

!!! info "Shared, but still created in an office"
    A customer, driver or other shared record is saved with the office you were in when you created it. That does not limit who can see or use it while Multi-Office is on.

---

## :fontawesome-solid-truck-arrow-right: Transferring an Order to Another Office

Use **Transfer to Office** when an order was entered in the wrong office, or when another office takes over the work.

1. Make sure you are in the office the order currently belongs to.
2. On the **Orders** list or the **Dispatch** board, open the caret menu next to the order's status button and click **Transfer to Office**.
3. The dialog **Transfer Order #&lt;order number&gt;** asks you to *Select the target office for this order*. Pick the office.
4. Click **Transfer Order** (or **Cancel**).

The order disappears from the current office's list and a message confirms **Order #&lt;order number&gt; transferred to &lt;office&gt;.** In the target office, the order shows a blue **Transferred** badge under its status. Hover over the badge to see **Transferred from &lt;office&gt;**.

<!-- TODO: Screenshot — Transfer Order dialog with the target office dropdown -->

What the transfer does:

- The order moves to the selected office and keeps an internal record of the office it came from (shown by the **Transferred** badge). The dialog notes: *The order and all its charges will move to the selected office. This action is recorded in the audit trail.*
- The order's status does not change.
- The list only offers offices **you** belong to, other than the one you are in. If you belong to only one office, the menu item is not shown.

!!! warning "Invoiced orders cannot be transferred"
    When an order is on an invoice, the menu item is greyed out as **Transfer (Invoiced)** (hover text: *Cannot transfer an invoiced order*). Remove the order from its invoice first if it really belongs to another office. See [Invoices](invoices.md).

See also [Order Workflow](order-workflow.md#transfer-to-office).

---

## :fontawesome-solid-chart-bar: Reports, Statements, Alerts and Emails

| Feature | Behaviour with Multi-Office |
|---------|-----------------------------|
| **Reports**: Income by Customer, Income by Shipper, Delivery by Zone, Daily Income, Order Sales / Profit, Drivers Delivery Report | Show only the current office's orders or invoices. Switch office to see another office. See [Reports](reports.md) |
| **Customer Reports** | Lists every customer (customers are shared). Statements emailed from it are per office (see below) |
| **Sales per Month** | The monthly figures are precomputed **separately for each office**, from that office's invoices. The page shows the current office's figures |
| **Aged Receivables (AR)** (Standard report) | Counts only invoices **issued by** the current office |
| **AR Export** (Performance report) | Includes the customers' invoices **without checking which office issued them**. Saved reports and the one-report-per-month rule apply per office. See [Aged Receivables](aged-receivables.md#office-scope-in-detail) |
| **Customer statements** (manual **Email**) | The attached PDF or Excel statement covers only the invoices of the office you are in. The subject ends with ` - <Office name>`. See [Customer Statements](customer-statements.md) |
| **Automatic statements** | One statement per office, sent only for offices where the customer has an unpaid balance. At most 20 statements are sent per run. See [Automatic Statements](automatic-statements.md#multi-office-accounts) |
| **Invoicing reminder** email | One email for all offices, with the subject **Invoicing Reminder (All Offices) - &lt;date&gt;** and one section per office. Offices with no late or undated uninvoiced orders are left out, and no email is sent if no office has any |
| **Container Alerts** page | The alert list and the **Unread**, **Ready for Pickup**, **Customs Released** and **Departed** cards cover orders of the current office plus alerts that have no order. The **LFD Approaching** card (and so the **All** total) and the upcoming LFD table are **not** limited to an office |
| **Container tracking digest** email | Every subscriber gets the same email, whatever their offices, with alerts grouped under a heading per office. Alerts with no order are under **Unassigned** |

!!! warning "Standard and Performance AR can differ per office"
    Because the **AR Export** (Performance) report does not filter invoices by issuing office, a customer billed by two offices shows all of its invoices in each office's Performance report, while the Standard report splits them by office. Use the Standard report when you need each office's own receivables.

!!! info "Who receives the invoicing reminder"
    The invoicing reminder is sent on Mondays, Wednesdays and Fridays to the active Admins, Managers and Accountants, whatever their offices. The office sections let each team find its own late orders. See [Container Alerts](container-alerts.md) for the tracking digest.

!!! warning "Mark All Read is not per office"
    On the **Container Alerts** page, **Mark All Read** marks every unread tracking alert as read, including alerts of other offices.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the office switcher

!!! info "Solution"
    The switcher only appears when the Multi-Office add-on is on and your user belongs to **more than one** office. Ask an Admin to check the **Offices** on your person record.

### :fontawesome-solid-plus: How do I create a new office?

!!! info "Solution"
    Offices are created by UTX. **Manage Offices** is a read-only list. Contact UTX support with the name of the new office. All existing Admins are added to it automatically; add other staff to it from their person record.

### :fontawesome-solid-magnifying-glass: An order or invoice has disappeared

!!! info "Solution"
    Check the office name in the top bar. Orders, invoices and checks only appear in their own office. Switch office, or look for a **Transferred** badge in the other office if someone moved the order.

### :fontawesome-solid-ban: Transfer to Office is missing or greyed out

!!! info "Solution"
    - Greyed out as **Transfer (Invoiced)**: the order is on an invoice and cannot be transferred.
    - Missing: you belong to only one office, your role cannot transfer orders (Customers, Warehouse and Garage users never can; Accountants only when order management is turned on for them), or Multi-Office is not on.

### :fontawesome-solid-users: The Companies count is the same for every office

!!! info "Solution"
    This is expected. With Multi-Office on, customers are shared by all offices, so **Companies** on **Manage Offices** shows the same account-wide count of company records on every row.

### :fontawesome-solid-envelope: A customer received two statements

!!! info "Solution"
    Statements are per office. A customer billed by more than one office can receive one statement per office, each covering only that office's invoices. The office name is at the end of the subject.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Best Practices"
    - Check the office name (and top bar color) before creating orders, invoices or checks.
    - Transfer orders before invoicing them. Once on an invoice, an order cannot change office.
    - Give customer contacts **one** office only.
    - Remember that customers, drivers, equipment, charge types and the other master lists are shared: a change made in one office affects every office.
    - Use the Standard **Aged Receivables (AR)** report for per-office receivables.
