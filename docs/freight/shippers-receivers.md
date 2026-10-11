# Shippers & Receivers

Keep a reusable address book of the pickup and delivery locations used on your orders, and link a location to a customer account for read-only portal visibility.

## :fontawesome-solid-building: Overview

A **Shipper / Receiver** is a pickup or delivery location: a company name, an address, a city and contact details. It is not the customer who pays for the order. Customers are managed separately in [Managing Customers](managing-customers.md).

- :fontawesome-solid-address-book: **Address book for orders.** On the order form, the **Search for a shipper / receiver** field looks up saved records and fills the address fields for you.
- :fontawesome-solid-wand-magic-sparkles: **Built automatically.** When you create an order on the order form with a pickup or delivery company name, UTX Freight creates a new Shipper / Receiver record or updates the matching one.
- :fontawesome-solid-map-location-dot: **Linked to a city and zone.** The **City (Must exist)** field links the record to a city from your city list. The **Zone** shown in the list comes from that city.
- :fontawesome-solid-link: **Consignee portal link.** You can link a Shipper / Receiver to a customer account. That customer's users then get read-only visibility of orders delivered to this location.
- :fontawesome-solid-toggle-on: **Active or disabled.** Only active shippers/receivers appear in orders.
- :fontawesome-solid-trash: **Delete only when unused.** You can delete a record only if no order uses it.

<!-- TODO: Screenshot — Shipper / Receiver list page showing the All Active / Disabled / Linked filters, the search box, the red "City or Country" notice and the table -->

---

## :fontawesome-solid-bolt: Quick Start

1. Click :fontawesome-solid-arrow-right: **Shipper / Receiver** in the left menu.
2. Click **Add a new Shipper / Receiver** at the top right.
3. Enter the **Company Name** and choose the **Office**.
4. Enter the **Address**, choose a city in **City (Must exist)** and enter the **Postal Code**.
5. Optionally fill in **Contact Info**, **Email** and **Comments**.
6. Click **Save Changes**.

!!! tip "You rarely need to add records by hand"
    Each new order created on the order form with a pickup or delivery company name adds that location to the list. Creating records by hand is mostly useful for setting up the **City**, **Comments** or **Linked Customer Account** before the first order.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access Level |
