# Duplicating Orders

Create one or many copies of an existing order in one step, for example when a customer sends several containers under the same P/O.

## :fontawesome-solid-copy: Overview

**Duplicate** copies the main details of an order (order type, customer, terminals, rate, booking and vessel information, addresses) into one or more new orders. Everything that belongs to one specific container or move (container number, drivers, equipment, most dates, documents, signatures, invoice) is left empty on the copies.

- :fontawesome-solid-bars: **Where**: **Duplicate** in the row action menu (the caret) on the **Orders** list. It is not available on the Dispatch page or inside an order.
- :fontawesome-solid-window-maximize: **The window**: titled **Duplicate *Type* Order**. It shows what is copied (grey box) and what is always reset (amber box).
- :fontawesome-solid-square-check: **Two options**: **Copy Reference Number** (on by default) and **Copy Container Status** (off by default).
- :fontawesome-solid-hashtag: **Number of copies**: create several copies at once.
- :fontawesome-solid-magnifying-glass: **After saving**: you land on the **Orders** list, searched by the original order's P/O, newest orders first.
- :fontawesome-solid-dollar-sign: **Charges**: the base rate is copied. Manual charges are not. The automatic Terminal Fee and fuel surcharge are recalculated on each copy where they apply.
- :fontawesome-solid-lock: **Original order**: never changed.

<!-- TODO: Screenshot — The Duplicate Import Order window with a test order: the P/O and order # line, the grey "The following fields will be copied" box, the amber "NOT copied (Always Reset)" box, Number of copies, and the two Optional fields to copy checkboxes. Use demo data only (no real P/O or order number). -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Orders** and find the order to copy.
2. Click the **caret** next to the row's action button and choose **Duplicate**.
3. Enter the **Number of copies**.
4. Leave **Copy Reference Number** checked to keep the reference number, or uncheck it. Check **Copy Container Status** if you want it copied.
5. Click **Create Orders**.
6. On the **Orders** list that opens, set the container number, dates, drivers and equipment on each new order.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Can duplicate orders? |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Yes, any order |
| :fontawesome-solid-user-tie: **Manager** | Yes, orders in their offices |
| :fontawesome-solid-headset: **Dispatch** / **Customer Service** | Yes, orders in their offices |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Yes, orders in their offices. This is on by default; if UTX support has turned off order management for accountants on your account, accountants do not see **Duplicate** |
| :fontawesome-solid-user: **Customer** | No. **Duplicate** is not shown, even when customers can create and edit orders |
| :fontawesome-solid-id-card: **Driver** | No |
| :fontawesome-solid-warehouse: **Warehouse** / :fontawesome-solid-wrench: **Garage** | No access to Orders |

**How to get there:**

- :fontawesome-solid-arrow-right: **Orders** > row **caret** > **Duplicate**

!!! info "Orders list only"
    **Duplicate** only works on the **Orders** list page. The Dispatch page and the order's own pages (View Details, Edit Order) do not have it. See [Orders](orders.md).

