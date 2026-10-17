# Order Legs & Move Locations

Break an order into legs (one move from a place to another place by a driver), let UTX Freight build the legs for Dry Van Moves and Container Transfers, and manage the list of **Move Locations** that legs can use.

## :fontawesome-solid-route: Overview

- :fontawesome-solid-shuffle: A **leg** is one move: **Move From** a place, by a **driver**, **Move To** another place. An order can have any number of legs.
- :fontawesome-solid-map-pin: The places a leg can use are your **Move Locations** (managed on the **Leg Move Locations** page) and your **Terminals**.
- :fontawesome-solid-wand-magic-sparkles: **Automatic legs** — for **Dry Van Move** and **Container Transfer** orders, UTX Freight builds the legs for you from the order's drivers and terminals. For all other order types, you add legs by hand.
- :fontawesome-solid-pen-to-square: You edit legs in the **Order Legs** panel of the **Dispatch**, **Quick Edit** and **Complete** pop-up windows, and in the **Order Legs** section of the full **Edit Order** form.
- :fontawesome-solid-circle: On the **Dispatch** board, each order shows its legs as numbered badges in the **Legs** column. Click a badge to mark that leg as the **active** leg.
- :fontawesome-solid-users: The **Legs** and **Details** buttons on the Dispatch board summarise today's legs per driver.

---

## :fontawesome-solid-bolt: Quick Start

**Add a leg to an order:**

1. On the **Orders** list or the **Dispatch** board, open the order's action menu and choose **Quick Edit** (or click the order's **Dispatch** / **Complete** button).
2. Click the **Order Legs** panel to expand it.
3. Click **(+) Add another**. A new leg row appears.
4. Pick where the move starts (first dropdown), the driver, and where it ends (last dropdown).
5. Save the window as usual.

**Add a Move Location:**

1. Click your name in the top bar :fontawesome-solid-arrow-right: **Manage Move Locations**.
2. Click **Add a new Leg Move Location**.
3. Enter the **Name**, check the **Office**, and click **Save**.

<!-- TODO: Screenshot — The Quick Edit window with the Order Legs panel expanded, showing two leg rows and the (+) Add another button -->

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Order Legs panel (Dispatch / Quick Edit / Complete windows) | Order Legs section (full Edit Order form) | Dispatch board Legs column, Legs and Details | Manage Move Locations |
|------|------|------|------|------|
| :fontawesome-solid-user-shield: **Admin** | Yes | Yes | Yes | Yes |
| :fontawesome-solid-user-tie: **Manager** | Yes | Yes | Yes | Yes |
| :fontawesome-solid-headset: **Dispatch** (and **Customer Service**) | Yes | Only with **Can manage rates?** turned on in their user profile | Yes | Yes |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No (panel not shown) | No | No (no access to the Dispatch board) | No |
| :fontawesome-solid-warehouse: **Warehouse** / :fontawesome-solid-wrench: **Garage** | No | No | No | No |
| :fontawesome-solid-user: **Customer** | No | No | No | No |

!!! info "Why some dispatchers don't see Order Legs on the full form"
    On the full **Edit Order** form, the **Order Legs** section sits with the rate sections, so it is only shown to users who can manage rates: Admins, Managers, and Dispatch users with **Can manage rates?**. Every Admin, Manager and Dispatch user can still edit legs from the **Quick Edit**, **Dispatch** and **Complete** windows.

### :fontawesome-solid-map: Where to find each screen

| Screen | How to open it |
|--------|----------------|
| **Order Legs** panel | Order action menu :fontawesome-solid-arrow-right: **Quick Edit**, or the order's **Dispatch** or **Complete** button :fontawesome-solid-arrow-right: **Order Legs** |
| **Order Legs** section | Order action menu :fontawesome-solid-arrow-right: **Edit Order** (near the bottom of the form, after **Order Expenses**) |
| **Legs** column | **Dispatch** board, one cell per order |
| **Driver Legs for Today** / **Details** | **Dispatch** board :fontawesome-solid-arrow-right: **Legs** or **Details** button (next to **Chassis**) |
| **Leg Move Locations** | Your name in the top bar :fontawesome-solid-arrow-right: **Manage Move Locations** |

