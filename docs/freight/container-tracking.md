# Container Tracking

See the latest terminal status of a container (CN Rail, Termont / Port of Montreal, or MGT Racine/Cast) from the order list, without logging in to the terminal websites.

## :fontawesome-solid-satellite-dish: Overview

**Container Tracking** (also called Track & Trace) checks your containers at the terminal on a schedule, stores the latest status, and shows it in a popup when you click the tracking icon on an order.

- :fontawesome-solid-puzzle-piece: **Three separate add-ons** -- one per tracking source. Each source is shown and checked only when its own add-on is on for your account (see [Add-ons and Options](add-ons-and-options.md)).
- :fontawesome-solid-train: **CN Rail** -- containers at a pickup terminal named **CN**.
- :fontawesome-solid-ship: **Termont (Port of Montreal)** -- containers at a pickup terminal whose name contains **TERMONT** or **VIAU**.
- :fontawesome-solid-ship: **MGT (Racine/Cast)** -- containers at a pickup terminal whose name contains **RACINE** or **CAST**.
- :fontawesome-solid-arrows-rotate: **Automatic checks** -- the system checks **in-progress** orders at those terminals on a schedule. You never trigger a check yourself.
- :fontawesome-solid-clock-rotate-left: **Change history** -- every change to the key tracking fields is recorded and shown at the bottom of the popup.
- :fontawesome-solid-wand-magic-sparkles: **Auto-fill** -- for Termont and MGT, blank order fields (seal, weight, steamship line, size, customs released) are filled in when new terminal data arrives.
- :fontawesome-solid-bell: **Alerts and bulk updates** -- status-change alerts are covered in [Container Alerts](container-alerts.md); updating ETA and Last Free Day on many orders at once is covered in [Tracking Bulk Update](tracking-bulk-update.md).

<!-- TODO: Screenshot — The Container Tracking popup for a Termont container with a green READY FOR PICKUP header -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Orders** (or **Dispatch**).
2. Find the order. In the **Container#** column, click the tracking icon (:fontawesome-solid-train: red train for CN, :fontawesome-solid-ship: blue ship for Termont, :fontawesome-solid-ship: orange ship for MGT). Its tooltip reads **Check container status**.
3. The tracking popup opens. A **green header** means the container is available (CN: de-ramped; Termont / MGT: ready for pickup). Check the **Customs** line before you dispatch.
4. Click **Close** when done.

!!! tip "Tip"
    The icon depends on the order's **pickup terminal**, not on the container number. If there is no icon, check the pickup terminal first. See [No tracking icon on an order](#no-tracking-icon-on-an-order).

---

## :fontawesome-solid-shield-halved: Access & Permissions

Each part of the feature has its own rule:

- **Tracking icon on Orders** -- needs permission to change container status on orders (the same permission as the inline container status edit).
- **Tracking icon on Dispatch** -- shown to everyone who can open **Dispatch**.
- **Tracking popup** -- needs full permission to manage the order (view-only access to an order is not enough).

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Icon on **Orders** and **Dispatch**, popup |
| :fontawesome-solid-user-tie: **Manager** | Icon on **Orders** and **Dispatch**, popup (own offices) |
| :fontawesome-solid-headset: **Dispatch** / **Customer Service** | Icon on **Orders** and **Dispatch**, popup (own offices) |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Icon on **Orders** and popup (own offices) only when your account lets accountants manage orders. This is on by default and set by UTX. No access to **Dispatch** |
| :fontawesome-solid-user: **Customer** | No tracking icon, no popup |
| :fontawesome-solid-id-card: **Driver** / **Broker** / **Yard Worker** | No tracking icon, no popup |
| :fontawesome-solid-warehouse: **Warehouse** / :fontawesome-solid-wrench: **Garage** | No access -- these roles have no access to orders |

**How to get there:**

- :fontawesome-solid-arrow-right: **Orders** or **Dispatch** -- tracking icon in the **Container#** column.
- :fontawesome-solid-arrow-right: **Dispatch** -- the **Alerts** button opens the Container Alerts page, where each container number also opens the tracking popup. See [Container Alerts](container-alerts.md).

!!! warning "Don't see any tracking icons?"
    Your account may not have the tracking add-on for that terminal. Each source (CN, Termont, MGT) is a separate add-on. Contact UTX support to enable it.

---

## :fontawesome-solid-arrows-rotate: Which Containers Are Checked

The system checks an order's container only when **all** of these are true:

- The add-on for that source is on.
- The order is **in progress**: status **New**, **App. Taken** (shown as **App. Made** on the Orders tabs), or **Dispatched**.
- The order was created on or after the **Order Archive Cutoff Date** in **Settings** (see [Application Settings](application-settings.md)).
- The order's **pickup terminal** is one of the terminals set up for that source.
- The container number is not blank and is not **N/A**.
- The container has not already left the terminal:
    - **CN:** skipped once its waybill status is **Departed** or **Completed**.
    - **Termont / MGT:** skipped once its transit state is **Out**.

