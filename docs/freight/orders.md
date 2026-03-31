# Orders Management

Create, track, and manage freight orders from creation through delivery and invoicing.

## :fontawesome-solid-truck: Overview

Orders are the core of UTX Freight. Every shipment — whether it is a container import, export, transfer, or dry van delivery — starts as an order. From the **Orders** page you can:

- :fontawesome-solid-plus: **Create** new orders across five order types
- :fontawesome-solid-magnifying-glass: **Search** by company, container number, PO#, or reference number
- :fontawesome-solid-filter: **Filter** by status, terminal, container status, and tags
- :fontawesome-solid-pencil: **Edit** order fields inline or via the edit form
- :fontawesome-solid-copy: **Duplicate** orders for batch processing
- :fontawesome-solid-file-export: **Export** orders to CSV
- :fontawesome-solid-truck: **Assign equipment** and dispatch to drivers

<!-- TODO: Screenshot — The Orders list page showing status badges at top, filter tabs, and a few order rows -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Orders** from the left menu.
2. Click **Create a new order**.
3. Select the **order type** (Import, Export, Transfer, etc.).
4. Fill in the customer, terminal, and container details.
5. Click **Submit**.

The order is created with status **New**. From here you can schedule an appointment, assign a driver, and dispatch.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-tie: **Admin / Manager** | Full access — create, edit, delete, dispatch, invoice |
| :fontawesome-solid-headset: **Dispatch** | Create, edit, dispatch orders |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | View all orders, complete dispatched orders |
| :fontawesome-solid-user: **Customer** | View their own orders, create new orders |

---

## :fontawesome-solid-list: Order Types

UTX Freight supports five order types:

| Type | Description |
|------|-------------|
| **Container Import** | Container arrives at a terminal and is delivered to a customer |
| **Container Export** | Empty container picked up from customer and delivered to a terminal |
| **Transfer** | Terminal-to-terminal move (no customer delivery address) |
| **Dry Van** | Ground shipment — pickup from one location, deliver to another |
| **International Export** | Export order with eBill of Lading support |

---

## :fontawesome-solid-plus: Creating an Order

1. Click **Create a new order** on the Orders page.
2. **Select the customer** — choose the company and contact person placing the order.
3. **Enter the reference number** (optional).
4. **Select the order type** — Container Import, Export, Transfer, Dry Van, or International Export.

### Container Information

| Field | Description |
|-------|-------------|
| **Pick-up terminal name** | The terminal where the container is picked up |
| **Container #** | The container number |
| **Booking #** | Booking reference number |
| **Steamship line** | The shipping line |
| **Vessel** | Vessel name |
| **Voyage** | Voyage number |
| **Pickup number** | Terminal pickup number (Import orders) |
| **Pickup date** | Scheduled pickup date |

### Delivery Address

| Field | Description |
|-------|-------------|
| **Company Name** | Delivery company (shipper/receiver) |
| **Delivery Address** | Street address for delivery |
| **Postal Code / Zip** | Postal or ZIP code |
| **Contact Person** | Contact name at delivery location |
| **Comments** | Delivery instructions |
| **Purchase Order (P.O.)** | Customer's PO number |

### Goods Information

| Field | Description |
|-------|-------------|
| **Container size** | Container size (20', 40', 40H, 45', 53', etc.) |
| **Packages** | Number of packages (Export) |
| **Weight** | Cargo weight |
| **Equipment** | Assigned chassis or trailer |
| **Hazardous content?** | Flag for hazmat containers |
| **Customs released** | Whether customs has cleared the container |

<!-- TODO: Screenshot — The order creation form showing the container information and delivery address sections -->

---

## :fontawesome-solid-arrows-rotate: Order Statuses

Every order moves through these statuses:

| Status | Meaning |
|--------|---------|
| **New** | Order created, not yet scheduled |
| **App. Taken** | Appointment made with the terminal or customer |
| **Dispatched** | Driver assigned and dispatched for pickup/delivery |
| **Completed** | Delivery confirmed with signature |

### Special Labels

Orders may also display these badges:

