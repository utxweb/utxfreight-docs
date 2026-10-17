# Setup Checklist

The setup checklist is a built-in page that checks your UTX Freight system and tells you, step by step, what still needs to be set up before you can raise a correct invoice.

## :fontawesome-solid-clipboard-check: Overview

- The checklist lives at the top of the left menu, for **Admin** and **Manager** users only. Its menu label is **Getting started**, **Setup check** or **Setup complete**, depending on where your system is.
- It has **6 stages** and up to **20 steps**, from pricing your zones to sending your first invoice.
- Every step is checked automatically against the data in your system. You do not tick steps off by hand. The one exception is the two steps that offer a **Looks right to me** button.
- While required steps are still open, exactly one step is marked **Do this next**: the first required step that is not done yet. Optional steps are never marked **Do this next**.
- Some steps are **Optional**. You can skip them and still invoice, and they are not counted in the progress bar.
- The checklist covers your **whole system**, not one office. Counts include every office.

For a walkthrough of creating your first customer, contact and order by hand, see [Getting Started](getting-started.md).

## :fontawesome-solid-bolt: Quick Start

1. In the left menu, click :fontawesome-solid-clipboard-check: **Getting started** (or **Setup check**).
2. The step marked **Do this next** is already open on the right.
3. Read **What we found** and **How to do it**, then click the button at the bottom of the panel (for example **Open Zones**) to go and do the work.
4. Come back to the checklist. The page re-checks everything each time it loads, so the step shows **Done** as soon as the work is saved.
5. Repeat until the title reads **Your setup is complete**.

## :fontawesome-solid-lock: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Sees the menu entry and can open the checklist. Can complete every step. |
| :fontawesome-solid-user-tie: **Manager** | Sees the menu entry and can open the checklist. Some steps point to pages a Manager cannot open (see the warning below). |
| :fontawesome-solid-headset: **Dispatch**, **Accountant**, **Customer Service**, **Customer**, **Warehouse**, **Garage**, drivers and other users | No menu entry. If they reach the checklist page some other way (for example from a saved link), they are sent to the home page with the message **You do not have access to the setup checklist.** |

**Navigation:** left menu :fontawesome-solid-arrow-right: **Getting started** / **Setup check** / **Setup complete** (the first item in the menu).

!!! warning "Some steps lead Managers to pages they cannot open"
    Three steps send you to pages that only Admins can use:

    - **Add your GST, QST and NIR numbers** and **Your email is configured** use the **Open Settings** button.
    - **Check what your website says** uses the **Open Manage Content** button.

    A Manager can see these steps but cannot open those pages. Ask an Admin to fill in the tax numbers. A Manager can still use **Looks right to me** on **Check what your website says**.

See [User Roles](user-roles.md) for what each role can do.

## :fontawesome-solid-bars: The Menu Entry

The checklist's entry in the left menu changes its label and icon as your setup progresses.

| Label | When it shows | Icon | Tooltip (on hover) |
|-------|---------------|------|--------------------|
| **Getting started** | No invoice exists yet, and required steps are still open | :fontawesome-solid-circle-exclamation: | **N steps before your first invoice** |
| **Setup check** | At least one invoice exists, and required steps are still open | :fontawesome-solid-circle-exclamation: | **N things still to set up** |
| **Setup complete** | Every required step is done | :fontawesome-solid-circle-check: (green) | **Everything on the setup checklist is done** |

*N* is the number of required steps still open. Optional steps are never counted.

The entry stays in the menu after setup is complete, so you can come back and read the checklist at any time.

!!! info "The menu entry can take up to 5 minutes to update"
    To keep every page fast, the menu label and count are refreshed at most every **5 minutes**. The checklist page itself always shows the current state. If you just finished a step and the menu still shows the old count, open the checklist page to see the true state. The menu catches up within 5 minutes.

    Saving the **Application Settings** page (for example, adding the tax numbers) or clicking **Looks right to me** refreshes the menu entry, so it is up to date on the next page you open.

<!-- TODO: Screenshot — left menu showing the "Getting started" entry with its warning icon, and the "Setup complete" entry with the green check -->

## :fontawesome-solid-table-columns: The Checklist Page

### Title and progress

The heading at the top of the page depends on where your system is:

| Situation | Title | Text under the title |
|-----------|-------|----------------------|
| No invoices yet | **Get *your company* to its first invoice** | The shortest path to your first invoice. Anything marked Optional can wait. |
| Already invoicing, steps still open | **What is still not set up** | You are already invoicing, so nothing here is urgent - but each of these is either costing you money or waiting to. Anything marked Optional can wait. |
| Every required step done | **Your setup is complete** | Everything on this list is done. It stays here if you ever want to read it again. |

Below the title:

- A **progress bar** with the text **X of Y done**. *Y* is the number of required steps (16, or 17 with the fuel surcharge add-on). Optional steps are left out of both numbers.
- A **summary line**:
    - Before your first invoice: **N steps between you and your first invoice**
    - Once you are invoicing: **N things still to set up**
    - When complete: **Everything is set up.**
    - If any required step in Stage 1 (**Set your prices**) is still open, the line adds **· N of them decide what you can charge**.

### Step list (left) and panel (right)

The page is split in two:

- **Left: the step list.** Steps are grouped under their stage heading, for example **Stage 1 Set your prices**. Each stage heading shows **X of Y done**, plus **N optional** if the stage has optional steps. A stage whose required steps are all done shows a ✓ before its count and collapses, unless the panel is showing one of its steps. Click a stage heading to open or close it.
- **Right: the panel.** Shows the details of the selected step. When you open the page, the panel shows the **Do this next** step (or the first step, once everything is done).

Click any step in the list to show it in the panel. Once a step in the list has keyboard focus, you can also use the **↑** and **↓** arrow keys to move up and down the list (the hint **↑ ↓ to walk the list** shows under the page). The arrow keys skip steps inside collapsed stages.

Each step in the list shows a mark, its name and a badge:

| Mark | Badge | Meaning |
|------|-------|---------|
| ✓ | **Done** | The step is done. |
| ✓ | **Done · check** | The step is done but has a warning worth reading. The warning shows under the step name with a ⚠ sign. |
| ▶ | **Do this next** | The first required step that is not done. Only one step has this badge at a time. |
| ○ | **Optional** | An optional step that is not done. You can skip it. |
| ○ | *(no badge)* | A required step that is not done, further down the list. |

Steps that are not done also show a short finding under their name, for example **No customers yet**.

### What the panel shows

