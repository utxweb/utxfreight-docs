# Order Status Workflow

Move an order from **New** to **Completed** with the status buttons, and undo, delete, transfer or view the history of an order from its actions menu.

## :fontawesome-solid-arrows-rotate: Overview

Every order moves through four statuses, one step at a time:

**New** :fontawesome-solid-arrow-right: **App. Taken** :fontawesome-solid-arrow-right: **Dispatched** :fontawesome-solid-arrow-right: **Completed**

- :fontawesome-solid-star: Each order row on the **Orders** list and the **Dispatch** board has a coloured **status button** that opens the modal for the next step: **Make App.**, **Dispatch** or **Complete**.
- :fontawesome-solid-envelope: **Dispatch** and **Complete** send a notification email to the customer. **Make App.** does not.
- :fontawesome-solid-user: Picking a driver does **not** change the status. Only the status buttons do.
- :fontawesome-solid-rotate-left: The caret next to the status button opens the actions menu, with **Reset Order to New**, **Go Back 1 Step**, **Delete Order**, **Transfer to Office** and **View History** (depending on your role and settings).
- :fontawesome-solid-calculator: Once an order is **Completed** or invoiced, its terminal fee and fuel surcharge are no longer recalculated automatically.

<!-- TODO: Screenshot — An order row on the Orders list showing the status label, the coloured status button and the open actions menu -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Orders** (or **Dispatch**) and find the order.
2. Click the gold **Make App.** button, enter the **Client Appointment Date** and **Client Appointment Time**, and click **Submit Appointment**.
3. Click the green **Dispatch** button, review the panels, and click **Dispatch Order**. The customer gets an email.
4. When the work is done, click the dark **Complete** button, upload the signed POD if you have it, and click **Complete Order**. The customer gets an email.
5. Made a mistake? Open the caret menu and use **Go Back 1 Step** or **Reset Order to New**.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Status buttons | Reset / Go Back | Delete Order | Transfer to Office | View History |
|------|----------------|-----------------|--------------|--------------------|--------------|
| :fontawesome-solid-user-tie: **Admin** | All | Yes | Yes | Yes (multi-office) | Yes (if order history is turned on) |
| :fontawesome-solid-user-tie: **Manager** | All, for orders in their offices | Yes | Yes | Yes (multi-office) | Yes (if order history is turned on) |
| :fontawesome-solid-headset: **Dispatch** | All, for orders in their offices | Yes | Yes | Yes (multi-office) | Only with **Can manage rates?** |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Depends on your installation (see below) | Depends on your installation | Depends on your installation | Depends on your installation (multi-office) | Depends on your installation |
| :fontawesome-solid-user: **Customer** | No — sees the grey **Actions** button | No | No | No | No |

!!! info "Accountants"
    Accountants see the **Complete** button on **Dispatched** orders in their offices. Whether they can actually use it, and whether they can make appointments, dispatch, reset, step back, delete, transfer orders and view their history, depends on whether order management is turned on for accountants in your UTX Freight installation. Contact UTX support if you are unsure.

!!! info "The grey Actions button"
    If you do not have permission for the next step (or the order is already **Completed**), the status button is replaced by a grey **Actions** button. It does nothing by itself. Use the caret next to it to open the actions menu.

**Where to find it:**

- :fontawesome-solid-arrow-right: **Orders** — status button and caret menu in the actions column of each row
- :fontawesome-solid-arrow-right: **Dispatch** — same button and menu on each order line

---

## :fontawesome-solid-list-check: Statuses and Colours

### Status labels

Each order row shows a status label with an icon. Hover over it to see its name.

| Status | Label hover text | Icon | Label colour | Filter tab on Orders |
|--------------------|------------------|------|--------------|----------------------|
| **New** | New Order | :fontawesome-solid-star: star | Red | **New** |
| **App. Taken** | Appointment Made | :fontawesome-solid-clock: clock | Orange / yellow | **App. Made** |
| **Dispatched** | Order Dispatched | :fontawesome-solid-road: road | Green | **Dispatched** |
| **Completed** | Order Completed | :fontawesome-solid-check: check | Grey | **Completed** |

!!! info "App. Taken vs. App. Made"
    It is the same status. Most screens, including the **Go Back 1 Step** toast, call it **App. Taken**. The filter tab and the counter at the top of the **Orders** list call it **App. Made**, the status filter icon on the **Dispatch** board shows **App Made** when you hover over it, and the label hover text says **Appointment Made**.

### Status buttons

The button on each row always shows the **next** step, and its colour tells you which step that is.

