# Garage Customers & Equipment

Keep the list of people and companies your garage works for, and the trucks, trailers and chassis you service for them, with a full service history per unit.

## :fontawesome-solid-screwdriver-wrench: Overview

- :fontawesome-solid-users: **Customers** (Garage sidebar) lists your garage customers: a person (first and last name) with an optional company name, email, phone and **Accountant Email**.
- :fontawesome-solid-truck: **Equipment** (Garage sidebar) lists the units you service. Each unit is a **Truck**, **Trailer** or **Chassis** and can have an **Owner (Customer)**.
- :fontawesome-solid-barcode: The equipment form has a **Decode** button that fills **Year**, **Make** and **Model** from the VIN using the public NHTSA VIN decoder.
- :fontawesome-solid-clock-rotate-left: Each unit has a **Service History** page with its work orders, **Total Work Orders**, **Total Spent** and **Last Service**.
- :fontawesome-solid-envelope: The customer's **Accountant Email** is added in CC on garage invoice, work summary and statement emails.
- :fontawesome-solid-ban: Equipment can be disabled and enabled again. Customers cannot be disabled or deleted from the screen, and neither can equipment be deleted.
- :fontawesome-solid-building: Both lists show only the office you are currently working in.
- :fontawesome-solid-code-branch: Garage customers and garage equipment are **separate** from the freight **Customers** and **Equipments** pages. See [How these differ from freight Customers and Equipments](#how-these-differ-from-freight-customers-and-equipments).

---

## :fontawesome-solid-bolt: Quick Start

1. Open the Garage: left menu :fontawesome-solid-arrow-right: **Garage**.
2. In the Garage sidebar, click **Customers** :fontawesome-solid-arrow-right: **New Customer**. Enter the **First Name** and **Last Name** (required), plus **Email**, **Accountant Email**, **Company Name** if you have them, and click **Create Customer**.
3. In the Garage sidebar, click **Equipment** :fontawesome-solid-arrow-right: **New Equipment**. Pick the **Equipment Type**, enter the **Unit Number** and **VIN**, click **Decode** to fill year, make and model, choose the **Owner (Customer)** and click **Create Equipment**.
4. Back on **Customers**, click the :fontawesome-solid-wrench: button on the customer's row to start a work order for them.
5. To see everything done on a unit, click the :fontawesome-solid-clock-rotate-left: (**Service History**) button on its row in **Equipment**.

---

## :fontawesome-solid-shield-halved: Access & Permissions

The Garage is an add-on. When it is not turned on for your installation, the **Garage** menu item does not appear and the Garage pages send you back to the dashboard.

| Role | Garage Customers (list, add, edit) | Garage Equipment (list, add, edit, disable/enable, service history) |
|------|------|------|
| :fontawesome-solid-user-tie: **Admin** | Yes | Yes |
| :fontawesome-solid-user-tie: **Manager** | Yes | Yes |
| :fontawesome-solid-wrench: **Garage** | Yes | Yes |
| :fontawesome-solid-headset: **Dispatch**, :fontawesome-solid-file-invoice-dollar: **Accountant**, other roles | No | No |

**Where to find it:**

- :fontawesome-solid-arrow-right: Left menu **Garage** :fontawesome-solid-arrow-right: Garage sidebar :fontawesome-solid-users: **Customers**
- :fontawesome-solid-arrow-right: Left menu **Garage** :fontawesome-solid-arrow-right: Garage sidebar :fontawesome-solid-truck: **Equipment**
- :fontawesome-solid-arrow-right: **Back to TMS** at the bottom of the Garage sidebar returns you to the freight side.

!!! info "Current office"
    Garage customers and equipment belong to an office. The lists, the edit pages and the **Service History** page only show records of the office you are currently working in. With [multiple offices](multi-office.md), switch office to see another office's garage records. See [User Roles](user-roles.md) for what each role can do elsewhere.

---

## :fontawesome-solid-users: Garage Customers

### :fontawesome-solid-list: The Customers list

The page header reads **Customers** — *Manage garage customers*, with a **New Customer** button on the right.

<!-- TODO: Screenshot — Garage Customers list showing the Active/Disabled tabs, the Search customers... box, and rows with the wrench, clipboard and edit action buttons -->

**Tabs**

| Tab | Shows |
|-----|-------|
| **Active** | Customers that are active (the default). Every customer you create is active. |
| **Disabled** | Customers that have been marked inactive. There is no button on the screen to disable a customer, so this tab is normally empty. |

**Search**

Type in the **Search customers...** box and press Enter or click :fontawesome-solid-magnifying-glass:. The search matches part of the **first name**, **last name** or **company name** (not email or phone) and is not case sensitive. It searches within the tab you are on.

**Columns**

The list is sorted by last name, then first name, 25 customers per page.

| Column | Shows |
|--------|-------|
| **Name** | First and last name |
| **Company** | Company name, or **-** |
| **Phone** | Phone, or **-** |
| **Email** | Email, or **-** |
| **Accountant Email** | Accountant email, or **-** |
| **Actions** | The three buttons below |

**Row actions**

| Button | Tooltip | What it does |
|--------|---------|-------------|
| :fontawesome-solid-wrench: | *New work order for (name)* | Opens a new work order with this customer already selected. See [Garage Work Orders](garage-work-orders.md). |
| :fontawesome-solid-clipboard-check: | *Work summary for (name)* | Opens the customer's work summary report. See [Garage Reports](garage-reports.md). |
| :fontawesome-solid-pen-to-square: | *Edit (name)* | Opens the customer form. |

When there are no customers in the tab, the list shows **No customers yet** — *Add your first customer to start creating work orders.* with a **New Customer** button.

### :fontawesome-solid-plus: Creating or editing a customer

1. Click **New Customer** (or the :fontawesome-solid-pen-to-square: button on a row to edit).
2. Fill in the fields below.
3. Click **Create Customer** (new) or **Update Customer** (edit). Click **Cancel** to go back to the list without saving.

The list shows *Customer created successfully.* or *Customer updated successfully.* If something is wrong, the form stays open with the errors in a red box at the top.

| Field | Required | Notes |
|-------|----------|-------|
| **First Name \*** | Yes | |
| **Last Name \*** | Yes | |
| **Email** | No | Must be a valid email address if filled. Garage invoices, work summaries and statements are sent **to** this address. |
| **Phone** | No | Free text |
| **Accountant Email** | No | Must be a valid email address if filled. Hint under the field: *CC'd automatically on invoice and work summary emails.* |
| **Company Name** | No | Shown in brackets after the name wherever a customer is picked (see below) |
| **Notes** | No | Free text |

The edit page title is **Edit Customer: (name)**, and the form card heading reads **Edit: (name)**.

!!! tip "Accountant Email"
    Use **Accountant Email** when invoices should also reach the customer's bookkeeper. It is added in **CC** on garage invoice emails and work summary emails, as the hint says, and also on garage statement of account emails (but not on a statement test send). The main **Email** stays in the **To** field.

#### :fontawesome-solid-id-card: How a customer's name is displayed

Outside the **Name** column of the Customers list (for example in the work order **Customer** search, the **Owner (Customer)** dropdown and the **Owner** column on Equipment), a customer appears as:

- **First Last (Company Name)** when a company name is filled in, for example *Jane Smith (Smith Hauling)*
- **First Last** when it is not

Fill in **Company Name** so customers with similar names are easy to tell apart.

#### :fontawesome-solid-bolt: Adding a customer from a work order

You don't have to leave the work order form to add a customer. On the work order form, the green :fontawesome-solid-plus: button next to the **Customer \*** field (tooltip *Quick create customer*) opens **Quick Create Customer**, which asks for **First Name \***, **Last Name \***, **Phone** and **Company**. Click **Create & Select**. If first or last name is empty you see *First name and last name are required.* The new customer is created in your current office, selected on the work order, and a *Customer created* message appears. The button is hidden while the work order is on a draft invoice, because the customer can't be changed then. Add the email and accountant email later from **Customers**.

### :fontawesome-solid-ban: No disable or delete for customers

The Customers page has no disable, enable or delete button. A customer you no longer serve stays on the **Active** tab. Edit the **Notes** if you want to mark them as inactive for your team.

---

## :fontawesome-solid-truck: Garage Equipment

### :fontawesome-solid-list: The Equipment list

The page header reads **Equipment** — *Track trucks, trailers, and chassis*, with a **New Equipment** button on the right.

<!-- TODO: Screenshot — Garage Equipment list showing the Active/Disabled tabs, the Truck/Trailer/Chassis type chips, the Search equipment... box, coloured type badges and the history, edit and disable action buttons -->

**Tabs**

| Tab | Shows |
|-----|-------|
| **Active** | Enabled units (the default) |
| **Disabled** | Units you have disabled |

**Type chips**

Next to the tabs are three chips: **Truck**, **Trailer**, **Chassis**. Click one to show only that type within the current tab. The selected chip is highlighted. There is no "All" chip: to remove the type filter, click the **Active** or **Disabled** tab again.

**Search**

Type in the **Search equipment...** box and press Enter or click :fontawesome-solid-magnifying-glass:. The search matches part of the **unit number**, **make**, **model**, **VIN** or **license plate** and is not case sensitive. It searches within the tab you are on.

!!! warning "Search and type chips don't combine"
    Running a search clears the type chip, and clicking a type chip clears the search text. Use one or the other.

**Columns**

The list is sorted by type (alphabetically: Chassis, Trailer, Truck), then unit number, 25 units per page.

| Column | Shows |
|--------|-------|
| **Type** | A coloured badge: **Truck** (blue), **Trailer** (green), **Chassis** (orange) |
| **Unit #** | Unit number, or **-** |
| **Year / Make / Model** | For example *2019 Freightliner Cascadia*, or **-** |
| **VIN** | VIN, or **-** |
| **Plate** | License plate, or **-** |
| **Owner** | The owner's display name (see [How a customer's name is displayed](#how-a-customers-name-is-displayed)), or **-** |
| **Actions** | The buttons below |

**Row actions**

| Button | What it does |
|--------|-------------|
| :fontawesome-solid-clock-rotate-left: (tooltip *Service History*) | Opens the unit's [Service History](#service-history) page |
| :fontawesome-solid-pen-to-square: | Opens the equipment form |
| :fontawesome-solid-ban: (red, Active tab) | Disables the unit after you confirm *Disable this equipment?* in the **Are you sure?** dialog |
| :fontawesome-solid-check: (green, Disabled tab) | Enables the unit again, no confirmation |

When there is nothing to show, the list reads **No equipment yet** — *Track trucks, trailers, and chassis serviced in your garage.* with a **New Equipment** button.

### :fontawesome-solid-plus: Creating or editing equipment

1. Click **New Equipment** (or the :fontawesome-solid-pen-to-square: button on a row, or **Edit** on the Service History page).
2. Fill in the fields below. Use **Decode** to fill year, make and model from the VIN.
3. Click **Create Equipment** (new) or **Update Equipment** (edit). Click **Cancel** to go back to the list.

The list shows *Equipment created successfully.* or *Equipment updated successfully.* Errors appear in a red box at the top of the form.

| Field | Required | Notes |
|-------|----------|-------|
| **Equipment Type \*** | Yes | **Truck**, **Trailer** or **Chassis**. Starts on *Select type...* |
| **Unit Number** | No | Your or the customer's unit number |
| **Year** | No | A number; the field accepts 1970 to 2030 |
| **Make** | No | Placeholder *e.g. Freightliner, Volvo* |
| **Model** | No | |
| **VIN** | No | Placeholder *Enter 17-character VIN*, with the **Decode** button next to it |
| **License Plate** | No | |
| **Odometer** | No | A whole number, 0 or more. Also raised automatically from a work order's **Odometer In** (see below) |
| **Owner (Customer)** | No | The garage customer who owns the unit. Starts on *No owner* |
| **Notes** | No | Free text |

The edit page title is **Edit Equipment: (unit name)**, and the form card heading reads **Edit: (unit name)**.

!!! info "Odometer updates from work orders"
    When you save a work order for this unit with an **Odometer In** value higher than the unit's current **Odometer**, the unit's **Odometer** is updated to that value automatically. A lower value never replaces it.

#### :fontawesome-solid-tag: How a unit's name is displayed

Outside the list, a unit is shown as **Type - Unit Number - Year Make Model**, skipping the parts that are empty. For example *Truck - 104 - 2019 Freightliner Cascadia*, or just *Trailer* when only the type is set. The year is only shown when a make or model is filled in. On a work order, the selected unit also shows its owner after a dash: *Truck - 104 - 2019 Freightliner Cascadia — Jane Smith (Smith Hauling)*.

#### :fontawesome-solid-barcode: VIN Decode

The purple **Decode** button (tooltip *Decode VIN via NHTSA*) looks the VIN up in the free public VIN decoder of the U.S. National Highway Traffic Safety Administration (NHTSA), directly from your browser.

1. Type or paste the VIN in the **VIN** field.
2. Click **Decode**. The button shows **Decoding...** while it waits (up to 10 seconds).
3. If the decoder returns any of make, model or model year, the **Year**, **Make** and **Model** fields are filled in and a **VIN Decoded** message shows the result for 2 seconds.
4. Check the values and click **Create Equipment** or **Update Equipment**. Decoding alone does not save anything.

| Message | Meaning |
|---------|---------|
| *Please enter a valid VIN (at least 11 characters).* | The VIN field is empty or shorter than 11 characters. Nothing is sent. |
| **VIN Decoded** — *(year make model)* | The fields were filled in. |
| *VIN was found but no make/model/year data returned. Please enter manually.* | The decoder answered but had no make, model or year for this VIN. |
| *Unexpected response from NHTSA. Please enter vehicle details manually.* | The decoder's answer could not be read. |
| *Could not reach NHTSA VIN decoder. Please enter vehicle details manually.* | The decoder could not be reached (no internet, blocked, or no answer within 10 seconds). |

!!! warning "Decode replaces Year, Make and Model"
    A successful decode writes all three fields at once. If the decoder returns only some of them, the others are emptied. Re-type anything you want to keep before saving.

!!! info "Decoder coverage"
    NHTSA mainly covers vehicles sold in the U.S. A Canadian-market or older unit may decode only partly or not at all. You can always type the values yourself. The VIN itself is not checked for length or format when you save.

#### :fontawesome-solid-user: The Owner (Customer) dropdown

The **Owner (Customer)** dropdown lists active garage customers sorted by last name, shown with their display name.

!!! warning "The Owner list includes customers from all offices"
    Unlike the Customers page, which only shows your current office, the **Owner (Customer)** dropdown lists active garage customers from **every** office. With [multiple offices](multi-office.md), make sure you pick the customer from the right office, especially when two offices have customers with the same name. Adding a **Company Name** helps tell them apart.

#### :fontawesome-solid-bolt: Adding equipment from a work order

On the work order form, the green :fontawesome-solid-plus: button next to the **Equipment** field (tooltip *Quick create equipment*) opens **Quick Create Equipment**: **Equipment Type \*** (if empty you see *Equipment type is required.*), **Unit Number**, **Year**, **Make**, **Model** and **License Plate**. Click **Create & Select**: the unit is created in your current office, selected on the work order, and an *Equipment created* message appears. When a customer is already selected on the work order, the new unit is linked to that customer as its owner. VIN, odometer and notes can be added later from **Equipment**. See [Garage Work Orders](garage-work-orders.md).

### :fontawesome-solid-ban: Disabling and enabling equipment

1. On the **Active** tab, click the red :fontawesome-solid-ban: button on the unit's row.
2. In the **Are you sure?** dialog (*Disable this equipment?*), click **Yes, proceed**.
3. The list shows *(unit name) disabled.* and the unit moves to the **Disabled** tab.

To bring it back, open the **Disabled** tab and click the green :fontawesome-solid-check: button. The list shows *(unit name) enabled.*

A disabled unit:

- no longer appears in the work order **Equipment** search, so it can't be picked for new work orders,
- keeps its service history and stays on any existing work orders,
- can still be opened and edited from the **Disabled** tab.

There is no delete for garage equipment.

### :fontawesome-solid-clock-rotate-left: Service History

Click :fontawesome-solid-clock-rotate-left: on a unit's row to open its page. The title is the unit's display name, with a type badge, the unit number and the VIN under it, and an **Edit** button on the right.

<!-- TODO: Screenshot — Garage equipment Service History page showing the detail cards, the Total Work Orders / Total Spent / Last Service stats and the Service History table -->

**Detail cards**

| Card | Shows |
|------|-------|
| **Year / Make / Model** | For example *2019 Freightliner Cascadia*, or **-** |
| **Odometer** | The unit's current **Odometer** (from the equipment form, or raised by a work order's **Odometer In**), with thousands separators, or **-** |
| **License Plate** | Plate, or **-** |
| **Owner** | Owner's display name, or **-** |

