# Bulk Tracking Updates (CN & Port Tracking)

Compare the ETA, Last Free Day and weight of all your in-progress container orders against CN Rail or the Montreal port terminals, and update them in one click from the Dispatch board.

## :fontawesome-solid-arrows-rotate: Overview

The **CN Tracking** and **Port Tracking** buttons on the [Dispatch board](dispatch.md) open a bulk update window. Instead of checking containers one by one (see [Container Tracking](container-tracking.md)), you see every in-progress order for that source side by side with what the railway or terminal reports, and you copy the new values onto the orders with **Update Selected**.

At a glance:

- :fontawesome-solid-train: **CN Tracking** -- asks CN **live** for the status of your containers each time you open it. Window title: **Shipments Tracking for Canadian National**.
- :fontawesome-solid-ship: **Port Tracking** -- reads the tracking data the app has **already stored** for Termont (Port of Montreal) and MGT (Racine/Cast). Window title: **Shipments Tracking for Port of Montreal** (this covers both Termont and MGT containers).
- :fontawesome-solid-code-compare: **Side-by-side comparison** -- for **ETA**, **LFD** and **Weight**, a check mark means the order already matches; an arrow (**->**) points to the new value from the source.
- :fontawesome-solid-pen-to-square: **Update Selected** -- overwrites ETA, LFD and weight on the checked orders. Port Tracking also fills in a **blank** seal number and steamship line.
- :fontawesome-solid-circle-exclamation: **No information table** -- lists New orders for that source that the railway/terminal returned nothing for.
- :fontawesome-solid-building: **Current office only** -- with [multiple offices](multi-office.md), only the orders of the office you are working in are listed.

<!-- TODO: Screenshot — The CN Tracking window on the Dispatch board, showing the comparison table and the Update Selected button -->

---

## :fontawesome-solid-bolt: Quick Start

1. From the left menu, click :fontawesome-solid-road: **Dispatch**.
2. Click :fontawesome-solid-train: **CN Tracking** or :fontawesome-solid-ship: **Port Tracking** (the button shows **Loading** while the data is gathered).
3. Review the table. Rows with a red value and an arrow (**->**) have something to update.
4. Uncheck any order you do **not** want to change (all rows are checked by default).
5. Click **Update Selected**.
6. The window closes, an **Updated** message appears at the top of the screen, and the changed orders refresh on the board.

---

## :fontawesome-solid-shield-halved: Access & Permissions

The buttons live on the Dispatch board, so the same roles apply.

| Role | Access |
|------|--------|
| :fontawesome-solid-user-tie: **Admin** | Full access |
| :fontawesome-solid-user-tie: **Manager** | Full access |
| :fontawesome-solid-headset: **Dispatch** | Full access |
| :fontawesome-solid-headset: **Customer Service** | Same as Dispatch |
| :fontawesome-solid-file-invoice-dollar: **Accountant**, **Customer**, **Driver**, other roles | No access -- they cannot open the Dispatch board |

**Which buttons you see** depends on your company's [add-ons](add-ons-and-options.md):

| Button | Shown when | Opens |
|--------|-----------|-------|
| :fontawesome-solid-train:{ .text-danger } **CN Tracking** | CN tracking add-on is enabled | **Shipments Tracking for Canadian National** |
| :fontawesome-solid-ship:{ .text-primary } **Port Tracking** | Port of Montreal (Termont) **or** MGT (Racine/Cast) tracking add-on is enabled | **Shipments Tracking for Port of Montreal** |

If an add-on is not enabled, its button's spot in the header is left empty.

**How to get there:**

- :fontawesome-solid-arrow-right: **Dispatch** :fontawesome-solid-arrow-right: **CN Tracking** or **Port Tracking** (header buttons, to the right of the status buttons)

---

## :fontawesome-solid-list: Which Orders Are Included

Both windows start from your **in-progress** orders -- status **New**, **App. Made** or **Dispatched** -- created on or after the **Order Archive Cutoff Date** in [Settings](application-settings.md), then keep only those whose **pickup terminal** belongs to the source:

| Window | Orders included | Where the data comes from |
|--------|-----------------|---------------------------|
| **CN Tracking** | Pickup terminal is a CN terminal | A **live request** to CN for those container numbers, made when you open the window |
| **Port Tracking** | Pickup terminal is a Termont, Racine or Cast terminal | Tracking data **already stored** in the app from the automatic Termont and MGT checks (see [Container Tracking](container-tracking.md)) |

With [multiple offices](multi-office.md), the list is then limited to the office you are currently working in.

Each order then goes into one of two tables:

- **Main table** -- the source returned data for the order's container.
- **No information table** -- the source returned nothing for it (see [No Information Table](#no-information-table)).

!!! info "CN: up to 200 containers per request"
    Each time you open **CN Tracking**, CN is asked about up to **200** containers.

!!! tip "Port Tracking is as fresh as the last automatic check"
    Port Tracking does not contact the terminals when you open it. It shows what the app stored during its last automatic check, so a container that just changed at the terminal may not be reflected yet.

---

## :fontawesome-solid-table: The Main Table

The heading shows a green badge with the number of orders found, followed by the source name (**Canadian National** or **Port of Montreal**).

### Columns

| Column | What it shows |
|--------|---------------|
| *(checkbox)* | Whether the order is included in **Update Selected**. All rows are checked when the window opens. The checkbox in the header checks or unchecks every row. |
| **Order** | The order status icon (hover for **New Order**, **Appointment Made** or **Order Dispatched**) and the order reference number |
| **Container** | Container number |
| **ETA** | The order's ETA date compared with the source's ETA |
| **LFD** | The order's Last Free Day compared with the source's Last Free Day |
| **Weight** | The order's weight compared with the source's weight |
| **Terminal** | *Port Tracking only.* The terminal section the container is at |
| **Customs** | *Port Tracking only.* The customs description from the terminal |
| **Status** | CN: the CN event name (hover for its full description). Port: a status badge (see below) |

### How values are compared

The **ETA**, **LFD** and **Weight** cells show the order's current value first:

| What you see | Meaning | Changed by Update Selected? |
|--------------|---------|-----------------------------|
| Green value + :fontawesome-solid-check:{ .text-success } | The order already matches the source | No |
| Red value **->** green value | The order differs from the source. The green value is the new one | **Yes** |
| Red **N/A** **->** green value | The order has no value; the source has one | **Yes** -- the field is filled in |
| Value **->** red **N/A** | The source has no value | No -- the order keeps its value |
| Red **N/A** **->** red **N/A** | Neither side has a value | No |
| **Not Available** (orange, Weight column) | The source reported a weight of 0 | No -- the order weight is left alone |

How each field is compared:

- **ETA** and **LFD** are compared by **calendar day** only (time of day is ignored).
- **Weight** is compared as **exact text**: the source value is written as the number followed by its unit, e.g. `24000 KG`. If the order says `24000 kgs` or `24,000 KG`, it counts as different and will be overwritten with the source's format.
    - **CN**: the **net** weight and the unit CN reports.
    - **Port**: the gross weight reported by the terminal, always with the unit **KG**.
- **CN ETA**: the CN ETA is only used when CN gives it for the Montreal (Taschereau) yard. An ETA for any other location is ignored, and the ETA column shows **N/A** on the right side.

### Port status and customs badges

| Badge | Meaning |
|-------|---------|
| **Ready** (green) | The terminal reports the container is available for pickup |
| **In Terminal** (blue) | The container is in the terminal but not yet available for pickup |
| **Departed** (grey) | The container has left the terminal |
| Any other text, or **Unknown** (grey) | The terminal's own visit state, or nothing reported |

The **Customs** column shows the terminal's customs text in **green** when it contains "release", in **orange** otherwise, and a grey **N/A** when the terminal reported nothing.

### Sort order

| Window | Sort order |
|--------|-----------|
| **CN Tracking** | By CN event, in CN's event code order: **De-ramped** first, then **Arrival Transit Location**, **Bad Order**, **Motor Carrier Arrival**, **Arrival at Destination**, and so on through **Ramped**, **Released**, etc. |
| **Port Tracking** | **Ready** first, then **In Terminal**, then **Departed**, then everything else |

---

## :fontawesome-solid-pen-to-square: Updating Orders

### Step-by-step: Update orders from tracking data

1. :fontawesome-solid-arrow-right: Open **CN Tracking** or **Port Tracking** from the Dispatch board.
2. :fontawesome-solid-eye: Look for red values with an arrow (**->**) -- those are the fields that will change.
3. :fontawesome-solid-square-check: Uncheck any row you want to leave untouched. Unchecked rows are not sent at all.
4. :fontawesome-solid-floppy-disk: Click **Update Selected** (it shows **Updating** while saving).
5. :fontawesome-solid-circle-check: The window closes and a message appears at the top of the screen. Orders that were changed refresh on the board.

### What gets changed

For every **checked** row, only fields that differ are sent:

| Order field | CN Tracking | Port Tracking |
|-------------|-------------|---------------|
| **ETA date** | Overwritten with the source ETA when it differs | Overwritten with the source ETA when it differs |
| **Last Free Day (LFD)** | Overwritten when it differs | Overwritten when it differs |
| **Weight** | Overwritten when it differs (not when the source says 0) | Overwritten when it differs (not when the source says 0) |
| **Seal number** | Not changed | Filled in **only if the order's seal number is blank** and the terminal has one |
| **Steamship line** | Not changed | Filled in **only if the order's steamship line is blank** and the terminal has one |

Rows where nothing differs are skipped, even if checked.

!!! info "Seal number and steamship line"
    The Port Tracking table has no seal or steamship line column. If the order has those fields blank and the terminal knows them, **Update Selected** fills them in. Existing values are never overwritten.

!!! danger "Update Selected overwrites what you typed"
    ETA, LFD and weight are **replaced** by the source value for every checked row that differs -- including dates or weights you entered by hand on purpose. Uncheck those rows before clicking **Update Selected**. There is no undo.

### Messages

| Message | When |
|---------|------|
| **Updated** -- *Orders were updated!* (green) | The save went through. This also appears when no row had anything to change |
| **Update Failed** -- *Errors were encountered while updating orders. Please verify the result on 'Track and Trace' page* (red) | An order could not be saved |

!!! tip "Check the result"
    Orders are saved one at a time. To confirm what was saved, reopen the window: rows that still show an arrow were not updated.

---

## :fontawesome-solid-circle-exclamation: No Information Table

Below the main table, a second heading shows a red badge and **Canadian National - No information currently available** (or **Port of Montreal - No information currently available**).

It lists orders for that source that the railway or terminal returned no data for -- for example, the container has not reached the rail network or terminal yet, or the container number is mistyped.

| Column | What it shows |
|--------|---------------|
| **Status** | Order status icon |
| **Order** | Order reference number -- a link that opens the **Orders** list searched for that order, in a new tab |
| **Container** | Container number |
| **Delivery Date** | The order's delivery date |
| **Message** | *No information returned from Canadian National* (or *Port of Montreal*) |
| **Last Status** | The last CN event name stored by the app for this container (for example **Ramped**), if any. Usually blank for port containers |
| **Received At** | The time of that stored CN event, if any. Blank for port containers |

!!! info "Only New orders are listed"
    The table lists **only orders with status New**. App. Made and Dispatched orders are not listed, as the note at the top of the table says. Orders whose container number is blank or **N/A** are also left out.

Orders in this table cannot be updated -- there is nothing to copy. Check the container number on the order, or wait for the source to report the container.

---

## :fontawesome-solid-bell: Alerts Panel (Port Tracking only)

When there are unread Termont or MGT alerts, the Port Tracking window opens with an orange panel at the top headed with the number of alerts shown (for example **1 Alert** or **3 Alerts**). It shows up to the **10 most recent** unread port alerts: an icon for the alert type, the container number, the alert message and how long ago it was raised.

| Icon | Alert type |
|------|-----------|
| :fontawesome-solid-truck:{ .text-success } | Ready for pickup |
| :fontawesome-solid-circle-check:{ .text-success } | Customs released |
| :fontawesome-solid-triangle-exclamation:{ .text-danger } | Last Free Day approaching |
| :fontawesome-solid-right-from-bracket:{ .text-info } | Departed |

!!! warning "Opening Port Tracking marks these alerts as read -- for everyone"
    As soon as the panel is displayed, the alerts shown in it are marked **read** for the whole company, not just for you. They disappear from the unread count on the :fontawesome-solid-bell: **Alerts** button and from the unread alerts for every other user.

    The alerts themselves are not deleted -- you can still find them on the [Container Alerts](container-alerts.md) page, whose list covers the last 90 days.

CN alerts are never shown in this panel, and the CN Tracking window has no alerts panel.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the CN Tracking or Port Tracking button

!!! info "Solution"
    Each button only appears when the matching tracking add-on is enabled for your company (CN for **CN Tracking**; Termont or MGT for **Port Tracking**). You also need access to the Dispatch board (Admin, Manager, Dispatch or Customer Service). Ask UTX support if the add-on should be turned on.

### :fontawesome-solid-magnifying-glass: An order is missing from both tables

!!! info "Solution"
    Check that:

    - The order status is **New**, **App. Made** or **Dispatched** (Completed orders are never included).
    - The order's **pickup terminal** is a CN terminal (CN Tracking) or a Termont, Racine or Cast terminal (Port Tracking).
    - With multiple offices, you are working in the order's office.
    - The order was created on or after the **Order Archive Cutoff Date** in [Settings](application-settings.md).

    An App. Made or Dispatched order with no tracking data is not listed in the no information table.

### :fontawesome-solid-weight-hanging: The weight keeps showing as different

!!! info "Solution"
    Weight is compared as exact text, including the unit. `24000 KG` and `24000 kgs` are treated as different. Click **Update Selected** once to store the source's format; after that the row shows a check mark.

### :fontawesome-solid-clock: Port Tracking shows old information

!!! info "Solution"
    Port Tracking uses data stored by the automatic terminal checks, not a live lookup. Wait for the next check. The container's own tracking popup on the order row reads the same stored data, and its **Updated ... ago** line shows when that container was last refreshed (see [Container Tracking](container-tracking.md)).

### :fontawesome-solid-bell-slash: My port alerts disappeared from the Alerts badge

!!! info "Solution"
    Someone (possibly you) opened **Port Tracking**, which marks the alerts shown in its panel as read for everyone. Review them on the [Container Alerts](container-alerts.md) page.

### :fontawesome-solid-triangle-exclamation: I got "Update Failed"

!!! info "Solution"
    Some orders may have saved and others not. Reopen the window: any row still showing a red value and an arrow was not updated. Open that order and save the field by hand to see what needs fixing.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Best Practices"
    - **Scan before you click.** Uncheck rows where you entered an ETA, LFD or weight by hand that you want to keep.
    - **Use CN Tracking at the start of the day** to pick up CN ETA and LFD changes in one pass instead of order by order.
    - **Read the Port alerts panel when it appears** -- once displayed, those alerts are marked read for the whole team.
    - **Work the no information table.** A New order that stays there for days often has a mistyped container number.
