# Zones, Cities & Zone Rates

Group your delivery cities into **zones**, give each zone a rate, and let UTX Freight fill the **Base rate** of an order automatically from the delivery city.

## :fontawesome-solid-map-location-dot: Overview

Zones and cities work together to price your orders:

- :fontawesome-solid-city: **Cities** are the locations (UN locations) that your Shippers / Receivers are linked to. UTX loads the city list for you when your account is set up, so most of the cities you need already exist.
- :fontawesome-solid-map-marker-alt: **Zones** are groups of cities. Each zone has one **rate** — the standard price for delivering to any city in that zone.
- :fontawesome-solid-link: Each city can belong to **one zone**. A city does not have its own rate: the **Rate** shown for a city always comes from its zone.
- :fontawesome-solid-user-tag: A customer can have a **custom rate** for a zone. That rate replaces the zone rate on that customer's orders.
- :fontawesome-solid-dollar-sign: When you choose the delivery location on an order, the **Base rate** is filled from the customer's custom zone rate, or otherwise from the zone rate of the delivery city.
- :fontawesome-solid-eye-slash: Zones and cities are never deleted. You can **disable** a zone, and you can mark a city as not **Active**.

---

## :fontawesome-solid-bolt: Quick Start

1. Click your **name** at the top of the screen to open the user menu, click **Manage Zones**, then click **Add a new Zone**.
2. Enter the **Name** and the **Rate for cities in this zone**, then click **Save Changes**.
3. Open the user menu again, click **Manage Cities**, then click **Shipping** to see the cities you actually deliver to.
4. Click the **Zone** value (or **N/A**) of each city and pick its zone.

From now on, when the rate lookup runs for an order delivered to a Shipper / Receiver in one of those cities, the order's **Base rate** is filled with the zone rate (see [How the Order Base Rate Is Set](#how-the-order-base-rate-is-set)).

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Manage Zones | Manage Cities |
|------|:---:|:---:|
| :fontawesome-solid-user-shield: **Admin** | Full access | Full access |
| :fontawesome-solid-user-tie: **Manager** | Full access | Full access |
| :fontawesome-solid-headset: **Dispatch** | No access | Full access only if **Can manage rates?** is checked on the dispatcher's profile |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access | No access |
| :fontawesome-solid-user: **Customer / Driver / Warehouse / Garage** | No access | No access |

!!! info "Dispatchers and Manage Cities"
    **Can manage rates?** is a checkbox on the dispatcher's person profile ("Specifies if this Dispatch can manage rates and charges across the app"). An Admin or Manager can turn it on. See [People & Invitations](people-and-invitations.md) and [User Roles](user-roles.md). Dispatchers never see **Manage Zones**, even with this permission.

**How to get there:**

- :fontawesome-solid-arrow-right: Click your **name** at the top of the screen to open the user menu, then click **Manage Zones**.
- :fontawesome-solid-arrow-right: Click your **name** at the top of the screen to open the user menu, then click **Manage Cities**.

Both items sit in the user menu with the other **Manage …** items. They are **not** inside the **Settings** page. A menu item only appears for users who have access. See [Navigation & Account](navigation-and-account.md).

!!! info "Multi-office"
    Zones and cities belong to an **office**. Both lists show the zones and cities of the office you are currently working in. When you create a zone or a city, the **Office** dropdown lists the offices you belong to. The **Custom Rates** matrix is the exception: it shows the active zones of all offices. See [Multi-Office](multi-office.md).

---

## :fontawesome-solid-map-marker-alt: Manage Zones

The **Zones** page lists the zones of your current office, sorted by name. The list has no page links and shows at most 50 zones.

<!-- TODO: Screenshot — Manage Zones list with All Active / Disabled filter, Custom Rates button, Rate and Cities columns -->

### Filters

| Filter | Shows |
|--------|-------|
| **All Active** | Active zones (the default) |
| **Disabled** | Zones that have been disabled |

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The zone name. Shown in **green** when the zone is active, in **red** when it is disabled |
| **Rate** | The zone rate (for example **$125.00**). Shows **N/A** when the zone has no rate or a rate of 0. Click it to edit the rate in place |
| **Active** | Whether the zone is active |
| **Cities** | The number of cities in the zone. When there is at least one city, a blue :fontawesome-solid-info: button opens the list of cities |
| *(Actions)* | The **Actions** menu: **Edit**, **View History**, **Disable** or **Enable** |

!!! info "How zone names are displayed"
    UTX Freight always displays a zone as **Zone** followed by its name. The word "zone" typed in the name is removed first, so a zone named `1` and a zone named `Zone 1` are both shown as **Zone 1**.