**Stats**

| Stat | How it is calculated |
|------|----------------------|
| **Total Work Orders** | Every work order for this unit, in any status, **including estimates** |
| **Total Spent** | For all those work orders (including estimates and work orders not yet invoiced): parts (quantity × charge price) plus labour (hours × rate). It does **not** include the shop supplies fee, taxes or payments |
| **Last Service** | The most recent **Date In** of a work order that is **not** an estimate, for example *Mar 04, 2026*. Shows **None** when the unit only has estimates or no work orders |

!!! info "Total Spent is not an invoiced total"
    **Total Spent** is the sum of parts and labour lines on the unit's work orders, not what was billed or paid. To see billed and paid amounts, use [Garage Invoices](garage-invoices.md) or [Garage Reports](garage-reports.md).

**Service History table**

Lists every work order for the unit, newest **Date In** first, 20 per page.

| Column | Shows |
|--------|-------|
| **WO #** | The work order number (for example *#123*), as a link to the work order |
| **Date** | **Date In**, or **-** |
| **Description** | The work order description, cut to 50 characters |
| **Status** | **Estimate** (yellow), **Approved** (blue), **In progress** (purple), **Completed** (green), **Invoiced** (grey) |
| **Total** | Parts + labour + **Shop Supplies Fee** of that work order, before taxes |

