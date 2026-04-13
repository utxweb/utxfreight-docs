# Managing Terminals

Create and manage the **terminals** — rail yards, port terminals, warehouses, and other pickup or return locations — used on every order.

## :fontawesome-solid-warehouse: Overview

Terminals are the **physical locations** where containers and equipment are picked up, dropped off, or transferred. Every order references a terminal for pickup, return, or both.

- :fontawesome-solid-warehouse: **Terminals** are reusable across all orders and never duplicated per customer.
- :fontawesome-solid-building: Each terminal belongs to an **office**. In single-office setups, there is only one office to pick. In multi-office setups, shared terminals appear across all offices.
- :fontawesome-solid-location-dot: A **city** can be linked to the terminal for reporting and ETA purposes.
- :fontawesome-solid-dollar-sign: An optional **default rate** can be set to auto-populate charges on orders using this terminal.
- :fontawesome-solid-eye-slash: Terminals can be **disabled** rather than deleted to preserve historical orders.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access Level |
|------|-------------|
| :fontawesome-solid-user-tie: **Admin / Manager** | Full access — create, edit, enable, disable |
| :fontawesome-solid-headset: **Dispatch** | View only by default — full access if your administrator has enabled **Dispatcher Terminal Management** |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | View only |
| :fontawesome-solid-user: **Customer / Driver** | No access |

!!! note "Dispatchers: don't see the menu?"
    If you are a Dispatcher and **Manage Terminals** does not appear in the settings menu, your company has not enabled dispatcher terminal management. Ask your administrator to turn it on, or ask them to create the terminal for you.

**How to get there:**

- :fontawesome-solid-arrow-right: From the top-right menu, open **Settings** → **Manage Terminals**

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Settings** → **Manage Terminals**.
2. Click **Add a new terminal** at the top right.
3. Enter the **terminal name** and pick the **office**.
4. Click **Save Changes**.

The new terminal is immediately available on the Orders and Dispatch pages.

---

## :fontawesome-solid-plus: Creating a Terminal

1. Navigate to :fontawesome-solid-arrow-right: **Settings** → **Manage Terminals**.
2. Click **Add a new terminal**.
3. Fill in the terminal details.
4. Click **Save Changes**.

### Terminal Information

| Field | Required | Description |
|-------|:---:|-------------|
| **Name** | :fontawesome-solid-check: | Terminal name — shown on orders, dispatch, and reports |
| **Office** | :fontawesome-solid-check: | The office this terminal belongs to. In multi-office setups, terminals can be shared across offices |
| **Address** | | Street address of the terminal |
| **City** | | Select from the city list. The city must already exist — add it under **Settings** → **Manage Cities** if missing |
| **Postal Code** | | Postal or ZIP code |
| **Contact Info** | | Free-form contact details (phone, hours, gate information) |
| **Email** | | Primary email address for the terminal |
| **Default Rate** | | Default charge that auto-populates on orders using this terminal. Leave blank if rates vary by customer |
| **Active** | | Whether the terminal is available for new orders. New terminals are Active by default |

!!! tip "Tip"
    The **Name** is the only field shown in most dropdowns. Keep it short and recognizable — for example `CN Montreal`, `Termont 68`, or `MGT Racine`.

---

## :fontawesome-solid-pen-to-square: Editing a Terminal

1. Go to :fontawesome-solid-arrow-right: **Settings** → **Manage Terminals**.
2. Click the terminal **name** or the :fontawesome-solid-pen: edit icon.
3. Update the fields and click **Save Changes**.

Changes apply immediately to all orders that reference the terminal, including those already in progress.

---

## :fontawesome-solid-eye-slash: Enabling & Disabling Terminals

Rather than deleting a terminal, **disable** it to remove it from order dropdowns while preserving historical orders and reports.

- **Disable** — click the :fontawesome-solid-ban: disable button on the terminal row. The terminal will no longer appear when assigning a pickup or return location on new orders.
- **Enable** — switch the list filter to **Disabled** to see inactive terminals, then click :fontawesome-solid-circle-check: **Enable**.

Existing orders that already reference a disabled terminal keep their assignment and continue to display it correctly.

---

## :fontawesome-solid-clock-rotate-left: History

Every terminal has a full **audit history** accessible from the terminal edit page. The history shows who created or changed the terminal, when, and which fields changed. Use this to track corrections or investigate routing mistakes.

---

## :fontawesome-solid-buildings: Multi-Office Setups

If your company uses the **Multi-Office Addon**, terminals are **shared across all offices** by default — create a terminal once and every office can use it on their orders. The **Office** field on the terminal record controls which office owns the data, but visibility is shared.

See the [Changelog :octicons-arrow-right-24:](changelog.md) for more on the Multi-Office Addon.

---

## :fontawesome-solid-triangle-exclamation: Common Issues

!!! warning "I can't see a terminal on the Orders page"
    The terminal is probably **disabled**. Go to **Settings** → **Manage Terminals**, filter to **Disabled**, and re-enable it.

!!! warning "The city I need isn't in the dropdown"
    Cities are managed separately under **Settings** → **Manage Cities**. Add the city first, then come back to the terminal.

!!! warning "I'm a dispatcher and there's no **Manage Terminals** menu item"
    Dispatcher terminal management is an optional permission. Contact your administrator to enable it, or ask them to add the terminal for you.