### Creating a Zone

1. Open the user menu (your **name**) :fontawesome-solid-arrow-right: **Manage Zones**.
2. Click **Add a new Zone** at the top right.
3. Fill in the **Zone Information** form (see the table below).
4. Click **Save Changes**. Click **Cancel** to go back to the list without saving.

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | :fontawesome-solid-check: | The zone name (placeholder: *zone name*). See the note above on how it is displayed |
| **Office** | :fontawesome-solid-check: | The office the zone belongs to. Lists the offices you belong to |
| **Rate for cities in this zone** | | The standard rate, in dollars, for delivering to any city of this zone. Leave it empty or at 0 if the zone has no standard rate (it then shows **N/A**) |
| **Active** | | In the **Zone visibility** section. Hint: *Only active zones will be used when creating new orders* |

### Changing a Zone Rate

**From the list (fastest):**

1. In the **Rate** column, click the rate (or **N/A**).
2. Type the new rate in the **Enter new rate** box.
3. Confirm. The row refreshes with the new rate.

**From the form:**

1. Open the **Actions** menu of the zone and click **Edit**.
2. Change **Rate for cities in this zone** and click **Save Changes**.

!!! warning "New rates apply to new lookups only"
    Changing a zone rate does not change orders that already exist. The new rate is used the next time a **Base rate** is filled from that zone on an order.

### Viewing the Cities in a Zone

In the **Cities** column, click the blue :fontawesome-solid-info: button next to the city count. A window titled **List of Cities in Zone ...** shows the names of all cities in the zone, in alphabetical order. Click **Close** to close it.

