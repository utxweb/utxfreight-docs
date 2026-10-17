# Driver Login Links

Copy a one-tap **Login Link** for a driver from the **Orders** page or the **Dispatch** board, and send it so the driver can open their dispatched orders on their phone without typing an Access Code.

## :fontawesome-solid-share-from-square: Overview

- :fontawesome-solid-puzzle-piece: **Add-on**: Login Links need the **Driver Login Links** add-on, which UTX turns on for your account. Without it the share icon never appears. See [Add-ons & Options](add-ons-and-options.md).
- :fontawesome-solid-share-from-square: **Share icon**: a :fontawesome-solid-share-from-square: icon (tooltip *Click to copy*) appears in a driver column when the order is at the step that column's driver handles and a driver is assigned. See [When the Share Icon Appears](#when-the-share-icon-appears).
- :fontawesome-solid-clipboard: **Copy, then send it yourself**: clicking the icon copies the link to your clipboard. UTX Freight does not send it for you. Paste it into a text message, a messaging app or an email.
- :fontawesome-solid-user: **One link per driver**: the link belongs to the driver, not to the order. It opens the driver's whole mobile order list, not only the order you copied it from.
- :fontawesome-solid-clock: **Valid 24 hours**: each copy extends the link by 24 hours. After it expires, the next copy creates a new link and the old one stops working.

---

## :fontawesome-solid-bolt: Quick Start

1. Go to **Orders** or **Dispatch** and find the order.
2. Make sure a driver is assigned and the order is **Dispatched**.
3. Click the :fontawesome-solid-share-from-square: share icon in the driver column.
4. Check the name in the blue message **Login Link copied for** *DRIVER NAME*.
5. Paste the link into a text message or email and send it to that driver.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-gear: **Admin** | Can copy Login Links on **Orders** and **Dispatch** |
| :fontawesome-solid-user-tie: **Manager** | Can copy Login Links on **Orders** and **Dispatch** |
| :fontawesome-solid-headset: **Dispatch** | Can copy Login Links on **Orders** and **Dispatch** |
| :fontawesome-solid-phone: **Customer Service** | Same as Dispatch |
| :fontawesome-solid-calculator: **Accountant** | Only on **Orders**, and only when your account lets accountants manage orders (otherwise the driver columns are hidden). Accountants cannot open **Dispatch**. |
| :fontawesome-solid-warehouse: **Warehouse** / :fontawesome-solid-screwdriver-wrench: **Garage** / :fontawesome-solid-building: **Customer** | No access |
| :fontawesome-solid-truck: **Driver** / :fontawesome-solid-handshake: **Broker** | Receive and open the link. They cannot copy links. |

**How to get there:**

- :fontawesome-solid-arrow-right: **Orders**: the driver columns of the order list
- :fontawesome-solid-arrow-right: **Dispatch**: the driver columns of the board

The two driver columns are headed **Delivery Driver** and **Return Driver** for container (intermodal) accounts, and **Pickup Driver** and **Delivery Driver** otherwise. This page calls them the **1st driver column** and the **2nd driver column**, as in [Driver Workflow](driver-workflow.md).

!!! info "Add-on required"
    If you never see the share icon, the **Driver Login Links** add-on is not turned on for your account. Ask UTX support to turn it on. See [Add-ons & Options](add-ons-and-options.md).

---

## :fontawesome-solid-eye: When the Share Icon Appears

The icon only shows when there is a driver to send the link to and the order is at the step that driver handles.

### Container Import orders (Orders and Dispatch)

| Column | Link copied for | Icon shows when |
|--------|-----------------|-----------------|
| **1st driver column** (delivery) | The driver in that column | The order is **ready for the first signature**: status **Dispatched**, the delivery has not been signed, no scanned POD is attached, and the container status is not **Dropped at customer**, **Returned to terminal** or **Empty at yard**. A driver must be assigned. |
| **2nd driver column** (return) | The driver in that column | The order is **ready for return**: the order is **Dispatched** or the delivery has been signed (or a scanned POD is attached), and the container status is not **Returned to terminal**. A driver must be assigned. |

So for an import, the delivery driver's icon goes away once the delivery is signed, a scanned POD is attached, or the container status becomes **Dropped at customer** or **Empty at yard**, and the return driver's icon stays until the container is **Returned to terminal**.

### Other order types (Export, International Export, Dry Van, Transfer)

For these orders the icon shows next to a driver when that driver is assigned and the order is ready for the step they handle. Transfer orders have only one driver column.

What "ready" means for these order types (the order status must be **Dispatched** in every case, and no scanned POD may be attached):

| Order type | Ready for the first signature | Ready for return |
|------------|-------------------------------|------------------|
| **Container Export / International Export** | No signature collected yet, and container status is not **Dropped at customer**, **Returned to terminal** or **Full at yard** | **Sign PICKUP** not collected yet, and container status is not **Live load**, **Returned to terminal** or **Empty at yard** |
| **Dry Van** | No signature collected yet | **Sign DELIVERY** not collected yet |
| **Transfer** | No signature collected yet, and container status is not **Returned to terminal** | No signature collected yet, and container status is not **Live load**, **Returned to terminal** or **Empty at yard** |

