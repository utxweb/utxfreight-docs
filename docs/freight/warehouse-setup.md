# Warehouse Buildings, Locations, Products, Units & Charges

Set up the master data the Warehouse add-on needs before you create warehouse orders: **Buildings**, **Locations**, **Products**, **Units of Measure** and warehouse **Charges**.

## :fontawesome-solid-warehouse: Overview

These five lists are the building blocks of a warehouse order. You set them up once, then pick from them on every order line and charge row.

- :fontawesome-solid-building: **Buildings** are your warehouse sites, with an address, a city, a contact and an email.
- :fontawesome-solid-location-dot: **Locations** are the storage spots inside a building (an aisle, a bay, a room). Every location belongs to one building.
- :fontawesome-solid-ruler-combined: **Units of Measure** describe the footprint of what you store (for example a pallet). Their **Length (inch)** and **Width (inch)** give the floor area in square feet that **Monthly** charges are billed on.
- :fontawesome-solid-box: **Products** are the goods you store, with a **Name**, a **Sku**, an optional default location and unit of measure, and an optional image.
- :fontawesome-solid-dollar-sign: **Charges** are the warehouse fees: charge types with **Service** = **Warehouse**. **Monthly** charges are billed per square foot per month; **Fixed** charges are added once.
- :fontawesome-solid-toggle-on: Buildings, locations, units of measure and products share the same list behaviour: **All Active** / **Disabled** filters, an **Actions** menu with **Edit**, **Disable** and **Enable**, and a short notification when you disable or enable an entry. See [Shared list behaviour](#shared-list-behaviour).
- :fontawesome-solid-trash-can: None of these records can be deleted from the screen. Disable them instead.

For how these records are used on orders and how storage is billed, see [Warehouse Module Overview](warehouse-overview.md) and [Warehouse Orders](warehouse-orders.md).

<!-- TODO: Screenshot — Main menu with the Warehouse group expanded (Orders, Product, Location, Charges, Unit of Measure, Building) -->

---

## :fontawesome-solid-bolt: Quick Start

Set things up in this order, because each step uses the one before it:

1. :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Building** → **Add a new Warehouse Building**. Enter the **Name** and click **Save Changes**.
2. :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Location** → **Add a new Warehouse Location**. Enter the **Name**, pick the **Building** and click **Save Changes**.
3. :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Unit of Measure** → **Add a new Unit Of Measure**. Enter the **Name**, **Length (inch)** and **Width (inch)** and click **Save Changes**.
4. :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Product** → **Add a new Warehouse Product**. Enter the **Name** and **Sku**, optionally pick a **Location** and **Unit of Measure**, and click **Save Changes**.
5. :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Charges** → **Add a new Order Charge**. Set **Charge Type** = **Income**, **Service** = **Warehouse**, choose **Value Type** **Monthly** (storage) or **Fixed** (one-time fee), enter the **Default Rate** and click **Save**.

You can now create a warehouse order. See [Warehouse Orders](warehouse-orders.md).

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Building, Location, Unit of Measure, Product | Charges |
|------|:---:|:---:|
| :fontawesome-solid-user-shield: **Admin** | Full access | Full access |
| :fontawesome-solid-warehouse: **Warehouse** | Full access | Full access |
| :fontawesome-solid-user-tie: **Manager** | No access | Full access to the Charge Types page, but no **Warehouse** menu |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access | Full access to the Charge Types page, but no **Warehouse** menu |
| :fontawesome-solid-headset: **Dispatch** | No access | Only when **Can manage rates?** is checked on the user's form, and no **Warehouse** menu |
| :fontawesome-solid-user: **All other roles** | No access | No access |

- The **Warehouse** add-on must be turned on. When it is off, the **Warehouse** menu group is hidden and opening a Building, Location, Unit of Measure or Product page redirects you away (Admins land on the freight **Orders** list, Warehouse users on the home page). The **Charges** page (Charge Types) stays available, but without the **Warehouse** and **Intermodal** filter buttons. See [Add-ons & Options](add-ons-and-options.md).
- The **Warehouse** menu group is only shown to **Admin** and **Warehouse** users.
- There are no finer permissions inside these pages: anyone who can open a list can add, edit, disable and enable its entries.

**How to get there:**

- :fontawesome-solid-arrow-right: Main menu :fontawesome-solid-warehouse: **Warehouse** — click it to expand the group, then click **Product**, **Location**, **Charges**, **Unit of Measure** or **Building**.
- :fontawesome-solid-arrow-right: **Warehouse** > **Charges** opens the Charge Types page (title **Order Charges**) already on its **Warehouse** filter. The same page is also in the user menu as **Charge Types**. See [Charge Types & Taxes](charge-types-and-taxes.md).

!!! info "Multi-office"
    Every building, location, unit of measure, product and charge has an **Office**. Each list shows the entries of the office you are currently working in. When the Multi-Office add-on is on, these records are shared: every office sees all of them, and the dropdowns on the setup forms (for example **Building** on a location, **Location** and **Unit of Measure** on a product) list the entries of every office. The **Office** dropdown on each form lists the offices you belong to. See [Multi-Office](multi-office.md).

---

## :fontawesome-solid-list: Shared List Behaviour

The **Building**, **Location**, **Unit of Measure** and **Product** pages all work the same way.

### Page header

| Page | Menu item | Page title | Subtitle | Add button |
|------|------|------|------|------|
| Buildings | **Building** | **Warehouse Buildings** | *Management of Warehouse Buildings* | **Add a new Warehouse Building** |
| Locations | **Location** | **Warehouse Locations** | *Management of Warehouse Locations* | **Add a new Warehouse Location** |
| Units of Measure | **Unit of Measure** | **Unit Of Measures** | *Management of Unit Of Measures* | **Add a new Unit Of Measure** |
| Products | **Product** | **Warehouse Products** | *Management of Warehouse Products* | **Add a new Warehouse Product** |
| Charges | **Charges** | **Order Charges** | *Management of Order Charges* | **Add a new Order Charge** |

The add button sits at the top right of the page. Clicking it opens the form on its own page, titled **New …** (for example **New Warehouse Building**). **Actions** → **Edit** opens the same form titled **Edit …** (for example **Edit Warehouse Building**).

### Filters

| Button | Shows |
|--------|-------|
| **All Active** | Entries whose **Active** box is checked. The page opens on this filter. |
| **Disabled** | Entries whose **Active** box is unchecked. |

The selected filter button is highlighted in green. Lists show 50 entries per page, with page links below the table.

### Name colour and Active column

- The **Name** is shown in **green** for an active entry and in **red** for a disabled one.
- The **Active** column shows a green :fontawesome-solid-circle-check: for active and a red :fontawesome-solid-circle-xmark: for disabled.

### Actions menu

Each row ends with an **Actions** button (:fontawesome-solid-gear:) and a dropdown arrow. The menu contains:

| Action | What it does |
|--------|--------------|
| **Edit** | Opens the form to change the entry. |
| **Disable** | Shown on active entries. Unchecks **Active** right away, without leaving the page. |
| **Enable** | Shown on disabled entries. Checks **Active** again, without leaving the page. |

After **Disable** or **Enable**, the row updates in place (the name changes colour and the **Active** icon flips) and a message appears at the top of the screen for about two seconds:

| Action | Message (title **Update**) | Colour |
|--------|------|------|
| Disable a building | *Warehouse building **Name** - Disabled* | Red |
| Enable a building | *Warehouse building **Name** - Enabled* | Green |
| Disable / Enable a location | *Warehouse location **Name** - Disabled* / *- Enabled* | Red / Green |
| Disable / Enable a unit of measure | *Unit of measure **Name** - Disabled* / *- Enabled* | Red / Green |
| Disable / Enable a product | *Warehouse product **Name** - Disabled* / *- Enabled* | Red / Green |

The row stays in the list you are looking at until you reload the page or switch filter. You can also disable or enable an entry by unchecking or checking **Active** in its form.

### Saving and cancelling

- Every form ends with **Save Changes** (blue) and **Cancel** (red, on the right).
- **Save Changes** saves and returns you to the list, on its **All Active** filter. While saving, the button reads *Please wait...*.
- If a required field is missing, the form stays open and shows the error next to the field.
- **Cancel** returns to the list without saving.

---

## :fontawesome-solid-building: Buildings

Menu: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Building**

<!-- TODO: Screenshot — Warehouse Buildings list with All Active / Disabled filters and the Actions menu open on one row -->

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The building name, green if active, red if disabled |
| **Address** | The street address |
| **Zip** | The postal code |
| **City** | The city picked in **City (Must exist)** |
| **Country** | **Canada** or **United States** |
| **Contact Info** | Free text, for example a contact name and phone number |
| **Email** | The building's email address |
| **Active** | Green check (active) or red cross (disabled) |
| *(Actions)* | **Edit**, **Disable** / **Enable** |

### Creating a Building

1. Click **Add a new Warehouse Building**.
2. Fill in the **Warehouse Building Information** form (see the table below).
3. Click **Save Changes**.

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | Yes | The building name (placeholder *warehouse building name*) |
| **Office** | Yes | The office the building belongs to. Lists the offices you belong to; no blank option |
| **Address** | No | The street address |
| **City (Must exist)** | No | Picked from the **active cities** of your current office. The city must already exist; add it first in **Manage Cities** if needed. See [Zones & Cities](zones-and-cities.md) |
| **Postal Code** | No | Shown in the **Zip** column |
| **Country** | No | **Canada** or **United States**. No blank option, so **Canada** is selected by default |
| **Contact Info** | No | Free text |
| **Email** | No | The building's email address |
| **Active** | — | In the **Warehouse building visibility** section. Checked by default for a new building |

!!! info "Why disable a building"
    Only **active** buildings of your current office are offered in the **Building** dropdown when you create or edit a location. Disabling a building does not change the locations that already belong to it.

---

## :fontawesome-solid-location-dot: Locations

Menu: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Location**

<!-- TODO: Screenshot — Warehouse Locations list showing Name, Building and Active columns -->

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The location name, green if active, red if disabled |
| **Building** | The building the location belongs to |
| **Active** | Green check (active) or red cross (disabled) |
| *(Actions)* | **Edit**, **Disable** / **Enable** |

### Creating a Location

1. Make sure the building exists and is active (see [Buildings](#buildings)).
2. Click **Add a new Warehouse Location**.
3. Fill in the **Warehouse Location Information** form (see the table below).
4. Click **Save Changes**.

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | Yes | The location name (placeholder *warehouse location name*), for example an aisle or bay code |
| **Office** | Yes | The office the location belongs to. Lists the offices you belong to; no blank option |
| **Building** | Yes | Picked from the **active buildings** of your current office. No blank option |
| **Active** | — | In the **Warehouse location visibility** section. Checked by default for a new location |

!!! info "Where locations are used"
    - A product's default **Location** is picked from the **active** locations of your current office.
    - Each line of a warehouse order has its own **Location**. See [Warehouse Orders](warehouse-orders.md).

---

## :fontawesome-solid-ruler-combined: Units of Measure

Menu: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Unit of Measure**

A unit of measure is the footprint of one stored item, such as a standard pallet. Its length and width are what **Monthly** warehouse charges are billed on.

<!-- TODO: Screenshot — Unit Of Measures list showing Name, Length, Width and Active columns -->

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The unit name, green if active, red if disabled |
| **Length** | The length in inches |
| **Width** | The width in inches |
| **Active** | Green check (active) or red cross (disabled) |
| *(Actions)* | **Edit**, **Disable** / **Enable** |

### Creating a Unit of Measure

1. Click **Add a new Unit Of Measure**.
2. Fill in the **Unit of Measure Information** form (see the table below).
3. Click **Save Changes**.

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | Yes | The unit name (placeholder *Unit of measure name*), for example *Pallet 48x40* |
| **Office** | Yes | The office the unit belongs to. Lists the offices you belong to; no blank option |
| **Length (inch)** | No, but needed for billing | Length of one item, **in inches**. Decimals are allowed |
| **Width (inch)** | No, but needed for billing | Width of one item, **in inches**. Decimals are allowed |
| **Active** | — | In the **Unit of measure visibility** section. Checked by default for a new unit |

### How length and width drive billing

For each line of a warehouse order, the app converts the line's unit of measure to square feet:

**sq ft = (Length (inch) ÷ 12) × (Width (inch) ÷ 12)**

Each **Monthly** charge on the order then adds:

**sq ft × Quantity × charge rate × number of months**

The number of months counts calendar months from the order's **Storage Date** to its **Closing Date** (or today, while the order is open), including both the first and the last month. **Fixed** charges are added once and do not use the unit of measure. See [How Storage Is Billed](warehouse-overview.md#how-storage-is-billed) for a worked example.

| Length (inch) | Width (inch) | sq ft per item |
|:---:|:---:|:---:|
| 48 | 40 | 4 × 3.33 = 13.33 |
| 48 | 48 | 4 × 4 = 16 |
| 120 | 96 | 10 × 8 = 80 |

!!! warning "Enter both dimensions, in inches"
    - If **Length (inch)** or **Width (inch)** is empty, order lines that use this unit are **skipped by Monthly charges**: only Fixed charges count for them.
    - The values are read as inches. Entering feet (for example 4 instead of 48) bills 1/144 of the expected area.
    - Editing a unit's dimensions changes the total shown for every warehouse order that uses it, including existing ones, because the **Warehouse Orders** list recalculates the total from the current values each time it is displayed.

---

## :fontawesome-solid-box: Products

Menu: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Product**

<!-- TODO: Screenshot — Warehouse Products list showing Name, Sku, Location, Unit of Measure, Image and Active columns -->

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The product name, green if active, red if disabled |
| **Sku** | The product SKU |
| **Location** | The product's default location |
| **Unit of Measure** | The product's default unit of measure |
| **Image** | An :fontawesome-solid-image: icon. Click it to open the product image in a new tab |
| **Active** | Green check (active) or red cross (disabled) |
| *(Actions)* | **Edit**, **Disable** / **Enable** |

### Creating a Product

1. Click **Add a new Warehouse Product**.
2. Fill in the **Warehouse Product Information** form (see the table below).
3. Click **Save Changes**.

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | Yes | The product name (placeholder *warehouse product name*) |
| **Sku** | Yes | The product SKU (placeholder *warehouse product sku*) |
| **Location** | No | Default location. Picked from the **active locations** of your current office; can be left blank |
| **Unit of Measure** | No | Default unit of measure. Picked from the **active units of measure** of your current office; can be left blank |
| **Image** | No | Upload a picture of the product, for example a JPG or PNG |
| **Office** | Always set | The office the product belongs to. Lists the offices you belong to; no blank option, so one is always selected |
| **Active** | — | In the **Warehouse product visibility** section. Checked by default for a new product |

!!! info "Default location and unit of measure"
    The product's **Location** and **Unit of Measure** are reference values shown in the Products list. On a warehouse order, you pick the **Unit of Measure** and **Location** on each order line.

!!! tip "Search warehouse orders by product"
    The search box on **Warehouse Orders** matches product **Name** and **Sku**, so a clear, unique SKU makes orders easy to find. See [Warehouse Orders](warehouse-orders.md).

---

## :fontawesome-solid-dollar-sign: Warehouse Charges

Menu: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Charges**

Warehouse charges are ordinary charge types (page title **Order Charges**) whose **Service** is **Warehouse**. The menu item opens the Charge Types page on its **Warehouse** filter. The full page is documented in [Charge Types & Taxes](charge-types-and-taxes.md); this section covers what matters for the warehouse.

<!-- TODO: Screenshot — Order Charges list on the Warehouse filter, showing Service = Warehouse and Rate Type Fixed / Monthly -->

### Filters

| Button | Shows |
|--------|-------|
| **All Active** | Active charge types of every service |
| **Disabled** | Disabled charge types of every service |
| **Warehouse** | Charge types whose **Service** is **Warehouse**, active and disabled, Income and Expense. This is where **Warehouse** > **Charges** opens |
| **Intermodal** | Charge types whose **Service** is **Intermodal**, active and disabled |

The **Warehouse** and **Intermodal** buttons are only shown when the Warehouse add-on is on. Charge types are sorted by name, 50 per page. When the Fuel Surcharge add-on is on, charge types whose **Use For** is **Fuel Surcharge** are hidden from this list (they are managed on the Fuel Schedule) and a **Back to Fuel Schedule** button is shown.

### Columns

| Column | Description |
|--------|-------------|
| **ID** | The charge type's number |
| *(icon)* | A :fontawesome-solid-warehouse: warehouse icon for Warehouse charges, a :fontawesome-solid-ship: ship icon for Intermodal ones |
| **Name** | Green if active, red if disabled |
| **Service** | **Warehouse** or **Intermodal** |
| **Type** | **Income** or **Expense** |
| **Default Rate** | The rate, shown as a dollar amount |
| **Rate Type** | **Fixed** or **Monthly** |
| **Use For** | **Terminal Fee** (or **Fuel Surcharge**) when set, otherwise *not set* |
| **Effective Period** | The **Applicable on** month when set, otherwise *not set* |
| **Active** | Green check (active) or red cross (disabled) |
| *(Actions)* | **Edit**, **View History** |

!!! info "No Disable / Enable action on charges"
    Unlike the other warehouse lists, the Charges **Actions** menu has no **Disable** or **Enable** item. To disable a charge, open **Edit**, uncheck **Active** and click **Save**.

### Creating a Warehouse Charge

1. Navigate to :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Charges**.
2. Click **Add a new Order Charge**.
3. Fill in the **Order Charge Information** form:

| Field | Set it to | Description |
|-------|------|-------------|
| **Name** | Required | The charge name shown on the warehouse order (placeholder *Category Name*), for example *Storage per sq ft* or *Handling in/out* |
| **Charge Type** | **Income** | **Income** (selected by default) or **Expense**. Only **Income** charges are offered on warehouse orders |
| **Default Rate** | Required, a number | For **Monthly**: the price **per square foot per month**. For **Fixed**: the flat amount |
| **Value Type** | **Fixed** or **Monthly** | **Fixed** is selected by default. See [Fixed vs Monthly](#fixed-vs-monthly) below |
| **Service** | **Warehouse** | **Warehouse** is only offered when the add-on is on. Only **Warehouse** charges are offered on warehouse orders |
| **Office** | Required | The office the charge belongs to. Lists the offices you belong to; no blank option |
| **Use as default for** | Leave blank | Used for the freight **Terminal Fee** (and **Fuel Surcharge** when the Fuel Surcharge add-on is on). Not used by warehouse orders |
| **Applicable on (Month)** | Leave blank | Only shown when the Fuel Surcharge add-on is on. Not used by warehouse orders |
| **Active** | Checked | Uncheck to move the charge to the **Disabled** filter |

4. Click **Save**. You return to the Charge Types list on **All Active** (not on the **Warehouse** filter).

### Fixed vs Monthly

| Value Type | How it is billed on a warehouse order | Typical use |
|------|------|------|
| **Fixed** | Added **once** to the order total, at the rate on the order | Receiving, handling, shipping out, labelling |
| **Monthly** | For every product line: **sq ft × Quantity × rate × number of months** | Storage space |

The square footage comes from the line's unit of measure (see [How length and width drive billing](#how-length-and-width-drive-billing)).

### Customer custom rates

A customer can have its own price for a warehouse charge, which replaces the **Default Rate** on that customer's orders.

1. Navigate to :fontawesome-solid-arrow-right: **Customers** and open the customer. **Customers** is available to Admins and Managers, and to Dispatch users when this has been turned on for your account (ask UTX support). Warehouse users cannot open **Customers**.
2. In **Custom rates for this customer**, click **(+) Add another**.
3. In the **Charge** dropdown, pick the charge in the **Warehouse** group. The group lists the **active** charges with the Warehouse service (Income and Expense).
4. Enter the customer's **Rate** and click **Save Changes**.

On a warehouse order for a person of that customer, the charge dropdown shows the custom rate, for example *Storage per sq ft (0.45$)*, and picking the charge pre-fills the **Rate** box with it. Changing the person in **Place the order on behalf of** reloads the charge rates for the new customer and resets the **Rate** box of every charge row already on the form to that customer's rate (or the **Default Rate**), so re-check any rate you typed by hand. The rate stays editable on each order. See [Managing Customers](managing-customers.md) and [Warehouse Orders](warehouse-orders.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the Warehouse menu or the setup pages

!!! info "Solution"
    The Warehouse add-on must be on and your role must be **Admin** or **Warehouse**. If the add-on is off, opening a Building, Location, Unit of Measure or Product page redirects you away from it. See [Add-ons & Options](add-ons-and-options.md) and [User Roles](user-roles.md).

### :fontawesome-solid-building: The Building dropdown is empty when I create a location

!!! info "Solution"
    The dropdown only lists **active** buildings of the office you are working in. Create the building first, or open **Building** → **Disabled** and use **Actions** → **Enable**.

### :fontawesome-solid-city: My city is missing from "City (Must exist)"

!!! info "Solution"
    The list shows the **active** cities of your current office. Add or enable the city in **Manage Cities** first. See [Zones & Cities](zones-and-cities.md).

### :fontawesome-solid-box: A location or unit of measure is missing from the product form

!!! info "Solution"
    The product form only offers **active** locations and units of measure of your current office. Check the **Disabled** filter on **Location** or **Unit of Measure** and enable the entry.

### :fontawesome-solid-dollar-sign: Storage is not billed for some product lines

!!! info "Solution"
    Open **Unit of Measure** and check that the unit used on those lines has both **Length (inch)** and **Width (inch)**. Without both, Monthly charges skip the line. Also check that the storage charge's **Value Type** is **Monthly**.

### :fontawesome-solid-calculator: The storage amount is far too high or too low

!!! info "Solution"
    Check that the unit's **Length (inch)** and **Width (inch)** are in **inches**, and that the Monthly charge's rate is a price **per square foot per month**. For example, a 48 × 40 pallet is 13.33 sq ft.

### :fontawesome-solid-ban: A charge is missing from the warehouse order

!!! info "Solution"
    Only charges with **Charge Type** = **Income** and **Service** = **Warehouse** are offered. Open **Warehouse** > **Charges** (the **Warehouse** filter shows Income and Expense) and check the **Type** and **Service** columns.

### :fontawesome-solid-user-tag: The customer's custom rate is not used

!!! info "Solution"
    Check that the custom rate on the customer points to the right charge in the **Warehouse** group, and that the order is placed on behalf of a person of that customer. If you changed the person after adding charges, check that the **Rate** box was refreshed.

### :fontawesome-solid-trash-can: How do I delete a building, location, unit, product or charge?

!!! info "Solution"
    You can't from the screen. Use **Actions** → **Disable** (or uncheck **Active** on a charge). Disabled entries move to the **Disabled** filter and stay linked to existing orders.

---

!!! tip "Best Practices"
    - Follow the setup order: **Building** → **Location** → **Unit of Measure** → **Product** → **Charges**.
    - Always enter both **Length (inch)** and **Width (inch)** on a unit of measure, in inches.
    - Use **Monthly** charges for storage (rate per sq ft per month) and **Fixed** charges for one-time fees.
    - Give each product a unique **Sku** so warehouse orders are easy to search.
    - Use **Custom rates for this customer** for negotiated prices instead of editing the rate on every order.
    - Disable entries you no longer use.
