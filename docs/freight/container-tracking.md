# Container Tracking

Real-time container tracking across three terminal sources -- see the status of every container without leaving the app.

## :fontawesome-solid-satellite-dish: Overview

The **Container Tracking** system (also called Track & Trace) automatically monitors your containers across three terminal sources and brings the latest status directly into the app. You do not need to log in to terminal websites or call anyone -- the system does the checking for you.

Here is how it works at a glance:

- :fontawesome-solid-clock: **Updates every 10 minutes** -- the system checks all three terminal sources automatically.
- :fontawesome-solid-train: **CN Rail** -- Canadian National intermodal yard (Taschereau).
- :fontawesome-solid-ship: **Termont** -- Port of Montreal, Sections 52 (Viau) & 68.
- :fontawesome-solid-ship: **MGT (Racine/Cast)** -- Montreal Gateway Terminals, Sections 62 & 77.
- :fontawesome-solid-bell: **Automatic alerts** -- you get notified when a container is ready for pickup, customs is released, the Last Free Day is approaching, or the container has departed.
- :fontawesome-solid-wand-magic-sparkles: **Auto-fills order fields** -- seal number, weight, steamship line, container size, and customs released status are filled in automatically when tracking data is available.

<!-- TODO: Add screenshot - The Container Tracking modal showing real-time status for a container at the Port of Montreal -->

---

## :fontawesome-solid-bolt: Quick Start

Already know how tracking works? Here is the fastest path to checking a container:

1. Go to :fontawesome-solid-arrow-right: **Orders** from the main menu.
2. Find the order with the container you want to check.
3. Click the :fontawesome-solid-train: **tracking icon** (train or ship) on that order's row.
4. The tracking modal opens with the latest status.

That's it -- no terminal logins, no phone calls. The status is pulled automatically every 10 minutes.

!!! tip "Tip"
    The tracking icon only appears on orders that have a **container number** and a **pickup terminal** matching one of the three supported sources (CN Rail, Termont, or MGT). If you don't see the icon, check that the order has both fields filled in correctly.

---

## :fontawesome-solid-shield-halved: Access & Permissions

Container Tracking is available to any user who can view orders. There are no special permissions required beyond normal order access.

| Role | Access Level |
|------|-------------|
| :fontawesome-solid-warehouse: **Warehouse** | Full access |
| :fontawesome-solid-user-tie: **Manager** | Full access |
| :fontawesome-solid-headset: **Dispatch** | Full access |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Full access |

**How to get there:**

- :fontawesome-solid-arrow-right: **Tracking modal:** Click the tracking icon on any order row in the Orders list.
- :fontawesome-solid-arrow-right: **Alerts dashboard:** From the left menu, click **Container Tracking** :fontawesome-solid-arrow-right: **Alerts**.

!!! warning "Can't find Container Tracking?"
    If you don't see the **Container Tracking** menu item, your company may not have the tracking add-on enabled. Contact your administrator to enable it.

---

## :fontawesome-solid-magnifying-glass: Checking a Container

To check the real-time status of a container, click the **tracking icon** on the order row. The icon tells you which terminal source the container is tracked at:

| Icon | Terminal Source | What It Means |
|------|---------------|---------------|
| :fontawesome-solid-train: Red train | **CN Rail** | Container is at the CN intermodal yard (Taschereau) |
| :fontawesome-solid-ship: Blue ship | **Termont** | Container is at Port of Montreal (Sections 52/68) |
| :fontawesome-solid-ship: Orange ship | **MGT (Racine/Cast)** | Container is at Montreal Gateway Terminals (Sections 62/77) |

### Step-by-step: Check a container

1. :fontawesome-solid-arrow-right: Go to **Orders** from the main menu.
2. :fontawesome-solid-magnifying-glass: Find the order by searching for the order number or container number.
3. :fontawesome-solid-arrow-pointer: Click the **tracking icon** (train or ship) on the right side of the order row.
4. :fontawesome-solid-window-restore: The **tracking modal** opens showing the latest status from the terminal.

<!-- TODO: Add screenshot - An order row showing the tracking icon (train icon for CN Rail) on the right side -->

!!! info "When does the tracking icon appear?"
    The tracking icon only appears when:

    - The order has a **container number** entered
    - The order has a **pickup terminal** that matches one of the three supported sources
    - The tracking add-on for that source is **enabled** on your account

---

## :fontawesome-solid-window-restore: Understanding the Tracking Modal

When you click the tracking icon, a modal opens showing everything the system knows about that container. The modal looks different depending on which terminal source the container is tracked at.

### :fontawesome-solid-train: CN Rail Modal

<!-- TODO: Add screenshot - The CN Rail tracking modal showing a blue header (in transit) with CLM status, container details, and key dates -->

**Header color tells you the status at a glance:**