!!! warning "Always check the name in the message"
    The blue message always names the driver whose link you copied. Read the name before you paste the link, and send it to that person.

<!-- TODO: Screenshot — An order row on the Dispatch board showing the share icon next to the delivery driver's name -->

---

## :fontawesome-solid-clipboard: Copying and Sending a Link

1. Click the :fontawesome-solid-share-from-square: share icon next to the driver's name.
2. The link is copied to your clipboard and a blue message appears in the top-right corner for about 5 seconds (it stays while your mouse is over it):
    - **Login Link copied for** :fontawesome-solid-user: *DRIVER NAME* (the name in capitals)
    - *Send this link using your messaging app or by email*
3. Paste the link into a text message, a messaging app or an email, and send it to the driver named in the message.

<figure markdown>
  ![The Login Link copied message naming the driver](../images/dispatch-magic-driver-link.png){ width="80%" }
  <figcaption>The confirmation shows whose Login Link was copied</figcaption>
</figure>

### If the copy fails

If the order has no driver for that step when you click (for example, the driver was removed after the page loaded), a red message appears instead:

- **Login Link failed to copy**
- **Please make sure a driver is assigned to the order**

The order row then reloads so you see its current drivers. Assign the driver and click the icon again.

---

## :fontawesome-solid-clock: How Long a Link Works

| Rule | Detail |
|------|--------|
| **One link per driver** | The link is tied to the driver, not to the order. Copying it from any order, on Orders or Dispatch, gives the same link while it is valid. |
| **Valid 24 hours** | The link works until 24 hours after it was last copied. |
| **Extended on each copy** | Copying it again while it is still valid keeps the same link and pushes the expiry to 24 hours from that moment. |
| **New link after expiry** | Copying it after it has expired creates a brand new link. The old link no longer works, even if it is still in the driver's messages. |

!!! warning "Re-sending an old message does not help"
    Once a link has expired, copy it again from **Orders** or **Dispatch** and send the new link. The old one will not sign the driver in.

---

## :fontawesome-solid-mobile-screen-button: What the Driver Sees

When the driver opens a valid link on their phone:

1. They are signed in as themselves, with no Access Code.
2. They land on their mobile order list. The link does **not** open one specific order. It shows all of their **Dispatched** orders where they are the driver for the waiting step, except containers that are **Returned to terminal**.

For the order list, signatures and the other steps, see [Driver Workflow](driver-workflow.md).

If the link has expired or is wrong, it does not sign the driver in. Unless they are still signed in on that phone, they are sent to the normal sign-in page. They can ask dispatch for a new link, or use **Mobile Login** with their Access Code. See [Mobile Users](mobile-users.md).

!!! danger "Treat the link like a password"
    Anyone who has the link can open the driver's orders as that driver until it expires. Send it only to the driver. See [Mobile Users](mobile-users.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the share icon

!!! info "Solution"
    Check, in this order:

    1. The **Driver Login Links** add-on is on for your account (UTX support turns it on). See [Add-ons & Options](add-ons-and-options.md).
    2. A driver is assigned to the step.
    3. The order is **Dispatched** and that step is still open. For example, on a Container Import the delivery driver's icon disappears once the delivery is signed, a scanned POD is attached, or the container is **Dropped at customer**. See [When the Share Icon Appears](#when-the-share-icon-appears).
    4. Your role can see the driver columns. See [Access & Permissions](#access-permissions).

### :fontawesome-solid-triangle-exclamation: "Login Link failed to copy"

!!! info "Solution"
    The order has no driver for that step. The row reloads to show the current drivers. Assign a driver and click the icon again.

### :fontawesome-solid-link-slash: The driver says the link doesn't work

!!! info "Solution"
    The link has probably expired (24 hours after it was last copied). Copy it again from **Orders** or **Dispatch** and send the new link. Old links stop working once a new one is created. Also make sure the driver opens it in their phone's web browser.

### :fontawesome-solid-user-xmark: The link opened the wrong driver's orders

!!! info "Solution"
    The link signs in the driver named in the **Login Link copied for** message. Copy again, check the name, and send it to the right person.

### :fontawesome-solid-list: The driver opened the link but doesn't see an order

!!! info "Solution"
    The link opens the driver's order list, which only shows **Dispatched** orders where they are the driver for the waiting step, and not containers **Returned to terminal**. Check the order status and the driver assignment. See [Driver Workflow](driver-workflow.md).

---

!!! tip "Best Practices"
    - **Read the name in the blue message** before you paste the link.
    - **Send the link close to the start of the driver's shift.** It lasts 24 hours from the last copy.
    - **Copy a fresh link** when a driver says the old one stopped working. Do not forward an old message.
    - **Send links only to the driver.** Anyone with the link can sign in as that driver until it expires.