- :fontawesome-solid-fire:{ .text-danger } **HAZMAT** — Hazardous materials flagged
- **OFF-HIRE** — Container marked as off-hire
- **DAMAGED** — Container reported as damaged

---

## :fontawesome-solid-filter: Filtering Orders

The filter bar at the top of the Orders page lets you narrow down the list:

### Status Filters

| Filter | Shows |
|--------|-------|
| **All** | All orders |
| **In Progress** | New + App. Taken + Dispatched |
| **New** | Orders with status New |
| **App. Made** | Orders with appointments scheduled |
| **Dispatched** | Orders dispatched to drivers |
| **Completed** | Delivered orders |
| **Not Invoiced** | Completed orders without an invoice |

### Terminal Filters

For intermodal orders, filter by pickup terminal:

- **CN** — CN Rail (Taschereau)
- **CP** — CP Rail
- **Racine** — Montreal Gateway Terminals (Racine)
- **Cast** — Montreal Gateway Terminals (Cast)
- **Termont** — Port of Montreal

### Container Status Filters

- **Empty @ Yard** / **Full @ Yard**
- **Pre-Pull** / **Inbound**

### Tag Filters

If tagging is enabled, click any **Tag** name to filter by that tag. See [Order Tagging](order-tagging.md) for details.

---

## :fontawesome-solid-pencil: Editing Orders

### Inline Editing

Several fields can be edited directly from the order list without opening the full form:

- **Container #**
- **Chassis #**
- **P/O #**
- **Container Status**
- **Delivery Date**
- **ETA**
- **Storage / Demurrage dates**

Click the field value on the order row to edit it in place.

### Full Edit

Click the order row to open the **Edit Order** modal with all fields available for modification.

<!-- TODO: Screenshot — An order row showing inline-editable fields (container #, chassis #, delivery date) -->

---

## :fontawesome-solid-truck: Equipment Assignment

Each order can have equipment (chassis, trailer, truck) assigned:

1. Click the :fontawesome-solid-truck: **equipment icon** on the order row.
2. The **Equipment Assignment Window** opens showing available equipment.
3. Select the equipment — the **Availability Status** updates in real-time.
4. Confirm the assignment.

For details, see [Equipment](equipment.md).

---

## :fontawesome-solid-copy: Duplicating Orders

Duplicate an order to quickly create multiple copies for the same P/O:

1. Click the **Duplicate** action on the order.
2. Set the **number of copies** (1-100).
3. Select optional fields to copy (Drivers, Equipment, Container Status).
4. Click **Create Orders**.

For full details, see [Order Duplication](order-duplication.md).

---

## :fontawesome-solid-file-export: Exporting Orders

Click **Export** to download the current filtered order list as a **CSV** file. The export includes all visible columns and respects the active filters.

---

## :fontawesome-solid-hashtag: Status Badges

At the top of the Orders page, colored badges show the count of orders in each status:

- **New Orders** — orders not yet scheduled
- **App. Made** — appointments scheduled
- **Dispatched** — currently out for delivery/pickup
- **Total** — total orders matching current filters

For intermodal orders, additional badges show:

- **Empty at Yard** / **Full at Yard** — container yard status counts

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### Can't find an order in the list

!!! info "Solution"
    Check your active filters — you may have a status or terminal filter active. Click **All** to clear filters. If the order is old, it may be past the **archive cutoff date** configured in **Settings**.

### Order is completed but can't be invoiced

!!! info "Solution"
    Only **Completed** orders can be invoiced. If the order shows as Dispatched, it needs to be completed first — either by the driver signing the POD or by manually completing it from the order actions.

---

## Screenshots Needed

!!! info "Screenshots to capture"
    1. **Orders list page** — showing status count badges at top, filter tabs (All / In Progress / New / etc.), and several order rows with data
    2. **Order creation form** — the first step showing customer selection and order type radio buttons
    3. **Order creation form** — container information section with fields filled in
    4. **Inline editing** — an order row showing a field being edited inline (e.g., container # or delivery date)
    5. **Status badges** — close-up of the colored status count badges at the top of the page