| Header Color | Meaning |
|-------------|---------|
| :fontawesome-solid-circle:{ .text-info } **Blue** | Container is in transit or at the yard (not yet de-ramped) |
| :fontawesome-solid-circle:{ .text-success } **Green** | Container is **de-ramped** -- off the train and available for pickup |

**What you will see inside:**

- **CLM Status** -- The CN Rail status code (e.g., "De-ramped" means it is off the train and ready).
- **Status & Location** -- Where the container is, the last event, and the destination.
- **Customs** -- Whether customs has released the container or if there is a hold.
- **Container Details** -- Equipment type, size, weight, and whether it is full or empty.
- **Key Dates** -- The **Destination ETA** and **Last Free Day** (LFD). If the LFD has expired, it is highlighted in red.
- **Audit History** -- A log of all status changes the system has recorded.

!!! tip "What does De-ramped mean?"
    **De-ramped** is the key status to watch for on CN Rail containers. When you see a green header with "DE-RAMPED / AVAILABLE", that means you can dispatch a driver to pick it up.

### :fontawesome-solid-ship: Termont / MGT Modal

<!-- TODO: Add screenshot - The Termont tracking modal showing a green header (ready for pickup) with customs status, carrier timeline, and key dates -->

**Header color tells you the status at a glance:**

| Header Color | Meaning |
|-------------|---------|
| :fontawesome-solid-circle:{ .text-success } **Green** | Container is **READY FOR PICKUP** |
| :fontawesome-solid-circle:{ .text-danger } **Red** | Container is **NOT AVAILABLE FOR PICKUP** (on hold or not yet cleared) |

**What you will see inside:**

- **Status & Availability** -- The terminal section and customs status.
- **Customs** -- Shows whether customs has released the container. If there is a hold, an orange warning bar appears at the top.
- **Container & Vessel** -- Shipping line, vessel name, voyage number, origin, and container size.
- **Carrier Timeline** -- Shows the **IN** (vessel arrival) and **OUT** (carrier pickup) dates and times.
- **Key Dates** -- The **Destination ETA** and **Last Free Day** (LFD). Expired LFDs are highlighted in red.
- **Audit History** -- A log of all status changes.

!!! warning "Orange warning bar = hold in effect"
    If you see an **orange warning bar** at the top of the modal saying something like "Hold" or "Customs Hold", the container cannot be picked up yet. Wait for the hold to be released before dispatching a driver.

---

## :fontawesome-solid-palette: Color Guide

The tracking system uses a consistent color scheme across the modal, the alerts dashboard, and the LFD table. Here is what each color means:

| Color | Meaning | Where You See It |
|-------|---------|-----------------|
| :fontawesome-solid-circle:{ .text-success } **Green** | Available for pickup, customs released, good news | Modal header, alert icons, LFD status |
| :fontawesome-solid-circle:{ .text-danger } **Red** | Not available, LFD expired, urgent action needed | Modal header, expired LFD rows, unread alert count |
| :fontawesome-solid-circle:{ .text-info } **Blue** | CN Rail tracking, customs released (informational) | CN modal header, customs released alert badge |
| :fontawesome-solid-circle:{ .text-warning } **Orange** | Customs hold, LFD approaching (1-2 days left) | Hold warning bar, LFD approaching alert badge, warning LFD rows |
| :fontawesome-solid-circle:{ .text-secondary } **Gray** | Departed, neutral, no data | Departed alert badge, unknown status |

!!! tip "The #1 Rule"
    **Green header = go pick it up.** Whether it is CN Rail (de-ramped) or Termont/MGT (ready for pickup), a green header always means you can dispatch a driver.

---

## :fontawesome-solid-bell: Container Alerts Dashboard

The Alerts Dashboard gives you a bird's-eye view of everything that has changed across all your tracked containers. Instead of checking each container one by one, the dashboard shows you all the important status changes in one place.

**How to get there:**

- :fontawesome-solid-arrow-right: From the left menu, click **Container Tracking** :fontawesome-solid-arrow-right: **Alerts**.

<!-- TODO: Add screenshot - The Container Alerts Dashboard showing integration health cards, summary cards, upcoming LFD table, and alert list -->

### :fontawesome-solid-table-cells-large: Summary Cards

At the top of the dashboard, five clickable cards show alert counts by type. Click any card to filter the alert list below.

| Card | Color | What It Means |
|------|-------|--------------|
| **Unread** | Red | Total alerts you have not seen yet |
| :fontawesome-solid-triangle-exclamation: **LFD Approaching** | Orange | Containers whose Last Free Day is within 2 days |
| :fontawesome-solid-truck: **Ready for Pickup** | Green | Containers that are off the train or cleared at the terminal |
| :fontawesome-solid-circle-check: **Customs Released** | Blue | Containers where customs has just cleared |
| :fontawesome-solid-right-from-bracket: **Departed** | Gray | Containers that have left the terminal |