With no work orders, the table shows *No service history for this equipment yet.* Click **Back to Equipment** at the bottom to return to the list.

---

## :fontawesome-solid-code-branch: How these differ from freight Customers and Equipments

The Garage keeps its own customers and equipment. Nothing is shared or synced with the freight side.

| | Garage | Freight |
|---|---|---|
| **Customers page** | Garage sidebar :fontawesome-solid-arrow-right: **Customers** | Left menu **Customers** ([Customers](managing-customers.md)) |
| **A customer is** | A person (first and last name) with an optional company name | A company, with people (users) invited under it |
| **Disable / delete customer** | Not available | Available (see [Customers](managing-customers.md)) |
| **Equipment page** | Garage sidebar :fontawesome-solid-arrow-right: **Equipment** | Left menu **Equipments** ([Equipment](equipment.md)) |
| **Equipment type** | Fixed: **Truck**, **Trailer**, **Chassis** | Types you create under the **Chassis**, **Truck** or **Trailer** sub categories |
| **Equipment is used on** | Garage work orders | Freight orders (chassis and trailers only) |
| **Tracks** | VIN, plate, odometer, owner, service history | Inspection date, mechanical status, availability |
| **Who can manage customers** | Admin, Manager, Garage | Admin, Manager (Dispatch only when the account allows it, see [Customers](managing-customers.md)) |
| **Who can manage equipment** | Admin, Manager, Garage | Admin, Manager, Dispatch, Customer Service |