| Current status | Button | Button colour | Opens |
|----------------|--------|---------------|-------|
| **New** | **Make App.** | Gold | Appointment modal |
| **App. Taken** | **Dispatch** | Green | Dispatch modal |
| **Dispatched** | **Complete** | Dark (black) | Complete modal |
| **Completed** | **Actions** | Grey | Nothing (use the caret menu) |

---

## :fontawesome-solid-clock: Step 1 — Make App.

Records the client appointment and moves the order from **New** to **App. Taken**.

1. Click the gold **Make App.** button on the order.
2. The modal title shows **Order** + the order number and description (and the office name in multi-office setups).
3. In the **Appointment Information** panel, fill in:

    | Field | Required | Notes |
    |-------|----------|-------|
    | **Client Appointment Date** | Yes | Pre-filled with the order's delivery/pickup date if no appointment exists yet. The **Delivery Date** is automatically updated to match this date. |
    | **Client Appointment Time** | Yes | Time picker (24-hour, HH:MM). |
    | **Special Note** | No | Comment which appears under the status for each order and on the driver's phone. |

4. Click **Submit Appointment**.

The toast **Appointment Made!** confirms the change. If a value is invalid, you see **Appointment not made!** — "The appointment failed - you submitted invalid information."

!!! warning "No email to the customer"
    The modal says it plainly: **Making appointment DOES NOT send a notification email to the customer.** If the customer needs to know the appointment, contact them separately.

<!-- TODO: Screenshot — The Make App. modal with Client Appointment Date, Client Appointment Time and Special Note -->

---

## :fontawesome-solid-road: Step 2 — Dispatch

Moves the order from **App. Taken** to **Dispatched**.

1. Click the green **Dispatch** button on the order.
2. The modal title shows **Dispatch Order** + the order number, description and container number.
3. Review or update the panels:

    | Panel | Who sees it | What's in it |
    |-------|-------------|--------------|
    | **Container Information** (**Delivery Information** for Dry Van orders) | Everyone who can dispatch | Delivery date (**Pickup date** for Export, International Export and Transfer orders), seal number and **Special Note**; RV number and customs release for Import orders; for Dry Van orders, pickup date, delivery date, **Special Note** and broker (no seal number) |
    | **Order Income** | Everyone who can dispatch | Base rate and charges (see [Order Charges & Expenses](order-charges-and-expenses.md)) |
    | **Order Expenses** | Admins, managers, and dispatchers with **Can manage rates?** | Expenses for the order, with **(+) Add another** |
    | **Order Legs** | Admins, managers and dispatchers | Legs of the move, with **(+) Add another** (Transfer orders show their legs read-only) — see [Order Legs & Move Locations](order-legs-and-move-locations.md) |

4. Click **Dispatch Order**.

The toast **Order Dispatched!** confirms the change. If a value is invalid, you see **Dispatching failed!** — "The dispatching failed - you submitted invalid information."

!!! info "Email sent on dispatch"
    The modal warns: *When you dispatch this order, a notification email will automatically be send to the customer.* The email subject is **Order #&lt;order number&gt; is now dispatched**, and it goes to the customer contact on the order — **only if that person has Email Notifications turned on** in their profile (see [People & Invitations](people-and-invitations.md)). If sending fails, the toast includes **Sending email failed!**

!!! tip "Picking a driver doesn't dispatch"
    Assigning a driver (for example by clicking the driver name on the **Dispatch** board) only saves the driver. The order stays at its current status until someone clicks **Dispatch** and **Dispatch Order**.

<!-- TODO: Screenshot — The Dispatch modal with the Container Information, Order Income, Order Expenses and Order Legs panels -->

---

## :fontawesome-solid-check: Step 3 — Complete

Moves the order from **Dispatched** to **Completed**.

1. Click the dark **Complete** button on the order.
2. The modal title shows **Complete Order** + the order number, description and container number.
3. Review or update the panels:

    | Panel | Who sees it | What's in it |
    |-------|-------------|--------------|
    | **Container Information** | Everyone who can complete | Dates (ETA, pickup, delivery, storage, demurrage, grounded, waybill), container size, steamship line, seal number, **Time In** / **Time Out**, **Cargo Weight**, **Packages**, **Hazmat**, **Damaged**, **Off-Hire**, **Scale**, pickup/delivery notes and **Special Note** (fields vary by order type) |
    | **Order Income** | Everyone who can complete | Base rate and charges |
    | **Order Expenses** | Admins, managers, and dispatchers with **Can manage rates?** | Expenses, with **(+) Add another** |
    | **Order Legs** | Admins, managers and dispatchers | Legs, with **(+) Add another** (read-only for Transfer orders) |
    | **Order Documents** | Everyone who can complete | **Signed POD file in .pdf format** upload |

