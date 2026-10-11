# Creating & Editing Orders

Use the full-page **New order** and **Edit order** form, the **Quick Edit** window and the **View Details** page to enter, change and review an order.

## :fontawesome-solid-file-pen: Overview

There are three places where you work with a single order:

- :fontawesome-solid-plus: **New order / Edit order** — the full-page form. Click **Create a new order** on the **Orders** page, or choose **Edit Order** from an order's action menu. The form adapts to the order type: sections appear, disappear and change their titles when you pick a **Job type**.
- :fontawesome-solid-pen-to-square: **Quick Edit** — a pop-up window opened from an order's action menu on the **Orders** or **Dispatch** page. Use it for day-to-day changes (dates, seal number, charges, expenses, legs) without leaving the list.
- :fontawesome-solid-eye: **View Details** — a read-only summary page of the order (**Order #...**).

Along the way, the form helps you:

- :fontawesome-solid-circle-check: Checks the **container number** against existing orders as soon as you leave the field.
- :fontawesome-solid-address-book: Fills the address from a saved **shipper / receiver** when you search for one, and saves new names you type to the **Shipper / Receiver** list.
- :fontawesome-solid-dollar-sign: Fills the **Base rate** from the delivery city's zone (or the customer's custom zone rate), and adds terminal and fuel charges automatically.
- :fontawesome-solid-lock: Stops you from overwriting changes saved by someone else while you had the full **Edit order** page open.

For the list itself (searching, filtering, statuses), see [Orders Management](orders.md).

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Orders** and click **Create a new order**.
2. *(Staff only)* In **Change Customer**, pick the customer in **Place the order on behalf of**.
3. In **Order Information**, choose the **Job type**. The rest of the form appears.
4. Fill the terminal and address sections, then enter the **Container number\*** (or **Trailer number\*** for a Dry Van Move). Wait for the green check mark.
5. Complete the remaining fields you need and click the submit button at the bottom of the form (**Create Job**).

You land back on the **Orders** list, searched for the new order, with the message **Order #X was successfully created.** The order starts with the status **New**.

<figure markdown>
  ![The New order form for a Container Import, with the customer, job type, pick up terminal, delivery address, container number and rate](../images/getting-started-import-form.png){ width="80%" }
  <figcaption>The New order form for a Container Import</figcaption>
</figure>

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Full form (New / Edit order) | Quick Edit | View Details |
|------|------------------------------|------------|--------------|
| :fontawesome-solid-user-tie: **Admin / Manager** | Create and edit, all sections | Yes, all panels | Yes, including **Administrative Information** |
| :fontawesome-solid-headset: **Dispatch** (and **Customer Service**) | Create and edit, all sections. **Rate**, **Order Expenses** and **Order Legs** need **Can manage rates?** turned on in their user profile | Yes. **Order Expenses** and the rate fields need **Can manage rates?** | Yes, including **Administrative Information** (**Base Rate** and **Total** need **Can manage rates?**) |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Create and edit only if order management by accountants is turned on for your account (ask UTX support). Otherwise, accountants can view orders and complete orders whose status is **Dispatched**. Staff-only sections are not shown | Same limits as the full form (from the **Orders** page) | Yes, without **Administrative Information** |
| :fontawesome-solid-user: **Customer** | Only if customer order entry is turned on for your account (ask UTX support), and only for their own company's orders while they are **New**; staff-only sections are not shown | Same limits as the full form | Yes, their own company's orders, without **Administrative Information** |

**Staff-only sections** of the full form (shown to Admin, Manager and Dispatch only): **Change Customer**, **Administrative information**, **Appointment Information**, **Rate**, **Order Expenses**, **Order Legs** and **Comments**.

!!! warning "Account suspension"
    While your UTX Freight account is suspended, the **Create a new order** button turns red with a :fontawesome-solid-ban: icon and opens a suspension notice instead of the form. Opening the New order page directly sends you back to the **Orders** list. No new orders can be created until the suspension is lifted.

### :fontawesome-solid-route: Where to find each screen