To add or remove cities from a zone, use [Manage Cities](#manage-cities).

### Disabling and Enabling a Zone

1. Open the **Actions** menu of the zone.
2. Click **Disable** (or **Enable** on a disabled zone).

The row updates immediately (the name turns red or green and the menu item switches) and a notification titled **Update** confirms the change (for example *Zone Zone 1 - Disabled*). After the list reloads, a disabled zone is listed under the **Disabled** filter instead of **All Active**.

A disabled zone:

- is no longer offered as a zone filter on **Manage Cities**, nor in the inline zone picker of the city list (it is still listed in the **Zone** field of the city form);
- is no longer a column of the **Custom Rates** matrix, nor of the zone rates shown in the order's rate history window;
- stays assigned to the cities that are already in it, and its rate is still used for orders delivered to those cities (see [Disabled zones](#how-the-order-base-rate-is-set)). Move those cities to another zone if you no longer want to use it.

!!! danger "Zones cannot be deleted"
    There is no delete action for zones. Disable a zone you no longer use instead.

### View History

**Actions** → **View History** shows the changes made to the zone (rate, name, active status, and so on).

---

## :fontawesome-solid-dollar-sign: Custom Rates Matrix

The **Custom Rates** button (:fontawesome-solid-dollar-sign:) at the top right of the Zones page opens a window that shows, at a glance, every customer that has at least one custom zone rate, and what each of them pays for each active zone.

<!-- TODO: Screenshot — Custom Rates matrix window with blue custom rates and green zone defaults -->

- Each **row** is a customer (the **Customer** column).
- Each **column** is an active zone.
- Each cell shows the customer's custom rate for that zone, or the zone's default rate when there is none.

### Color Guide

| Display | Meaning |
|---------|---------|
| :fontawesome-solid-circle: **Blue rate** | A **custom** rate for this customer (above $0.00) |
| :fontawesome-solid-circle: **Green rate** | The zone's **default** rate. The customer has no custom rate for this zone, or a custom rate of 0 |
| **N/A** (grey) | No custom rate above 0 for this customer, and the zone has no rate |

!!! warning "A custom rate of 0 looks like the default here"
    The matrix only shows a custom rate in blue when it is above 0. If a customer has a custom rate of 0 for a zone, the cell shows the zone's default rate in green, but the order lookup uses the custom rate and fills a **Base rate** of 0.

The legend under the table reads: *Blue rates are custom for the Customer* and *Green rates are defaults for the Zone*.

!!! info "The matrix is read-only"
    You cannot edit rates in this window. Zone defaults are changed on the Zones page. Custom rates are set on the customer, in the **Custom rates for this customer** section of the customer form. See [Managing Customers](managing-customers.md#custom-rates).

---

## :fontawesome-solid-city: Manage Cities

The **Cities** page lists the cities of your current office, 50 per page. The cities on each page are sorted by name.

<!-- TODO: Screenshot — Manage Cities list with All / Shipping / zone filters, Filter cities search and Zone/Rate columns -->

!!! info "The city list is preloaded"
    UTX loads the city list (UN locations) for your account. It usually holds several hundred cities, of which you only deliver to a small number. Use the **Shipping** filter to work on the cities that matter.

The notice at the top of the list reminds you that the **Rate** of a city is pulled from the **Zone** associated with the city. You need to select a zone for each city to have the rate selected automatically when you choose a Shipper or Receiver on an order.

### Filters and Search

| Filter | Shows |
|--------|-------|
| **All** | All cities (the default) |
| **Shipping** | Cities of the Shipper / Receivers used as the delivery location on at least one order (tooltip: *Cities where at least one order has been delivered*) |
| **Zone ...** | One button per active zone. Shows the cities assigned to that zone |

Type at least 2 characters in **Filter cities** to search by city name or UN code. The search runs on the whole city list of your office, whichever filter is selected. Clear the box to show the full list again.

### Columns

| Column | Description |
|--------|-------------|
| **Name** | The city name. Shown in **green** when the city is active, in **red** when it is not |
| **Zone** | The zone of the city, or **N/A** when the city has no zone. Click it to change the zone in place |
| **Rate** | The rate of the city's zone. Shows **N/A** when the city has no zone or the zone has no rate. Not editable here: change it on the zone |
| **State** | Province or state code |
| **Country** | `CA` or `US` |
| **Code** | The UN location code |
| **Active** | Whether the city is active |
| *(Actions)* | The **Actions** menu: **Edit**, **View History** |

### Assigning a City to a Zone

**From the list (fastest):**

1. Click **Shipping** (or search for the city).
2. In the **Zone** column, click the zone name or **N/A**.
3. In **Select new zone**, pick an active zone, or the empty choice to remove the city from its zone.
4. Confirm. The row refreshes and the **Rate** column shows the new zone's rate.

The picker lists the active zones of your current office.

**From the form:**

1. Open the **Actions** menu of the city and click **Edit**.
2. Choose the **Zone** and click **Save Changes**.

!!! tip "Work through the Shipping list"
    Click **Shipping** and make sure no city shows **N/A** in the **Zone** column. Every one of those cities is a delivery location on at least one order, and orders delivered there get a **Base rate** of $0.00 until the city has a zone.

### Creating or Editing a City

1. Open the user menu (your **name**) :fontawesome-solid-arrow-right: **Manage Cities**.
2. Click **Add a new City** at the top right, or **Actions** → **Edit** on an existing city.
3. Fill in the **Un Location Information (EDI Compatible)** form.
4. Click **Save Changes**. Click **Cancel** to go back to the list without saving.

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | :fontawesome-solid-check: | The city name |
| **Office** | :fontawesome-solid-check: | The office the city belongs to. Lists the offices you belong to |
| **State** | | Province or state, chosen from the Canadian provinces and US states |
| **Country** | | **Canada (CA)** or **United States (US)** |
| **UN Code** | | The UN location code of the city |
| **Zone** | | The zone of the city. Lists all the zones of your current office, including disabled ones |
| **Active** | | Hint: *Only active cities appear in client configuration*. Inactive cities cannot be chosen in **City (Must exist)** on a Shipper / Receiver |

!!! tip "Check before adding a city"
    The list is preloaded, so search for the city with **Filter cities** (by name or UN code) before creating it. A duplicate city with no zone is a common reason for a $0.00 base rate.

!!! danger "Cities cannot be deleted"
    There is no delete action for cities. Uncheck **Active** on a city you don't want to use.

### View History

**Actions** → **View History** shows the changes made to the city, including zone changes.

---

## :fontawesome-solid-calculator: How the Order Base Rate Is Set

UTX Freight looks up the zone rate and writes the result into the order's **Base rate** field at these moments:

- **New order form:** when you choose the delivery **City**, when you pick a Shipper / Receiver with **Search for a shipper / receiver** (it fills the delivery **City**), and when you change the customer in **Place the order on behalf of**.
- **Existing order** (edit, dispatch and complete windows): when you change the customer in **Place the order on behalf of**, or when you click the green :fontawesome-solid-rotate-right: icon next to the **Total** in **Order Charges for Invoice Breakdown**. The lookup uses the order's saved delivery Shipper / Receiver. The icon is only shown to users who can manage rates.

The lookup works like this:

1. It finds the **delivery city**. When the order has a delivery Shipper / Receiver, that is the city in its **City (Must exist)** field; otherwise it is the delivery **City** chosen on the form.
2. It finds the **zone** of that city.
3. If the company of the order's customer has a **custom rate** for that zone, the Base rate is the **custom rate** (even if that custom rate is 0).
4. Otherwise, the Base rate is the **zone rate**.
5. If there is no delivery city, or the city has **no zone**, the Base rate is set to **0**.

A notification shows the result. On an existing order it appears at the top of the screen under the title **Rate Update**; on the new order form it appears next to the field you changed.

| Notification | Meaning |
|-------------|---------|
| **Zone ... - Rate $...** | The zone rate was used |
| **Zone ... - Custom Rate $...** | The customer's custom rate for that zone was used |
| **No ZONE found for this city** | The city has no zone (or no delivery city was found). The Base rate is set to 0 |

The amount (the **- Rate $...** part) is only shown to users who can manage rates (Admin, Manager, and Dispatch with **Can manage rates?**). Other users see the zone name only.

!!! info "Rate history window"
    On an existing order, the blue :fontawesome-solid-info: icon next to **Base rate** opens **Rate History for** *customer*. Its top table shows, for each active zone, the rate for this customer: blue with an asterisk (\*) for a custom rate, green for the zone default, **N/A** when there is neither.

You can always overwrite the **Base rate** on the order. See [Order Form](order-form.md) for the rest of the rate calculation (default rate of the customer, terminal fees, fuel surcharge). Changing a zone rate or a custom rate later does not change the Base rate of existing orders.

!!! info "Disabled zones"
    The lookup uses the zone the city is assigned to, whether that zone is active or disabled. The hint on the zone form (*Only active zones will be used when creating new orders*) does not stop this. To stop using a zone's rate, move its cities to another zone.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-ban: The Base rate shows 0 or "No ZONE found for this city"

!!! info "Solution"
    The delivery city has no zone. Open the user menu → **Manage Cities**, find the city (check the **City (Must exist)** of the delivery Shipper / Receiver), and set its **Zone**. Then run the lookup again (select the delivery location again on a new order, or click the green :fontawesome-solid-rotate-right: icon next to the **Total** on an existing order), or type the **Base rate** yourself.

### :fontawesome-solid-ban: The city has a zone but the Base rate is still 0

!!! info "Solution"
    The zone itself has no rate (it shows **N/A** on the Zones page). Set **Rate for cities in this zone**. Also check that the customer does not have a custom rate of 0 for that zone in **Custom rates for this customer**.

### :fontawesome-solid-user-tag: A customer is not getting their custom rate

!!! info "Solution"
    Custom rates are per zone. Open the **Custom Rates** matrix on the Zones page and check the customer's row: a **blue** rate is custom, a **green** rate is the zone default. If the cell is green, the customer has no custom rate above 0 for that zone: add or fix the zone in **Custom rates for this customer** on the customer. Also check that the delivery city is in the zone you expect.

### :fontawesome-solid-eye-slash: I can't see Manage Zones or Manage Cities

!!! info "Solution"
    **Manage Zones** is only available to Admins and Managers. **Manage Cities** is also available to Dispatchers whose profile has **Can manage rates?** checked. Ask an Admin or Manager.

### :fontawesome-solid-trash: How do I delete a zone or a city?

!!! info "Solution"
    You can't. Zones and cities are kept so that past orders and Shipper / Receiver records stay intact. Disable the zone (**Actions** → **Disable**) or uncheck **Active** on the city.

### :fontawesome-solid-list: A zone is missing from the city filters or from the zone picker

!!! info "Solution"
    Only **active** zones appear as filters and in the inline **Select new zone** picker on Manage Cities. Enable the zone on the Zones page (**Disabled** filter → **Actions** → **Enable**).

### :fontawesome-solid-triangle-exclamation: Editing a zone rate or enabling/disabling a zone shows an error

!!! info "Solution"
    This was a bug: editing a rate in the list, or clicking **Disable** / **Enable**, failed with an error. It is fixed in version 3.12.15. Reload the page and try again. If it still happens, contact UTX support.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Keep your zones and cities clean"
    - Set up zones first, then assign zones using the **Shipping** filter on **Manage Cities**. You don't need to assign a zone to every preloaded city.
    - Give every zone a rate, even a rough one, so orders never start at $0.00.
    - Use customer **custom rates** for negotiated prices instead of creating extra zones per customer.
    - Check the **Custom Rates** matrix after a price change to confirm what each customer will pay.
    - Disable zones you no longer use, and move their cities to an active zone.
    - Make sure every Shipper / Receiver has a **City (Must exist)** set. See [Shippers & Receivers](shippers-receivers.md).