4. Click **Complete Order**.

The toast **Order Completed!** confirms the change. If a value is invalid, you see **Completing order failed!** — "Completing the order failed - you submitted invalid information."

### Uploading the signed POD

In the **Order Documents** panel, choose a PDF in **Signed POD file in .pdf format**.

- If a signed POD is already attached, the hint reads *Uploading a new file will replace the existing PDF: &lt;file name&gt;*, and a **Check to remove the existing PDF** box lets you remove it.
- Once a signed POD is attached, a PDF icon appears in the order row on the **Orders** list so you can open it.

See [Order Documents & POD](order-documents-and-pod.md) for other document types.

!!! info "Email sent on completion"
    The modal warns: *When you complete this order, a notification email will automatically be send to the customer.* The subject is **Order Completed for order #&lt;order number&gt;**, sent to the customer contact on the order **only if they have Email Notifications turned on**.

<!-- TODO: Screenshot — The Complete modal with the Order Documents panel open showing the signed POD upload -->

---

## :fontawesome-solid-calculator: When Automatic Charges Stop Recalculating

When you save an order with **Edit Order** or through the Make App., Dispatch and Complete modals, UTX Freight recalculates the automatic charges and the order total:

- **Terminal fee** (Import and Export orders) — from the terminal's default rate or the customer's special terminal rate
- **Fuel surcharge** (Import, Export and Transfer orders, when the fuel surcharge add-on is on and **Auto compute fuel surcharges for this order** is enabled) — see [Fuel Surcharge](fuel-surcharge.md)

!!! warning "Completed and invoiced orders are frozen"
    Once an order is **Completed** or attached to an invoice, its terminal fee and fuel surcharge are **no longer recalculated**. This includes the save that completes the order: the charges keep the values they had while the order was **Dispatched**. Fix terminal or fuel charges **before** you complete, or adjust them manually afterwards. To have them recalculated again, use **Go Back 1 Step** or **Reset Order to New** (and remove the order from its invoice first if it is invoiced), then save the order. Going back or resetting does not recalculate the charges by itself.

---

## :fontawesome-solid-rotate-left: Undoing a Status Change

Both actions are in the caret menu and appear only when the order is **not** already **New**. They are available to admins, managers and dispatchers in the order's office (and to accountants when order management is turned on for them). Neither action recalculates charges or sends an email.

### Go Back 1 Step

Moves the order back one status: **Completed** → **Dispatched** → **App. Taken** → **New**.

1. Open the caret menu and click **Go Back 1 Step**.
2. Confirm in the dialog *Are you sure you want to Go Back One Step for the status of this order?* by clicking **GO BACK ONE STEP**.

Toast: **Order status changed!** — "The orders status was moved to '&lt;new status&gt;'".

When stepping back from **App. Taken** to **New**, the appointment date, appointment time and delivery date are cleared.

!!! info "Orders list only"
    **Go Back 1 Step** is in the actions menu on the **Orders** list. The **Dispatch** board menu has **Reset Order to New** but not **Go Back 1 Step**.

### Reset Order to New

Sends the order straight back to **New** from any status.

1. Open the caret menu and click **Reset Order to New**.
2. Confirm in the dialog *Are you sure you want to Reset the status of this order, it will be set back to NEW?* by clicking **RESET THE STATUS**.

Toast: **Order Reset!** — "The orders status was reset to 'new'".

!!! warning "Reset clears dates"
    **Reset Order to New** clears the **appointment date**, **appointment time** and **delivery date**. You'll need to make the appointment again.

### "Order not updated!"

If the order cannot be saved (for example, it fails a validation such as a blank container number, or a missing terminal on an Import or Export order), the status does **not** change and you see a red toast **Order not updated!** with the reason: "The order was not saved: &lt;errors&gt;." (or "The order could not be saved. Please try again or contact the administrator." when no reason is available). Fix the order with **Edit Order** and try again.

---

## :fontawesome-solid-trash: Delete Order

Available in the **Orders** list caret menu to users who can fully manage the order (admins, managers, dispatchers; accountants only when order management is on for them). It is not on the Dispatch board menu.

1. Open the caret menu and click **Delete Order**.
2. Confirm in the dialog *Are you sure you want to delete this order?* by clicking **DELETE THIS ORDER**.

You return to the page you came from with the message **Order #&lt;order number&gt; was deleted.**

!!! danger "Deleting is permanent"
    Deleting an order also deletes its **legs**, **charges**, **expenses**, **documents** (including PODs) and **container tracking alerts**. This cannot be undone.

