# Order Rates, Charges & Expenses

How UTX Freight prices an order (base rate, zone rates, customer custom rates, automatic Terminal Fee and fuel surcharge, additional charges) and how you record what the order costs you (Order Expenses).

## :fontawesome-solid-dollar-sign: Overview

Every order has two money sides:

- :fontawesome-solid-file-invoice-dollar: **Income** -- what you bill the customer. This is the **Base rate** plus any **Additional Charges**. Their sum is the order **total**, and it is what ends up on the invoice.
- :fontawesome-solid-money-bill: **Expenses** -- what the order costs you (driver pay, broker fees, other costs). Expenses never change the order total. They feed the **Expenses** page, **Checks** and the **Order Sales / Profit** report.

Here is how the income side is built:

- :fontawesome-solid-map-location-dot: **Zone rate lookup** -- the delivery city's zone gives the base rate. If the customer has a custom rate for that zone, the custom rate wins.
- :fontawesome-solid-warehouse: **Terminal Fee** -- added automatically on Import and Export orders, from the terminal's default rate or the customer's custom terminal rate.
- :fontawesome-solid-gas-pump: **Fuel surcharge** -- added automatically (when the fuel surcharge add-on is on) as a percentage of the base rate.
- :fontawesome-solid-plus: **Additional Charges** -- any other income charge type you add by hand.
- :fontawesome-solid-clock-rotate-left: **Rate history** -- one click shows the customer's zone rates and what you billed on similar invoiced orders.

