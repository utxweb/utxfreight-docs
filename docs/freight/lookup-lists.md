# Brokers, Steamship Lines & Container Sizes

Maintain the three small reference lists that feed dropdowns on your orders: **Brokers**, **Steamship Lines** and **Container Sizes**.

## :fontawesome-solid-list: Overview

These lists are simple: each entry has a name, an office and, for steamship lines and container sizes, a description and an **Active** checkbox.

- :fontawesome-solid-handshake: **Brokers** (**Manage Brokers**): a list of broker names that you can pick as the **Broker** on a Dry Van order and as a payee in **Order Expenses**. Available to Admins and Managers.
- :fontawesome-solid-ship: **Steamship Lines** (**Manage Steamship Lines**): the shipping lines offered in the **Steamship line** field of container orders. Admins only, intermodal accounts only.
- :fontawesome-solid-box: **Container Sizes** (**Manage Container Sizes**): the sizes offered in the **Container size** field of container orders. Admins only, intermodal accounts only.
- :fontawesome-solid-building: Every entry belongs to an **office**. Each list shows the entries of the office you are currently working in.
- :fontawesome-solid-clock-rotate-left: Changes are recorded (when data auditing is turned on for your account) and can be viewed with **Actions** → **View History**.
- :fontawesome-solid-trash: A broker can be deleted only while no order and no expense uses it. Steamship lines and container sizes cannot be deleted from the screen; uncheck **Active** instead.

!!! warning "Three different things are called \"broker\""
    UTX Freight uses the word *broker* in three unrelated places. They are separate records and are not linked to each other:

    | What | Where you manage it | What it is used for |
    |------|---------------------|---------------------|
    | **Broker records** (this page) | User menu → **Manage Brokers** | The **Broker** field on Dry Van orders, and the **Broker** group of payees in **Order Expenses** |
    | **Customer companies flagged Broker** | **Customers** → edit a customer → **Broker** checkbox. See [Managing Customers](managing-customers.md) | The **Transport Company / Broker** field on Dry Van orders, the blue **Broker** label and the **Brokers** filter on the Customers list |
    | **Mobile users with the Broker role** | **Mobile Users** → **Drivers, Brokers & Yard**. See [Mobile Users](mobile-users.md) | People who sign in from a phone. They have exactly the same rights as a Driver and appear in the driver lists |

    Adding a name on **Manage Brokers** does **not** create a customer or a mobile user, and checking **Broker** on a customer does **not** add it to **Manage Brokers**.

---

## :fontawesome-solid-bolt: Quick Start

1. Click your **name** at the top of the screen to open the user menu.
2. Click **Manage Brokers**, **Manage Steamship Lines** or **Manage Container Sizes**.
3. Click **Add a new Broker** (or **Add a new Steamship Line**, **Add a new Container Size**) at the top right.
4. Enter the **Name**, check the **Office**, and click **Save Changes**.

The new entry is now available in the matching dropdown on your orders.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Manage Brokers | Manage Steamship Lines | Manage Container Sizes |
|------|:---:|:---:|:---:|
| :fontawesome-solid-user-shield: **Admin** | Full access | Full access | Full access |
| :fontawesome-solid-user-tie: **Manager** | Full access | No access | No access |
| :fontawesome-solid-headset: **Dispatch** | No access | No access | No access |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access | No access | No access |
| :fontawesome-solid-user: **All other roles** (Customer, Customer Service, Warehouse, Garage) and mobile users | No access | No access | No access |

**How to get there:**

- :fontawesome-solid-arrow-right: Click your **name** at the top of the screen to open the user menu, then click **Manage Brokers**, **Manage Steamship Lines** or **Manage Container Sizes**.

These items sit in the user menu with the other **Manage …** items (**Manage Cities**, **Manage Zones** and so on). They are **not** inside the **Settings** page. A menu item only appears for users who have access to it.

!!! info "Intermodal only"
    **Manage Steamship Lines** and **Manage Container Sizes** only appear when your account runs in intermodal (container) mode. **Manage Brokers** appears in every mode.

