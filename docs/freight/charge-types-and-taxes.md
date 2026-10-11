# Charge Types, Expense Types & Taxes

Set up the lists that price your orders, record your costs and tax your invoices: **Charge Types**, **Expense Types** and **Manage Taxes**.

## :fontawesome-solid-dollar-sign: Overview

These three lists are master data. You set them up once, then pick from them every day on orders and invoices.

- :fontawesome-solid-file-invoice-dollar: **Charge Types** (page title **Order Charges**) are the extra charges you bill, such as chassis or waiting time, plus the costs you track as **Expense** charge types. **Income** charge types are added to an order's total, so they end up on the invoice.
- :fontawesome-solid-warehouse: One charge type can be marked as the **Terminal Fee**. The app uses it to add the terminal's rate to Import and Export orders automatically.
- :fontawesome-solid-gas-pump: With the Fuel Surcharge add-on, the monthly fuel rates are also charge types, but they are managed on the **Fuel Schedule** page and hidden from the Charge Types list.
- :fontawesome-solid-money-bill: **Expense Types** (page title **Expense Categories**) are the "who did we pay" entries for costs that are not a driver or a broker. They appear in the **Other Expense** group of an order's expense rows.
- :fontawesome-solid-percent: **Manage Taxes** holds your GST and QST percentages. You choose a tax on each invoice, and the app adds GST and QST to the invoice subtotal.
- :fontawesome-solid-screwdriver-wrench: Taxes are **shared with Garage**. **Garage** > **Taxes** edits the same tax records.
- :fontawesome-solid-clock-rotate-left: Every change to a charge type, expense type or tax is recorded and can be viewed with **View History**.

---

## :fontawesome-solid-bolt: Quick Start

1. Click your **name** in the top menu :fontawesome-solid-arrow-right: **Charge Types**.
2. Click **Edit** in the **Actions** menu of each charge type you bill for and enter your own **Default Rate**. Uncheck **Active** on the ones you never use.
3. Make sure one charge type has **Use as default for** set to **Terminal Fee** if you charge terminal fees.
4. Click your **name** :fontawesome-solid-arrow-right: **Expense Types** and add the non-driver costs you pay (for example tolls or repairs).
5. Click your **name** :fontawesome-solid-arrow-right: **Manage Taxes** and check that the **GST** and **QST** percentages are right.