!!! danger "Suspended accounts"
    While your UTX Freight account is suspended, no new orders can be created, including copies. See [Orders](orders.md#account-suspension).

---

## :fontawesome-solid-window-maximize: The Duplicate Window

Clicking **Duplicate** opens a window with these parts, from top to bottom:

| Part | What it shows |
|------|---------------|
| **Title** | **Duplicate *Type* Order**, with the order type in bold, for example **Duplicate Import Order**, **Duplicate Export Order**, **Duplicate Transfer Order**, **Duplicate Dry Van Order** or **Duplicate International Export Order** |
| **Office notice** | Multi-office accounts only: a blue box **New order(s) will be created in: *office name***, showing the office you are currently working in |
| **Instructions** | **You are creating multiple orders under the P/O #*P/O*** and **The order #*order number* will be duplicated.** |
| **The following fields will be copied:** | Grey box. A list of the fields copied for this order type, each with a green check mark, in alphabetical order. See [What is copied](#what-is-copied) |
| **The following fields are NOT copied (Always Reset):** | Amber box. The nine fields that are always reset. See [What is always reset](#what-is-always-reset) |
| **Number of copies:** | How many new orders to create. Starts at **1** |
| **Optional fields to copy:** | Two checkboxes: **Copy Reference Number** and **Copy Container Status** |
| **Close** / **Create Orders** | **Close** cancels. **Create Orders** creates the copies |

After you click **Create Orders**, the button's label is replaced by a loading icon and the button is disabled while the copies are created.

!!! warning "Number of copies"
    Enter a whole number from 1 to 100. Check the number before you click **Create Orders**: there is no undo.

    - If the field is empty or not a number, the window shows **Error Number of copies must be a number!** and nothing is created.

---

## :fontawesome-solid-square-check: Optional Fields to Copy

| Checkbox | Default | What it does |
|----------|---------|--------------|
| **Copy Reference Number** | Checked | Copies the order's reference number. Uncheck it to leave the reference number empty on the copies |
| **Copy Container Status** | Unchecked | Copies the container status (see [Container Statuses](container-statuses.md)). Unchecked, the copies have no container status |

These are the only two options. Drivers, equipment and the pickup number are never copied.

---

## :fontawesome-solid-circle-check: What Is Copied

### All order types

| Field (as listed in the window) | Notes |
|--------|-------|
| **Order Type** | Same type as the original |
| **Customer (Requested By)** | The person the order is requested by. The order's transport company is copied too and is grouped under this same label |
| **Broker** | |
| **Zone** | |
| **Office** | The copies stay in the original order's office |
| **Pickup Terminal** | |
| **Return Terminal** | |
| **Container Size** | |
| **Booking Number** | |
| **Vessel** | |
| **Voyage** | |
| **Steamship Line** | |
| **Status Comment** | |
| **Base Rate + Automatic Charges** | The base rate is copied as is. Automatic charges are recalculated, see [Charges on copies](#charges-on-copies) |

### By order type

| Order type | Also copied |
|------------|-------------|
| **Import**, **Export**, **Dry Van**, **International Export** | **Delivery Information**: delivery company, company name, address, contact info, ZIP, instructions and P/O number. **Pickup Information**: pickup company, company name, address, contact info, ZIP, instructions and P/O number |
| **Export** | **Packages**, **Weight**, **Vessel Earliest Return Date**, **Vessel Cutoff Date** |
| **Transfer** | **Delivery Date**. Delivery and pickup information is not copied |

Plus, when checked: **Reference Number** and **Container Status**.

### Set on every copy

| Field | Value on the copy |
|-------|-------------------|
| **Status** | **New** |
| **Container #** | **N/A** |
| **Order date** | Today's date |

---

## :fontawesome-solid-rotate-left: What Is Always Reset

The amber box lists these nine items. They are never copied:

| Item (as shown) | Result on the copy |
|-----------------|--------------------|
| **Invoice (Reset to Uninvoiced)** | Not on any invoice |
| **Order Status (Reset to New)** | **New** |
| **Container Number (Reset to N/A)** | **N/A** |
| **Drivers** | No drivers assigned |
| **Equipment** | No equipment or chassis |
| **Pickup Number** | Empty |
| **Documents (PODs, eBoLs, etc)** | No documents |
| **Signatures** | No signatures |
| **Manual Charges (See Automatic Charges in green)** | Only automatic charges are added again |

### Other fields that are not copied

Anything not in the copied list above starts empty on the copy, even though the amber box does not mention it. This includes, among others:

- Appointment, pickup, delivery and return dates (Transfer orders keep the delivery date)
- The vessel cutoff time on Export orders (the cutoff date is copied)
- Seal number, chassis number, comments, tag, and the hazardous and genset flags
- Delivery and pickup city, country and e-mail typed by hand on the order. When the original uses a saved shipper/receiver, these are read from that shipper/receiver, so they still show on the copy
- Legs and move locations, order expenses, and container tracking alerts
- The **Auto compute fuel surcharges for this order** choice: copies always start with it on, even if it was off on the original
- On **International Export** orders: packages, weight and vessel dates (only **Export** orders copy them)

Check each copy and fill in what you need.

---

## :fontawesome-solid-dollar-sign: Charges on Copies

The base rate is copied. If the original order has no base rate, the customer's default rate is used. Manual charges are never copied. The automatic charges are recalculated on each copy:

| Order type | Terminal Fee | Fuel surcharge |
|------------|--------------|----------------|
| **Import** | Yes, from the pickup terminal | Not at first. The copy has no delivery date, so there is no fuel charge until you set one and save the order |
| **Export** | Yes, from the return terminal | Not at first, same as Import |
| **Transfer** | No | Yes, when the original has a delivery date, because the delivery date is copied |
| **Dry Van** | No | No |
| **International Export** | No | No |

The usual rules still apply: the Terminal Fee needs a **Terminal Fee** charge type and a rate on the terminal or a custom rate for the customer; the fuel surcharge needs the Fuel Surcharge add-on, a rate for the delivery date's month, a customer that is not exempt, and **Auto compute fuel surcharges for this order** on (it is always on for a new copy). The fuel surcharge is a percentage of the base rate. See [Order Charges & Expenses](order-charges-and-expenses.md) and [Fuel Surcharge](fuel-surcharge.md).

!!! warning "Dry Van and International Export copies"
    These copies get no automatic charges at all. Only the base rate carries over. Add any other charges by hand.

---

## :fontawesome-solid-magnifying-glass: After You Click Create Orders

You are sent to the **Orders** list with a search already filled in, sorted with the newest orders first, across all statuses:

- **Original has a P/O**: the search is the P/O text.
- **Original has no P/O**: the search is **N/A**.

A green message confirms the duplication: ***N* new orders were created based on the P/O #*P/O*** (or ***N* new orders were created** when there is no P/O).

!!! warning "Unrelated orders can appear in the results"
    The list uses the normal free-text search, not a P/O filter. Besides orders with exactly that P/O, it also shows any order whose reference number, container #, booking #, customer, shipper/receiver, equipment, order type or container size contains the same text. If the P/O is a number, the order whose order # matches that number can appear too. When the search is **N/A**, every order with no container number appears, because their container # is **N/A**. The new copies are at the top because the list is sorted newest first. See [Orders](orders.md).

!!! info "Transfer orders with a P/O"
    Transfer copies do not get the delivery P/O number. If the original Transfer order has one, the search may not find the copies (unless the copied reference number contains the same text). Clear the search and look for the new orders with status **New** and container **N/A**.

---

## :fontawesome-solid-circle-info: Notes

- **No new-order e-mail**: copies are created without the **New Order** notification e-mail that a regular new order sends to admins and office managers.
- **History**: when order history is enabled for the account, **View History** on a copy (for users who can see it) shows it being created. The original order gets no history entry, because it is not changed.
- **Office**: copies stay in the original order's office. To move one to another office, use **Transfer to Office** in the caret menu (see [Multi-Office](multi-office.md)).
- **One place to duplicate**: all copies are made from the **Duplicate** window with the same options. There is no separate screen or bulk tool for duplication.

---

## :fontawesome-solid-lightbulb: Use Cases

### Several containers on one P/O

Create the first order, then duplicate it for the other containers. Set the container number on each copy.

### Template orders

Keep an order with the usual terminals, rate and booking details, and duplicate it when a similar job comes in. Update the customer or details on the copy if needed.

### Batch creation

Enter the number of containers in **Number of copies** to create them all at once (for example 5 copies for 5 containers).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see Duplicate in the menu

!!! info "Solution"
    **Duplicate** is only on the **Orders** list, not on the Dispatch page or inside an order. Customers and drivers never see it. Accountants see it unless UTX support has turned off order management for accountants on your account (it is on by default).

### :fontawesome-solid-ban: I clicked Create Orders but nothing was created

!!! info "Solution"
    Check whether the account is suspended (look for the red **System Notice: Account Suspended** banner). No orders, including copies, can be created while the account is suspended. Also check that **Number of copies** was at least 1.

### :fontawesome-solid-list: Orders that aren't copies appear after duplicating

!!! info "Solution"
    The list is searched by free text, so other orders that contain the P/O text (or **N/A**) in another field also match. The copies are the newest rows at the top, with status **New** and container **N/A**.

### :fontawesome-solid-user-slash: The drivers and equipment were not copied

!!! info "Solution"
    Drivers, equipment and the pickup number are always reset. There is no option to copy them. Assign them on each copy from the **Orders** list or the Dispatch page.

### :fontawesome-solid-gas-pump: My Import or Export copy has no fuel surcharge

!!! info "Solution"
    The fuel surcharge is based on the delivery date, which is not copied on Import and Export orders. Set the delivery date and save the order to add it.

### :fontawesome-solid-file-invoice-dollar: Extra charges from the original are missing

!!! info "Solution"
    Manual charges are never copied. Only the base rate is copied, and the Terminal Fee and fuel surcharge are recalculated where they apply. Add any other charges to each copy.

---

## :fontawesome-solid-star: Best Practices

!!! tip "Getting the most out of duplication"
    - Complete and check the first order before duplicating it, so every copy starts right.
    - Double-check **Number of copies**: there is no undo.
    - Uncheck **Copy Reference Number** when each container has its own reference.
    - Right after duplicating, fill in the container number on each copy so the orders are easy to tell apart.
    - For Dry Van and International Export copies, add the charges by hand.
