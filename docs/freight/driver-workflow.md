# Driver Mobile App

What Drivers and Brokers see and do on their phone: sign in, open their dispatched orders, collect signatures, and mark containers as returned.

## :fontawesome-solid-mobile-screen-button: Overview

Drivers and Brokers use UTX Freight in their **phone's web browser**. There is no app to install. The site switches to a simplified mobile layout on its own.

- :fontawesome-solid-right-to-bracket: **Sign in** with an **Access Code** (the **Mobile Login** button) or with a **Login Link** copied by dispatch.
- :fontawesome-solid-list: **See your work** — the list shows **Dispatched** orders where you are the driver for the next step, grouped in sections such as **Import: Deliver to client** or **Export: Drop Empty**.
- :fontawesome-solid-signature: **Collect signatures** — the person at the site signs with a finger. You can also enter the seal number, waiting time and, for exports, the container number and weight.
- :fontawesome-solid-circle-check: **Finish moves without a signature** — tap **Drop Completed** (import empty return) or **Transfer Completed** (transfers).
- :fontawesome-solid-arrows-rotate: **Automatic updates** — signing and completing a step update the order's container status and dates for the office. You never set the container status by hand.

!!! info "Signing does not complete the order"
    Nothing you do on the phone changes the **order status**. The order stays **Dispatched** until the office changes it, for example to **Completed**. See [Order Workflow](order-workflow.md).

---

## :fontawesome-solid-bolt: Quick Start

1. Open the **Login Link** dispatch sent you, or go to the sign-in page, tap **Mobile Login**, type your **Access Code** and tap **Sign in**.
2. Your orders appear, grouped by step. Tap an order to open its details.
3. Tap the button at the bottom of the order: **Sign DELIVERY**, **Sign PICKUP**, **Sign DROP**, **Drop Completed** or **Transfer Completed**.
4. For a signature, enter the **\* Name of signee**, have the person sign, fill in any container details, and tap **Submit Signature**.
5. You return to the list. The step you just finished is gone. Tap **Refresh** at any time to load new assignments.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | What they can do |
|------|------------------|
| :fontawesome-solid-truck: **Driver** | Sees the mobile order list. Can open, sign, and mark as returned only orders where they are one of the assigned drivers. |
| :fontawesome-solid-handshake: **Broker** | Same as Driver. |
| :fontawesome-solid-warehouse: **Yard Worker** | Signs in the same way but does not get the order list. See [Yard Management](yard-management.md). |
| :fontawesome-solid-user-tie: **Admin**, **Manager**, **Dispatch** | Assign drivers in the driver columns on **Orders** and **Dispatch**, and copy a driver's **Login Link** from there. An **Accountant** sees the driver columns on **Orders** only when the account is set up to let accountants manage orders. |

Mobile users (Drivers, Brokers, Yard Workers) and their Access Codes are set up under **Mobile Users**. See [Mobile Users](mobile-users.md).

**How the mobile layout is chosen:**

- Browsers that identify themselves as mobile (most phones) get the mobile layout automatically. Some tablets, such as iPads, report themselves as desktop browsers and get the normal site.
- On any device you can force it by adding `?mobile=1` to the address, and turn it off with `?mobile=0`. The choice is remembered for the session. Office users on the mobile layout see a **View normal site** link to switch back.

**Mobile layout:**

- **Header** — a **Home** button on the left, your company name in the middle (on the order list, followed by the office name when you use [multiple offices](multi-office.md)), and a **Logout** button on the right.
- **Footer** — *Delivered by* followed by your name, so you can confirm who is signed in.

---

## :fontawesome-solid-right-to-bracket: Signing In

There are two ways to sign in. Drivers and Brokers both land on their order list. A Yard Worker lands on the container search page instead.

### Access Code (Mobile Login)

1. On your phone, open the UTX Freight sign-in page.
2. Under **Are you a driver or yard worker ?**, tap **Mobile Login**.
3. Type your **Access Code** (the characters are hidden) and tap **Sign in**.