!!! info "Same truck in both places"
    If you service your own fleet in the Garage, enter the unit again under Garage **Equipment** (for example with your company as a garage customer and owner). Work orders, inspection dates and mechanical status are not copied between the two lists.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-user-slash: How do I disable or delete a garage customer?

!!! info "Solution"
    You can't from the screen. Garage customers have no disable, enable or delete button. Leave the customer as is, or add a note in **Notes**.

### :fontawesome-solid-eye-slash: A unit doesn't show up when I search for it on a work order

!!! info "Solution"
    The work order **Equipment** search only shows **active** units of your **current office**, and once a **Customer** is selected on the work order it only shows that customer's units (the **Owner (Customer)** must match). Check the **Disabled** tab on **Equipment** and enable the unit with the green :fontawesome-solid-check: button, set the unit's **Owner (Customer)** to the work order's customer, or switch to the office the unit was created in.

### :fontawesome-solid-user-group: The Owner dropdown shows customers I don't see on the Customers page

!!! info "Solution"
    The **Owner (Customer)** dropdown lists active garage customers from all offices, while the Customers page only shows your current office. Pick the customer that belongs to your office. A **Company Name** on each customer makes them easier to tell apart.

### :fontawesome-solid-barcode: Decode says it could not reach NHTSA

!!! info "Solution"
    The lookup runs from your browser to the public NHTSA service. Check your internet connection, and that your network or browser extensions don't block it, then try again. If it still fails, type **Year**, **Make** and **Model** yourself and save.