### :fontawesome-solid-tags: Alert Types Explained

| Alert Type | Icon | What Happened | What You Should Do |
|-----------|------|--------------|-------------------|
| **Pickup Ready** | :fontawesome-solid-truck: | Container is off the train (CN) or cleared for pickup (Termont/MGT) | Dispatch a driver |
| **Customs Released** | :fontawesome-solid-circle-check: | Customs has cleared the container | If customs was the last blocker, dispatch a driver |
| **LFD Approaching** | :fontawesome-solid-triangle-exclamation: | Last Free Day is today, tomorrow, or the day after | Schedule pickup now to avoid demurrage charges |
| **Departed** | :fontawesome-solid-right-from-bracket: | Container has left the terminal | No action needed |

!!! warning "LFD alerts only fire once"
    The **LFD Approaching** alert fires once per container and will **not** repeat for an already-expired LFD. If you miss it, check the Upcoming Last Free Days table for expired containers.

### :fontawesome-solid-list: Reading the Alert List

Each alert in the table shows:

| Column | What It Shows |
|--------|-------------|
| **Icon** | Color-coded icon matching the alert type |
| **Source** | Which terminal (CN Rail, Termont, or MGT) |
| **Container** | The container number -- click it to open the tracking modal |
| **Type** | A colored badge showing the alert type |
| **Message** | A plain-text description of what changed |
| **Order** | The order reference number -- click it to open the order |
| **When** | Date and time the alert was created |

Unread alerts appear in **bold** with a red **NEW** badge. Once you have reviewed the alerts, click **Mark All Read** to clear the bold formatting and badges.

!!! info "Mark All Read is safe"
    Marking alerts as read does **not** delete them. They stay in the list for reference -- only the bold text and NEW badge are removed.

---

## :fontawesome-solid-calendar-xmark: Upcoming Last Free Days

The **Upcoming Last Free Days** table appears on the Alerts Dashboard when any container has an LFD within the next 7 days. This is your go-to section for avoiding demurrage charges.

<!-- TODO: Add screenshot - The Upcoming Last Free Days table showing containers with color-coded urgency rows -->

### :fontawesome-solid-palette: Row Color Coding

| Row Color | Meaning | Action |
|-----------|---------|--------|
| :fontawesome-solid-circle:{ .text-danger } **Red** | LFD has **expired** -- demurrage charges are now accruing | Pick up immediately or contact the terminal |
| :fontawesome-solid-circle:{ .text-warning } **Yellow** | LFD is **1-2 days away** | Schedule pickup today |
| No highlight | LFD is **3+ days away** | Plan pickup within the coming days |

### :fontawesome-solid-table-columns: Table Columns

| Column | What It Shows |
|--------|-------------|
| **Source** | Terminal icon and name (CN Rail, Termont, or MGT) |
| **Container** | The container number -- click it to open the tracking modal |
| **Shipping Line** | The steamship/shipping line operating the container |
| **Terminal** | The specific terminal section where the container is located |
| **Last Free Day** | The date by which you must pick up the container to avoid demurrage |
| **Days Left** | A badge showing how many days remain -- EXPIRED (red), TOMORROW (yellow), or a day count |
| **Status** | Whether the container is ready for pickup or still pending |

!!! danger "Critical: Expired LFD = Demurrage"
    **Demurrage charges start the day after the Last Free Day expires.** If you see a red EXPIRED badge, that container is already costing you money every day it sits at the terminal. Take action immediately.

---

## :fontawesome-solid-heart-pulse: Integration Health

At the top of the Alerts Dashboard, you will see **Integration Health** cards -- one for each terminal source your account tracks. These cards tell you whether the system is successfully pulling data from each terminal.

<!-- TODO: Add screenshot - Integration Health cards showing CN Rail (green border, healthy), Termont (green border, healthy), and MGT (red border, stale) -->

| Border Color | Meaning |
|-------------|---------|
| :fontawesome-solid-circle:{ .text-success } **Green border** | Data was pulled **within the last 30 minutes** and the pull was successful. Everything is up to date. |
| :fontawesome-solid-circle:{ .text-danger } **Red border** | The last pull was **over an hour ago** or it **failed**. Data may be out of date. |

Each card also shows:

- **Last pull** -- How long ago the system last checked that terminal (e.g., "5 minutes ago").
- **Containers checked** -- How many containers were checked in the last pull.
- **Containers updated** -- How many containers had status changes.

!!! warning "Red border = data may be outdated"
    If you see a **red border** on a health card, it means the data from that terminal may be stale. The system will keep trying to pull data automatically. If the red border persists for more than a few hours, contact your administrator.

---

## :fontawesome-solid-wand-magic-sparkles: Auto-Populated Order Fields