| Screen | How to open it |
|--------|----------------|
| **New order** | **Orders** :fontawesome-solid-arrow-right: **Create a new order** |
| **Edit order** | Order action menu (the arrow next to the order's action button) :fontawesome-solid-arrow-right: **Edit Order** |
| **Quick Edit** | Order action menu :fontawesome-solid-arrow-right: **Quick Edit** (on **Orders** or **Dispatch**) |
| **Documents** (Quick Edit, documents only) | Order action menu :fontawesome-solid-arrow-right: **Documents** |
| **View Details** | Order action menu :fontawesome-solid-arrow-right: **View Details** |

---

## :fontawesome-solid-list-check: The Full Order Form

The **New order** and **Edit order** pages use the same form. Sections appear in this order. Until you choose a **Job type**, only the customer and **Order Information** sections are visible.

### :fontawesome-solid-user: Customer Information / Change Customer

- **Customers** see a read-only **Customer Information** block with their company name, their own name and email, and the company address. The order is always placed under their own login.
- **Staff** see the **Customer Information** block for the order's current customer (on a new order, this is your own login until you save), followed by **Change Customer**:

| Field | Description |
|-------|-------------|
| **Place the order on behalf of** | Searchable list of customer logins, shown as `NAME [ Company ]`. Hint: *You can create an order on behalf of any customer.* If you leave it empty on a new order, the order is placed under your own login. |

When you change the customer, the form:

- recalculates the **Base rate** for the selected delivery city or shipper / receiver (see [Rate](#rate)), and
- selects the customer company's default **Tag / Group** (when tagging is enabled — see [Order Tagging](order-tagging.md)).

### :fontawesome-solid-circle-info: Order Information

| Field | When shown | Description |
|-------|-----------|-------------|
| **Reference number** | Always | Your own or the customer's reference for the order. |
| **Waybill date** | Container Import, when EDI invoicing is enabled | Date picker. |
| **Job type** \* | Always | **Container Import**, **Container Export**, **Container Transfer**, **Dry Van Move** or **International Export** (only the types enabled for your company are listed). |
| **Tag / Group** | When the tagging add-on is enabled | If tags are optional on your account (set by UTX support), the list has a blank choice; otherwise a tag is always selected. |
| **Office** | Multi-office companies | Read-only. Shows the office the order belongs to. |

### :fontawesome-solid-building: Transport Company (Dry Van Move only)

| Field | Description |
|-------|-------------|
| **Transport Company ( broker )** | Companies flagged as brokers. Hint: *Leave blank unless delivered by third party* |

### :fontawesome-solid-warehouse: Pick up Terminal

| Field | Description |
|-------|-------------|
| **Terminal Name** | Active terminals of your office. **Required** for Container Import and Container Export. |

Shown for Container Import, Container Export and Container Transfer. Hidden for Dry Van Move and International Export.

### :fontawesome-solid-location-dot: Pick Up Address (Dry Van Move only)

On a **new** order:

| Field | Description |
|-------|-------------|
| **Search for a shipper / receiver** | Type at least 2 letters of a previously used shipper / receiver and pick it from the list to fill the fields below. |
| **Name**, **Address**, **City**, **Zip**, **Contact** | The pickup location. |
| **Pickup Date** | Shown in this section for Dry Van Moves when you create the order. |
| **Comments** | Pickup instructions. Filled from the shipper / receiver's comments when you use the search. |
| **P.O.** | Purchase order number for the pickup. |

On an **existing** order, the search and address fields are replaced by a **Pickup company** dropdown of active shippers / receivers. **Comments** and **P.O.** stay editable.

### :fontawesome-solid-map-location-dot: Delivery Address

On a **new** order:

| Field | Description |
|-------|-------------|
| **Search for a shipper / receiver** | Type at least 2 letters of the name or city and pick a saved shipper / receiver. Fills **Name**, **Address**, **City**, **Zip**, **Contact**, **Email** and **Comments**. |
| **Name**, **Address**, **City**, **Zip**, **Contact**, **Email** | The delivery (or loading) location. |
| **Delivery Date** | Shown in this section for Dry Van Moves when you create the order. |
| **Comments** | Delivery instructions. |
| **P.O.** | The customer's purchase order number. |

On an **existing** order, the search and address fields are replaced by a **Delivery company** dropdown of active shippers / receivers. **Comments** and **P.O.** stay editable.

Hidden for Container Transfer (terminal-to-terminal move).

!!! info "Rate from the delivery city"
    Choosing a delivery **City** (or a **Delivery company** on an existing order) looks up the city's zone. A notice next to the field shows the zone name and, if you can manage rates, the rate (for example *Custom Rate $...* when the customer has a custom rate for that zone). The **Base rate** is set to that rate. If the city has no zone you see **No ZONE found for this city** and the **Base rate** is set to 0. See [Zones & Cities](zones-and-cities.md).

### :fontawesome-solid-box: Information

| Field | Import | Export | Transfer | Dry Van | Intl Export |
|-------|:------:|:------:|:--------:|:-------:|:-----------:|
| **Container number\*** | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | — | :fontawesome-solid-check: |
| **Trailer number\*** | — | — | — | :fontawesome-solid-check: | — |
| **Last Free Day (LFD)** | :fontawesome-solid-check: | :fontawesome-solid-check: | — | — | :fontawesome-solid-check: |
| **Container size** | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | — | :fontawesome-solid-check: |
| **Damaged** | :fontawesome-solid-check: | — | — | — | — |
| **Equipment type** | — | — | — | :fontawesome-solid-check: | — |
| **Total miles** | — | — | — | :fontawesome-solid-check: | — |
| **Booking number** | — | :fontawesome-solid-check: | :fontawesome-solid-check: | — | :fontawesome-solid-check: |
| **Pickup number** | :fontawesome-solid-check: | — | — | — | — |
| **Reservation number** | :fontawesome-solid-check: | — | — | — | — |
| **Steamship line** | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | — | :fontawesome-solid-check: |
| **Off-Hire** | :fontawesome-solid-check: | — | — | — | — |
| **Search for a vessel** | — | :fontawesome-solid-check: | — | — | — |
| **Vessel** | — | :fontawesome-solid-check: | — | — | — |
| **Earliest Return Date (ERD)** | — | :fontawesome-solid-check: | — | — | — |
| **Cutoff date** | — | :fontawesome-solid-check: | — | — | — |
| **ETA date** | :fontawesome-solid-check: | — | — | — | — |
| **Grounded date** | :fontawesome-solid-check: | — | — | — | — |
| **Storage date** | :fontawesome-solid-check: | — | — | — | — |
| **Demurrage date** | :fontawesome-solid-check: | — | — | — | — |

Two date fields change their label with the order type:

| Order type | First date field | Second date field |
|------------|------------------|-------------------|
| Container Import | **Pickup Date** (after **Pickup number**) | **Delivery Date** (after **Storage date**) |
| Container Export | **Pickup Date** (after **Booking number**) | **Delivery Date** (after **Cutoff date**) |
| Container Transfer | **Pickup Date** (after **Booking number**) | **Delivery Date** |
| Dry Van Move | **Pickup Date** (in **Pick Up Address**) | **Delivery Date** (in **Delivery Address**) |
| International Export | **Pickup Date** | **Delivery Date** |

!!! info "Which date is which"
    On Container Export and Container Transfer orders the two labels are swapped compared with Container Import:

    - The field labelled **Pickup Date** holds the order's *delivery date* (the same field the Import form calls **Delivery Date**). **Quick Edit** shows it as **Pickup date**, and **View Details** shows it as **Delivery date** under **Administrative Information**. The fuel surcharge is based on this date.
    - The field labelled **Delivery Date** holds the order's *pickup date*, which **View Details** shows as **Pickup date** under **Container Information**.

**Search for a vessel** (Container Export) suggests vessel names already used on your office's orders (type at least 2 letters) and copies your pick into **Vessel**.

**Container size** is entered here, in **Information**, not under **Goods**.

### :fontawesome-solid-boxes-stacked: Goods

| Field | Import | Export | Transfer | Dry Van | Intl Export |
|-------|:------:|:------:|:--------:|:-------:|:-----------:|
| **Packages** (hint *Ex.: 12 SKIDS*) | :fontawesome-solid-check: | :fontawesome-solid-check: | — | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Weight** (hint *Ex.: 2669 KGS*) | :fontawesome-solid-check: | :fontawesome-solid-check: | — | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Hazardous** | :fontawesome-solid-check: | :fontawesome-solid-check: | — | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Scale** (**Scale Full**, **Scale Empty**, **Both**) | — | :fontawesome-solid-check: | — | — | — |
| **Equipment** | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **Seal number** | :fontawesome-solid-check: | :fontawesome-solid-check: | — | — | :fontawesome-solid-check: |
| **Customs released** | :fontawesome-solid-check: | — | — | — | — |
| **Goods description** | — | — | — | :fontawesome-solid-check: | :fontawesome-solid-check: |

**Equipment** lists your office's active equipment (for example chassis). See [Equipment](equipment.md).

### :fontawesome-solid-rotate-left: Return Address

| Field | Description |
|-------|-------------|
| **Terminal Name** | Where the container goes back to. |
| **Instructions** | Return instructions. |
| **Return Date** / **Last Return Date** | **Return Date** for Container Import, **Last Return Date** for Container Export. Not shown for Container Transfer. |

Shown for Container Import, Container Export and Container Transfer. Hidden for Dry Van Move and International Export.

### :fontawesome-solid-heading: Section titles by order type

The terminal and address sections are renamed when you pick the **Job type**:

| Order type | Pick up Terminal becomes | Delivery Address becomes | Return Address becomes |
|------------|--------------------------|--------------------------|------------------------|
| **Container Import** | Full container pick up terminal | Container delivery address | Empty container return terminal |
| **Container Export** | Empty container pick up terminal | Empty container loading address | Full container return terminal |
| **Container Transfer** | Empty container pick up terminal | *(hidden)* | Empty container return terminal |
| **Dry Van Move** | *(hidden — uses Pick Up Address)* | Delivery address | *(hidden)* |
| **International Export** | *(hidden)* | Consignee address | *(hidden)* |

### :fontawesome-solid-user-shield: Administrative information (staff only)

| Field | When shown | Description |
|-------|-----------|-------------|
| **Time in** / **Time out** | Export, Transfer, Intl Export | 15-minute steps. |
| **Broker** | Dry Van Move | Brokers of the current office. |
| **Special Note** | Always | See [Special Note](#special-note). |
| **Container status** | Import, Export, Transfer, Intl Export | See [Container Statuses](container-statuses.md). |
| **Signed POD file in .pdf format** | Always | Upload a signed POD. If one exists, the hint names it, uploading replaces it, and **Check to remove the existing PDF** deletes it. See [Order Documents & POD](order-documents-and-pod.md). |

### :fontawesome-solid-calendar-check: Appointment Information (staff only)

Shown only when editing an order whose status is no longer **New**. Fields: **App date** and **App time** (5-minute steps). See [Order Workflow](order-workflow.md).

### :fontawesome-solid-dollar-sign: Rate

Admin and Manager, and Dispatch users with **Can manage rates?** turned on in their user profile (see [Access & Permissions](#access-permissions)).

| Field | Description |
|-------|-------------|
| **Base rate** | Filled automatically from the zone of the delivery city (or the customer's custom rate for that zone). You can overwrite it. |
| **Auto compute fuel surcharges for this order** | **Yes** (default) or **No**. Shown when the fuel surcharge add-on is enabled. See [Fuel Surcharge](fuel-surcharge.md). |
| **Order Charges for Invoice Breakdown** | Extra charges. Click **(+) Add another charge**; picking a **Charge category** fills its default rate. |
| **Total** | Base rate plus charges, updated when you change a rate or add or remove a charge. |

See [Order Charges & Expenses](order-charges-and-expenses.md).

### :fontawesome-solid-receipt: Order Expenses and Order Legs

Admin and Manager, and Dispatch users with **Can manage rates?** turned on.

- **Order Expenses** — click **(+) Add another expense** to record a cost for the order (**Expense category**, **Expense**, **Rate**, **Note**). Picking an **Expense** fills its default rate.
- **Order Legs** — click **(+) Add another leg** to add a move. On an existing Container Transfer the legs are shown read-only.

See [Order Charges & Expenses](order-charges-and-expenses.md) and [Order Legs & Move Locations](order-legs-and-move-locations.md).

### :fontawesome-solid-comment: Comments (staff only)

| Field | Description |
|-------|-------------|
| **Comments** | Hint: *Add any additional information about the order*. Shown on **View Details** under **Administrative Information**. |

At the bottom, click the submit button (**Create Job** on a new order, **Update Job** when editing; it shows **Please wait...** while saving) or **Cancel** to go back to the **Orders** list.

<!-- TODO: Screenshot — Full Edit order form for a Container Export showing the renamed sections (Empty container pick up terminal, Empty container loading address, Full container return terminal) -->

---

## :fontawesome-solid-triangle-exclamation: Validation

| Rule | Details |
|------|---------|
| **Container number / Trailer number is required** | The order cannot be saved without it. |
| **Job type is required** | |
| **Pick up terminal is required for Container Import and Container Export** | Not required for Transfer, Dry Van Move or International Export. |
| **ETA date must be a valid date** | Only checked when a date is entered. |
| **Container number is saved in uppercase** | Spaces at the start and end are removed. `abcd1234567` is saved as `ABCD1234567`. |

If a rule fails, the form is shown again with the error and your entries kept. Nothing is saved.

### :fontawesome-solid-magnifying-glass: Container number duplicate check

When you change the **Container number** (or **Trailer number**) and leave the field, UTX Freight looks for other orders with the same number, in any office (ignoring upper/lower case). When editing, the current order is ignored.

| Indicator | Meaning |
|-----------|---------|
| :fontawesome-solid-circle-check: **Green check mark** | No other order uses this number. |
| :fontawesome-solid-circle-xmark: **Red X** with a **Search Orders** link | One or more orders already use this number. **Search Orders** opens the **Orders** list in a new tab, searched for that number. |

!!! warning "The check is a warning, not a block"
    A red X does not stop you from saving. Click **Search Orders** to make sure you are not creating a duplicate by mistake.

---

## :fontawesome-solid-circle-plus: What Happens When You Create an Order

1. The order gets the next order number (shown as **Order #X**), the status **New**, and today's date as the **Order date**.
2. The order is placed in your current office.
3. **Base rate:** whatever is in the form is kept (normally the zone rate filled by the form). If the Base rate is empty and the customer company has a default rate, that default rate is used.
4. **Terminal fee:** for Container Import (pick up terminal) and Container Export (return terminal), the terminal's rate (or the customer's special rate for that terminal, if one exists) is added as a charge with the note **Computed Terminal Fee**. This needs a charge category set as the default for terminal fees, and a rate above 0. See [Managing Terminals](managing-terminals.md).
5. **Fuel surcharge:** when the fuel surcharge add-on is on and **Auto compute fuel surcharges for this order** is **Yes**, a charge with the note **Computed Fuel Surcharge ...%** (the percentage applied to the **Base rate**) is added for Import, Export and Transfer orders that have a delivery date (see [Which date is which](#information)) with a fuel rate above 0 for that date, unless the customer is exempt. See [Fuel Surcharge](fuel-surcharge.md).
6. **Shippers / receivers:** names typed in **Delivery Address** or **Pick Up Address** are saved to **Shipper / Receiver**. If an entry with the same name and address exists, it is updated with the new city, zip, contact and email; otherwise a new one is created. The order is linked to it. See [Shippers & Receivers](shippers-receivers.md).
7. A **New Order #X from <customer company>** email is sent to the active admins, with the office's managers in copy (only users who receive notifications).
8. You return to the **Orders** list, searched for the new order number, with the message **Order #X was successfully created.**

---

## :fontawesome-solid-pen-to-square: Editing an Order (Full Form)

1. In the order's action menu, click **Edit Order**.
2. Change the fields you need. On an existing order, the address sections use **Pickup company** / **Delivery company** dropdowns instead of the search.
3. Click **Update Job**.

You go back to the page you came from (or the **Orders** list) with **Order #X was successfully updated.** No email is sent to the customer when you save the full form. Terminal fees and the fuel surcharge are recalculated, as long as the order is not completed or invoiced.

!!! info "Shippers / receivers on edit"
    Saving the Edit order form does not add or update entries in **Shipper / Receiver**. Pick an existing entry in **Pickup company** / **Delivery company**, or manage the list in [Shippers & Receivers](shippers-receivers.md).

### :fontawesome-solid-user-lock: Concurrent edits

If another user saved the same order after you opened the Edit order page, your save is refused and you are sent back to a fresh Edit order page with:

> **This order was modified by another user while you were editing. Your changes were NOT saved. Please try again.**

The page now shows the other user's changes. Re-enter your changes and save again.

---

## :fontawesome-solid-window-maximize: Quick Edit

**Quick Edit** opens a window on top of the **Orders** or **Dispatch** list. Who can open it follows the same rules as the full form (see [Access & Permissions](#access-permissions)).

- **Title:** `Edit Order <order #> - <order type> - <container number>`, for example *Edit Order 781039 - Container Import - ABCD1234567*. Multi-office companies also see the office name.
- **Header:** the customer's company name and address, the customer login's name and email, the zone name, and the delivery city.

Below the header, collapsible panels:

| Panel | Who sees it | Contents |
|-------|-------------|----------|
| **Container Information** | Everyone who can edit the order (open by default) | Type-specific fields, see below |
| **Order Income & Billing** | Everyone who can edit the order | Staff: **Customer** with **Place the order on behalf of**. Admin, Manager, and Dispatch with **Can manage rates?**: **Order Charges for Invoice Breakdown** with **Base rate**, rate history (:fontawesome-solid-info:), the **Total**, **Auto compute fuel surcharges for this order** (fuel add-on), and **Additional Charges** with **(+) Add another** |
| **Order Expenses** | Admin, Manager, and Dispatch with **Can manage rates?** | Expenses with **(+) Add another** |
| **Order Legs** | Admin, Manager, Dispatch | Legs with **(+) Add another** (read-only for Container Transfer) |

The **Documents** menu item opens the same window with only the **Order Documents** panel: **Order POD** (**Signed POD file in .pdf format**, **Check to remove the existing PDF**) and **Additional Documents** with **(+) Add document**. See [Order Documents & POD](order-documents-and-pod.md).

### :fontawesome-solid-box-open: Container Information panel fields

| Field | Shown for |
|-------|-----------|
| **Tag / Group** | All types, when the tagging add-on is enabled |
| **Transport Company / Broker** | Dry Van Move |
| **Waybill date**, **Waybill number(reference)** | Import and Export, when EDI invoicing is enabled |
| **ETA date**, **Rv number**, **Grounded date**, **Customs released**, **Storage date**, **Seal number**, **Delivery date**, **Container size**, **Demurrage date**, **Steamship line** | Container Import |
| **Pickup date**, **Steamship line**, **Seal number**, **Container size** | Container Export, International Export, Container Transfer |
| **Pickup date**, **Delivery date** | Dry Van Move |
| **Hazmat** | All types except Transfer |
| **Off-Hire**, **Damaged** | Container Import |
| **Scale** | Container Export |
| **Packages**, **Pickup Notes**, **Delivery Notes**, **Goods Description** | Dry Van Move |
| **Cargo Weight** | All types except Transfer |
| **Time In**, **Time Out** | All types except Dry Van Move |
| **Special Note** | All types (shown to everyone who can open Quick Edit, customers included) |

The container number, terminals and addresses are not editable in Quick Edit. Use **Edit Order** for those.

### :fontawesome-solid-floppy-disk: Saving

Click **Update Order** (or **Close** to discard). The order's row in the list refreshes, and a message appears at the top of the page:

| Result | Message |
|--------|---------|
| Saved | **Order Updated!** — *The order was updated* |
| Not saved | **Update failed!** — *The update failed - you submitted invalid information.* |

Saving recalculates terminal and fuel charges in the same way as the full form. No email is sent to the customer.

<!-- TODO: Screenshot — Quick Edit window for a Container Import with the Container Information panel open -->

---

## :fontawesome-solid-note-sticky: Special Note

The **Special Note** field is in **Administrative information** on the full form (Admin, Manager and Dispatch only) and at the bottom of the **Container Information** panel in Quick Edit (everyone who can open Quick Edit). Its hint reads *Comment which appears under the status for each order and on the drivers phone*. It:

- appears in red under the order number on the **Orders** list (not shown to customers) and on the **Dispatch** list,
- is shown in the driver mobile view for Dry Van Moves and in the yard management mobile view, and
- is printed on the Dry Van **Carrier Confirmation**.

Use it for instructions everyone must see at a glance, such as gate codes or "call before delivery". Use **Comments** for internal notes.

---

## :fontawesome-solid-eye: View Details

**View Details** opens the page **Order #X** with read-only information:

| Section | Fields |
|---------|--------|
| *(Customer)* | Company name, customer login name and email, company address |
| **Order Information** | Order date, Reference #, Type, Pick up terminal |
| **Client Information** | Company name, Address, Zip, Contact information, Instructions, P.O. # (from the delivery address) |
| **Return Address** | Terminal, Instructions, Return date (Container Import) or Last return date (other types) |
| **Container Information** | Container #, Booking #, Steamship line, Pickup #, Pickup date, Vessel, Voyage, Zone |
| **Goods Information** | Container size, Packages, Weight, CBM, Hazardous, Chassis #, RV #, Seal #, Customs released |
| **Administrative Information** *(Admin, Manager, Dispatch only)* | Base Rate and Total (Admin, Manager, and Dispatch with **Can manage rates?**), Appointment date, Appointment time, Delivery date, Comments |

Click **Back** to return to the **Orders** list.

<!-- TODO: Screenshot — View Details page of an order showing Order Information through Administrative Information -->

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I only see Customer Information and Order Information on the New order page

!!! info "Solution"
    The rest of the form stays hidden until you choose a **Job type**. Pick the type and the type-specific sections appear.

### :fontawesome-solid-circle-xmark: The container number shows a red X

!!! info "Solution"
    Another order already uses that number. Click **Search Orders** to see it. If it is a legitimate new move for the same container (for example a later import), you can still save. Otherwise, correct the number.

### :fontawesome-solid-ban: The order will not save

!!! info "Solution"
    Container Import and Container Export orders need a **Terminal Name** in the pick up terminal section. Every order also needs a **Container number** (or **Trailer number** for Dry Van) and a **Job type**.

### :fontawesome-solid-dollar-sign: The Base rate stayed at 0 or shows "No ZONE found for this city"

!!! info "Solution"
    The delivery city is not linked to a zone, so the form set the **Base rate** to 0. Add the city to a zone in [Zones & Cities](zones-and-cities.md), or type the **Base rate** yourself. The customer company's default rate is applied on creation only when the **Base rate** is empty, not when it is 0.

### :fontawesome-solid-user-lock: "This order was modified by another user while you were editing..."

!!! info "Solution"
    Someone saved the order after you opened it. The page has been reloaded with their changes. Re-enter your changes and click **Update Job** again.

### :fontawesome-solid-lock: A customer cannot edit an order or create one

!!! info "Solution"
    Customers can only create and edit orders when customer order entry is turned on for your account (ask UTX support), and only while the order is **New**. Once an appointment is taken or the order is dispatched, it is read-only for them. During an account suspension nobody can create new orders.

### :fontawesome-solid-address-book: A shipper / receiver does not appear in the search

!!! info "Solution"
    The search shows only **active** shippers / receivers of your current office whose name or city contains what you typed, and needs at least 2 letters. Check the entry in [Shippers & Receivers](shippers-receivers.md).

---

!!! tip "Best Practices"
    - Pick the **Job type** first. The form then shows only the fields that matter for that move.
    - Check the green check mark on the container number before you save.
    - Use **Search for a shipper / receiver** instead of retyping addresses. It keeps the Shipper / Receiver list clean and fills the zone rate.
    - Use **Quick Edit** for routine updates and **Edit Order** when you need to change the customer, terminals, addresses or container number.
    - Keep **Special Note** short. Drivers read it on their phone.
