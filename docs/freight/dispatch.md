# Dispatch

Manage daily dispatch operations — assign drivers, track deliveries, and monitor equipment from one board.

## :fontawesome-solid-road: Overview

The **Dispatch** page is the daily operations hub for dispatchers and managers. It shows all orders that are scheduled, dispatched, or in progress for the current week, organized by delivery date.

- :fontawesome-solid-calendar-days: **Date tabs** — quickly jump between yesterday, today, tomorrow, or any day of the week
- :fontawesome-solid-filter: **Status filters** — filter by New, App. Made, or Dispatched
- :fontawesome-solid-truck: **Equipment view** — check chassis and trailer availability
- :fontawesome-solid-user: **Driver legs** — see each driver's assignments for the day
- :fontawesome-solid-train: **Container tracking** — check CN Rail, Termont, and MGT status directly from the board
- :fontawesome-solid-share-from-square: **Magic Driver Link** — send drivers a link to auto-login and see their assigned orders

<!-- TODO: Screenshot — The Dispatch board showing date tabs, status filter circles, and order rows with driver assignments -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Dispatch** from the left menu.
2. The board shows **today's dispatched orders** by default.
3. Use the **date tabs** (Yesterday, Today, Tomorrow, Mon-Sun) to view other days.
4. Click the colored **status circles** to filter by New (red), App. Made (yellow), or Dispatched (green).

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-tie: **Admin / Manager** | Full access |
| :fontawesome-solid-headset: **Dispatch** | Full access |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | View only |

**How to get there:**

- :fontawesome-solid-arrow-right: From the left menu, click **Dispatch**

---

## :fontawesome-solid-calendar-days: Date Navigation

The top of the Dispatch board shows day tabs:

| Tab | Shows |
|-----|-------|
| **Yesterday** | Orders from the previous day |
| **Today** | Today's orders (default view) |
| **Tomorrow** | Tomorrow's scheduled orders |
| **Mon – Sun** | Individual day of the week |
| **Any Date** | All orders regardless of date |
| **No Date** | Orders without a scheduled date |

For intermodal orders, additional sort tabs let you organize by:

- **Delivery** — sort by delivery date (default)
- **ETA** — sort by Earliest Time of Arrival
- **LFD** — sort by Last Free Day
- **CUT** — sort by vessel cutoff date

For ground orders:

- **Pickup** — sort by pickup date
- **Delivery** — sort by delivery date

---

## :fontawesome-solid-circle:{ .text-success } Status Filters

Three colored circles at the top of the board filter orders by status:

| Circle | Color | Status |
|--------|-------|--------|
| :fontawesome-solid-circle:{ .text-danger } | Red | **New Orders** |
| :fontawesome-solid-circle:{ .text-warning } | Yellow | **App. Made** |
| :fontawesome-solid-circle:{ .text-success } | Green | **Dispatched** |
| :fontawesome-solid-circle: | Black | **Remove Filters** (show all) |

Click a circle to show only orders in that status. Click the black circle to clear the filter.

---

## :fontawesome-solid-truck: Dispatching an Order

To dispatch an order to a driver:

1. Find the order on the Dispatch board.
2. Select a **Delivery Driver** from the driver dropdown on the order row.
3. The order status changes to **Dispatched**.
4. The driver receives the order on their mobile device (or via Magic Driver Link).

### Assigning Equipment

Click the :fontawesome-solid-truck: **equipment icon** on the order row to open the Equipment Assignment Window. Select the chassis or trailer for the delivery.

---

## :fontawesome-solid-share-from-square: Magic Driver Link

Once an order is **Dispatched** and a **Driver** is selected, a :fontawesome-solid-share-from-square: **Magic Driver Link** icon appears beside the driver name.

- Click the icon to **copy a link** to your clipboard.
- Paste the link into a **messaging app** or **email** and send it to the driver.
- The driver clicks the link to **auto-login** and see all their assigned orders.

<!-- TODO: Screenshot — An order row showing the Magic Driver Link icon next to the driver name -->

---

## :fontawesome-solid-filter: Container Status Filters

For intermodal orders, the Dispatch board shows additional container status filters:

| Filter | Meaning |
|--------|---------|
| **Pre-Pull** | Container is being pre-positioned |
| **Dropped @ Customer** | Container delivered, awaiting unloading |
| **Empty @ Customer** | Unloaded container at customer site |
| **Full @ Customer** | Loaded container ready for pickup |
| **Empty @ Yard** | Empty container at the yard |
| **Full @ Yard** | Full container at the yard |

---

## :fontawesome-solid-train: Container Tracking from Dispatch

Track containers directly from the Dispatch board:

- :fontawesome-solid-train:{ .text-danger } **CN Rail** — click the red train icon
- :fontawesome-solid-ship:{ .text-primary } **Termont** — click the blue ship icon
- :fontawesome-solid-ship:{ .text-warning } **MGT** — click the orange ship icon
- :fontawesome-solid-bell: **Alerts** — click the bell icon to view tracking alerts (with unread count badge)

For full details, see [Container Tracking](container-tracking.md).

---

## :fontawesome-solid-user: Driver Legs

Click the :fontawesome-solid-user: **Legs** icon to view a driver's delivery and pickup assignments for the day. This shows the sequence of stops the driver needs to make.

---

## :fontawesome-solid-magnifying-glass: Searching the Dispatch Board

Use the search box at the top to filter by company name, container number, or driver name.

!!! info "Search scope"
    The search only looks within dispatched orders on the current board. To search across **all** orders, use the search box on the **Orders** page instead.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### Order doesn't appear on the Dispatch board

!!! info "Solution"
    The Dispatch board only shows orders for the **current week** by default. Check that the order has a **delivery date** set within the displayed range. Also verify the status — only orders with status New, App. Taken, or Dispatched appear.

### Driver can't see their orders on mobile

!!! info "Solution"
    Make sure the order is **Dispatched** with the driver assigned. The driver needs to either use the **Magic Driver Link** or log in through the mobile app. Orders only appear on mobile once they are dispatched.

---

## Screenshots Needed

!!! info "Screenshots to capture"
    1. **Dispatch board** — full view showing date tabs (Yesterday/Today/Tomorrow), colored status circles, and order rows with driver assignments
    2. **Container status filters** — the filter buttons showing Pre-Pull, Dropped @ Customer, etc.
    3. **Magic Driver Link** — close-up of an order row showing the share icon next to the driver name
    4. **Date and sort tabs** — showing the day tabs and the Delivery/ETA/LFD/CUT sort options