|------|-------------|
| :fontawesome-solid-user-shield: **Admin** | Full access: create, edit, disable/enable, delete, view history and **Export** |
| :fontawesome-solid-user-tie: **Manager** | Create, edit, disable/enable, delete and view history. No export |
| :fontawesome-solid-headset: **Dispatch** | Create, edit, disable/enable, delete and view history. No export |
| :fontawesome-solid-phone: **Customer Service** | Same as Dispatch |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access to the Shipper / Receiver list |
| :fontawesome-solid-warehouse: **Warehouse** / :fontawesome-solid-wrench: **Garage** | No access |
| :fontawesome-solid-user: **Customer** | No access to the list. Customer users linked through a consignee link can view the matching orders (see [Consignee Links](#consignee-links)) |

When multi-office is turned on, Shipper / Receiver records are shared across offices: the list shows the records of every office and anyone with access can manage them. When multi-office is off, the list shows the shippers/receivers of the office you are working in, and Managers and Dispatch users can only manage records that belong to their own offices. See [Multi-Office](multi-office.md).

**How to get there:**

- :fontawesome-solid-arrow-right: Click **Shipper / Receiver** in the left menu, **or**
- :fontawesome-solid-arrow-right: Open the user menu at the top right and click **Manage Clients**.

Both links open the same page, titled **Shipper / Receiver**.

---

## :fontawesome-solid-list: The Shipper / Receiver List

### Filters

The filter buttons sit at the top left of the page.

| Filter | Shows |
|--------|-------|
| **All Active** | Active shippers/receivers (the default) |
| **Disabled** | Disabled shippers/receivers |
| :fontawesome-solid-link: **Linked** | Shippers/receivers linked to a customer account for portal visibility, active or not |

All filters sort the results alphabetically by company name and show 50 records per page.

### Search

Type in the **Filter shippers / receivers by company name or city** box. The list refreshes once you have typed at least 2 characters, and it resets when you clear the box. The search matches:

- part of the **Company Name**, or
- part of the name of the linked city (the **City (Must exist)** value).

The search always looks in **active** records, whatever filter button is highlighted, and clearing the box brings back the active list. To find a disabled record, click **Disabled** and browse the list. The search does not look at the old free-text city of records shown in red (see below).

### Columns

| Column | Description |
|--------|-------------|
| **Company Name** | Shown in **green** when the record is active and in **red** when it is disabled |
| **Zone** | Zone of the linked city, shown as a badge. Shows **N/A** when the record has no city or the city has no zone |
| **Address** | Street address |
| **Zip** | Postal code |
| **City** | City name |
| **Country** | Country of the linked city (for example `CA` or `US`) |
| **Code** | Location code of the linked city |
| **Contact info** | Contact name or phone |
| **Email** | Email address |
| **Comments** | The first 25 characters of the comments |
| **Orders** | Number of orders that use this record as pickup company or delivery company |
| **Linked Account** | Name of the linked customer account with a :fontawesome-solid-link: badge, or **—** if there is none |
| **Active** | Whether the record is active |
| *(no heading)* | **Actions** button with a menu: **Edit**, **View History**, **Disable** / **Enable** and **Delete** |

### Colour Guide

| Colour | Meaning |
|--------|---------|
| :fontawesome-solid-circle:{ style="color: #28a745" } **Green** City / Country / Code | The record is linked to a city from your city list |
| :fontawesome-solid-circle:{ style="color: #dc3545" } **Red** City / Country (Code empty) | The record has no linked city and still uses the old free-text city and country |
| :fontawesome-solid-circle:{ style="color: #28a745" } **Green** Company Name | Active |
| :fontawesome-solid-circle:{ style="color: #dc3545" } **Red** Company Name | Disabled |

!!! warning "Fix records with a red City or Country"
    The notice at the top of the list says it: any **City or Country in RED** does not use the normalized location and should be updated. Edit the Shipper / Receiver, choose a city in **City (Must exist)**, and click **Save Changes**. Until you do, the record has no zone (**N/A**).

---

## :fontawesome-solid-pen-to-square: Adding or Editing a Shipper / Receiver

- **To add:** click **Add a new Shipper / Receiver** at the top right of the list.
- **To edit:** open the **Actions** menu on the row and click **Edit**.

The form opens on its own page (**New Shipper / Receiver** or **Edit Shipper / Receiver**). Click **Save Changes** to save, or **Cancel** to return to the list.

<!-- TODO: Screenshot — Edit Shipper / Receiver form showing Shipper / Receiver Information, Portal Access — Consignee Link, Shipper / Receiver visibility and System update note sections -->

### Shipper / Receiver Information

| Field | Description |
|-------|-------------|
| **Company Name** | Required. Leading and trailing spaces are removed when you save |
| **Office** | Required. The office the record belongs to. The list contains the offices assigned to you |
| **Address** | Street address |
| **City (Must exist)** | Choose a city from the active cities of the current office (of all offices when multi-office is on). The city must already exist. Add it first in [Zones & Cities](zones-and-cities.md) if it is missing. The city sets the **Zone** and **Code** shown in the list |
| **Postal Code** | Postal or ZIP code |
| **Contact Info** | Contact name, phone or other details |
| **Email** | Email address |
| **Comments** | The comments show up when you create an order. When you pick this record with the order form search, the comments are copied into the address **Comments** field |

### Portal Access — Consignee Link

| Field | Description |
|-------|-------------|
| **Linked Customer Account** | Choose an active customer account, or **— No linked account —** |

Linking a shipper/receiver to a **Customer account** gives that customer's users read-only visibility into all orders **delivered** to this location, even orders created for other customers (for example, other freight forwarders). See [Consignee Links](#consignee-links) below.

### Shipper / Receiver visibility

| Field | Description |
|-------|-------------|
| **Active** | Only active shippers/receivers appear in orders |

### System update note

This section shows the old **City** and **Country** fields. They are read-only and cannot be edited. The note explains that city and country are deprecated and should be set with the **City (Must exist)** field instead, so that city names and the rates per city stay consistent.

---

## :fontawesome-solid-link: Consignee Links

A consignee link lets a customer see the deliveries made to their location, for example a warehouse that receives containers booked by several freight forwarders.

How it works:

1. Edit the Shipper / Receiver that is the delivery location.
2. In **Portal Access — Consignee Link**, choose the customer in **Linked Customer Account**.
3. Click **Save Changes**.

From then on, users of that customer account can:

- :fontawesome-solid-eye: **view** (read only) every order whose **delivery** company is this Shipper / Receiver, including orders placed by other customers, and
- :fontawesome-solid-file: **open the documents** attached to those orders.

They cannot edit these orders. Pricing is never shown to linked users.

!!! info "Delivery only"
    The link applies to orders where this record is the **delivery** company. Orders where it is only the pickup company are not shared with the linked customer.

!!! tip "Find all linked locations"
    Use the :fontawesome-solid-link: **Linked** filter to list every Shipper / Receiver linked to a customer account. You can link several locations to the same customer.

!!! info "If the customer account is deleted"
    Deleting a customer account removes the link from its shippers/receivers. The Shipper / Receiver records stay.

For what customers see in the portal, see [Customer Portal](customer-portal.md).

---

## :fontawesome-solid-wand-magic-sparkles: Automatic Creation from Orders

You don't need to add every location by hand. When an order is **created** on the order form (saved for the first time):

- If the order has a **delivery** company name, UTX Freight looks for a matching Shipper / Receiver and links it to the order as the delivery company.
- If the order has a **pickup** company name, it does the same for the pickup company.

**What counts as a match:**

| Setup | A record matches when |
|-------|-----------------------|
| Single office | Same company name (exact), same office and same address |
| Multi-office | Same company name (not case sensitive) and same address, in any office |

**When a match is found**, the record is updated with the values from the order. Only the fields that are filled in on the order are copied: address, city, postal code, contact, email (delivery only) and office. Blank order fields do not erase existing values. **Comments**, **Active** and **Linked Customer Account** are never changed by an order.

**When no match is found**, a new record is created with the company name, address, city, postal code, contact info and office from the order. Delivery locations also get the delivery email. Pickup locations have no email.

!!! warning "Small differences create duplicates"
    A different spelling of the address (for example `123 Main St` vs `123 Main Street`) creates a second record. To avoid duplicates, use the **Search for a shipper / receiver** field on the order form instead of typing the address by hand.

!!! info "Editing an order does not update the list"
    Records are created or updated only when an order is created on the order form. Saving changes to an existing order does not create or update Shipper / Receiver records. Orders saved from the [Auto Orders](auto-orders.md) review window do not create records either: the delivery company is chosen from the existing list there.

---

## :fontawesome-solid-magnifying-glass: Using Shippers & Receivers on the Order Form

On a new order, the **Pick Up Address** and **Delivery Address** sections each have a **Search for a shipper / receiver** field: *"Type the name of a previously used shipper / receiver in an order to automatically fill the following fields."*

1. Type at least 2 characters of the company name or the city.
2. Pick a suggestion. Each suggestion shows the company name, address, city and province, and the contact info in brackets.
3. The fields below fill in automatically:

| Order field | Pick Up Address | Delivery Address |
|-------------|:---:|:---:|
| **Name** | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Address** | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **City** | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Zip** | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Contact** | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Email** | — | :fontawesome-solid-check: |
| **Comments** (from the record's comments) | :fontawesome-solid-check: | :fontawesome-solid-check: |

If the record has no linked city, the **City** field is left empty. The record's comments replace whatever was already in **Comments**.

The search only suggests **active** shippers/receivers of the current office (of all offices when multi-office is on).

When you edit an existing order, the pickup and delivery company are chosen from a list of active shippers/receivers instead of the search field.

!!! tip "Adding a location while reviewing an Auto Order"
    In the [Auto Orders](auto-orders.md) review window, the **New Client** button under **Delivery** opens a short **Shipper / Receiver Information** form (**Company Name**, **Office**, **Address**, **City (Must exist)**, **Postal Code**, **Contact Info**, **Email**). Click **Create** to add the record, then choose it as the delivery company.

See [Order Form](order-form.md) for the rest of the order fields.

---

## :fontawesome-solid-toggle-off: Disabling and Enabling

Disable a location you no longer use so it stops appearing in orders, without losing its history.

1. Find the record in the list.
2. Open the **Actions** menu and click **Disable**.

The row updates right away. Use the **Disabled** filter to find it again and click **Enable** to bring it back. You can also change the **Active** checkbox in the form.

Disabling a record does not change existing orders.

---

## :fontawesome-solid-trash: Deleting a Shipper / Receiver

You can delete a record **only if no order uses it**, as pickup company or as delivery company. The **Delete** action appears in the **Actions** menu only when the **Orders** column shows **0**.

1. Open the **Actions** menu on the row.
2. Click **Delete**.
3. Confirm with **Are you sure?**

!!! danger "Deleting cannot be undone"
    For a location that has orders, use **Disable** instead. Disabled records keep their order history and can be enabled again.

---

## :fontawesome-solid-clock-rotate-left: Viewing History

Every change to a Shipper / Receiver is recorded. Open the **Actions** menu and click **View History** to see who changed which fields and when, including changes made automatically when orders were created.

---

## :fontawesome-solid-file-csv: Exporting to CSV

**Admin only.** Click the green **Export** button at the top right of the list to download a CSV file.

The export:

- contains only shippers/receivers used as the **delivery** company on orders created in the **last 12 months**,
- does not apply the filter or search you have on screen,
- includes records from all offices,
- is sorted by company name.

| CSV column | Content |
|------------|---------|
| **Id** | Internal record ID |
| **Company name** | Company name |
| **Zone name** | Zone of the linked city, or `N/A` |
| **Address** | Street address |
| **Zip** | Postal code |
| **City name** | Linked city name, or the old free-text city if there is no linked city |
| **Country name** | Country of the linked city, or the old free-text country |
| **Contact info** | Contact info |
| **Active** | `true` or `false` |

The file name includes the date, for example `...-shippers-receivers-2026-10-10.csv`. For other exports, see [Data Exports](data-exports.md).

!!! info "Records missing from the export?"
    Shippers/receivers used only as a pickup company, or not used on any order in the last 12 months, are not in the export, even if they are active.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-ban: A shipper/receiver does not appear in the order form search

!!! info "Solution"
    Check these in order:

    1. The record may be **disabled**. Use the **Disabled** filter and click **Enable**.
    2. You must type at least **2 characters** of the company name or of the linked city name.
    3. When multi-office is off, the search shows records of the **current office** only. Switch to the right office, or check the **Office** field of the record.

### :fontawesome-solid-trash: There is no Delete option for a record

!!! info "Solution"
    **Delete** only appears when no order uses the record (the **Orders** column shows **0**). Use **Disable** instead to hide it from new orders.

### :fontawesome-solid-map-pin: The Zone column shows N/A

!!! info "Solution"
    The record has no city in **City (Must exist)**, or that city is not assigned to a zone. Edit the record and choose a city. If the city has no zone, assign one in [Zones & Cities](zones-and-cities.md).

### :fontawesome-solid-city: The city I need is not in the City (Must exist) list

!!! info "Solution"
    The list shows only **active** cities of the current office (of all offices when multi-office is on). Add or enable the city in [Zones & Cities](zones-and-cities.md), then edit the Shipper / Receiver again.

### :fontawesome-solid-clone: The same location appears twice

!!! info "Solution"
    Orders with a slightly different company name or address create a new record. Disable the duplicate you don't want, or delete it if its **Orders** count is **0**. Next time, pick the location with **Search for a shipper / receiver** on the order form.

### :fontawesome-solid-file-csv: I can't see the Export button

!!! info "Solution"
    Export is available to the **Admin** role only.

### :fontawesome-solid-eye-slash: A linked customer can't see an order

!!! info "Solution"
    The customer only sees orders whose **delivery** company is the linked Shipper / Receiver. Check the order's delivery company. If the order was typed with a different name or address, it may be linked to another (duplicate) record. Link that record too, or correct the order.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Keep your address book clean"
    - Always set **City (Must exist)** so every location has a zone. Fix the records shown in red.
    - Use **Search for a shipper / receiver** on new orders instead of retyping addresses, to avoid duplicates.
    - Put dock hours, appointment rules or gate instructions in **Comments**. They are copied into the order when you pick the location.
    - Disable locations you no longer use instead of deleting them.
    - Review the **Linked** filter from time to time to make sure each consignee link still points to the right customer.