Orders are processed in groups: 200 orders at a time for CN, 50 for MGT, and 10 for Termont (with a 2-second pause between Termont groups). Within a group, a container number that is on several orders is checked once.

**How often?** The checks run automatically on a schedule set by UTX. Use the **Updated ... ago** line at the bottom of the popup to see when that container was last refreshed.

!!! info "Completed orders"
    The icon can still appear on a **Completed** order, and the popup still shows the last data stored for that container. It is no longer refreshed, because only in-progress orders are checked.

---

## :fontawesome-solid-magnifying-glass: The Tracking Icon

The icon sits in the **Container#** column, before the container number and the HAZMAT / scale / damaged labels.

| Icon | Source | Shown when |
|------|--------|-----------|
| :fontawesome-solid-train: Red train | **CN Rail** | CN tracking add-on is on and the pickup terminal is a CN terminal |
| :fontawesome-solid-ship: Orange ship | **MGT (Racine/Cast)** | MGT tracking add-on is on and the pickup terminal is a Racine or Cast terminal |
| :fontawesome-solid-ship: Blue ship | **Termont** | Port of Montreal tracking add-on is on and the pickup terminal is a Termont / Viau terminal |

**Rules on the Orders page:**

- You need permission to change container status on orders (see [Access & Permissions](#access-permissions)). Without it, you see the container number with its status label but no icon.
- If the container number is **longer than 20 characters** (for example several numbers separated by `/`), there is **no** tracking icon. Each `/` becomes a line break so the numbers are shown on separate lines.
- The icon is shown even before a container number is entered. In that case the popup says the container was not found.

**On the Dispatch page** the same icon appears in the container column for every order at a tracking terminal, for everyone who can open **Dispatch**, whatever the length of the container number.

<!-- TODO: Screenshot — An order row on the Orders page with the red CN train icon in the Container# column -->

---

## :fontawesome-solid-window-restore: The Tracking Popup

Click the icon to open the popup. Its layout depends on the source. Fields with no data show a dash (**—**). Both layouts have a **Container Tracking** tab, the **Updated ... ago** line, the [change history](#change-history) table, and a **Close** button.

!!! info "How the source is chosen"
    The popup picks the source from the start of the order's pickup terminal name:

    - **CN** :fontawesome-solid-arrow-right: CN Rail
    - **TERMONT** or **VIAU** :fontawesome-solid-arrow-right: Termont
    - **RACINE** or **CAST** :fontawesome-solid-arrow-right: MGT (Racine/Cast)

    It then looks up the stored tracking data for that source and the order's container number. If nothing is stored, the [not-found popup](#container-not-found) opens instead.

### :fontawesome-solid-train: CN Rail popup

<!-- TODO: Screenshot — The CN Rail tracking popup with a blue header showing the CLM status, Status & Location and Container Details sections, and Key Dates -->

**Header:** train icon and container number, with **CN Rail**, the size, and Empty/Full underneath. The badge on the right shows the status.

| Header color | Badge | Meaning |
|-------------|-------|---------|
| :fontawesome-solid-circle:{ .text-success } **Green** | **DE-RAMPED / AVAILABLE** | The CLM status contains "De-ramped": the container is off the train |
| :fontawesome-solid-circle:{ .text-info } **Blue** | The current CLM status (or **TRACKING** if there is none) | Anything else: in transit, at the yard, not yet de-ramped |

**Orange bar (CN):** appears when CN reports a customs status and the customs description does not contain "release". It reads **Customs Hold:** followed by the customs status, with the hold description underneath.

**Sections:**

| Section | Fields |
|---------|--------|
| **Status & Location** | **CLM Status**, **Event Location**, **Last Event** (date and time, when known), **Destination**, **Lot Location** (when known), **Customs** |
| **Container Details** | **Equipment Type**, **Size**, **Empty/Full** (blue **Full** or gray **Empty** label), **Gross Weight** (KG), **Net Weight**, **Waybill Status** -- each shown only when CN sends it, except Empty/Full |
| **GPS Location** | **Position**, **Location**, **GPS Time** -- only when CN sends a GPS position |
| **Bill of Lading** | **BOL Number**, **Shipper**, **Consignee**, **Commodity** -- only when CN sends a BOL number |
| **Key Dates** | **Destination ETA**, **Last Free Day** (see [Last Free Day colors](#last-free-day-colors)) |
| **Technical Details** (click to expand) | **EDI 214**, **EDI 322**, **CLM Code** |

The **Customs** field shows **No customs info** (gray) when there is nothing, a green check and the description when the description contains "release", or an orange warning triangle and the description (or hold status) otherwise.

!!! tip "What does De-ramped mean?"
    **De-ramped** means the container is off the train at the CN yard. A green header with **DE-RAMPED / AVAILABLE** is the signal to plan the pickup -- after checking the **Customs** line for a hold.

### :fontawesome-solid-ship: Termont / MGT popup

Termont and MGT (Racine/Cast) use the same layout.

<!-- TODO: Screenshot — The Termont tracking popup with a green READY FOR PICKUP header, Status & Availability, Container & Vessel, Carrier Timeline and Key Dates -->

**Header:** cube icon and container number, with the source (**Termont** or **MGT (Racine/Cast)**), the shipping line, and size and type underneath.

| Header color | Badge | Meaning |
|-------------|-------|---------|
| :fontawesome-solid-circle:{ .text-success } **Green** | **READY FOR PICKUP** | The terminal reports the container as available for pickup |
| :fontawesome-solid-circle:{ .text-danger } **Red** | **NOT AVAILABLE FOR PICKUP** | Any other answer, including no answer |

**Orange bar (Termont / MGT):** shows the **terminal's hold message** (for example "On Hold - Not available for pick up") whenever the terminal reports one. It is a terminal hold, which may or may not be customs-related -- check the **Customs** line for the customs status.

**Sections:**

| Section | Fields |
|---------|--------|
| **Status & Availability** | **Terminal** (the terminal section), **Customs**, **Customs Date** (when known), **Hold/Perm** (when known) |
| **Container & Vessel** | **Shipping Line**, **Vessel**, **Voyage**, **Origin**, **Size / Type** (when known), **Empty/Full** |
| **Carrier Timeline** | **IN** -- ship icon, vessel name, arrival date and time. **OUT** -- carrier type icon (vessel, truck, or rail), carrier name, date and time. A row with no carrier and no date reads **Not yet departed** (this can also appear on **IN** when no arrival data is known) |
| **Key Dates** | **Destination ETA**, **Last Free Day** (see [Last Free Day colors](#last-free-day-colors)) |
| **Technical Details** (click to expand) | **Visit State** (**Active**, **Departed**, or **Unknown** when not reported), **Transit State** (**In**, **Out**, or **Unknown**), **Seal Number**, **Gross Weight** (KG), **Booking/BL** |

The **Customs** field works the same way as on the CN popup: **No customs info**, a green check when the description contains "release", or an orange warning triangle.

### :fontawesome-solid-calendar-xmark: Last Free Day colors

The **Last Free Day** in the **Key Dates** box is colored by how many days are left:

| Color | Days left |
|-------|-----------|
| :fontawesome-solid-circle:{ .text-success } **Green** | 3 or more days |
| :fontawesome-solid-circle:{ .text-warning } **Orange** | 1 or 2 days |
| :fontawesome-solid-circle:{ .text-danger } **Red**, light red background, **EXPIRED** | The Last Free Day is **today or earlier** |

!!! warning "EXPIRED shows on the Last Free Day itself"
    The popup marks the date **EXPIRED** from the Last Free Day onward, including the day itself. Treat it as "pick up today at the latest".

!!! danger "Storage and demurrage after the Last Free Day"
    Once the Last Free Day has passed, the terminal or steamship line may start charging storage or demurrage. The exact charges and when they start depend on the terminal and the line, not on UTX Freight. Plan pickups before the date shown.

---

## :fontawesome-solid-clock-rotate-left: Change History

At the bottom of the CN and Termont / MGT popups, a table lists changes the system recorded for that container, newest first.

| Column | What it shows |
|--------|---------------|
| **Tracker** | The tracking source, for example **CN** or **POM** (Port of Montreal / Termont) |
| **Changes** | Each changed field with its old and new value |
| **When** | Date and time of the change |

Only these fields are tracked:

| Label in the table | Meaning |
|--------------------|---------|
| **Status** | CN CLM status |
| **Destination ETA** | ETA reported by the terminal |
| **Last free day** | Last Free Day reported by the terminal |
| **Pickup availability** | Termont / MGT available for pickup (Yes / No) |
| **Visit state** | Termont / MGT visit state; CN waybill status |
| **Transit state** | Termont / MGT transit state (In / Out) |
| **Customs status** | Customs hold status |
| **Customs description** | Customs description (for example a release or hold reason) |

Changes to other data (vessel, seal, weight, location and so on) update the popup but do not appear in the history.

The first **5** rows are shown. If there are more, click **Show all** to see the rest.

---

## :fontawesome-solid-wand-magic-sparkles: Auto-Filled Order Fields

When new Termont or MGT data arrives for a container, the system fills in blank fields on every in-progress order with that container number.

**When it runs:**

- Only for **Termont** and **MGT (Racine/Cast)**. CN data never fills order fields.
- Only when the terminal data for that container **changed** (or is new) since the last check.
- Only on **in-progress** orders (New, App. Taken, Dispatched) created on or after the archive cutoff that have the **same container number**.
- Only fields that are **blank** on the order. Existing values are never overwritten.

| Order field | What is filled |
|-------------|----------------|
| :fontawesome-solid-lock: **Seal Number** | The seal number from the terminal |
| :fontawesome-solid-weight-hanging: **Weight** | The terminal's gross weight followed by KG (for example **24000 KG**) |
| :fontawesome-solid-ship: **Steamship Line** | The steamship line whose name matches the terminal's shipping line (not case-sensitive). If there is no exact match, a line whose name **starts with** the terminal's value. Nothing if there is no match |
| :fontawesome-solid-cube: **Container Size** | The container size whose name equals the terminal's size, written either as **40** or **40'**. Nothing if there is no match |
| :fontawesome-solid-circle-check: **Customs released** | Set to **Yes** when the terminal's customs description contains "release" |

!!! info "ETA and Last Free Day are never auto-filled"
    Tracking does not copy the **ETA** or **Last Free Day** to the order. Use the bulk update tools (**CN Tracking** and **Port Tracking** on **Dispatch**) to apply them. See [Tracking Bulk Update](tracking-bulk-update.md).

---

## :fontawesome-solid-bell: Alerts and Bulk Updates

- :fontawesome-solid-bell: **Container Alerts** -- open from the **Alerts** button on **Dispatch**. Lists pickup-ready, customs-released, LFD-approaching and departed alerts, upcoming Last Free Days, and the health of each tracking source. Click a container number there to open the same tracking popup. See [Container Alerts](container-alerts.md).
- :fontawesome-solid-list-check: **Bulk update** -- the **CN Tracking** and **Port Tracking** buttons on **Dispatch**. See [Tracking Bulk Update](tracking-bulk-update.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-magnifying-glass: Container not found

!!! info "Solution"
    The popup titled **Container Information** says **This container number was not found.** and **There is no information available at this time.** It means no tracking data is stored for that source and container number. Common causes:

    - The container has not been checked yet (new order, or the terminal does not know it yet).
    - The container number on the order is blank, **N/A**, or has a typo.
    - The order is not in progress, or was created before the **Order Archive Cutoff Date**, so it was never checked.
    - The container number on the order has extra characters (for example several numbers in one field), so it does not match the stored container number.
    - The tracking add-on for that source was off when the container was at the terminal.
    - The pickup terminal name does not **start** with CN, TERMONT, VIAU, RACINE or CAST. See [Managing Terminals](managing-terminals.md).

### :fontawesome-solid-eye-slash: No tracking icon on an order

!!! info "Solution"
    Check, in order:

    1. **Pickup terminal** -- it must be a tracking terminal: its name must start with **CN**, **TERMONT**, **VIAU**, **RACINE** or **CAST**. See [Managing Terminals](managing-terminals.md).
    2. **Add-on** -- the add-on for that source must be on.
    3. **Permission** -- on **Orders** you need permission to change container status. Customers, drivers, and accountants without order management do not see the icon.
    4. **Container number length** -- on **Orders**, numbers longer than 20 characters have no icon.

    If you just created or renamed a terminal and the icon still does not appear, contact UTX support.

### :fontawesome-solid-link: "Container status opens in a popup"

!!! info "Solution"
    The tracking popup only works from a click inside the app. If you open its address directly (for example from a bookmark), you are sent back to the previous page, or to Container Alerts, with the message **Container status opens in a popup. Click the container number in the list to see it.** Click the tracking icon or the container number instead.

### :fontawesome-solid-clock: Data seems out of date

!!! info "Solution"
    Look at **Updated ... ago** at the bottom of the popup. It changes each time the terminal returns data for that container, even if nothing changed. If it is old:

    - The order may no longer be in progress, or the container is marked departed (CN **Departed** / **Completed**, Termont/MGT transit **Out**) and is no longer checked.
    - The terminal may not be returning data. Check the source's health card on [Container Alerts](container-alerts.md).

### :fontawesome-solid-ban: Customs hold still showing after release

!!! info "Solution"
    Customs information comes from the terminal and updates only on the next successful check. If it stays on hold after several checks, confirm with the terminal or your customs broker.

### :fontawesome-solid-lightbulb: Best practices

!!! tip "Best Practices"
    **Name terminals carefully.** Start each tracking terminal's name with CN, TERMONT, VIAU, RACINE or CAST.

    **Enter one container number per order.** Long multi-number entries (over 20 characters) lose the tracking icon on Orders, and tracking sends the whole field to the terminal as one container number, so it is unlikely to be found.

    **Green header = check customs, then dispatch.** On CN, de-ramped does not mean customs is released -- read the **Customs** line.

    **Use bulk update for dates.** ETA and Last Free Day are not copied to orders automatically.
