# Customer & Consignee Portal

What your customers see and can do when they sign in to UTX Freight: their company's orders, optional order creation and editing, PODs, and the read-only consignee view for linked shippers/receivers.

## :fontawesome-solid-user: Overview

Every person you add under a customer company can sign in to UTX Freight with the **Customer** role. Customers get a short version of the app built around one page: **Orders**.

- :fontawesome-solid-building: **Company-wide visibility**: a customer user sees every order placed for **anyone in their company**, not only their own, in the office they are working in.
- :fontawesome-solid-eye: **View only by default**: customers can search, filter and open order details. They cannot change statuses, edit fields inline, or see drivers and pricing.
- :fontawesome-solid-pencil: **Optional order management**: when the account option `customer_can_manage_orders` is on, customers can also create orders and edit orders that are still **New**. The option is **off** by default.
- :fontawesome-solid-file-pdf: **PODs**: customers can open the scanned POD and the signed POD of their orders.
- :fontawesome-solid-envelope: **Emails**: the person on the order gets an email when it is dispatched and when it is completed (if their **Email Notifications** setting is on). Invoices, statements and PODs are emailed by your staff.
- :fontawesome-solid-link: **Consignee view**: when a customer company is linked to a **Shipper / Receiver** record, its users also see, read-only, every order delivered to that location, from any freight forwarder, with no pricing.
- :fontawesome-solid-ban: **No back office**: customers cannot open **Dispatch**, **Invoices**, **Reports** or any other menu.

<!-- TODO: Screenshot — The Orders page as seen by a Customer user: header counters, search bar, status tabs, and order rows without driver and rate columns -->

---

## :fontawesome-solid-bolt: Quick Start

**For your staff (giving a customer access):**

1. Go to :fontawesome-solid-arrow-right: **Customers**, find the company, and click :fontawesome-solid-plus: **Add Person**.
2. Enter the person's details and click **Add this person**. They get an invitation email right away and choose their own password. See [People & Invitations](people-and-invitations.md).
3. Optional: to give the company the consignee view, go to :fontawesome-solid-arrow-right: **Shipper / Receiver**, edit the delivery location, pick the company in **Linked Customer Account**, and click **Save Changes**.

**For the customer:**

1. Accept the invitation and sign in. The **Orders** page opens.
2. Type a container #, order # or P/O in the **Container #, Order # and more** box and click **Search**, or use the status tabs (**All**, **In Progress**, **New**, **App. Made**, **Dispatched**, **Completed**).
3. Open an order with the caret next to the grey **Actions** button :fontawesome-solid-arrow-right: **View Details**.
4. Click the PDF or signature icon in the **POD** column to open the order's POD.

---

## :fontawesome-solid-shield-halved: Access & Permissions

What a **Customer** user can do, compared with your staff:

| Action | Customer | Customer (consignee orders) |
|--------|----------|-----------------------------|
| See orders on the **Orders** page | :fontawesome-solid-check: All orders of their company, in their office(s) | :fontawesome-solid-check: Orders delivered to the linked shipper/receiver |
| **View Details** | :fontawesome-solid-check: | :fontawesome-solid-check: |
| Open the scanned or signed POD (**POD** column) | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Create a new order** | Only when `customer_can_manage_orders` is on | — |
| **Edit Order** | Only when `customer_can_manage_orders` is on, and only while the order is **New** | :fontawesome-solid-xmark: Never |
| Change status (**Make App.**, **Dispatch**, **Complete**), Reset, Go Back 1 Step | :fontawesome-solid-xmark: | :fontawesome-solid-xmark: |
| Inline editing on the list (dates, numbers, container status) | :fontawesome-solid-xmark: | :fontawesome-solid-xmark: |
| **Duplicate**, **Delete Order**, **Transfer to Office**, **View History** | :fontawesome-solid-xmark: | :fontawesome-solid-xmark: |
| See rates, totals, invoice links | :fontawesome-solid-xmark: | :fontawesome-solid-xmark: |
| See drivers and the **Special Note** | :fontawesome-solid-xmark: | :fontawesome-solid-xmark: |
| **Send POD to client** (**Email POD** column) | :fontawesome-solid-xmark: | :fontawesome-solid-xmark: |
| **Dispatch**, **Invoices**, **Customers**, **Shipper / Receiver**, **Equipments**, **Reports** menus | :fontawesome-solid-xmark: | :fontawesome-solid-xmark: |
| **Edit Profile** (own details and **Email Notifications**) | :fontawesome-solid-check: | :fontawesome-solid-check: |