!!! tip "Setup checklist"
    The setup checklist has a **Check your charge types** step that sends you to this page. See [Check your charge types](#the-check-your-charge-types-setup-step).

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Charge Types | Expense Types | Manage Taxes |
|------|-------------|---------------|--------------|
| :fontawesome-solid-user-shield: **Admin** | Full access | Full access | Full access |
| :fontawesome-solid-user-tie: **Manager** | Full access | Full access | Full access |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Full access | Full access | Full access |
| :fontawesome-solid-warehouse: **Warehouse** | Full access | No access | No access |
| :fontawesome-solid-headset: **Dispatch** | Only with **Can manage rates?** | Only with **Can manage rates?** | No access |
| :fontawesome-solid-user: **All other roles** (Customer, Driver, Garage and others) | No access | No access | No access |

**Can manage rates?** is a checkbox on the dispatcher's profile. See [People & Invitations](people-and-invitations.md).

**How to get there:**

- :fontawesome-solid-arrow-right: Click your **name** at the top of the screen to open the user menu. **Charge Types**, **Expense Types** and **Manage Taxes** are grouped together near the bottom, after the **Manage …** items. Each item only appears if your role allows it.
- :fontawesome-solid-arrow-right: With the Warehouse add-on, **Warehouse** > **Charges** in the left menu opens the Charge Types page already filtered to **Warehouse**.
- :fontawesome-solid-arrow-right: With the Fuel Surcharge add-on, the Charge Types page has a **Back to Fuel Schedule** button.

!!! info "Garage users and taxes"
    Garage users do not see **Manage Taxes**, but anyone who can open Garage (Admin, Manager and Garage users, when the Garage add-on is on) can edit taxes from **Garage** > **Taxes**. See [Taxes are shared with Garage](#taxes-are-shared-with-garage).

---

## :fontawesome-solid-file-invoice-dollar: Charge Types

The page opens with the title **Order Charges** and the subtitle **Management of Order Charges**.

<!-- TODO: Screenshot — Order Charges list with the All Active / Disabled filter buttons -->

### Filters

The buttons at the top of the list filter what you see. The page opens on **All Active**.

| Button | Shows |
|--------|-------|
| **All Active** | Active charge types only. |
| **Disabled** | Charge types whose **Active** box is unchecked. |
| **Warehouse** | Warehouse charge types, active and disabled. Only shown with the Warehouse add-on. |
| **Intermodal** | Intermodal charge types, active and disabled. Only shown with the Warehouse add-on. |

The list is sorted by name and shows 50 charge types per page.

!!! info "Fuel surcharge rows are hidden when the add-on is on"
    With the Fuel Surcharge add-on, the monthly fuel rates (charge types used as **Fuel Surcharge**) are left out of this list. Manage them on the **Fuel Schedule** page instead. See [Fuel Surcharge](fuel-surcharge.md). Without the add-on, any existing fuel surcharge rows are listed here like any other charge type.

### Columns

| Column | What It Shows |
|--------|---------------|
| **ID** | The charge type's internal number. |
| *(icon)* | A ship icon for **Intermodal** charge types, a warehouse icon for the others. |
| **Name** | Green when the charge type is active, red when it is disabled. |
| **Service** | The service the charge type belongs to, for example **Intermodal** or **Warehouse**. |
| **Type** | **Income** or **Expense**. |
| **Default Rate** | The default amount, shown in dollars. |
| **Rate Type** | The **Value Type**: **Fixed** or **Monthly**. |
| **Use For** | **Terminal Fee** or **Fuel Surcharge** in green, or **not set**. |
| **Effective Period** | The month the charge applies to (for example **Mar 2026**), when one is set, or **not set**. Fuel surcharge rows show the date as **Week of** *date*. |
| **Active** | Whether the charge type is active. |
| *(Actions)* | **Edit** and **View History**. |

### Adding or editing a charge type

1. Open **Charge Types** from the user menu.
2. Click **Add a new Order Charge** at the top right, or open the **Actions** menu on a row and click **Edit**.
3. Fill in the **Order Charge Information** form (see the table below).
4. Click **Save**. **Cancel** returns to the list without saving.

<!-- TODO: Screenshot — Order Charge Information form -->

| Field | What It Does |
|-------|-------------|
| **Name** | The name shown in the order dropdowns and on the invoice breakdown. Required. |
| **Charge Type** | **Income**: billed to the customer, listed under **Additional Charges** on the order. **Expense**: a cost to you, listed in the expense type dropdown of **Order Expenses**. |
| **Default Rate** | The amount copied onto the order when the charge type is picked. Required and must be a number. You can still change the amount on each order. |
| **Value Type** | **Fixed** or **Monthly**. Used by warehouse orders: a **Fixed** charge is added once, a **Monthly** charge is multiplied, for each product line, by the square footage of its unit of measure, its quantity and the number of calendar months in storage (the storage month and the closing month both count). |
| **Service** | **Intermodal** charge types are offered on freight orders. **Warehouse** charge types are offered on warehouse orders (Warehouse add-on only). |
| **Office** | The office the charge type belongs to. Lists the offices you have access to. The Charge Types page only lists the charge types of the office you are working in. |
| **Use as default for** | Leave blank for a normal charge. Choose **Terminal Fee** to use this charge type for the automatic terminal fee. With the Fuel Surcharge add-on, **Fuel Surcharge** is also listed. |
| **Applicable on (Month)** | Only shown with the Fuel Surcharge add-on. The month a fuel surcharge rate applies to. Use the **Fuel Schedule** page to set fuel rates rather than this field. |
| **Active** | Uncheck to disable the charge type. |

!!! warning "Charge types cannot be deleted"
    There is no **Delete** option for charge types. To stop using one, edit it and uncheck **Active**. Existing orders that used it keep their charges.

### How charge types feed orders and invoices

- :fontawesome-solid-plus: **Additional Charges.** On the order form, **Order Charges for Invoice Breakdown** > **Additional Charges** lists your **Income** charge types for the **Intermodal** service, written as **Name (rate$)**. Picking one copies its **Default Rate** into the amount. See [Order Charges & Expenses](order-charges-and-expenses.md).
- :fontawesome-solid-calculator: **Order total.** The order total is the base rate plus all its order charges. The invoice subtotal is the sum of its orders' totals, so every income charge ends up on the invoice. See [Invoices](invoices.md).
- :fontawesome-solid-money-bill: **Order Expenses.** The second dropdown of each expense row lists your **Expense** charge types. Picking one copies its default rate into **Rate**. Expenses never change the order total or the invoice.
- :fontawesome-solid-warehouse: **Warehouse orders.** The warehouse order charges list your **Income** charge types for the **Warehouse** service. When the customer has its own rate for a charge type (**Custom rates for this customer** on the customer, **Warehouse** group), the dropdown shows that rate. See [Warehouse Orders](warehouse-orders.md).

!!! warning "Disabling does not remove a charge type from the order dropdowns"
    Unchecking **Active** moves the charge type to the **Disabled** filter, takes it out of the setup checklist count and removes it from the **Warehouse** group of a customer's custom rates. In the current version, the **Additional Charges** and expense type dropdowns on the order form, and the warehouse order charges, still list disabled charge types. These dropdowns are also not filtered by office: in a multi-office system they list the charge types of every office. Rename a charge type you never want picked (for example add "DO NOT USE") if it keeps getting selected.

### The Terminal Fee default

Set **Use as default for** to **Terminal Fee** on the charge type you bill terminal fees with. When an Import or Export order that is not Completed and not invoiced is created, and each time it is saved from the order form, the app:

1. Finds the charge type marked **Terminal Fee**.
2. Takes the rate of the order's terminal (the pick up terminal for Import, the return terminal for Export), or the customer's custom rate for that terminal if one exists.
3. If that rate is $1 or more, replaces any existing Terminal Fee charge on the order with one charge at that rate, with the note **Computed Terminal Fee**. Rates below $1 are ignored.

The **Default Rate** of the Terminal Fee charge type itself is not used for this. The amount always comes from the terminal or the customer's custom terminal rate. See [Managing Terminals](managing-terminals.md).

!!! warning "Keep exactly one Terminal Fee charge type"
    If no charge type is marked **Terminal Fee**, no terminal fee is ever added. If several are marked, only one is used: the first by name, whether it is active or not, and in a multi-office system whichever office it belongs to. Keep a single one.

### The Fuel Surcharge default

Charge types with **Use as default for** set to **Fuel Surcharge** are the monthly fuel rates. Their rate is a **percentage** of the order's base rate, not a dollar amount, and must be greater than 0 and at most 100. When the rate changes, the name is updated automatically to **Fuel Surcharge N%**.

With the Fuel Surcharge add-on, these records are created and edited from the **Fuel Schedule** page and do not appear in the Charge Types list. See [Fuel Surcharge](fuel-surcharge.md).

---

## :fontawesome-solid-money-bill: Expense Types

The page opens with the title **Expense Categories** and the subtitle **Management of Expense Categories**.

Expense types are the payees for order costs that are not a driver or a broker, such as tolls, repairs or a subcontractor.

<!-- TODO: Screenshot — Expense Categories list -->

### Columns

| Column | What It Shows |
|--------|---------------|
| **Name** | The expense type's name. |
| **Charges Count** | How many expense lines use this expense type. |
| **Active** | Whether the expense type is active. |
| *(Actions)* | **Edit**, **View History** and, when **Charges Count** is 0, **Delete**. |

There are no filter buttons on this page.

### Adding or editing an expense type

1. Open **Expense Types** from the user menu.
2. Click **Add a new Expense Category**, or open the **Actions** menu on a row and click **Edit**.
3. Fill in the **Expense Category Information** form.
4. Click **Save**.

| Field | What It Does |
|-------|-------------|
| **Name** | The name shown in the payee dropdown. Required. |
| **Office** | The office the expense type belongs to. Hint: *Office for which this expense applies*. |
| **Active** | Hint: *Only active expenses will be visible for new orders*. |

!!! info "Active and the payee dropdown"
    In the current version, the order's payee dropdown lists every expense type, including those with **Active** unchecked, and is not filtered by office.

### Deleting an expense type

**Delete** only appears in the **Actions** menu when **Charges Count** is 0. Click it and confirm **Are you sure?**. An expense type that has been used on an order cannot be deleted.

### Where expense types appear

- :fontawesome-solid-money-bill: **Order Expenses.** The first dropdown (the payee) of each expense row is grouped into **Driver**, **Broker** and **Other Expense**. Your expense types are the **Other Expense** group. See [Order Charges & Expenses](order-charges-and-expenses.md).
- :fontawesome-solid-filter: **Expenses page.** The **Select a filter** dropdown lets you filter expense lines by one expense type. See [Expenses & Checks](expenses-and-checks.md).

!!! tip "Expense Types vs Expense charge types"
    An **expense type** says *who* you paid (the payee). An **Expense** charge type (Charge Types page, **Charge Type** = **Expense**) says *what* the cost was and can pre-fill its amount. An expense row can use both.

---

## :fontawesome-solid-percent: Manage Taxes

The page opens with the title **Taxes**. Each tax holds a GST percentage and a QST percentage.

<!-- TODO: Screenshot — Taxes list with GST, QST and Invoices columns -->

### Columns

| Column | What It Shows |
|--------|---------------|
| **Name** | The tax name, shown in the invoice's tax dropdown. |
| **Gst** | The GST (federal) percentage. |
| **Qst** | The QST (provincial) percentage. |
| **Invoices** | How many freight invoices use this tax. |
| **Active** | Whether the tax is active. |
| *(Actions)* | **Edit**, **View History** and, when **Invoices** is 0, **Delete**. |

### Adding or editing a tax

1. Open **Manage Taxes** from the user menu.
2. Click **Add a new Tax**, or open the **Actions** menu on a row and click **Edit**.
3. Fill in the **Tax Information** form.
4. Click **Save**.

| Field | What It Does |
|-------|-------------|
| **Name** | The name shown in the invoice's tax dropdown. |
| **Office** | The office the tax belongs to. |
| **GST** | The federal tax percentage. Enter `5` for 5%. |
| **QST** | The provincial tax percentage. Enter `9.975` for 9.975%. Enter `0` if you do not charge a provincial tax. |
| **Active** | Used by Garage (see below). |

### How taxes are applied to freight invoices

1. On the invoice form, choose the tax in the **Tax** dropdown. It lists your office's taxes.
2. The app calculates **GST** as the invoice subtotal × the GST % and **QST** as the subtotal × the QST %, each rounded to the cent (QST is only rounded on invoices dated December 1, 2022 or later).
3. The invoice total is the subtotal plus GST plus QST. With no tax selected, no tax is added.

The printed invoice shows the lines **GST (*rate*%)** and **QST (*rate*%)**, using the percentages of the chosen tax. See [Creating Invoices](creating-invoices.md).

!!! warning "Changing a percentage changes existing invoices"
    Freight invoices store which tax they use, not the amount. If you edit the GST or QST % of a tax that is already on invoices, those invoices are recalculated with the new percentage. When a rate changes, create a **new** tax with the new percentages and use it on new invoices, and leave the old one as it is.

!!! info "GST/QST numbers are elsewhere"
    Your GST and QST **registration numbers** printed on invoices are set in **Settings**, not here. See [Application Settings](application-settings.md).

### Deleting a tax

- **Delete** only appears in the **Actions** menu when the **Invoices** column is 0 (no freight invoice uses the tax).
- If the Garage add-on is on and a garage invoice uses the tax, deleting is refused with the message **Cannot delete — used by N garage invoices.** (**garage invoice** when N is 1).

### Taxes are shared with Garage

**Manage Taxes** and **Garage** > **Taxes** (page title **Tax Rates**) show and edit the **same** tax records. A change made on one page applies to both freight and garage invoices. **Manage Taxes** lists only the taxes of the office you are working in, while **Garage** > **Taxes** lists the taxes of every office.

| | Manage Taxes (freight) | Garage > Taxes |
|---|---|---|
| Who can open it | Admin, Manager, Accountant | Anyone with Garage access (Admin, Manager, Garage) |
| **Invoices** column counts | Freight invoices | Garage invoices |
| Delete is allowed when | No freight invoice uses it (and no garage invoice, with the Garage add-on) | No garage invoice and no freight invoice uses it |
| **Active** | No effect on the freight **Tax** dropdown | Only active taxes are offered on garage invoices, and work orders use the office's first active tax |

See [Garage Settings & Taxes](garage-settings-and-taxes.md).

---

## :fontawesome-solid-list-check: The Check your charge types setup step

The setup checklist's **Check your charge types** step (stage **What appears on your invoice**) exists because new systems come with pre-filled charge types, such as waiting time, chassis detention and storage, at guessed prices.

- The **Open Charge Types** button opens this page.
- The step is done when at least one active charge type has been edited since setup (saved more than a minute after it was created), or someone clicked **Looks right to me**.
- It counts active charge types only and never counts fuel surcharge rows, so editing a fuel rate does not complete it.
- **What we found** reads, for example, **12 charges, 2 changed since setup**, **12 charges, none changed since setup** or **12 charges, confirmed as they are**.

See [Setup Checklist](setup-checklist.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I can't see Charge Types, Expense Types or Manage Taxes in my menu

!!! info "Solution"
    These items are in the user menu (click your **name**), not in the left menu or **Settings**. Dispatchers need **Can manage rates?** on their profile for Charge Types and Expense Types, and cannot open Manage Taxes. Warehouse users only see Charge Types. See the [Access & Permissions](#access-permissions) table.

### :fontawesome-solid-gas-pump: My fuel surcharge charge types are missing from the list

!!! info "Solution"
    With the Fuel Surcharge add-on, fuel rates are hidden from the Charge Types page. Click **Back to Fuel Schedule** and manage them there. See [Fuel Surcharge](fuel-surcharge.md).

### :fontawesome-solid-trash: There is no Delete option for a charge type

!!! info "Solution"
    Charge types cannot be deleted. Edit the charge type and uncheck **Active** instead.

### :fontawesome-solid-trash: I can't delete an expense type or a tax

!!! info "Solution"
    An expense type can only be deleted when its **Charges Count** is 0. A tax can only be deleted when no invoice uses it. Uncheck **Active** instead, or leave it as it is.

### :fontawesome-solid-warehouse: No terminal fee is added to my orders

!!! info "Solution"
    One charge type must have **Use as default for** = **Terminal Fee**, and the order's terminal (or the customer's custom terminal rate) must have a rate of at least $1. The fee is only added to Import and Export orders that are not Completed or invoiced, when the order is created or saved from the order form. See [Managing Terminals](managing-terminals.md).

### :fontawesome-solid-percent: Old invoices show a different tax amount after I edited a tax

!!! info "Solution"
    Freight invoices recalculate GST and QST from the tax they point to. Put the old percentages back on that tax, then create a new tax for the new rate and use it on new invoices.

### :fontawesome-solid-list: A disabled charge type still appears on the order form

!!! info "Solution"
    In the current version, the order form's charge and expense type dropdowns do not filter out disabled charge types. Rename the charge type so nobody picks it by mistake.

---

!!! tip "Best Practices"
    - Review every pre-filled charge type and put your own price on the ones you bill for.
    - Keep exactly one charge type marked **Terminal Fee**.
    - Use clear names: the charge type name is what your customer sees on the invoice breakdown.
    - Create a new tax when a rate changes instead of editing the one already used on invoices.
    - Add an expense type for each regular non-driver cost and record those costs as expense rows on the order, so the **Order Sales / Profit** report (which subtracts every expense row from the order total) shows real margins.