!!! info "Multi-office"
    Each **Manage …** page shows the entries of the office you are currently working in. When you create or edit an entry, the **Office** dropdown lists the offices you belong to. See [Multi-Office](multi-office.md).

    The dropdowns on the order itself are not limited the same way: the **Steamship line** and **Container size** fields of the order form, the **Broker** field of the dispatch form and the **Broker** group of **Order Expenses** list the entries of **every** office. Only the quick pickers on the **Orders** and **Dispatch** lists are limited to your current office. Giving entries distinct names per office avoids confusion.

---

## :fontawesome-solid-handshake: Manage Brokers

The **Brokers** page (subtitle *Management of Brokers*) lists every broker of your current office, sorted by name, on a single page.

<!-- TODO: Screenshot — Brokers list showing Name, Orders and Charges columns, the Expense report button and the Actions menu open on one row -->

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The broker name |
| **Orders** | The number of orders that have this broker in their **Broker** field |
| **Charges** | The number of expense lines (in **Order Expenses**) that have this broker as the payee |
| *(Expense report)* | The :fontawesome-solid-dollar-sign: **Expense report** button. See [Expense report](#expense-report) |
| *(Actions)* | The **Actions** menu: **Edit**, **View History**, **Delete** |

### Creating a Broker

1. Open the user menu → **Manage Brokers**.
2. Click **Add a new Broker**.
3. Fill in the **Broker Information** form (see the table below).
4. Click **Save Changes**. You return to the Brokers list.

Click **Cancel** to go back to the list without saving.

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | Yes | The broker name (placeholder *broker name*) |
| **Office** | Yes | The office the broker belongs to. Lists the offices you belong to; no blank option |

Brokers have no **Active** checkbox and cannot be disabled.

### Editing a Broker

**Actions** → **Edit** opens the same form, titled **Edit Broker**. Change the **Name** or **Office** and click **Save Changes**.

Renaming a broker changes the name everywhere it is shown, including on existing orders and expenses, because they point to the broker record rather than storing a copy of the name.

### Expense report

The :fontawesome-solid-dollar-sign: **Expense report** button opens the **Expenses** page (subtitle *Tracking of expenses for brokers*) with **Expense payment status** set to **Unpaid Only**. It is meant to show what you still owe the broker.

!!! warning "The Expense report opens empty"
    The button does not pass the broker in the format the **Expenses** page expects, so the page always opens with **no expenses** listed and **Select a filter** showing **No Filter**. To see the broker's expenses, choose the broker under **Select a filter** (in the **Broker** group) and click **Search**.

On the **Expenses** page you can refine the list with:

| Filter | Options |
|--------|---------|
| **Select a filter** | **No Filter**, or one payee. Payees are grouped by type: brokers (group **Broker**), mobile users and expense types |
| **Order status** | **All statuses**, or one order status |
| **Expense payment status** | **Paid and Unpaid**, **Paid Only**, **Unpaid Only** |

Click **Search** to apply the filters. An expense counts as paid once it is attached to a check. See [Order Charges & Expenses](order-charges-and-expenses.md).

The **Expenses** page and its **Select a filter** list are not limited to your current office.

### Deleting a Broker

**Actions** → **Delete** asks *Are you sure?* and then removes the broker permanently.

The **Delete** item only appears when **both** the **Orders** and **Charges** columns are **0**. A broker used on any order or any expense line cannot be deleted. There is no way to hide such a broker; rename it if you need to (for example, add *(old)* to the name).

!!! danger "Deleting cannot be undone"
    A deleted broker is gone from the list and from every dropdown. Only delete brokers that were created by mistake.

### Where Broker records are used

- :fontawesome-solid-truck: **Broker** field on Dry Van orders: on the dispatch form, in the **Delivery Information** panel, next to **Special Note**. It is only shown for Dry Van orders. See [Dispatch](dispatch.md).
- :fontawesome-solid-money-bill: **Order Expenses**: the payee dropdown (the first field of each expense line) has a **Broker** group listing your brokers. **Order Expenses** is shown to users who can manage rates. See [Order Charges & Expenses](order-charges-and-expenses.md).
- :fontawesome-solid-dollar-sign: **Expenses** page: the **Select a filter** dropdown has a **Broker** group.

---

## :fontawesome-solid-ship: Manage Steamship Lines

The **Steamship Lines** page (subtitle *Management of Steamship Lines*) lists the steamship lines of your current office.

<!-- TODO: Screenshot — Steamship Lines list showing Name, Description, Orders and Active columns with the Actions menu open -->

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The steamship line name |
| **Description** | The optional description |
| **Orders** | Always shows **-**. The number of orders is not counted on this page |
| **Active** | A green :fontawesome-solid-circle-check: when active, a red :fontawesome-solid-circle-xmark: when inactive |
| *(Actions)* | The **Actions** menu: **Edit**, **View History** |

### Creating or Editing a Steamship Line

1. Open the user menu → **Manage Steamship Lines**.
2. Click **Add a new Steamship Line**, or **Actions** → **Edit** on an existing line.
3. Fill in the **Steamship Line Information** form.
4. Click **Save Changes** (or **Cancel** to go back without saving).

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | Yes | The name shown in the **Steamship line** dropdown on orders (placeholder *Shipping Line*) |
| **Office** | Yes | The office the line belongs to. Lists the offices you belong to |
| **Description** | No | Free text (placeholder *Steamship Line description*) |
| **Active** | No | Checked by default. Hint: *Only active shipping lines will be visible for new orders* |

### Where Steamship Lines are used

- The **Steamship line** field on Container Import, Container Export, Container Transfer and International Export orders. See [Order Form](order-form.md).
- On the **Orders** and **Dispatch** lists, users who can change the container status can click an order's steamship line to pick another one (window *Select Steamship Line*).

---

## :fontawesome-solid-box: Manage Container Sizes

The **Container Sizes** page (subtitle *Management of Container Sizes*) lists the container sizes of your current office.

<!-- TODO: Screenshot — Container Sizes list showing Name, Description, Orders and Active columns with the Actions menu open -->

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The container size name, as shown on orders (for example `40HC`) |
| **Description** | The optional description |
| **Orders** | Always shows **-**. The number of orders is not counted on this page |
| **Active** | A green :fontawesome-solid-circle-check: when active, a red :fontawesome-solid-circle-xmark: when inactive |
| *(Actions)* | The **Actions** menu: **Edit**, **View History** |

### Creating or Editing a Container Size

1. Open the user menu → **Manage Container Sizes**.
2. Click **Add a new Container Size**, or **Actions** → **Edit** on an existing size.
3. Fill in the **Container Size Information** form.
4. Click **Save Changes** (or **Cancel** to go back without saving).

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | Yes | The name shown in the **Container size** dropdown and on the order lists (placeholder *Container size*) |
| **Office** | Yes | The office the size belongs to. Lists the offices you belong to |
| **Description** | No | Free text (placeholder *Container size description*) |
| **Active** | No | Checked by default. Hint: *Only active container sizes will be visible for new orders* |

### Where Container Sizes are used

- The **Container size** field on Container Import, Container Export, Container Transfer and International Export orders. See [Order Form](order-form.md).
- On the **Orders** and **Dispatch** lists, users who can change the container status can click an order's container size to pick another one (window *Select Size*).

!!! tip "Keep names consistent"
    Some automatic features fill these fields by matching the **Name**: orders created from scanned documents look up the container size by a standard size code (such as `20`, `40DV`, `40HC`, `45HC`), and container tracking fills an empty steamship line or container size by matching the carrier name or size reported for the container. When no entry matches, the field is left blank. Use standard names and avoid near-duplicates.

---

## :fontawesome-solid-toggle-on: Active vs. Delete (Steamship Lines & Container Sizes)

- :fontawesome-solid-ban: **Delete** is not offered for steamship lines or container sizes. The list does not count orders, so it cannot confirm that an entry is unused, and the **Delete** item stays hidden.
- :fontawesome-solid-toggle-off: To retire an entry, **Edit** it and uncheck **Active**.

!!! warning "Inactive entries are moved down, not hidden"
    In the order dropdowns, active entries are listed first (alphabetically), followed by inactive ones. Unchecking **Active** moves an entry to the end of the dropdown; it does not remove it. Existing orders keep their steamship line or container size either way.

---

## :fontawesome-solid-clock-rotate-left: View History

Every list on this page has **Actions** → **View History**. It opens a **History** window without leaving the page.

History is only recorded while data auditing is turned on for your account. Changes made while it was off do not appear, and an entry with no recorded changes shows an empty table.

<!-- TODO: Screenshot — History modal for a steamship line showing User, Changes and When columns with a red -> green value change -->

| Column | Description |
|--------|-------------|
| **User** | The name of the person who made the change. Changes with no recorded user show **System** |
| **Changes** | One line per field that changed, with the field name (for example **Name**, **Description**, **Active**, **Office**) and its value |
| **When** | The date (for example *Oct 10, 2026*) with the time underneath (for example *2:15 pm*) |

How to read the **Changes** column:

- The most recent change is at the top.
- An edited value shows the **old value in red**, an arrow (**->**), and the **new value in green**.
- When the entry was created, its values are shown in green only.
- The **Office** is shown by office name. **Active** is shown as `true` or `false`.
- Fields that were empty (or unchecked) both before and after are not shown.
- Edits that changed nothing are not listed.

Click **Close** (or the **×**) to close the window.

!!! info "Same window everywhere"
    The same **History** window is used on other lists, such as zones, cities, terminals, charge types, expense types, taxes, equipment and document types.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I can't see Manage Steamship Lines or Manage Container Sizes

!!! info "Solution"
    Both are available to **Admins** only, and only when your account runs in intermodal mode. Managers can open **Manage Brokers** but not these two lists. Ask an Admin. Also make sure you are looking in the user menu under your **name**, not on the **Settings** page.

### :fontawesome-solid-trash: There is no Delete option for a broker

!!! info "Solution"
    **Delete** only appears when the broker's **Orders** and **Charges** columns are both **0**. Remove the broker from those orders and expense lines first, or keep the broker and rename it.

### :fontawesome-solid-trash: How do I delete a steamship line or a container size?

!!! info "Solution"
    You can't from the screen. **Edit** the entry and uncheck **Active**. It moves to the end of the order dropdowns, and past orders keep their value.

### :fontawesome-solid-list: I unchecked Active but the entry still shows in the order form

!!! info "Solution"
    That is expected. Inactive steamship lines and container sizes are still listed, after the active ones. If an entry is a duplicate or a typo, rename it to something clearly marked (for example *Do not use*) so nobody picks it by mistake.

### :fontawesome-solid-user: I added a broker but I can't find it in the Transport Company / Broker field

!!! info "Solution"
    The **Transport Company / Broker** field lists **customer companies** with the **Broker** checkbox checked, not the entries of **Manage Brokers**. Edit the customer and check **Broker** (see [Managing Customers](managing-customers.md)). The entries of **Manage Brokers** appear in the **Broker** field of the Dry Van dispatch form and in the **Broker** group of **Order Expenses**.

### :fontawesome-solid-mobile-screen: I added a broker but they can't sign in on their phone

!!! info "Solution"
    A broker record is just a name in a list; it has no login. To let a broker use the mobile app, create a mobile user with the **Broker** role under **Mobile Users** → **Drivers, Brokers & Yard**. See [Mobile Users](mobile-users.md).

### :fontawesome-solid-dollar-sign: The Expense report is empty

!!! info "Solution"
    This is a known limitation: the **Expense report** button always opens an empty list. On the **Expenses** page, choose the broker under **Select a filter** (in the **Broker** group), pick the **Expense payment status** you want, and click **Search**. The button starts on **Unpaid Only**: if everything has already been paid by check, switch to **Paid and Unpaid**.

---

!!! tip "Best Practices"
    - Set up steamship lines and container sizes once, when your account is configured, using the names your customers and terminals use.
    - Retire old entries by unchecking **Active** rather than renaming them to something else, so past orders keep the right value.
    - Use **Manage Brokers** for the third parties you pay on Dry Van moves, and the customer **Broker** checkbox for transport companies that carry the freight. Do not mix them up.
    - Before deleting a broker, check **View History** to confirm it really was created by mistake.