### :fontawesome-solid-barcode: Decode cleared a field I had filled in

!!! info "Solution"
    A successful decode writes **Year**, **Make** and **Model** together, and empties any of them the decoder didn't return. Re-type the missing value before you click **Update Equipment**. Nothing changes until you save, so you can also click **Cancel**.

### :fontawesome-solid-envelope: The accountant didn't get the invoice email

!!! info "Solution"
    Open the customer from **Customers** :fontawesome-solid-arrow-right: :fontawesome-solid-pen-to-square: and check the **Accountant Email** is filled and spelled correctly. It is added in CC only when the email is sent after it was saved.

### :fontawesome-solid-calculator: Total Spent doesn't match the customer's invoices

!!! info "Solution"
    **Total Spent** adds parts and labour of every work order on the unit, including estimates and work orders not yet invoiced, and leaves out the shop supplies fee and taxes. Invoices only cover invoiced work orders (an invoice can group several, possibly for other units) and can add taxes and discounts. See [Service History](#service-history).

### :fontawesome-solid-magnifying-glass: My search ignores the Truck/Trailer/Chassis chip

!!! info "Solution"
    The search box and the type chips don't combine: searching clears the chip and clicking a chip clears the search. Search by unit number, make, model, VIN or plate, or use a chip on its own.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Best Practices"
    - Fill in **Company Name** for every customer that is a business. It shows next to the name everywhere you pick a customer.
    - Add an **Accountant Email** for customers whose bookkeeper should get invoices, so you don't have to forward them.
    - Always enter the **VIN** and use **Decode**, then check the result. The VIN is also searchable on the Equipment list.
    - Set the **Owner (Customer)** on every unit. On a work order, once a customer is selected, the **Equipment** search lists only that customer's units, so a unit without an owner won't show up there.
    - Disable units that are sold or scrapped instead of leaving them active. Their service history is kept.
    - Enter **Odometer In** on each work order. It keeps the unit's **Odometer** current automatically, so the Service History page shows the latest reading.