| Part | What it contains |
|------|------------------|
| Stage and state | The stage number followed by **Done**, **Do this next**, **Optional** or **Still to do**. |
| Step name | The name of the step, for example **Set the price of each zone**. |
| **What we found** | What the checklist found in your system, for example **3 of 5 zones priced**. A warning, if any, shows here too. |
| Why | A short paragraph explaining why the step matters. |
| **How to do it** | Numbered instructions. |
| Button | Takes you to the page where you do the work, for example **Open Zones**. **Open Feedback** opens the Feedback form in a pop-up instead of leaving the page. |
| **Looks right to me** | Only on **Check your charge types** and **Check what your website says**. See [Looks right to me](#looks-right-to-me). |

<!-- TODO: Screenshot — the checklist page with the step list on the left and the panel for the "Do this next" step on the right -->

## :fontawesome-solid-list-ol: Stages and Steps

The steps appear in this order. The **Done when** column is the exact rule the checklist uses to mark a step done.

### Stage 1 — Set your prices

| Step | Button | Done when |
|------|--------|-----------|
| **Your cities are loaded** | **Open Cities** | At least one active city exists. Cities are loaded when your system is built, so this is normally already done. |
| **Set the price of each zone** | **Open Zones** | At least one active zone has a price above $0.00. |
| **Put the cities you deliver to in a zone** | **Open Cities** (with the **Shipping** filter) | Every city you have delivered to has a zone. Also done if you have no deliveries yet. |
| **Set the default rate on your terminals** | **Open Terminals** | A charge type is set as **Use as default for: Terminal Fee**, **and** at least one active terminal has a default rate above $0.00. Both are needed. |

!!! warning "Zones at $0.00"
    **Set the price of each zone** is marked done as soon as **one** active zone has a price. If other active zones are still at $0.00, the step shows **Done · check** with the warning **N active zones still have no price and will invoice at $0.00**. An order delivered into one of those zones is invoiced for nothing, with no other warning. Price those zones, or disable the ones you do not use. See [Zones and Cities](zones-and-cities.md).

**Put the cities you deliver to in a zone** only counts cities that a delivery address on one of your orders points to, not the full city list. The **Shipping** filter on the Cities page shows the same list. A city with no zone prices at $0.00.

For terminals, see [Managing Terminals](managing-terminals.md) and [Charge Types and Taxes](charge-types-and-taxes.md).

### Stage 2 — Who you haul for

| Step | Optional | Button | Done when |
|------|----------|--------|-----------|
| **Add your first customer** | | **Open Customers** | At least one active customer company exists. Your own company does not count, and neither does the UTX Web Inc. support company. |
| **Add a contact at that customer** | | **Open Customers** | At least one active user with the **Customer** role exists. |
| **Add your shippers and receivers** | Optional | **Open Shipper / Receiver** | At least one active shipper/receiver exists, **and** every active shipper/receiver has a city set. |
| **Set special prices for a customer** | Optional | **Open Customers** | At least one customer has a negotiated price on a zone. |

!!! warning "Adding a contact sends an invitation"
    Saving a new person emails them an invitation straight away. To set up a contact quietly, use an address like **yourcompany+1@utxfreight.ca** and change it later. See [People and Invitations](people-and-invitations.md).

A shipper or receiver with no city set prices at $0.00, however well your zones are set. See [Shippers and Receivers](shippers-receivers.md).

### Stage 3 — Your yard

| Step | Optional | Button | Done when |
|------|----------|--------|-----------|
| **Add one chassis** | | **Open Equipments** | At least one active piece of equipment (of any type) exists. |
| **Add one driver** | | **Open Mobile Users** | At least one active mobile user with the **Driver** or **Broker** role exists. |
| **Add your office staff** | Optional | **Open Customers** | At least one active user with the **Dispatch**, **Accountant**, **Manager** or **Customer Service** role exists. |

See [Equipment](equipment.md) and [Mobile Users](mobile-users.md). Office staff are added as people on your own company, at the top of the Customers list.

### Stage 4 — What appears on your invoice

| Step | Button | Done when |
|------|--------|-----------|
| **Add your GST, QST and NIR numbers** | **Open Settings** | **GST Number** and **QST Number** (under **Invoice Settings**) and **NIR Number** (under **POD Settings**) on the **Application Settings** page are **all** filled in. |
| **Set this month's fuel surcharge** | **Open Fuel Schedule** | A general (not customer-specific) monthly fuel surcharge rate exists for the current month. **Only shown when your system has the fuel surcharge add-on. To have it turned on, ask UTX support.** |
| **Check your charge types** | **Open Charge Types** | At least one active charge type was changed more than one minute after it was created, **or** someone clicked **Looks right to me**. |
| **Check what your website says** | **Open Manage Content** | Someone clicked **Looks right to me**. Editing the pages does not mark this step done on its own. |
| **Your email is configured** | **Open Settings** | Always done. Email sending is set up when your system is built. The step is there so you can check where customer replies go. |

!!! info "These are your registration numbers, not tax rates"
    The GST, QST and NIR numbers are your own registration numbers, printed on every invoice and proof of delivery. The tax rates are already set. The **What we found** line names whichever numbers are still blank, for example **QST and NIR numbers are still blank**.

!!! warning "The fuel surcharge does not carry forward"
    The fuel step checks the **current month** only. At the start of each month the step goes back to not done until you add that month's rate. Without a rate, orders are built with no fuel charge. See [Fuel Surcharge](fuel-surcharge.md).

**Check your charge types** counts only active charge types, and leaves out any charge type set as **Use as default for: Fuel Surcharge** (the monthly fuel rates). Editing a fuel rate therefore does not complete this step.

### Stage 5 — Your first invoice

| Step | Button | Done when |
|------|--------|-----------|
| **Create your first order** | **Open Orders** | At least one order exists. |
| **Dispatch it to your driver** | **Open Dispatch** | At least one order has a driver (mobile user) assigned. |
| **Invoice it and email it to yourself** | **Open Invoices** | At least one invoice exists. |

When you create the order, watch the price appear as you choose the delivery address. If it shows $0.00, go back to Stage 1. See [Orders](orders.md), [Dispatch](dispatch.md) and [Creating Invoices](creating-invoices.md).

!!! info "Your first invoice changes the checklist's wording"
    As soon as one invoice exists, the menu label changes from **Getting started** to **Setup check**, and the page title changes to **What is still not set up**. The steps and rules stay the same.

### Stage 6 — Tell us how it went

| Step | Button | Done when |
|------|--------|-----------|
| **Send us a note when you are done** | **Open Feedback** | At least one Feedback note exists in your system, sent by any user. |

**Open Feedback** opens the same Feedback form as the **Feedback** button in the bar at the top of every page.

## :fontawesome-solid-thumbs-up: Looks right to me

Two steps start with pre-filled content, so there is no blank value for the checklist to detect:

- **Check your charge types**
- **Check what your website says**

If you have reviewed them and they are fine as they are, click **Looks right to me** in the panel.

1. Select the step in the list.
2. Review the page behind the button (**Open Charge Types** or **Open Manage Content**).
3. Back on the checklist, click **Looks right to me**.
4. A confirmation asks: **Mark "*step name*" as checked? You can still change anything on that page later.**
5. Click **Yes, it looks right** (or **Cancel**).

The step is marked **Done**, the next step becomes **Do this next**, and the step list, progress bar and summary update without reloading the page. The menu entry updates on the next page you open. The panel then shows **Confirmed *time* ago**, for example **Confirmed 3 minutes ago**. **What we found** reads **N charges, confirmed as they are** or **N pages, confirmed as they are**.

The button only shows while the step is not done. On **Check your charge types**, if you have already edited a charge type, the step is done and the button does not appear.

If the confirmation cannot be saved, this message appears next to the button: **Could not save that. Nothing was changed - tell us if it keeps happening.**

!!! info "Confirmations apply to the whole system"
    A confirmation is saved once for your whole system, not per user or per office. There is no button to undo it.

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-rotate: I finished a step but the menu still shows the old count

!!! info "Solution"
    The menu entry can take up to 5 minutes to update. Open the checklist page: it is always up to date. The menu catches up within 5 minutes, or on the next page you open after saving the Application Settings page or clicking **Looks right to me**.

### :fontawesome-solid-ban: I get "You do not have access to the setup checklist."

!!! info "Solution"
    The checklist is for **Admin** and **Manager** users only. Ask an Admin to check the step for you, or to change your role. See [User Roles](user-roles.md).

### :fontawesome-solid-lock: As a Manager, I cannot open Settings or Manage Content from the checklist

!!! info "Solution"
    Settings and Manage Content are Admin-only pages. Ask an Admin to add the GST, QST and NIR numbers. For **Check what your website says**, you can click **Looks right to me** if the website text is correct, or ask an Admin to edit it.

### :fontawesome-solid-triangle-exclamation: "Set the price of each zone" says Done · check

!!! info "Solution"
    At least one zone is priced, but other active zones are still at $0.00 and will invoice for nothing. Open **Zones**, price the zones you deliver into, and disable the ones you do not use.

### :fontawesome-solid-building: The counts include another office's data

!!! info "Solution"
    This is expected. The checklist asks whether the whole system is ready to invoice, so it counts every office, not just the one you are working in. See [Multi-Office](multi-office.md).

### :fontawesome-solid-gas-pump: "Set this month's fuel surcharge" was done last month and is open again

!!! info "Solution"
    The step checks the current month only. Add this month's rate on the **Fuel Schedule** page. See [Fuel Surcharge](fuel-surcharge.md).

### :fontawesome-solid-pen: I edited my website pages but "Check what your website says" is still open

!!! info "Solution"
    This step is only marked done when someone clicks **Looks right to me**. Editing the pages does not complete it.

### :fontawesome-solid-eye-slash: The checklist entry is missing from my menu

!!! info "Solution"
    The entry only shows for Admin and Manager users. If you are an Admin or Manager and the entry is missing, reload the page. If it is still missing, contact UTX support through **Feedback**.

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Getting the most out of the checklist"
    - Work from top to bottom. **Do this next** always points at the most important open step.
    - Do Stage 1 first. An order in an unpriced zone or a shipper with no city invoices at $0.00, and nothing else warns you.
    - Disable the zones, terminals and charge types you never use. They stop being counted and leave the dropdowns.
    - Email your first invoice to yourself, not to the customer, and check what arrives.
    - Check the checklist at the start of each month if you use the fuel surcharge add-on.