When the system pulls tracking data from Termont or MGT, it can automatically fill in certain fields on your orders. This saves you from manually entering data that the terminal already knows.

The following fields are auto-populated **only if the field is currently blank** on the order:

| Field | Where It Comes From |
|-------|-------------------|
| :fontawesome-solid-lock: **Seal Number** | The seal number reported by the terminal |
| :fontawesome-solid-weight-hanging: **Weight** | The gross weight of the container (in KG) |
| :fontawesome-solid-ship: **Steamship Line** | Matched by name from the terminal's shipping line data |
| :fontawesome-solid-cube: **Container Size** | Matched by size (e.g., 20', 40', 53') from the terminal data |
| :fontawesome-solid-circle-check: **Customs Released** | Automatically set to "Yes" when customs status shows "Released" |

!!! tip "Your data is safe"
    Auto-population **never overwrites** data you have already entered. If a field already has a value, the system leaves it alone. Only blank fields are filled in.

!!! info "Which terminals auto-populate?"
    Auto-population currently works for **Termont** and **MGT (Racine/Cast)** containers. CN Rail containers provide status updates but do not auto-populate order fields.

---

## :fontawesome-solid-envelope: Email Alerts

The system sends a **daily digest email** summarizing all new tracking alerts since the last email. This way, even if you are not logged in, you stay informed about important container status changes.

**What the email includes:**

- :fontawesome-solid-truck: **Pickup Ready** alerts -- containers you can dispatch drivers to pick up.
- :fontawesome-solid-circle-check: **Customs Released** alerts -- containers where customs has just cleared.
- :fontawesome-solid-triangle-exclamation: **LFD Approaching** alerts -- containers with an upcoming Last Free Day.
- :fontawesome-solid-right-from-bracket: **Departed** alerts -- containers that have left the terminal.

Alerts are grouped by type in the email so you can quickly scan for the most important items first.

!!! info "No duplicate emails"
    Each alert is only included in **one email**. Once an alert has been sent in a digest, it will not appear in future emails. Check the Alerts Dashboard in the app for the complete history.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-magnifying-glass: Container not found in the tracking modal

!!! info "Solution"
    If the modal says **"This container number was not found"**, it means the system has not yet received tracking data for this container. This can happen if:

    - The container has not arrived at the terminal yet.
    - The container number on the order is incorrect (check for typos).
    - The container is at a terminal that is not one of the three supported sources.

    Wait for the container to arrive at a supported terminal, or double-check the container number on the order.

### :fontawesome-solid-eye-slash: No tracking icon on an order

!!! info "Solution"
    The tracking icon only appears when **all three conditions** are met:

    1. The order has a **container number** entered.
    2. The order has a **pickup terminal** assigned.
    3. The pickup terminal matches one of the three supported sources (CN Rail, Termont, or MGT).

    If any of these are missing, the tracking icon will not appear. Fill in the missing fields and the icon will show up automatically.

### :fontawesome-solid-circle-exclamation: LFD has expired -- what do I do?

!!! danger "Action Required"
    An expired Last Free Day means **demurrage charges are accruing** on that container. You should:

    1. Dispatch a driver to pick up the container as soon as possible.
    2. If pickup is not possible, contact the terminal to discuss options.
    3. Check the tracking modal for any holds (customs or terminal) that might be preventing pickup.

    The longer the container sits past its LFD, the higher the demurrage charges will be.

### :fontawesome-solid-clock: Data seems stale or outdated

!!! info "Solution"
    The system pulls new data every **10 minutes**. Check the **Integration Health** cards on the Alerts Dashboard:

    - **Green border** = data is fresh (pulled within 30 minutes).
    - **Red border** = last pull was over an hour ago or it failed.

    If a health card shows a red border for an extended period, contact your administrator. The tracking modal also shows "Updated X minutes ago" at the bottom so you can see exactly when that container's data was last refreshed.

### :fontawesome-solid-ban: Customs hold is showing but customs was already released

!!! info "Solution"
    Customs status updates come directly from the terminal and may have a slight delay. If customs was released very recently, wait for the next automatic pull (within 10 minutes). If the hold persists after several pulls, the terminal may still be reporting it -- contact the terminal directly to confirm.

### :fontawesome-solid-lightbulb: Tips for getting the most out of Container Tracking

!!! tip "Best Practices"
    **Check the Alerts Dashboard daily.** It gives you a full picture of all containers that need attention.

    **Watch the LFD table.** Red and yellow rows need immediate action to avoid demurrage.

    **Click container numbers.** Anywhere you see a container number as a link, click it to open the full tracking modal.

    **Use the email digest.** Even when you are away from the app, the daily digest keeps you informed of critical changes.

    **Monitor Integration Health.** If a health card turns red, data from that terminal may be stale -- factor this into your planning.
