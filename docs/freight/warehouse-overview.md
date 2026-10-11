# Warehouse Module Overview

The **Warehouse** add-on lets you bill customers for storing their goods: you record what a customer stores, where, and on what kind of space, and UTX Freight works out the storage charge from the floor space used and the number of months the goods stay in the warehouse.

## :fontawesome-solid-warehouse: Overview

- :fontawesome-solid-puzzle-piece: **Warehouse** is an add-on. It only appears when it is turned on for your installation. See [Add-ons & Options](add-ons-and-options.md).
- :fontawesome-solid-bars: It adds a **Warehouse** group to the main (left) menu with six items: **Orders**, **Product**, **Location**, **Charges**, **Unit of Measure** and **Building**.
- :fontawesome-solid-box: The core record is the **Warehouse Order**: a storage order placed on behalf of a customer, with a **Storage Date**, an optional **Container Number**, one or more product lines (product, quantity, unit of measure, location) and the charges to bill.
- :fontawesome-solid-ruler-combined: Storage is billed by **space and time**. Each unit of measure has a **Length (inch)** and **Width (inch)**, which give a floor area in square feet. **Monthly** charges are multiplied by that area, the quantity stored and the number of months; **Fixed** charges are added once. See [How storage is billed](#how-storage-is-billed).
- :fontawesome-solid-flag-checkered: A warehouse order stays open (it is listed under the **Open** filter and its status icon reads "New Order") while the goods are in storage. When they leave, you click **Complete** and enter a **Closing Date**, which stops the month count.
- :fontawesome-solid-user-gear: Only **Admin** and **Warehouse** users can use it. A **Warehouse** user lands on **Warehouse Orders** after signing in and does not see the freight **Orders** page.
- :fontawesome-solid-users: Only customers whose **Service** is **Warehouse** or **Intermodal & Warehouse** can have warehouse orders.

!!! info "Warehouse orders are separate from freight orders"
    Warehouse orders have their own list, numbering and statuses. They do not appear in the freight **Orders** list, on **Dispatch**, or in the driver app, and they are not turned into freight invoices from the **Invoices** page.

<!-- TODO: Screenshot — Main menu with the Warehouse group expanded (Orders, Product, Location, Charges, Unit of Measure, Building) and the Warehouse Orders page open -->

---

## :fontawesome-solid-bolt: Quick Start

1. Create at least one **Building**: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Building**.
2. Create the **Locations** inside that building: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Location**.
3. Create your **Units of Measure** with their **Length (inch)** and **Width (inch)**: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Unit of Measure**.
4. Create the **Products** you store (name and SKU, optional default location and unit of measure): :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Product**.
5. Create your warehouse **Charges** with **Charge Type** = **Income** and **Service** = **Warehouse**: :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Charges**.
6. Make sure the customer's **Service** is **Warehouse** or **Intermodal & Warehouse** and that it has at least one active person: :fontawesome-solid-arrow-right: **Customers**.
7. Go to :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Orders** and click **Create new Warehouse Order**.

Details for each setup step are in [Warehouse Setup](warehouse-setup.md). Creating, completing and searching orders is covered in [Warehouse Orders](warehouse-orders.md).

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Warehouse access |
|------|------------------|
| :fontawesome-solid-user-tie: **Admin** | Full access to every Warehouse page, plus all freight pages |
| :fontawesome-solid-warehouse: **Warehouse** | Full access to warehouse **Orders**, **Product**, **Location**, **Charges**, **Unit of Measure** and **Building**. On the **Charges** page they can manage every charge, not only Warehouse ones. No access to freight **Orders**, **Dispatch**, **Invoices** or **Customers** |
| :fontawesome-solid-headset: **Manager**, **Dispatch**, **Customer Service**, **Accountant**, **Customer**, **Garage**, drivers and yard workers | No access. The **Warehouse** menu group is hidden |

- The add-on must be turned on. If it is off, the **Warehouse** menu group is hidden for everyone, and opening a Warehouse page sends you back to the main application.
- The **Warehouse** role is only offered in the role list when the Warehouse add-on is on. See [User Roles](user-roles.md) and [People & Invitations](people-and-invitations.md).
- Inside the Warehouse module there are no finer permissions: a Warehouse user can create, edit and complete orders, and create, edit, enable and disable buildings, locations, units of measure, products and charges.

!!! warning "Managers do not see the Warehouse menu"
    Unlike the Garage add-on, the Warehouse module is not available to the **Manager** role. Only **Admin** and **Warehouse** users see the **Warehouse** menu group.

**Where to find it:**

- :fontawesome-solid-arrow-right: Main menu :fontawesome-solid-warehouse: **Warehouse** — click it to expand the group, then pick an item.

### :fontawesome-solid-building: Offices

- **Warehouse orders are not office-scoped.** Admin and Warehouse users see every warehouse order in the **Warehouse Orders** list, whatever office they are working in.
- **Setup records belong to an office.** Buildings, locations, units of measure, products and charges each have an **Office** field, and their setup lists show the records of the office you are currently working in.
- **The warehouse order form is not filtered by office.** The product, unit of measure and location lists on an order line show products, units of measure and locations from all offices. The charge list shows Income charges with the Warehouse service, also from all offices.
- The customer list in the order form (**Place the order on behalf of**) shows the people of the current office.

See [Multi-Office](multi-office.md) for how offices work.

---

## :fontawesome-solid-door-open: Landing Page

| Who signs in | Where they land |
|------|------|
| **Warehouse** user, add-on on | **Warehouse Orders** (the **Open** filter) |
| **Warehouse** user, add-on off | The home page of the application. There is nothing else for this role to open |
| **Admin** | The freight **Orders** page, as usual. Open the **Warehouse** menu group to get to warehouse orders |

The **Warehouse Orders** page header shows three counters, **Open Orders**, **Completed** and **Total**, and the **Create new Warehouse Order** button. Below it are the filters **All**, **Open**, **Completed** and **Not Invoiced**, and a toggle between the **Orders** view (one row per order) and the **Products** view (one row per product line).

!!! info "What a Warehouse user sees in the menu"
    A Warehouse user's main menu contains the **Warehouse** group. The freight **Orders** item is hidden for this role, as are **Dispatch**, **Invoices**, **Customers** and the other freight items. If the Fuel Surcharge add-on is also on, the **Fuel Schedule** item is visible to Warehouse users too, because they can manage charges.

---

## :fontawesome-solid-bars: The Warehouse Menu

The **Warehouse** group lists its items in this order:

| Menu item | What it opens | Details |
|------|------|------|
| :fontawesome-solid-box: **Orders** | **Warehouse Orders**: the list of storage orders, with **Create new Warehouse Order** | [Warehouse Orders](warehouse-orders.md) |
| :fontawesome-solid-barcode: **Product** | The products you store, each with a **Name**, **Sku**, an optional default **Location** and default **Unit of Measure**, and an optional **Image** | [Warehouse Setup](warehouse-setup.md) |
| :fontawesome-solid-location-dot: **Location** | Storage locations, each belonging to a **Building** | [Warehouse Setup](warehouse-setup.md) |
| :fontawesome-solid-dollar-sign: **Charges** | The **Charges** list opened on its **Warehouse** filter: charge types whose **Service** is Warehouse | [Warehouse Setup](warehouse-setup.md), [Charge Types & Taxes](charge-types-and-taxes.md) |
| :fontawesome-solid-ruler-combined: **Unit of Measure** | Units of measure with their **Length (inch)** and **Width (inch)**, which drive the space calculation | [Warehouse Setup](warehouse-setup.md) |
| :fontawesome-solid-building: **Building** | Warehouse buildings, with **Address**, **City (Must exist)**, **Postal Code**, **Country**, **Contact Info** and **Email** | [Warehouse Setup](warehouse-setup.md) |

---

## :fontawesome-solid-list-ol: Setup Order

Some records must exist before others can be created. Set things up in this order:

| Step | What | Why it comes here |
|------|------|------|
| 1 | :fontawesome-solid-building: **Building** | A location must belong to a building. The building's **City (Must exist)** is picked from your active cities, so add the city first if needed (see [Zones & Cities](zones-and-cities.md)) |
| 2 | :fontawesome-solid-location-dot: **Location** | Each location needs a **Building**. Only active buildings are offered |
| 3 | :fontawesome-solid-ruler-combined: **Unit of Measure** | Gives the floor area used for monthly billing. Fill in both **Length (inch)** and **Width (inch)** |
| 4 | :fontawesome-solid-barcode: **Product** | A product's optional default **Location** and **Unit of Measure** are picked from the active ones you created in steps 2 and 3. **Name** and **Sku** are required. The defaults are shown in the product list; they are not filled in automatically on warehouse order lines |
| 5 | :fontawesome-solid-dollar-sign: **Charges** | Create charges with **Charge Type** = **Income** and **Service** = **Warehouse**. Use **Value Type** = **Monthly** for storage billed per square foot per month, and **Fixed** for one-time fees (handling, in/out, etc.) |
| 6 | :fontawesome-solid-users: **Customer** with the Warehouse service | Only customers whose **Service** is **Warehouse** or **Intermodal & Warehouse** can be picked on a warehouse order (see below) |

!!! tip "Only Income charges with the Warehouse service appear on orders"
    The charge list on a warehouse order shows only charges whose **Charge Type** is **Income** and whose **Service** is **Warehouse**. A charge set to **Expense**, or to the **Intermodal** service, will not be offered.

### :fontawesome-solid-users: Customers and the Warehouse service

Customers are set up in the freight **Customers** page by a user who can manage customers, such as an Admin or Manager (Warehouse users cannot open **Customers**). See [Managing Customers](managing-customers.md).

1. Navigate to :fontawesome-solid-arrow-right: **Customers** and open or create the customer.
2. Set **Service** to **Warehouse** or **Intermodal & Warehouse**.
3. Make sure the customer is active and has at least one active person. A warehouse order is placed on behalf of a person, and the order form lists each person as their name in capitals followed by the customer name in brackets.
4. Optional: under **Custom rates for this customer**, pick a charge from the **Warehouse** group and enter the customer's own rate. When you pick one of this customer's people on a warehouse order, the charge list shows that rate next to the charge name and pre-fills it in the rate box.
5. Click **Save**.

With the add-on on, the **Customers** list also has **Warehouse** and **Intermodal** filters, so you can see which customers have each service.

---

## :fontawesome-solid-tags: Company Service Types

Every customer has a **Service** that says what you do for them. The choices depend on which add-ons are on:

| Service | Shown when | Effect |
|------|------|------|
| **Intermodal** | Always | The customer's people can be picked on freight orders. They cannot be picked on warehouse orders |
| **Warehouse** | Warehouse add-on on | The customer's people can be picked on warehouse orders. They do not appear in the freight order form's **Place the order on behalf of** list |
| **Intermodal & Warehouse** | Warehouse add-on on | The customer can be used on both freight orders and warehouse orders |
| **Garage** | Garage add-on on | Used by the Garage add-on. See [Garage Module Overview](garage-overview.md) |

Charges also carry a **Service** (for example **Intermodal** or **Warehouse**). The **Warehouse** service is only offered on the charge form when the Warehouse add-on is on.

---

## :fontawesome-solid-calculator: How Storage Is Billed

The amount shown in the **Invoiced Rate** column of the **Warehouse Orders** list is calculated as follows:

1. **Fixed** charges on the order are added once, at the rate entered on the order.
2. For each product line, the floor area is worked out from its unit of measure: (**Length (inch)** ÷ 12) × (**Width (inch)** ÷ 12) = square feet.
3. For each **Monthly** charge on the order: square feet × **Quantity** × charge rate × number of months, added for every product line.
4. The number of months counts calendar months from the **Storage Date** to the **Closing Date**, **including both the first and the last month**. While the order is still open, today's date is used instead of a closing date.

!!! info "Example"
    A unit of measure of 48 × 40 inches is 4 ft × 3.33 ft = 13.33 sq ft. Ten of them stored from March 20 to May 5 count as 3 months (March, April, May). With a Monthly charge of $0.50: 13.33 × 10 × 0.50 × 3 = $200.00. A Fixed charge of $75 on the same order brings the total to $275.00.

!!! warning "Units of measure without dimensions are not billed monthly"
    If a unit of measure is missing its **Length (inch)** or **Width (inch)**, product lines using it add nothing to Monthly charges. Fixed charges are not affected, because they are added once per order.

The **Invoiced Rate** column (and the **Closing Date** column) is shown on every filter except **Open**. On the **All** filter, open orders are calculated up to today. UTX Freight does not create invoices from warehouse orders.

See [Warehouse Orders](warehouse-orders.md) for the full order workflow.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the Warehouse menu

!!! info "Solution"
    Check two things: the Warehouse add-on must be turned on for your installation (see [Add-ons & Options](add-ons-and-options.md)), and your role must be **Admin** or **Warehouse**. Managers, dispatchers and other roles do not see the **Warehouse** group.

### :fontawesome-solid-user-slash: A customer is missing from "Place the order on behalf of"

!!! info "Solution"
    The list only shows active people of active customers whose **Service** is **Warehouse** or **Intermodal & Warehouse**, in the office you are currently working in. Open the customer in **Customers**, check its **Service**, and make sure it has at least one active person.

### :fontawesome-solid-ban: A charge is missing from the order's charge list

!!! info "Solution"
    Open :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Charges** and check that the charge's **Charge Type** is **Income** and its **Service** is **Warehouse**. Charges with the **Intermodal** service or the **Expense** type are not offered on warehouse orders.

### :fontawesome-solid-truck: A Warehouse user can't open Orders

!!! info "Solution"
    That is by design. The **Warehouse** role has no access to freight orders. Warehouse users work from :fontawesome-solid-arrow-right: **Warehouse** :fontawesome-solid-arrow-right: **Orders**. If the person also needs freight orders, give them an **Admin** account instead. See [User Roles](user-roles.md).

### :fontawesome-solid-location-dot: I can't pick a building when creating a location

!!! info "Solution"
    The **Building** list only shows active buildings of the office you are working in. Create the building first (or enable it), then come back to **Location**.

### :fontawesome-solid-dollar-sign: The order total is lower than expected

!!! info "Solution"
    Check the unit of measure on each product line: without both **Length (inch)** and **Width (inch)** it adds nothing to Monthly charges. Also check that the storage charge is set to **Value Type** = **Monthly**; a **Fixed** charge is only counted once.

---

!!! tip "Best Practices"
    - Follow the setup order: **Building** :fontawesome-solid-arrow-right: **Location** :fontawesome-solid-arrow-right: **Unit of Measure** :fontawesome-solid-arrow-right: **Product** :fontawesome-solid-arrow-right: **Charges** :fontawesome-solid-arrow-right: customer **Service**.
    - Always enter both dimensions on a unit of measure; they are what monthly storage is billed on.
    - Keep storage fees as **Monthly** charges and one-time fees (handling, receiving, shipping out) as **Fixed** charges.
    - Use **Custom rates for this customer** on the customer to give a customer its own warehouse prices instead of editing the rate on each order.
    - Complete orders as soon as the goods leave, so the month count stops at the right **Closing Date**.