---

## :fontawesome-solid-list-ol: The Order Legs Panel

Each leg is one row with three choices and a remove button:

| Part | What it is |
|------|------------|
| **Move From** | Where the move starts. A dropdown grouped under **Move Location** (your active move locations, see [Disabling and deleting](#disabling-and-deleting)) and **Terminal** (active terminals). |
| Driver | The driver who does this move. Lists the active drivers of your current office. Can be left blank. |
| **Move To** | Where the move ends. Same grouped dropdown as **Move From**. |
| **(-) Remove** | Removes the leg when you save. |

The buttons and labels differ slightly between the two places you edit legs:

| | **Dispatch** / **Quick Edit** / **Complete** windows | Full **Edit Order** form |
|---|---|---|
| Labels | None — the row reads left to right: Move From, driver, Move To | **Move From**, **Driver**, **Move To** |
| Add a leg | **(+) Add another** | **(+) Add another leg** |
| Remove a leg | **(-) Remove** | **(-) Remove leg** |

To add a leg:

1. Click **(+) Add another** (or **(+) Add another leg**).
2. Choose the **Move From** location or terminal.
3. Choose the driver.
4. Choose the **Move To** location or terminal.
5. Save the window or form.

!!! tip "Check both dropdowns on a new leg"
    **Move From** and **Move To** have no empty choice. A new row starts on the first entry of the list, so always pick both places before you save.

Legs are listed in the order they were created.

### :fontawesome-solid-lock: Container Transfer legs are read-only

For a **Container Transfer**, the **Order Legs** panel shows the legs as text instead of dropdowns, one line per leg:

> From *(pickup terminal)* To *(return terminal)* By *(driver)*

**N/A** replaces any part that is not set (for example **By N/A** when no driver is assigned). There is no **(+) Add another** button. To change a Transfer leg, change the order's terminals or driver — see [Automatic Legs](#automatic-legs).

On the full form this applies to Transfers that are already saved. While you create a new Transfer the editable rows are shown, but the legs are replaced by the automatic Transfer leg as soon as you save.

---

## :fontawesome-solid-wand-magic-sparkles: Automatic Legs

UTX Freight builds legs automatically for two order types only: **Dry Van Move** and **Container Transfer**. Container Import, Container Export and International Export orders never get automatic legs — their legs are exactly what you enter.

### :fontawesome-solid-arrow-right-arrow-left: Container Transfer

A Transfer always has **one leg**:

| Move From | Driver | Move To |
|-----------|--------|---------|
| The order's pickup terminal | The pickup driver (the first driver column on the **Orders** list and **Dispatch** board) | The order's return terminal |

Every time the legs are rebuilt, all existing legs of the Transfer are deleted and this single leg is created again.

### :fontawesome-solid-truck: Dry Van Move

A Dry Van Move has two drivers: the **pickup driver** (first driver column on the **Orders** list and **Dispatch** board) and the **delivery driver** (second driver column). The legs depend on which drivers are set:

| Drivers on the order | Legs created |
|----------------------|--------------|
| Only one driver, or the same driver for both | 1 leg: **Pickup Location** :fontawesome-solid-arrow-right: **Delivery Location**, by that driver |
| Two different drivers | Leg 1: **Pickup Location** :fontawesome-solid-arrow-right: **Storage**, by the pickup driver<br>Leg 2: **Storage** :fontawesome-solid-arrow-right: **Delivery Location**, by the delivery driver |
| No driver | No new leg. An existing **Pickup Location** :fontawesome-solid-arrow-right: **Delivery Location** leg is removed; other legs are kept. |

!!! warning "Manual Dry Van legs are replaced"
    When a Dry Van Move has at least one driver, rebuilding the legs **deletes every leg on the order** (including legs you added by hand) and creates the legs shown above. If you need extra legs on a Dry Van Move, add them after the drivers are set, and add them from the **Quick Edit** window — see below for what triggers a rebuild.

**Pickup Location**, **Delivery Location** and **Storage** are ordinary Move Locations. UTX Freight creates them automatically the first time it builds Dry Van legs, if they do not exist yet. They then appear on the **Leg Move Locations** page and in the leg dropdowns like any other move location.

!!! danger "Do not rename Pickup Location, Delivery Location or Storage"
    UTX Freight finds these three locations by their exact name. If you rename one, the next Dry Van order creates a new location with the original name, and you end up with two.

### :fontawesome-solid-rotate: When the legs are rebuilt

Automatic legs (Dry Van Move and Container Transfer only) are rebuilt when:

- :fontawesome-solid-floppy-disk: You **create** the order from the full new-order form, or **save** the full **Edit Order** form (the **Submit Order** button).
- :fontawesome-solid-user: You change the delivery driver or the pickup driver directly in the driver column of the **Orders** list or the **Dispatch** board.
- :fontawesome-solid-warehouse: You change the **Return To** terminal directly in the **Orders** list or the **Dispatch** board.

They are **not** rebuilt when:

- You save the **Dispatch**, **Quick Edit** or **Complete** window. The legs are saved exactly as they are in the **Order Legs** panel.
- The order is created with **Duplicate** or from the **Auto Orders** review window. These orders start with no legs (duplicates do not copy legs) until one of the actions above builds them. See [Order Duplication](order-duplication.md) and [Auto Orders](auto-orders.md).

!!! info "Rebuilt legs are new legs"
    A rebuild deletes the old legs and creates new ones. Any leg you had marked as active on the Dispatch board is no longer active afterwards.

---

## :fontawesome-solid-circle-dot: Active Leg and the Dispatch Board

The **Legs** column of the **Dispatch** board shows one numbered badge per leg (**1**, **2**, **3**...), in the order the legs were created. Hover over a badge to see the leg as **From** *place* **To** *place* **By** *driver*.

| Badge colour | Meaning |
|--------------|---------|
| Blue | The active leg |
| Grey | Not the active leg |

To mark a leg as active, click its badge. The badge turns blue and every other leg of that order turns grey — an order has at most one active leg. Click the blue badge again to clear it, leaving no active leg.

The active leg is a marker for your dispatch team on the board. It does not change the order's status or what the driver sees.

<!-- TODO: Screenshot — A Dispatch board row with three leg badges in the Legs column, the second one blue -->

### :fontawesome-solid-users: Legs and Details buttons

Two buttons at the top of the **Dispatch** board, next to **Chassis**, summarise the legs of the current office's orders whose **delivery date is today** (whatever their status):

| Button | Window | Shows |
|--------|--------|-------|
| **Legs** | **Driver Legs for Today** | One row per driver: **Driver** and the number of **Legs** they have today |
| **Details** | **Driver Legs Details for Today** | One row per order: **Order #**, then **Leg #1**, **Leg #2**... with the driver of each leg |

Only orders that have at least one leg are counted. Legs without a driver are not counted in **Legs**. For the board itself, see [Dispatch](dispatch.md).

!!! tip "Search by leg driver"
    The Dispatch board search also matches the names of the drivers on an order's legs, so you can type a driver's name to find every order where they have a leg.

The **Driver Delivery Report** in **Reports** also lists a driver's legs (Leg, Date, Order #, Container #, Move) for orders delivered in the chosen period. See [Reports](reports.md).

---

## :fontawesome-solid-map-location-dot: Managing Move Locations

Move Locations are the named places (yards, storage lots, drop points...) you can use in **Move From** and **Move To**, in addition to your terminals.

Go to your name in the top bar :fontawesome-solid-arrow-right: **Manage Move Locations**. The page is titled **Leg Move Locations** and lists the move locations of your **current office**, sorted by name.

| Column | What it shows |
|--------|---------------|
| **Name** | The location name, as it appears in the leg dropdowns |
| **Active** | Green check mark (active) or red cross (inactive) |
| *(no heading)* | An **Actions** button with **Edit** and **View History** |

<!-- TODO: Screenshot — The Leg Move Locations page with Pickup Location, Delivery Location and Storage listed -->

### :fontawesome-solid-plus: Add or edit a move location

1. Click **Add a new Leg Move Location**, or **Actions** :fontawesome-solid-arrow-right: **Edit** on an existing row.
2. Fill the **Move Location Information** form:

    | Field | Required | Notes |
    |-------|----------|-------|
    | **Name** | Yes | Placeholder: *Location Name*. |
    | **Office** | Yes | Hint: *Office for which this move location applies*. Lists the offices you belong to. |
    | **Active** | No | Hint: *Only active move locations will be visible for new orders*. Checked by default for a new location. |

3. Click **Save** to return to the list, or **Cancel** to leave without saving.

**View History** opens the change history of the location (who changed what, and when).

### :fontawesome-solid-ban: Disabling and deleting

There is no **Delete** action for move locations. To retire a location, **Edit** it and uncheck **Active**. Only active move locations are offered for new orders.

Terminals work the same way: only **active** terminals appear under **Terminal** in the dropdowns. See [Managing Terminals](managing-terminals.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the Order Legs section on the Edit Order form

!!! info "Solution"
    On the full form, **Order Legs** is only shown to Admins, Managers and Dispatch users with **Can manage rates?**. Use **Quick Edit** instead: its **Order Legs** panel is available to every Admin, Manager and Dispatch user. Accountants and customers cannot edit legs.

### :fontawesome-solid-eraser: The legs I added to a Dry Van Move disappeared

!!! info "Solution"
    When a Dry Van Move has a driver, saving the full **Edit Order** form or changing a driver inline on the **Orders** list or **Dispatch** board rebuilds the legs and deletes all existing ones. Re-add your extra legs from **Quick Edit** after the drivers are final.

### :fontawesome-solid-lock: I can't edit the legs of a Container Transfer

!!! info "Solution"
    Transfer legs are always generated from the order's pickup terminal, return terminal and pickup driver, so they are shown read-only. Change those order fields instead.

### :fontawesome-solid-copy: Storage, Pickup Location or Delivery Location appears twice

!!! info "Solution"
    One of these locations was renamed, so UTX Freight created a new one with the original name. Rename the old copy to something clearly different (or uncheck **Active**). Keep the exact names **Pickup Location**, **Delivery Location** and **Storage** on the copies UTX Freight uses.

### :fontawesome-solid-trash-can: How do I delete a move location?

!!! info "Solution"
    You can't — the page has no **Delete** action. Edit the location and uncheck **Active**.

### :fontawesome-solid-circle-dot: My active leg is no longer highlighted

!!! info "Solution"
    The legs were rebuilt (Dry Van Move or Container Transfer), which creates new legs that are not active. Click the badge again on the **Dispatch** board.

---

## :fontawesome-solid-star: Best Practices

!!! tip "Getting the most out of legs"
    - For **Dry Van Moves**, set both drivers first and let UTX Freight build the legs; only add extra legs afterwards from **Quick Edit**.
    - For **Container Transfers**, keep the pickup terminal, return terminal and pickup driver correct — the leg follows them.
    - Keep your **Move Locations** list short and clearly named, and uncheck **Active** on locations you no longer use.
    - Use the **active** badge on the Dispatch board to show the team which leg is in progress.
    - Check **Legs** and **Details** on the Dispatch board each morning to balance today's work between drivers.
