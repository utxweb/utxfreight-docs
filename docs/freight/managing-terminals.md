# Terminals

Create and manage the **terminals** (rail yards, port terminals and other pickup or return locations) that your orders pick containers up from and return them to.

## :fontawesome-solid-warehouse: Overview

Terminals are the **physical locations** where containers are picked up and returned. On an order, the **Pick up Terminal** and the **Return Address** terminal are both chosen from this list.

- :fontawesome-solid-landmark: The **Terminals** page lists every terminal with its address, city, contact details, **Default Rate** and whether it is active.
- :fontawesome-solid-building: Each terminal belongs to an **office**. Without the Multi-Office add-on, each office only sees its own terminals. With it, every office shares the same list.
- :fontawesome-solid-dollar-sign: The **Default Rate** is the terminal fee. On Container Import and Container Export orders it is added automatically as a **Computed Terminal Fee** charge, as long as a charge type is set as the **Terminal Fee**.
- :fontawesome-solid-user-tag: A customer can have its own rate for a terminal under **Custom rates for this customer**. That rate replaces the terminal's **Default Rate** for that customer.
- :fontawesome-solid-tag: Some terminal **names** are read by the app to drive order filters and container tracking (`CN`, `CP`, Termont, Viau, Racine, Cast). Choose and change names carefully.
- :fontawesome-solid-eye-slash: Terminals cannot be deleted. **Disable** a terminal to remove it from new orders. Orders that already use it are not affected.
- :fontawesome-solid-clock-rotate-left: Every change is recorded and can be viewed with **View History**.

!!! info "Intermodal only"
    Terminals are part of the intermodal (container) workflow. The **Manage Terminals** menu item only appears when your account runs in intermodal mode.

---

## :fontawesome-solid-bolt: Quick Start

1. Click your **name** in the top menu :fontawesome-solid-arrow-right: **Manage Terminals**.
2. Click **Add a new Terminal** at the top right.
3. Enter the **Name** and pick the **Office**.
4. Optionally fill in the address, **City (Must exist)**, contact details and **Default Rate**.
5. Click **Save Changes**.

The terminal is immediately available in the terminal dropdowns on the order forms.