!!! warning "Invoiced orders cannot be deleted"
    If the order is on an invoice, **Delete Order** is greyed out. Clicking it shows **INVOICED ORDER** — "This order is invoiced and cannot be deleted. Remove it from the invoice first." See [Invoices](invoices.md).

---

## :fontawesome-solid-right-left: Transfer to Office

Only when **multi-office** is enabled (see [Multi-Office](multi-office.md)), for admins, managers and dispatchers (and accountants when order management is turned on for them) who belong to at least one office other than the one they are working in. It is on both the **Orders** list and the **Dispatch** board menus.

1. Open the caret menu and click **Transfer to Office**.
2. The dialog **Transfer Order #&lt;order number&gt;** asks you to *Select the target office for this order*, and notes: *The order and all its charges will move to the selected office. This action is recorded in the audit trail.*
3. Pick the office and click **Transfer Order** (or **Cancel**).

The row disappears from the current office's list and a toast confirms **Order #&lt;order number&gt; transferred to &lt;office&gt;.** In the target office, the order shows a blue **Transferred** badge under its status; hover over it to see which office it came from.

- **Transfer (Invoiced)** — greyed out when the order is on an invoice (hover text: *Cannot transfer an invoiced order*).
- The status does not change when you transfer an order.
- You can only transfer to offices you belong to.

---

## :fontawesome-solid-clock-rotate-left: View History

Opens the **Order History** modal with the list of changes made to the order.

- The menu item only appears when order history is turned on for your account. Ask UTX support if you want it turned on.
- Admins and managers see it. Dispatchers see it only if **Can manage rates?** is checked in their profile. Accountants see it only when order management is turned on for them.

---

## :fontawesome-solid-bell: Summary — Toasts and Emails

| Action | Success toast | Failure toast | Customer email |
|--------|---------------|---------------|----------------|
| **Submit Appointment** | Appointment Made! | Appointment not made! | None |
| **Dispatch Order** | Order Dispatched! | Dispatching failed! | *Order #X is now dispatched* (if Email Notifications on) |
| **Complete Order** | Order Completed! | Completing order failed! | *Order Completed for order #X* (if Email Notifications on) |
| **Go Back 1 Step** | Order status changed! | Order not updated! | None |
| **Reset Order to New** | Order Reset! | Order not updated! | None |
| **Delete Order** | Order #X was deleted. | — | None |
| **Transfer Order** | Order #X transferred to &lt;office&gt;. | An error message explaining why | None |

See [Notifications & Emails](notifications-and-emails.md) for all emails UTX Freight sends.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-ban: I only see a grey Actions button

!!! info "Solution"
    Either the order is already **Completed**, or your role does not allow the next step. Customers always see **Actions**. Accountants see **Complete** on dispatched orders, but whether they can use it, **Make App.** or **Dispatch** depends on your installation. Ask an admin or manager to move the order.

### :fontawesome-solid-user: I assigned a driver but the order is still App. Made

!!! info "Solution"
    Assigning a driver never changes the status. Click the green **Dispatch** button and then **Dispatch Order**.

### :fontawesome-solid-envelope: The customer didn't receive the dispatch or completion email

!!! info "Solution"
    The email only goes to the customer contact on the order, and only if their **Email Notifications** setting is on. Check the contact under the customer's people list. Remember that **Make App.** never sends an email.

### :fontawesome-solid-gas-pump: The fuel surcharge or terminal fee is wrong on a completed order

!!! info "Solution"
    Automatic charges are frozen once the order is **Completed** or invoiced. Correct the charge manually, or use **Go Back 1 Step** to return the order to **Dispatched**, save it so the charges recalculate, and complete it again. Invoiced orders must be removed from the invoice first.

### :fontawesome-solid-trash: Delete Order is greyed out

!!! info "Solution"
    The order is on an invoice. Remove it from the invoice first, then delete it.

### :fontawesome-solid-triangle-exclamation: "Order not updated!" when resetting or going back

!!! info "Solution"
    The order has invalid data (for example a blank container number, or a missing terminal on an Import or Export order). Open **Edit Order**, fix the field named in the message, then try again.

### :fontawesome-solid-clock-rotate-left: I can't find View History

!!! info "Solution"
    Order history must be turned on for your account (ask UTX support), and dispatchers also need **Can manage rates?** checked in their profile.

---

!!! tip "Best Practices"
    - Check the terminal fee and fuel surcharge **before** clicking **Complete Order**, since they stop recalculating afterwards.
    - Upload the signed POD in the **Complete** modal so it's ready when you invoice.
    - Prefer **Go Back 1 Step** over **Reset Order to New** when you only need to undo the last step — reset clears the appointment and delivery dates.
    - Make sure the customer contact has **Email Notifications** turned on if they expect dispatch and completion emails.