- The sidebar shows only **Orders**. The user menu shows **Edit Profile** and **Logout**. See [Navigation & Account](navigation-and-account.md).
- If a customer opens a page they are not allowed to see (for example by typing its address), UTX Freight sends them back to **Orders**.
- The top bar also shows **Feedback** and **Online Documentation**, and the office switcher on [Multi-Office](multi-office.md) accounts when the customer belongs to more than one office.
- `customer_can_manage_orders` is an account-wide option set in your UTX Freight configuration. It applies to all customers at once; you cannot turn it on for a single customer. Contact UTX support to change it.

**Who sets things up:**

| Task | Who can do it |
|------|---------------|
| Add customer people (invitations) | Admin, Manager. Dispatch when `dispatch_can_manage_customers` is on. See [Customers](managing-customers.md) |
| Link a shipper/receiver to a customer account (consignee) | Admin, Manager, Dispatch (anyone who can edit **Shipper / Receiver**). See [Shippers & Receivers](shippers-receivers.md) |

---

## :fontawesome-solid-list: What Customers See on the Orders Page

Customers use the same **Orders** page as your staff (see [Orders](orders.md)), with fewer columns, filters and actions.

### :fontawesome-solid-building: Which orders are listed

A customer sees an order when **both** are true:

- the order was placed for **any person of the customer's company** (the **Place the order on behalf of** person), and
- the order belongs to one of the customer's offices.

The list shows the orders of the office the customer is currently working in. On [Multi-Office](multi-office.md) accounts, a customer who belongs to more than one office can change office with the office switcher in the top bar.

!!! info "Company-wide, not per person"
    Every user of a customer company sees the same orders: all orders placed for anyone in that company. There is no setting to limit a customer user to only their own orders. If two groups in one company must not see each other's orders, set them up as two separate customers.

### :fontawesome-solid-hashtag: Header and filters