To set or change only the fee, click the amount (or **not set**) in the **Default Rate** column and type the new rate. See [Editing the Default Rate in the list](#editing-the-default-rate-in-the-list).

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access Level |
|------|-------------|
| :fontawesome-solid-user-shield: **Admin** | Full access: create, edit, edit the rate in the list, enable, disable, view history |
| :fontawesome-solid-user-tie: **Manager** | Full access to the terminals of their own offices. With the Multi-Office add-on, full access to all terminals |
| :fontawesome-solid-headset: **Dispatch** | **No access** by default. Full access (same as Manager) only if UTX has turned on dispatcher terminal management for your account |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access |
| :fontawesome-solid-user: **All other roles** (Customer, Driver and others) | No access |

!!! warning "There is no view-only access"
    A user either manages terminals or does not see the page at all. Dispatchers and Accountants without access do not see **Manage Terminals** in their menu.

!!! info "Dispatchers: turning on terminal management"
    Dispatcher terminal management is an account-level option set by UTX. It is **not** a toggle in **Settings**, and it applies to all dispatchers on the account at once. To have it turned on, contact UTX support. Until then, ask an Admin or Manager to create or change terminals for you.

**How to get there:**

- :fontawesome-solid-arrow-right: Click your **name** at the top of the screen to open the user menu, then click **Manage Terminals**.

**Manage Terminals** is in the user menu with the other **Manage …** items (**Manage Cities**, **Manage Zones** and so on). It is **not** inside the **Settings** page.

---

## :fontawesome-solid-list: The Terminals List

The page is titled **Terminals** (*Management of Terminals*). Two filter buttons at the top left switch the list:

- **All Active**: active terminals (the default view).
- **Disabled**: terminals that have been disabled.

Terminals are sorted by name, **25 per page**, with page links at the bottom.

<!-- TODO: Screenshot — Terminals list showing the All Active / Disabled filter, the Default Rate column with a green rate and a grey "not set", and the Actions dropdown open -->

### Columns

| Column | What it shows |
|--------|---------------|
| **Terminal Name** | The terminal name in bold. **Green** when the terminal is active, **red** when it is disabled. The name is not a link. |
| **Address** | Street address |
| **Zip** | Postal code |
| **City** | The linked city, in green |
| **Country** | The linked city's country, in green |
| **Contact info** | Free-form contact details |
| **Email** | Terminal email |
| **Default Rate** | The terminal fee in bold green (for example **$12.50**), or a grey **not set** when the rate is $0.00 |
| **Active** | A green check mark for active, a red cross for disabled |
| *(Actions)* | The **Actions** dropdown for the row |

### Row Actions

Click **Actions** (or the arrow next to it) at the end of a row:

| Action | What it does |
|--------|-------------|
| **Edit** | Opens the **Edit Terminal** page with the full form |
| **View History** | Opens the **History** window for this terminal |
| **Disable** | Shown for active terminals. Disables the terminal |
| **Enable** | Shown for disabled terminals. Re-activates the terminal |

There is **no Delete** action. Use **Disable** for terminals you no longer use.

---

## :fontawesome-solid-plus: Creating a Terminal

1. Go to :fontawesome-solid-arrow-right: your **name** :fontawesome-solid-arrow-right: **Manage Terminals**.
2. Click **Add a new Terminal**. The **New Terminal** page opens.
3. Fill in the **Terminal Information** form (see the table below).
4. Click **Save Changes**, or **Cancel** to go back to the list without saving.

### Terminal Information

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | :fontawesome-solid-check: | Terminal name (placeholder *Terminal name*). Shown in order dropdowns, on the Orders and Dispatch pages and on reports. Some names drive filters and tracking, see [Terminal Names, Filters and Tracking](#terminal-names-filters-and-tracking) |
| **Office** | :fontawesome-solid-check: | The office that owns the terminal. The dropdown lists the offices you belong to and has no blank option, so your first office is pre-selected |
| **Address** | | Street address (placeholder *Address*) |
| **City (Must exist)** | | The terminal's city, picked from a searchable list of the active cities of your current office (all active cities with the Multi-Office add-on). Shown in the **City** and **Country** columns of the list. Used for display only. If the city is missing, add it first under **Manage Cities**. See [Zones and Cities](zones-and-cities.md) |
| **Postal Code** | | Postal or ZIP code (placeholder *Postal Code*) |
| **Contact Info** | | Free-form contact details such as phone, hours or gate information (placeholder *Contact Info*) |
| **Email** | | Terminal email address (placeholder *Email*) |
| **Default Rate** | | The terminal fee. Hint: *This rate will be applied as a charge to all orders using this terminal* Starts at 0 (shown as **not set** in the list). See [Terminal Fee](#terminal-fee) for exactly when it is applied |
| **Active** | | Under **Terminal visibility**. Hint: *Only active terminals will be visible for new orders* Checked by default for a new terminal |

If **Name** is left blank, the form comes back with an error under the field and nothing is saved.

!!! tip "Keep names short and recognizable"
    The **Name** is what users see in every dropdown. Use a short, clear name such as `Termont 68`, and check [Terminal Names, Filters and Tracking](#terminal-names-filters-and-tracking) before you choose one.

---

## :fontawesome-solid-pen-to-square: Editing a Terminal

1. Go to :fontawesome-solid-arrow-right: your **name** :fontawesome-solid-arrow-right: **Manage Terminals**.
2. On the terminal's row, click **Actions** :fontawesome-solid-arrow-right: **Edit**.
3. Change the fields on the **Edit Terminal** page and click **Save Changes**.

Changes to the name, address and contact details show everywhere the terminal is used, including orders already in progress, because orders point to the terminal record. Changes to the **Default Rate** work differently. See [Terminal Fee](#terminal-fee).

!!! danger "Check before renaming a terminal"
    Renaming a terminal can change which orders appear under the **CN**, **CP**, **Racine**, **Cast** and **Termont** filters, which orders are tracked, and which source is used to look up the container status for orders that pick up there. Read [Terminal Names, Filters and Tracking](#terminal-names-filters-and-tracking) before you rename.

---

## :fontawesome-solid-dollar-sign: Editing the Default Rate in the List

You can change a terminal's fee without opening the full form. This is the fastest way to price several terminals in a row, for example during the setup checklist.

1. In the **Default Rate** column, click the amount, or **not set** if there is no rate yet.
2. A small editor opens, titled **Enter the default terminal fee**.
3. Type the rate and confirm.

The row refreshes with the new rate.

**Accepted formats:**

| You type | Saved as |
|----------|----------|
| `12.50` | $12.50 |
| `12,50` | $12.50 (comma is read as a decimal point) |
| `$12.50` | $12.50 (dollar sign is ignored) |
| ` 12 ` | $12.00 (spaces are ignored) |
| `0` | $0.00 (shown as **not set**) |

Anything else (letters, a negative amount, an empty value, a thousands separator such as `1,250.00`, more than one decimal point) is rejected with the message **"&lt;what you typed&gt; is not an amount"**, and the rate is not changed. To remove a rate, enter `0`.

!!! info "Who can edit in the list"
    The rate is clickable only for users who can manage the terminal. It is the same permission as the rest of the page.

---

## :fontawesome-solid-file-invoice-dollar: Terminal Fee

The **Default Rate** is turned into a charge on the order automatically. This is how it works.

### What is needed

- A charge type set as **Use as default for: Terminal Fee**. Set this on the charge type in **Charge Types** (see [Charge Types and Taxes](charge-types-and-taxes.md)). If no charge type is set as the Terminal Fee, **no terminal fee is ever added**, whatever the terminal rates are.
- A rate of **$1.00 or more**, either the terminal's **Default Rate** or the customer's custom rate for that terminal. Rates below $1.00 (including **not set**) do not add a charge.

### Which terminal is charged

| Order type | Terminal used for the fee |
|------------|---------------------------|
| **Container Import** | The **pick up** terminal (*Full container pick up terminal*) |
| **Container Export** | The **return** terminal (*Full container return terminal*) |
| Any other type (Container Transfer, Dry Van Move and so on) | No terminal fee |

### Which rate is used

1. If the order's customer has a **Custom rates for this customer** row for that terminal, the custom rate is used.
2. Otherwise, the terminal's **Default Rate** is used.

If the customer's custom rate for the terminal is under $1.00 (for example `0`), no Terminal Fee is added to that customer's new orders for that terminal, even if the terminal has a **Default Rate**.

To set a customer-specific terminal rate, edit the customer, go to **Custom rates for this customer**, click **(+) Add another**, pick the terminal from the **Terminal** group of the **Charge** dropdown and enter the **Rate**. Only active terminals are listed (from every office). See [Managing Customers](managing-customers.md).

### When the fee is calculated

The fee is calculated when the order is **created**, and again each time the order is **saved** (full form, Quick Edit, dispatch and the other order actions that save charges). Each time:

- Any existing charge of the Terminal Fee charge type on the order is **removed** and replaced by one charge with the current rate and the note **Computed Terminal Fee**.
- It only happens while the order is **not invoiced** and **not completed**. Completed and invoiced orders keep the charges they already have.
- If the rate is under $1.00, nothing is added and an existing Terminal Fee charge is left as it is.
- If several charge types are set as **Terminal Fee**, only the first one found is used.

With the Fuel Surcharge add-on, clicking **Recalculate** for a month on the **Fuel Schedule** also re-saves that month's open orders, so their Terminal Fee is recalculated too. See [Fuel Surcharge](fuel-surcharge.md).

!!! warning "Changing a rate does not reprice existing orders"
    When you change a terminal's **Default Rate** (or a customer's custom terminal rate), orders that already exist keep their old Terminal Fee. An open order picks up the new rate only the next time it is saved. Completed and invoiced orders never change.

!!! warning "Manual changes to the Terminal Fee are overwritten"
    If you edit the amount of the Terminal Fee charge by hand on an open order, it is replaced by the computed rate the next time the order is saved (as long as the computed rate is $1.00 or more). To charge a customer a different terminal fee permanently, use a custom rate on the customer instead.

---

## :fontawesome-solid-eye-slash: Enabling & Disabling Terminals

Terminals cannot be deleted. Instead, **disable** a terminal to take it out of the dropdowns used on orders and custom rates.

**To disable a terminal:**

1. In the **All Active** list, click **Actions** :fontawesome-solid-arrow-right: **Disable** on the terminal's row.
2. A notification confirms **Terminal &lt;name&gt; - Disabled**. The name turns red and the **Active** column shows a red cross. The row stays on screen until you reload the list, then it moves to **Disabled**.

**To enable a terminal:**

1. Click the **Disabled** filter button.
2. Click **Actions** :fontawesome-solid-arrow-right: **Enable** on the terminal's row.
3. A notification confirms **Terminal &lt;name&gt; - Enabled**.

You can also check or uncheck **Active** on the **Edit Terminal** form.

Orders that already use a disabled terminal keep it and continue to show its name.

---

## :fontawesome-solid-clock-rotate-left: History

Every change to a terminal is recorded.

1. On the terminal's row, click **Actions** :fontawesome-solid-arrow-right: **View History**.
2. The **History** window opens with one line per change, newest first:

| Column | What it shows |
|--------|---------------|
| **User** | Who made the change (or **System** for automatic changes) |
| **Changes** | Each field that changed, with its old and new value. Field names are shown as stored (for example **Default rate**, **Contact info**; the city appears as **Unlocation**). The office and city values are shown by name |
| **When** | The date and time of the change |

Use it to see who changed a rate or renamed a terminal, and when.

---

## :fontawesome-solid-route: Terminal Names, Filters and Tracking

The app reads some terminal **names** to decide which orders appear under the terminal filters, which orders get container tracking, and where to look up the container status. Matching ignores upper and lower case, and looks at terminals of every office.

| Group | Terminals that belong to it |
|-------|-----------------------------|
| **CN** | A terminal named exactly `CN` |
| **CP** | A terminal named exactly `CP` |
| **Racine** | Any terminal whose name contains `RACINE` |
| **Cast** | Any terminal whose name contains `CAST` |
| **Termont** | Any terminal whose name contains `TERMONT` or `VIAU` |

### Order filters

The **TERMINAL** filters on the **Orders** page (and the terminal filters on the **Dispatch** page) only appear when at least one terminal belongs to the group. They show orders by **pick up** terminal.

The **Orders** page shows all five filters. The **Dispatch** page shows **CN**, **CP** and **Termont**. See [Orders](orders.md) and [Dispatch](dispatch.md).

### Container tracking

- **Which orders are tracked.** Automatic container tracking (CN, Termont / Port of Montreal and MGT for Racine and Cast, each a separate add-on) and the tracking icon in the order list apply to orders whose **pick up** terminal is in the CN, Termont, Racine or Cast group.
- **Which source the status window uses.** When you open the container status of an order, the source is picked from the **first word** of the pick up terminal's name:

| First word of the terminal name | Tracking source |
|---------------------------------|-----------------|
| `RACINE` or `CAST` | MGT (Montreal Gateway Terminals) |
| `TERMONT` or `VIAU` | Termont |
| `CN` | CN |

See [Container Tracking](container-tracking.md).

!!! warning "New or renamed terminals are not picked up for tracking right away"
    The lists of CN, Termont, Racine and Cast terminals used for container tracking, the tracking icon and the **CN** filter are read when the application starts, not each time you save a terminal. After you create or rename one of these terminals, contact UTX support so the change takes effect. The **CP**, **Racine**, **Cast** and **Termont** filters on the **Orders** and **Dispatch** pages use the current names immediately.

!!! info "Auto Orders"
    When an order is created automatically from a document, the pick up terminal is chosen from the text: CN or Canadian National goes to the first **CN** terminal, CP to the first **CP** terminal, Racine to the first **Racine** terminal and Termont to the first **Termont** terminal. See [Auto Orders](auto-orders.md).

!!! danger "Rename with care"
    - Renaming `CN` or `CP` to anything else (even `CN Montreal`), or removing `Termont`, `Viau`, `Racine` or `Cast` from a name, takes that terminal's orders out of the matching filter, and (for CN, Termont, Racine and Cast) out of container tracking once the change takes effect.
    - Changing the **first word** of a Racine, Cast, Termont, Viau or CN terminal can stop the container status from being found for orders that pick up there.
    - Giving an unrelated terminal a name that contains `CAST`, `RACINE`, `TERMONT` or `VIAU` (or naming it exactly `CN` or `CP`) puts its orders under that filter (and into container tracking, where it applies).

    If you are not sure, contact UTX support before renaming.

---

## :fontawesome-solid-building: Multi-Office Setups

The **Office** field and what you see in the list depend on whether your account has the **Multi-Office** add-on.

| | Without Multi-Office | With Multi-Office |
|---|---|---|
| **Terminals list** | Only the terminals of your current office | All terminals, from every office |
| **Terminal dropdowns on orders** | Active terminals of your current office | All active terminals |
| **Who can manage a terminal** | Admins, and Managers (and enabled Dispatchers) of the terminal's office | Admins, Managers and enabled Dispatchers, for every terminal |
| **Office field** | Decides which office sees and uses the terminal | Records the owning office only. Every office sees and uses the terminal |

The **Office** dropdown lists the offices you belong to. If you belong to more than one office, pick the right one before saving. Without Multi-Office, a terminal saved under the wrong office will not appear for the other office.

See [Multi-Office](multi-office.md).

---

## :fontawesome-solid-list-check: Setup Checklist

The setup checklist has a step called **Set the default rate on your terminals**, with an **Open Terminals** button that brings you to this page. The step is done when **both** are true:

- A charge type is set as **Use as default for: Terminal Fee**.
- At least one **active** terminal has a **Default Rate** above $0.00.

What the step suggests:

1. Open **Charge Types** and mark one of them as the **Terminal Fee**.
2. Open **Terminals** and set a default rate on the ones you actually pull from (the in-list rate editor is the fastest way).
3. Disable the terminals you never use so they leave the dropdowns.

See [Setup Checklist](setup-checklist.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-ban: I can't see a terminal on the order form

!!! info "Solution"
    The terminal is probably **disabled**. Go to your **name** > **Manage Terminals**, click **Disabled**, and use **Actions** > **Enable** on it. Without the Multi-Office add-on, also check that the terminal belongs to the office you are working in.

### :fontawesome-solid-user-lock: There is no **Manage Terminals** item in my menu

!!! info "Solution"
    Check the following:

    - Your account must run in intermodal mode. The item is hidden otherwise.
    - **Dispatchers** only see it if UTX has turned on dispatcher terminal management for your account. Ask an Admin or Manager, or contact UTX support.
    - **Accountants** and other roles do not have access to terminals.
    - Look in the user menu under your **name**, not on the **Settings** page.

### :fontawesome-solid-city: The city I need isn't in the dropdown

!!! info "Solution"
    The **City (Must exist)** dropdown only lists **active** cities of your current office. Add or enable the city under **Manage Cities** first, then come back to the terminal. See [Zones and Cities](zones-and-cities.md). The city is for display only, so you can also leave it blank.

### :fontawesome-solid-dollar-sign: The terminal has a rate but no Terminal Fee appears on the order

!!! info "Solution"
    Check each of these:

    - A charge type is set as **Use as default for: Terminal Fee**.
    - The order is a **Container Import** (the fee uses the pick up terminal) or a **Container Export** (the fee uses the return terminal).
    - The rate is **$1.00 or more**. Check the customer's **Custom rates for this customer** too, because a custom rate for that terminal replaces the default rate.
    - The order is not **completed** or **invoiced**.
    - The order has been saved since the rate was set. Open it and save it to recalculate.

### :fontawesome-solid-rotate: I changed a terminal rate but my orders still show the old fee

!!! info "Solution"
    A rate change does not reprice existing orders. Open orders get the new rate the next time they are saved. Completed and invoiced orders keep the fee they had.

### :fontawesome-solid-triangle-exclamation: The rate editor says "… is not an amount"

!!! info "Solution"
    Type a plain positive number such as `12.50`, `12,50` or `$12.50`. Letters, negative numbers and empty values are rejected. To clear a rate, enter `0`.

### :fontawesome-solid-trash: How do I delete a terminal?

!!! info "Solution"
    Terminals cannot be deleted. Use **Actions** > **Disable**. The terminal leaves the dropdowns and orders that already use it keep it.

### :fontawesome-solid-filter: Orders disappeared from the CN, CP, Racine, Cast or Termont filter

!!! info "Solution"
    These filters match on the terminal **name** (`CN` and `CP` must be the exact name). Check **View History** on the terminal to see whether it was renamed, and restore the name if needed. See [Terminal Names, Filters and Tracking](#terminal-names-filters-and-tracking).

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Best Practices"
    - Set up the **Terminal Fee** charge type first, then price your terminals. Without it, terminal rates are never charged.
    - Use the in-list **Default Rate** editor to price several terminals quickly.
    - Use **Custom rates for this customer** for negotiated terminal fees instead of editing the charge on each order.
    - After changing a rate, re-save the open orders that should use the new fee.
    - **Disable** terminals you never use so they leave the dropdowns.
    - Do not rename CN, CP, Racine, Cast, Termont or Viau terminals without checking the impact on filters and tracking.