!!! info "Who sees rates"
    Only users who can manage rates (**Admin**, **Manager**, and **Dispatch** or **Customer Service** users with **Can manage rates?** checked) see the rate fields, charges and expenses. See [Access & Permissions](#access-permissions).

---

## :fontawesome-solid-bolt: Quick Start

Already familiar with order pricing? Here is the fastest path:

1. Open the order's **Edit**, **Dispatch** or **Complete** form.
2. Expand the **Order Income** panel (called **Order Income & Billing** on the Edit form).
3. Check the **Base rate**. Click the green :fontawesome-solid-rotate-right: refresh icon to look up the zone rate again, or the :fontawesome-solid-info: icon to see rate history.
4. Under **Additional Charges**, click **(+) Add another**, pick a charge type and adjust the amount if needed.
5. Optionally expand **Order Expenses** and add what you pay the driver, broker or other payee.
6. Save the form. The total is recalculated and saved. On the **Edit** and **Dispatch** forms of an open order, the Terminal Fee and fuel surcharge are also recomputed (see [Automatic Terminal Fee](#automatic-terminal-fee)).

<!-- TODO: Screenshot — Order Income panel showing Base rate, the "i" and refresh icons, the green total and Additional Charges -->

---

## :fontawesome-solid-shield-halved: Access & Permissions

Pricing lives inside the order forms (**Edit**, **Dispatch** and **Complete**). What you see depends on your role:

| Role | Customer section | Order Charges for Invoice Breakdown | Order Expenses |
| ---- | ---- | ---- | ---- |
| :fontawesome-solid-user-shield: **Admin** | Yes | Yes | Yes |
| :fontawesome-solid-user-tie: **Manager** | Yes | Yes | Yes |
| :fontawesome-solid-headset: **Dispatch** / **Customer Service** with **Can manage rates?** | Yes | Yes | Yes |
| :fontawesome-solid-headset: **Dispatch** / **Customer Service** without **Can manage rates?** | Yes | No | No |
| :fontawesome-solid-user: **All other roles** | No | No | No |

- The **Customer** section holds the **Place the order on behalf of** field (shown inside the Order Income panel).
- Users who cannot manage rates do not see the base rate, but the form still carries it as a hidden value, so saving the order normally keeps its existing rate. Exception: changing **Place the order on behalf of** runs the zone lookup and replaces that hidden base rate (see [Zone Rate Lookup](#zone-rate-lookup)).
- **Can manage rates?** is a checkbox on a Dispatch or Customer Service user's profile, and only an Admin can change it. See [People & Invitations](people-and-invitations.md) and [User Roles](user-roles.md).
- In the **Rate Update** message (see below), users who cannot manage rates see only the zone name, never the dollar amount.

---

## :fontawesome-solid-calculator: Order Charges for Invoice Breakdown

This section sits inside the **Order Income** panel (**Order Income & Billing** on the Edit form). It is only visible to users who can manage rates.

| Element | What It Does |
| ---- | ---- |
| **Base rate** | The main price of the order. Filled automatically by the zone lookup, and you can type over it. |
| :fontawesome-solid-info: **i** icon (blue, tooltip "Check rate history") | Opens the **Rate History** window for this order's customer. See [Rate History](#rate-history). |
| **$ total** (large green number) | Base rate plus every Additional Charge on the form. It updates as you type. |
| :fontawesome-solid-rotate-right: **Refresh** icon (green) | Runs the zone rate lookup again and replaces the **Base rate** with the result. |
| **Auto compute fuel surcharges for this order** | Yes / No. Only shown when the fuel surcharge add-on is on. Defaults to **Yes**. Set it to **No** to stop the fuel surcharge being computed for this order. A fuel charge already on the order stays until you remove it with **(-) Remove**. |
| **Additional Charges** | The list of income charges on this order, including the automatic Terminal Fee and fuel surcharge rows once they have been added. |
| **(+) Add another** | Adds a new Additional Charge row. |
| **(-) Remove** | Removes that charge row. |

### :fontawesome-solid-list: Additional Charges

Each Additional Charge row has a charge type dropdown and an amount.

- The dropdown lists your **Income** charge types for the intermodal service, written as **Name (rate$)** -- for example `Chassis (75.0$)`. Fuel surcharge charge types show a percent instead: `Fuel Surcharge 15% (15.0%)`.
- When you pick a charge type, its default rate is copied into the amount field. You can then change the amount for this order only.
- Charge types are set up under **Manage Charge Types**. See [Charge Types & Taxes](charge-types-and-taxes.md).

### Step-by-step: Add a charge to an order

1. :fontawesome-solid-arrow-right: Open the order's **Edit**, **Dispatch** or **Complete** form.
2. :fontawesome-solid-folder-open: Expand **Order Income** (or **Order Income & Billing**).
3. :fontawesome-solid-plus: Under **Additional Charges**, click **(+) Add another**.
4. :fontawesome-solid-list: Pick the charge type from the dropdown. The amount fills in from its default rate.
5. :fontawesome-solid-pencil: Change the amount if this order needs a different price.
6. :fontawesome-solid-circle-check: Save the form.

### :fontawesome-solid-equals: How the total is calculated

!!! info "Info"
    Total = Base rate + sum of all Additional Charges

The green total on screen is a live preview. When you save, the order total is recalculated on the server **after** the automatic Terminal Fee and fuel surcharge are refreshed, so the saved total can differ from what you saw before saving. The total is rounded to the cent.

---

## :fontawesome-solid-map-location-dot: Zone Rate Lookup

The zone rate lookup sets the **Base rate** from the order's delivery location.

### What triggers it

In the Edit, Dispatch and Complete forms, the lookup runs when:

- you change **Place the order on behalf of** (the customer), or
- you click the green :fontawesome-solid-rotate-right: refresh icon.

### How the rate is found

1. UTX Freight takes the shipper / receiver saved on the order and uses **its city**.
2. It finds the **zone** that city belongs to and takes the zone's rate.
3. If the order's customer has a **custom rate** for that zone, the custom rate is used instead.
4. The result replaces the **Base rate** and the total is recalculated.

Zones, cities and zone prices are set up in [Zones & Cities](zones-and-cities.md). Customer custom rates are set on the customer (see [Customer Custom Rates](#customer-custom-rates)).

### The "Rate Update" message

A **Rate Update** message appears at the top of the screen with the result:

| Message | Meaning |
| ---- | ---- |
| `Zone N - Rate $x` (green) | The city is in zone **Zone N** and the zone's default rate **$x** was applied. |
| `Zone N - Custom Rate $x` (blue) | The city is in zone **Zone N** and this customer's custom rate **$x** was applied. |
| `No ZONE found for this city` | No zone could be found -- the shipper / receiver has no city, or the city has no zone. |

"Zone N" is the name you gave the zone. Users who cannot manage rates see only the zone name (or **No ZONE found for this city**) without the rate.

!!! warning "No zone means a $0.00 base rate"
    When the lookup finds no zone, it still replaces the Base rate -- with **0**. For rate managers the message reads `No ZONE found for this city - Rate $ 0.00`. If you see it, fix the city's zone (or the shipper / receiver's city) and click refresh again, or type the base rate by hand before saving.

!!! info "Default Order Rate"
    When a new order is created without a base rate and the customer company has a **Default Order Rate** (shown read-only under **Rate to apply for new orders** on the customer), that rate is used as the starting base rate.

---

## :fontawesome-solid-clock-rotate-left: Rate History

Click the blue :fontawesome-solid-info: icon next to **Base rate** to open the **Rate History** window. Its title reads **Rate History for _Customer_ (invoiced _imports_ only)**, using the order's customer company and order type (for example `imports` or `exports`).

<!-- TODO: Screenshot — Rate History modal with the zone rate table and the comparable orders table -->

### Zone rate table

The top block, **Rates for _Customer_**, shows one column per active zone with the rate this customer pays there:

| Display | Meaning |
| ---- | ---- |
| :fontawesome-solid-circle:{ .text-primary } **Blue rate with `*`** | Custom rate for this customer. |
| :fontawesome-solid-circle:{ .text-success } **Green rate** | The zone's default rate. |
| **N/A** (grey) | No rate set for this zone. |

### Comparable invoiced orders

Below the zone table is a list of past orders for comparison. An order is listed only if it:

- belongs to the same customer company,
- has the same order type (Import, Export, ...),
- has the same pickup terminal,
- is **Completed**, **invoiced**, and has a delivery date.

The list shows up to **10** of the most recent such orders delivered to the **same shipper / receiver** as this order, followed by up to **10** more delivered **elsewhere**, newest first.

| Column | What It Shows |
| ---- | ---- |
| **Order#** | Order reference |
| **Date** | Delivery date |
| **Terminal** | Pickup terminal |
| **Base Rate** | Base rate billed |
| **Total** | Order total billed |
| **Delivered To** | Shipper / receiver |
| **Charges** | Each charge on the order (including automatic Terminal Fee and fuel rows) as **Charge type: $ amount** |

Click **Close** to return to the order.

---

## :fontawesome-solid-warehouse: Automatic Terminal Fee

UTX Freight can add a terminal fee to each order automatically.

### Requirements

- A charge type with **Use as default for** set to **Terminal Fee** must exist (see [Charge Types & Taxes](charge-types-and-taxes.md)). If several exist, only one is used, so keep a single Terminal Fee charge type.
- The order must be an **Import** or **Export** order, and the terminal it uses (see below) must be filled in.
- The order must not be **Completed** or invoiced.

### Which terminal and which rate

| Order type | Terminal used |
| ---- | ---- |
| **Import** | The **pickup terminal** |
| **Export** | The **return terminal** |

The rate is the terminal's **Default Rate** (see [Managing Terminals](managing-terminals.md)). If the customer has a custom rate for that terminal, the custom rate is used instead.

### How it is applied

- The fee is added when the order is created and refreshed every time the open order is saved from the **Edit** or **Dispatch** form. Saving the **Complete** form marks the order **Completed** first, so that save does not refresh it.
- Each refresh removes the existing Terminal Fee charge and adds a new one, with the note **Computed Terminal Fee**. Editing the amount by hand therefore does not stick -- change the terminal's rate or the customer's custom rate instead.
- Rates under **$1** are ignored: no Terminal Fee is added.
- Transfer and other order types never get an automatic Terminal Fee.

---

## :fontawesome-solid-gas-pump: Automatic Fuel Surcharge

When the fuel surcharge add-on is on, a fuel surcharge charge is computed for the order. In short:

- Applies to **Import**, **Export** and **Transfer** orders that are not **Completed** or invoiced.
- **Auto compute fuel surcharges for this order** must be **Yes**.
- The rate is the monthly fuel rate for the month of the order's **delivery date**. A customer-specific rate for that month wins over the general rate.
- Amount = **Base rate x fuel %**, rounded to the cent, with the note **Computed Fuel Surcharge N%** (or **Computed Fuel Surcharge N% (custom rate for _Customer_)**).
- The existing fuel charge is replaced on each save. A rate under 1% removes the fuel charge and adds nothing. If the order has no delivery date, or no fuel rate exists for that month, the existing fuel charge is left as it is.
- Customers marked **Exempt from Fuel Surcharge** get no fuel charge, and any existing one is removed on save.

Full details, including how to set monthly rates and recalculate open orders: [Fuel Surcharge](fuel-surcharge.md).

---

## :fontawesome-solid-building: Customer Custom Rates

On the customer's edit page, the **Custom rates for this customer** section lets you set prices that override defaults for this customer only. Each row has a **Charge** dropdown grouped by:

| Group | Overrides |
| ---- | ---- |
| **Zone** | The zone rate used by the zone rate lookup. Shown in blue with `*` in Rate History. |
| **Terminal** | The terminal's Default Rate for the automatic Terminal Fee. |
| **Warehouse** | Warehouse charge types (used by warehouse orders). |

Enter the **Rate**, click **(+) Add another** for more rows, and save the customer. See [Managing Customers](managing-customers.md).

---

## :fontawesome-solid-money-bill: Order Expenses

The **Order Expenses** panel records what the order costs you. It appears on the Edit, Dispatch and Complete forms, for users who can manage rates only.

<!-- TODO: Screenshot — Order Expenses panel with a Driver payee row and an expense type -->

Each expense row has:

| Field | What It Does |
| ---- | ---- |
| **Payee** (first dropdown) | Who you pay. Grouped into **Driver**, **Broker** and **Other Expense** (your expense categories). Changing it clears the **Rate**, so pick the payee before the expense type. |
| **Expense type** (second dropdown) | Optional. Lists your **Expense** charge types as **Name (rate$)**. Picking one copies its default rate into **Rate**. |
| **Rate** | The amount of the expense. |
| **Comment** | Free-text note. |
| **(-) Remove** | Removes the row. |

Click **(+) Add another** to add a row, then save the form.

### Where expenses go

- :fontawesome-solid-ban: **Not the order total.** Expenses never change the total or the invoice.
- :fontawesome-solid-money-bill: **Expenses** page -- every expense line is listed there.
- :fontawesome-solid-money-check: **Checks** -- expenses on **Completed** orders that are not yet on a check can be added to a check.
- :fontawesome-solid-chart-line: **Reports** > **Order Sales / Profit** -- shows each order's **Expenses** and **Profits** (total minus expenses).

See [Expenses & Checks](expenses-and-checks.md) and [Reports](reports.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I can't see the base rate or charges on the order

!!! info "Solution"
    Only Admin, Manager, and Dispatch or Customer Service users with **Can manage rates?** see **Order Charges for Invoice Breakdown** and **Order Expenses**. Ask an Admin to check **Can manage rates?** on your profile.

### :fontawesome-solid-map-location-dot: The message says "No ZONE found for this city"

!!! info "Solution"
    The lookup uses the city of the order's shipper / receiver. Make sure the shipper / receiver has a city, and that the city is assigned to a zone with a price. Then click the green refresh icon. See [Zones & Cities](zones-and-cities.md).

### :fontawesome-solid-rotate: My base rate changed to a different amount (or 0) on its own

!!! info "Solution"
    Changing **Place the order on behalf of** runs the zone lookup and replaces the base rate with the new customer's zone or custom rate -- or with 0 if no zone is found. Re-enter the rate before saving if you need a different amount.

### :fontawesome-solid-warehouse: No Terminal Fee was added

!!! info "Solution"
    Check that: a charge type has **Use as default for** = **Terminal Fee**; the order is Import or Export; the right terminal is set (pickup for Import, return for Export); the terminal's Default Rate (or the customer's custom terminal rate) is at least $1; and the order is not Completed or invoiced.

### :fontawesome-solid-pencil: I edited the Terminal Fee or fuel surcharge amount and it went back

!!! info "Solution"
    Both are recomputed every time the open order is saved from the **Edit** or **Dispatch** form. Change the terminal rate, the customer's custom rate or the fuel rate instead. For fuel, you can set **Auto compute fuel surcharges for this order** to **No**.

### :fontawesome-solid-lock: Charges stopped updating after I completed the order

!!! info "Solution"
    By design: once an order is **Completed** or invoiced, the Terminal Fee and fuel surcharge are no longer recomputed. This includes the save from the **Complete** form itself. Manual changes to Additional Charges are still saved.

### :fontawesome-solid-chart-line: I added expenses but the invoice total didn't change

!!! info "Solution"
    Expenses are costs, not income. They show on the Expenses page, Checks and the **Order Sales / Profit** report, never on the invoice. To bill the customer for something, add it under **Additional Charges**.

---

!!! tip "Best Practices"
    - Set zone prices and assign every delivery city to a zone before creating orders, so the base rate fills in by itself.
    - Use customer custom rates (zone or terminal) instead of editing each order by hand.
    - Keep exactly one charge type marked **Terminal Fee**.
    - Glance at **Rate History** before quoting a customer -- it shows what you billed on the same lane.
    - Record driver and broker pay in **Order Expenses** so the **Order Sales / Profit** report shows real margins.