The Access Code is set by your office on your mobile user record. Codes of 4 characters or fewer are never accepted. Your mobile user must be **Active** (not disabled or deleted) to sign in this way. If the code is wrong, the page simply comes back empty, with no error message. See [Mobile Users](mobile-users.md) for the code rules.

<!-- TODO: Screenshot — Phone sign-in page showing "Are you a driver or yard worker ?" with the Mobile Login button, and the Access Code screen -->

### Login Link

A **Login Link** signs a driver in with one tap, without typing a code. It requires the **magic_link** add-on. See [Add-ons & Options](add-ons-and-options.md).

**How dispatch gets the link:**

1. On **Orders** or **Dispatch**, find the order. The icon only shows while a driver step on the order is still waiting and a driver is assigned.
2. A :fontawesome-solid-share-from-square: share icon (*Click to copy*) appears next to a driver's name.
3. Click it. The link is copied to the clipboard and a message confirms **Login Link copied for** *DRIVER NAME*, with *Send this link using your messaging app or by email*. If no driver is assigned, you get **Login Link failed to copy** (*Please make sure a driver is assigned to the order*).
4. Paste the link into a text message or email to the driver.

<figure markdown>
  ![The share icon next to the driver's name on the Dispatch board](../images/dispatch-magic-driver-link.png){ width="80%" }
  <figcaption>Click the share icon next to the driver's name to copy their Login Link</figcaption>
</figure>

**How the link works:**

| Rule | Detail |
|------|--------|
| **One per driver** | The link belongs to the driver, not to the order. Copying it from any order gives the same link while it is valid. |
| **Valid 24 hours** | The link expires 24 hours after it was last copied. |
| **Extended on reuse** | Copying the link again while it is still valid extends it by another 24 hours from that moment. |
| **New link after expiry** | Copying it after it has expired creates a brand new link. The old one no longer works. |

!!! warning "Check the name in the confirmation"
    The link copied is always for the driver named in the **Login Link copied for** message. On **Container Import** orders, each icon copies the link of the driver shown in its own column. On the other order types (Container Export, International Export, Dry Van, Transfer), the icon on the **Orders** page copies the link of the driver in the *other* driver column, and on **Dispatch** whether the icon shows depends on the other column's step. Check the name before you send the link.

!!! warning "Disabling a driver does not cancel their Login Link"
    A Login Link that has not expired still signs the driver in, even after the driver is disabled on **Mobile Users**. Only the **Access Code** sign-in checks that the driver is active. Wait 24 hours from the last copy before assuming a disabled driver can no longer get in.

!!! warning "Send the new link after it expires"
    An expired link does not sign the driver in. Copy the link again from **Orders** or **Dispatch** and send the new one. Re-sending an old message will not work.

---

## :fontawesome-solid-list: Your Order List

### What appears

The list shows orders that meet **all** of these conditions:

- The order status is **Dispatched** (not **new**, **App. Taken** or **Completed**).
- You are the driver assigned to the step that is waiting (see the table below).
- The container status is not **Returned to terminal**.
- The order belongs to your current office.
- The order was created after the **Order Archive Cutoff Date** in Application Settings, if one is set. See [Application Settings](application-settings.md).

There is **no "all orders for the day" view**, and no date filter. Orders are sorted by delivery date, then appointment time, earliest first, and then grouped into sections.

!!! warning "The list shows at most 30 orders per order type"
    The list loads up to **30** of your dispatched orders for each order type (Container Import; Container Export and International Export together; Dry Van; Transfer) and has no next page. The 30 count every dispatched order you are assigned to in either driver slot, including ones whose steps are already done but which the office has not completed yet. If you have more, the latest by delivery date will not appear until earlier ones are completed by the office or returned to terminal.

### Sections and which driver they belong to

Each order has two driver slots. On the office **Orders** and **Dispatch** pages they are the first driver column (headed **Delivery Driver** for container companies, **Pickup Driver** otherwise) and the second driver column (headed **Return Driver** for container companies, **Delivery Driver** otherwise). Each step on the phone belongs to one of those slots:

| Section on the phone | Order type | Driver slot | Button |
|----------------------|-----------|-------------|--------|
| **Import: Deliver to client** | Container Import | 1st driver column | **Sign DELIVERY** |
| **Import: Return empty** | Container Import | 2nd driver column | **Drop Completed** |
| **Export: Drop Empty** | Container Export, International Export | 1st driver column | **Sign DROP** |
| **Export: Pickup Full** | Container Export, International Export | 2nd driver column | **Sign PICKUP** |
| **LCL: Pickup** | Dry Van | 1st driver column | **Sign PICKUP** |
| **LCL: Delivery** | Dry Van | 2nd driver column | **Sign DELIVERY** |
| **TF:** *terminal* **->** *terminal* | Transfer | 1st driver column | **Transfer Completed** |

Sections appear in this order and only when they contain at least one order.

!!! info "Both steps can show at the same time"
    The second step does not wait for the first one to be signed. For example, the driver in the second column of a Container Import sees it under **Import: Return empty** as soon as the order is dispatched. If the same driver is in both slots, the order shows in both sections.

!!! info "The TF section heading"
    The **TF:** heading shows the pick up and return terminals of the first transfer in the section. When you have several transfers, check **PICK UP TERMINAL** and **RETURN TERMINAL** inside each order.

### The order card

Each order is a collapsed row. The title reads:

**AT YARD -** *(only when the container status contains "at yard", such as **Empty at yard** or **Full at yard**)* + customer name (or **- Not Available**) + **-** + the order type code in brackets: **[CI]** (Container Import), **[CX]** (Container Export), **[IX]** (International Export), **[DV]** (Dry Van), **[TF]** (Transfer).

Tap the row to open it. Every container order starts with **CUSTOMER** and **POD #** (the order number). The other fields depend on which step of the order is still open, not on the section: while the first step is still waiting, the card shows the first step's fields in both sections. Once the first step is done, the second section shows the second step's fields.

| Field (as shown) | Deliver to client | Return empty | Drop Empty | Pickup Full | Transfer |
|------------------|:-:|:-:|:-:|:-:|:-:|
| **NOTE** (the order's Special Note, in red; hidden when empty) | ✓ | ✓ | ✓ | ✓ | ✓ |
| **PICK UP TERMINAL** | ✓ | | ✓ | | ✓ |
| **RETURN TERMINAL** | | ✓ | | ✓ | ✓ |
| **CONTAINER STATUS** (hidden when empty) | ✓ | ✓ | ✓ | ✓ | ✓ |
| **APPOINTMENT** (date @ time) | ✓ | | ✓ | | |
| **ADDRESS** (street, city, postal code) | ✓ | ✓ | ✓ | ✓ | |
| **Container #** | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Booking #** | | | ✓ | ✓ | ✓ |
| **Steamship line** | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Container Size** | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Pickup #** | ✓ | | ✓ | ✓ | |
| **Chassis #** | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Cargo Type** (shows **HAZMAT** in red; hidden otherwise) | ✓ | | | | |
| **Weight** | ✓ | | | | |
| **PO #** | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Seal #** | ✓ | | | ✓ | ✓ |
| **RV #** | ✓ | ✓ | | | ✓ |

**Dry Van (LCL) cards** use a different layout:

| Field | What it shows |
|-------|---------------|
| **ORDER #** | The order number |
| **NOTE** | The Special Note, in red (only when filled) |
| **PICKUP FROM** | Pickup company, address, city, postal code, and the pickup PO number (bold) |
| **DELIVER TO** | Delivery company, address, city, postal code, and the delivery PO number (bold) |

The **NOTE** comes from the **Special Note** field on the order. Dispatch uses it for instructions to the driver. See [Order Form](order-form.md).

<!-- TODO: Screenshot — Mobile order list with the "Import: Deliver to client" and "Import: Return empty" sections, one card opened -->

### Refresh

Tap **Refresh** at the bottom of the list to reload it. New assignments and changes made by the office appear only after a refresh.

---

## :fontawesome-solid-signature: Collecting a Signature

1. Open the order and tap its sign button (**Sign DELIVERY**, **Sign PICKUP** or **Sign DROP**).
2. Type the **\* Name of signee** (required).
3. Have the person sign under **Sign below** with a finger. Tap **Clear** to start over.
4. Fill in the container details if shown (see below).
5. Tap **Submit Signature**. Tap **Cancel** instead to go back to the list without saving.

The form heading depends on the button:

| Button | Form heading |
|--------|--------------|
| **Sign DELIVERY** (Import) | **Delivery Signature** |
| **Sign DROP** (Export) | **Drop Signature** |
| **Sign PICKUP** (Export) | **Pickup Signature** |
| **Sign PICKUP** (LCL) | **Pickup Signature** |
| **Sign DELIVERY** (LCL) | **Pickup Signature** |

### Form fields

| Field | Shown for | Notes |
|-------|-----------|-------|
| **\* Name of signee** | All | Required. The form asks *Please enter your name* if it is empty. |
| **Sign below** pad + **Clear** | All | The form asks *Please sign the document* if nothing was drawn. |
| **Seal Number** (under **Container Information**) | All except Dry Van | Saved only when filled. |
| **Container Number** | Container Export only (not International Export) | Replaces the order's container number when filled. |
| **Weight** | Container Export only (not International Export) | Saved as entered. Leaving it blank clears the weight on the order. |
| **Time In:** / **Time Out:** (under **Waiting Time**) | All except Dry Van | 24-hour time picker in 15-minute steps. |

!!! warning "International Export drop: waiting time is not kept"
    On **Sign DROP** for an International Export, the **Time In:** and **Time Out:** fields are shown but not saved. Tell dispatch the waiting time another way.

<!-- TODO: Screenshot — Mobile signature form showing "* Name of signee", the signature pad with Clear, Container Information, Waiting Time and the Submit Signature button -->

### What happens when you submit

| Step | Saved on the order | Automatic changes |
|------|--------------------|-------------------|
| **Sign DELIVERY** (Import) | Signature, signee name, date and time | Container status becomes **Dropped at customer**. The order's **delivery date** is set to today. |
| **Sign DROP** (Export) | Pickup signature, signee name, date and time | Container status becomes **Dropped at customer** (Container Export only). |
| **Sign PICKUP** (Export) | Signature, signee name, date and time | None |
| **Sign PICKUP** (LCL) | Pickup signature, signee name, date and time | None |
| **Sign DELIVERY** (LCL) | Signature, signee name, date and time | None |

The order status is never changed. The office sees the signed document on the order. See [Order Documents & POD](order-documents-and-pod.md).

---

## :fontawesome-solid-circle-check: Drop Completed and Transfer Completed

These two buttons finish a step **without** a signature pad.

### Drop Completed (Import: Return empty)

1. Open the order under **Import: Return empty**.
2. Tap **Drop Completed** once the empty container is back at the terminal. There is no confirmation step.

The container status becomes **Returned to terminal** and the time is recorded (the office sees it under the driver's name in the **Return Driver** column). The order leaves your list.

### Transfer Completed (TF)

1. Open the order under the **TF:** section.
2. Check the **Container Number**. The field is pre-filled with the order's container number; correct it if needed.
3. Tap **Transfer Completed**.

If the field is empty, the app can stop you with the label in red reading **Container Number cannot be empty!** This check does not run reliably on every order in the list. If an empty field does go through, the order keeps its existing container number.

A filled-in container number replaces the one on the order. The container status becomes **Returned to terminal**, and the completion time is recorded. The order leaves your list.

<!-- TODO: Screenshot — Transfer order opened on the phone with the Container Number field and the Transfer Completed button -->

---

## :fontawesome-solid-arrow-right-from-bracket: When an Order Leaves Your List

An order disappears from **every** section when it is no longer **Dispatched** (for example the office sets it to **Completed**) or when its container status becomes **Returned to terminal**. Each step also has its own exit:

| Section | Leaves when |
|---------|-------------|
| **Import: Deliver to client** | A delivery signature is captured, a scanned POD is uploaded, or the container status is **Dropped at customer**, **Returned to terminal** or **Empty at yard** |
| **Import: Return empty** | **Drop Completed** is tapped (container status **Returned to terminal**) |
| **Export: Drop Empty** | Any signature is captured on the order, a scanned POD is uploaded, or the container status is **Dropped at customer**, **Returned to terminal** or **Full at yard** |
| **Export: Pickup Full** | The **Sign PICKUP** signature is captured, a scanned POD is uploaded, or the container status is **Live load**, **Returned to terminal** or **Empty at yard** |
| **LCL: Pickup** | Any signature is captured on the order, or a scanned POD is uploaded |
| **LCL: Delivery** | The **Sign DELIVERY** signature is captured, or a scanned POD is uploaded |
| **TF:** | **Transfer Completed** is tapped, any signature is captured, or a scanned POD is uploaded |

Container statuses set by the office count too. For example, if dispatch sets **Dropped at customer** on an import, the order leaves **Import: Deliver to client** even without a signature. See [Container Statuses](container-statuses.md).

!!! info "A scanned POD removes the step"
    When the office uploads a scanned, signed POD for the order, the signature steps leave the driver's list as if they were signed. See [Order Documents & POD](order-documents-and-pod.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-link-slash: The Login Link doesn't sign me in

!!! info "Solution"
    The link expires 24 hours after dispatch last copied it. Once expired, a new link is created the next time it is copied, and the old one stops working. Ask dispatch to copy the link again from **Orders** or **Dispatch** and send you the new one. You can always sign in with **Mobile Login** and your **Access Code** instead.

### :fontawesome-solid-key: The Access Code screen just comes back empty

!!! info "Solution"
    The code was not accepted. No error message is shown. Check the code with your office and make sure your mobile user is active. See [Mobile Users](mobile-users.md).

### :fontawesome-solid-eye-slash: An order is missing from my list

!!! info "Solution"
    Tap **Refresh** first. Then check with dispatch that:

    - the order status is **Dispatched**,
    - you are in the right driver slot for the step (see [Sections and which driver they belong to](#sections-and-which-driver-they-belong-to)),
    - the container status is not **Returned to terminal** or another status that removes the step (see [When an Order Leaves Your List](#when-an-order-leaves-your-list)),
    - you are not over the 30-orders-per-order-type limit,
    - the order was created after the **Order Archive Cutoff Date**.

### :fontawesome-solid-hand-pointer: How do I change the container status?

!!! info "Solution"
    You can't set it by hand on the phone. It changes automatically: **Dropped at customer** when you sign a Container Import delivery or a Container Export drop, and **Returned to terminal** when you tap **Drop Completed** or **Transfer Completed**. Any other status change is done by the office.

### :fontawesome-solid-signature: I submitted a signature but there is no signature image on the order

!!! info "Solution"
    If the signature image does not reach the server, no error is shown and you are sent back to the list. The other details (signee name, time, container details, and the automatic container status change) are still saved, so the order may leave your list. Before tapping **Submit Signature**, check the signature is visible on the pad and that you have a data connection. If it happens, tell dispatch so they can collect a scanned POD instead.

### :fontawesome-solid-flag-checkered: I signed but the order still shows as Dispatched in the office

!!! info "Solution"
    That is expected. Signing never changes the order status. The office completes the order.

### :fontawesome-solid-comment-sms: Will I get the link by SMS?

!!! info "Solution"
    Dispatch copies the **Login Link** and sends it to you themselves, by text message or email. Ask your dispatcher how they send it.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips for drivers and dispatch"
    - **Tap Refresh** before you head out and after each stop.
    - **Read the NOTE** in red on each order. It carries dispatch's instructions.
    - **Check the name and signature** on the pad before tapping **Submit Signature**.
    - **Enter the container number** on Container Export signatures and on transfers. A filled-in number replaces what is on the order.
    - **Dispatch:** put each driver in the right slot (1st or 2nd driver column). The phone only shows a step to the driver in that slot.
    - **Dispatch:** copy a fresh **Login Link** at the start of the day. Copying it again keeps it valid for another 24 hours.