- **Counters**: **New Orders**, **App. Made**, **Dispatched**, **Total**, and on intermodal accounts the yard counters (**Empty at Yard**, **Full at Yard**, and **Pre-Pull** when that container status exists). They count only the orders the customer can see.
- **Create a new order** button: only when `customer_can_manage_orders` is on.
- **Search** box (**Container #, Order # and more**) and **Clear All**.
- **Status tabs**: **All**, **In Progress**, **New**, **App. Made**, **Dispatched**, **Completed**. On intermodal accounts with order tagging, tag buttons also appear.

Customers do **not** see the **Not Invoiced** and **Late Invoicing** tabs, the **ORDER TYPE**, **CONTAINER STATUS** and **TERMINAL** filter cards, or the **ACTION & ORDERS** card (**Equipment**, **Legend**, **Export**).

### :fontawesome-solid-table: Columns

Customers see the order's status, order #, **P/O#**, **Deliver To** and **Bill To** (the company that placed the order), the delivery/pickup date and appointment time, container or trailer details (size, steamship line, weight, container #, booking and seal #, **Last Free Day**), the vessel, the pickup terminal and pickup #, the chassis or equipment, **C.Status**, **Return To** / **Return Date**, and the **POD** and **DOC** columns. Columns depend on your account type (intermodal or ground), as described in [Orders](orders.md). All values are read-only.

Customers do **not** see:

- the **ETA**, **Storage** (STO), **Demurrage** (DEM), **ERD** and **Cutoff Date** values (these cells stay empty for customers),
- the **Driver** columns,
- the **Invoiced** / **Rate** column (invoice link, total and zone),
- the **Email POD** column,
- the **Special Note** (the red comment your staff can add under the status).

!!! warning "The Special Note is internal"
    The **Special Note** ("Comment which appears under the status for each order and on the drivers phone") is shown to your staff and to drivers. It is hidden from customers on the Orders list and is not shown on **View Details**. Use it for internal instructions. Don't rely on it to tell the customer anything.

### :fontawesome-solid-bars: Row actions

The status button is always the grey **Actions** button for customers: they can't move an order to the next status. The caret next to it opens the menu:

| Menu item | When a customer sees it |
|-----------|-------------------------|
| **View Details** | Always |
| **Edit Order** | Only when `customer_can_manage_orders` is on and the order is a **New** order of their own company. Consignee orders can't be edited |
| **Quick Edit**, **Documents** | Same condition as **Edit Order**. Saving from these windows is reserved for staff, so customers should use **Edit Order** |

Customers never see **Duplicate**, **Reset Order to New**, **Go Back 1 Step**, **Transfer to Office**, **View History**, **Remove Signature**, **Delete Order**, **View POD** / **View eBoL**, **View Internal POD** or **View Carrier Confirmation**.

### :fontawesome-solid-file-lines: View Details

**View Details** opens the page **Order #&lt;number&gt;** with the ordering company and the name and email of the person the order is placed for, **Order Information**, **Client Information** (delivery company, address, contact, instructions, P.O. #), **Return Address**, **Container Information** (including the zone name) and **Goods Information**.

The **Administrative Information** section (rates, total, appointment date and time, delivery date, comments) is shown to Admin, Manager and Dispatch only. Customers don't see it.

---

## :fontawesome-solid-plus: Creating and Editing Orders (Optional)

These features are available only when the account option `customer_can_manage_orders` is **on**. It is **off** by default. When it is off, customers have no **Create a new order** button and no **Edit Order** item.

### Creating an order

1. On **Orders**, click **Create a new order**.
2. The **New order** form opens. The **Customer Information** box shows the customer's own company and name. A customer always places orders for themselves: there is no **Place the order on behalf of** field.
3. Fill in the order. See [Order Form](order-form.md) for the fields.
4. Click **Create Job** (or **Cancel**).

The order is created with the status **New** in the office the customer is working in. The customer returns to **Orders**, searched for the new order, with the message **Order #&lt;number&gt; was successfully created.**

Creating an order sends the **New Order** email (subject *New Order #&lt;number&gt; from &lt;company&gt;*) to your Admins who have **Email Notifications** on, with the office Managers who have **Email Notifications** on in CC. See [Notifications & Emails](notifications-and-emails.md).

Staff-only sections of the form are not shown to customers: **Change Customer**, **Administrative information** (including **Special Note** and the signed POD upload), **Appointment Information**, rates, **Order Expenses**, **Order Legs** and **Comments**.

### Editing an order

1. On **Orders**, click the caret next to **Actions** :fontawesome-solid-arrow-right: **Edit Order**.
2. Change the fields and click **Update Job** (or **Cancel**).

The customer sees **Order #&lt;number&gt; was successfully updated.** The person on the order can't be changed by a customer.

Customers can edit **any New order of their company**, including orders a colleague placed or your staff entered for them.

!!! warning "Only while the order is New"
    As soon as your staff take an appointment (**App. Made**), the order becomes read-only for the customer and **Edit Order** disappears. If the customer needs a change after that, they must contact you.

!!! info "Someone else changed the order"
    If your staff saved the order while the customer was editing it, the customer's changes are not saved and they see: *This order was modified by another user while you were editing. Your changes were NOT saved. Please try again.*

### Deleting an order

The **Delete Order** item in the actions menu is shown to staff only. A customer who wants a New order cancelled should ask you to delete it. See [Order Workflow](order-workflow.md).

---

## :fontawesome-solid-file-pdf: Documents and PODs

The **POD** column shows icons once a POD exists. Customers (and consignees) can open them:

| Icon | What it opens |
|------|---------------|
| :fontawesome-solid-file-pdf: Red PDF | The scanned signed POD uploaded by your staff |
| :fontawesome-solid-file-signature: Green signature (*Open signed POD*) | The signed POD captured on the driver's phone |

The **DOC** column shows an icon when documents are attached to the order, but only to users who can edit the order. Customers therefore only see the icon on their **New** orders when `customer_can_manage_orders` is on, and the window it opens can't be saved by a customer. Customers can't upload documents or the signed POD; your staff do that. To send documents to a customer, include them in the invoice email or use **Send POD to client**. See [Order Documents & POD](order-documents-and-pod.md).

---

## :fontawesome-solid-envelope: Emails Customers Receive

| Email | Subject | Sent to | When |
|-------|---------|---------|------|
| **Dispatched** | *Order #&lt;number&gt; is now dispatched* | The person the order is placed for | When your staff dispatch the order with the **Dispatch** window. Includes the new status, appointment date and time, order #, client name, reference #, and the container # and pickup terminal (or pickup and delivery addresses) |
| **Completed** | *Order Completed for order #&lt;number&gt;* | The person the order is placed for | When your staff complete the order with the **Complete** window. Includes the empty container return date when set |
| **Invoice** | Set by your staff when sending | The addresses entered when sending (by default the customer's **Accountant Email**) | When your staff email an invoice. The invoice PDF is attached with the POD of each order, and optionally the order documents. See [Invoice Email & Payments](invoice-email-and-payments.md) |
| **Statement of account** | *&lt;Your company&gt; Statement of Account as of &lt;date&gt;* (followed by the office name on multi-office accounts) | The customer's **Accountant Email** (pre-filled, and editable, when your staff send it by hand) | When your staff send a statement, or on the customer's automatic schedule. PDF or Excel, per the customer's **Default Statement Format**. See [Customer Statements](customer-statements.md) and [Automatic Statements](automatic-statements.md) |
| **POD** | *&lt;Your company&gt; Order #&lt;number&gt; Delivered* | The addresses entered in **Send POD to client** (pre-filled with the delivery **Email** of the order) | When your staff click the envelope in the **Email POD** column. The signed or scanned POD is attached |

- The **Dispatched** and **Completed** emails go only to the person on the order, and only when that person has **Email Notifications** ticked (customers can change this under **Edit Profile**). Other users of the same company don't get them.
- Taking an appointment (**Make App.**) never emails the customer. See [Order Workflow](order-workflow.md).
- Invoice, statement and POD emails go to addresses, not to user accounts. The customer doesn't need a login to receive them.

---

## :fontawesome-solid-link: Consignee View

A **consignee** is a customer user whose company is linked to one or more **Shipper / Receiver** records. Typically this is the receiver of the goods (for example, a warehouse or importer) that wants to follow every container delivered to its door, whichever freight forwarder ordered the move.

### How it works

- Linked users see, **read-only**, every order whose delivery location (**Deliver To**) is one of the linked shipper/receiver records, **from any customer** (freight forwarder). They also keep seeing their own company's orders as usual.
- Only the delivery location counts. Orders where the linked location is the pickup location are not added.
- Pricing is never shown, the same as for every customer.
- Consignee orders can't be edited, even when `customer_can_manage_orders` is on. Consignees can use **View Details** and open the POD.
- The **Bill To** line shows the company that placed the order (the forwarder).
- As for other customers, the list shows the orders of the office the user is currently working in.

A blue banner appears above the Orders list for consignee users:

> :fontawesome-solid-eye: **Consignee view:** you are seeing all delivery orders addressed to *&lt;linked shipper/receiver names&gt;* — from all freight forwarders. Pricing details are not shown.

<!-- TODO: Screenshot — Orders page for a consignee user showing the blue "Consignee view" banner -->

### Linking a shipper/receiver to a customer account

1. Go to :fontawesome-solid-arrow-right: **Shipper / Receiver** and edit the delivery location.
2. In the **Portal Access — Consignee Link** section, choose the customer company in **Linked Customer Account**. The list shows all active companies.
3. Click **Save Changes**.

All users of that customer company become consignees for that location right away. To remove access, set **Linked Customer Account** back to **— No linked account —** and save.

A linked shipper/receiver shows the company name with a :fontawesome-solid-link: badge in the **Linked Account** column of the **Shipper / Receiver** list. Use the **Linked** filter to see all linked records. See [Shippers & Receivers](shippers-receivers.md).

<!-- TODO: Screenshot — Shipper / Receiver edit form showing the "Portal Access — Consignee Link" section with the Linked Customer Account dropdown -->

!!! warning "Consignees see other forwarders' orders"
    Linking gives the customer visibility of orders placed by **your other customers** for that delivery location: order numbers, container details, dates, the forwarder's name in **Bill To**, the forwarder contact's name and email on **View Details**, and PODs. Only link a location to the company that actually operates it.

!!! info "One link per location"
    Each shipper/receiver record can be linked to one customer company. A customer company can be linked to several shipper/receiver records; the banner lists them all.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-plus: The customer has no "Create a new order" button

!!! info "Solution"
    Customer order creation is controlled by the account option `customer_can_manage_orders`, which is off by default. Contact UTX support to turn it on. It applies to all customers. Also check that your account isn't suspended: during a suspension nobody can create orders.

### :fontawesome-solid-pencil: The customer can't edit an order

!!! info "Solution"
    Customers can only edit orders that are still **New**, and only when `customer_can_manage_orders` is on. Once an appointment is made the order is read-only for them. Orders seen through the consignee view are never editable. Make the change for them, or use **Reset Order to New** if the order must go back to the customer.

### :fontawesome-solid-eye-slash: A customer user can't see an order

!!! info "Solution"
    Check that the order is placed for a person of **their** company (the **Bill To** line) and that it belongs to the office they are working in. If the customer belongs to several offices (multi-office accounts), they need to switch office with the office switcher. For a consignee, check that the order's **Deliver To** is the shipper/receiver record that is linked to their company (a duplicate record with the same name is not linked). Also try the **All** tab: the list opens on **In Progress**.

### :fontawesome-solid-users: A customer user sees orders placed by colleagues

!!! info "Solution"
    This is expected. Customer users see all orders of their company. To separate two groups, create them as two customers.

### :fontawesome-solid-envelope: The customer didn't get the dispatched or completed email

!!! info "Solution"
    These emails go only to the person the order is placed for, and only if their **Email Notifications** setting is ticked. Check it on the person's **Edit Person** page (or ask the customer to check **Edit Profile**). **Make App.** never sends an email.

### :fontawesome-solid-dollar-sign: The customer asks for prices or invoices in the portal

!!! info "Solution"
    Customers never see rates, totals or invoices in UTX Freight, and they can't open **Invoices**. Email the invoice from **Invoices**, or send a statement. Make sure the customer's **Accountant Email** is filled in.

### :fontawesome-solid-note-sticky: The customer didn't see our Special Note

!!! info "Solution"
    The **Special Note** is internal: staff and drivers see it, customers don't. Send the information to the customer by email or phone instead.

### :fontawesome-solid-file-circle-xmark: The POD column is empty

!!! info "Solution"
    The icons appear only once the driver has signed on the phone or your staff have uploaded the scanned signed POD. Customers can't upload it themselves.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips for the customer portal"
    - Invite every customer contact who needs to follow orders. They all see the company's orders, so you don't need to forward updates by hand.
    - Make sure the main contact on each customer has **Email Notifications** on, so they get the dispatched and completed emails.
    - Keep the **Special Note** for internal and driver instructions. Customers never see it.
    - Link a shipper/receiver to a customer account only after confirming the customer operates that location. Consignees see orders from all your other customers delivered there.
    - Keep one shipper/receiver record per location. Orders delivered to a duplicate record that isn't linked won't show in the consignee view.
