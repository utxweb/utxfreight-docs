# Driver Login Links & SMS

Copy a one-tap **Login Link** for a driver from the **Orders** page or the **Dispatch** board, and send it so the driver can open their dispatched orders on their phone without typing an Access Code.

## :fontawesome-solid-share-from-square: Overview

- :fontawesome-solid-puzzle-piece: **Add-on**: Login Links need the **magic_link** add-on. Without it the share icon never appears. See [Add-ons & Options](add-ons-and-options.md).
- :fontawesome-solid-share-from-square: **Share icon**: a :fontawesome-solid-share-from-square: icon (tooltip *Click to copy*) appears in a driver column when the order is at the step that column's driver handles and a driver is assigned. See [When the Share Icon Appears](#when-the-share-icon-appears).
- :fontawesome-solid-clipboard: **Copy, then send it yourself**: clicking the icon copies the link to your clipboard. UTX Freight does not send it for you. Paste it into a text message, a messaging app or an email.
- :fontawesome-solid-user: **One link per driver**: the link belongs to the driver, not to the order. It opens the driver's whole mobile order list, not only the order you copied it from.
- :fontawesome-solid-clock: **Valid 24 hours**: each copy extends the link by 24 hours. After it expires, the next copy creates a new link and the old one stops working.
- :fontawesome-solid-comment-sms: **SMS**: the **sms** add-on was built to text the driver directly from the order. It is **currently unavailable**. See [SMS notifications (currently unavailable)](#sms-notifications-currently-unavailable).

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
    If you never see the share icon, the **magic_link** add-on is not turned on for your account. Contact UTX to turn it on. See [Add-ons & Options](add-ons-and-options.md).

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

For these orders the icon follows the rules below. They are not the same on the two screens.

| Screen | Column | Link copied for | Icon shows when |
|--------|--------|-----------------|-----------------|
| **Orders** | 1st driver column | The driver in the **2nd** driver column | Ready for the first signature and a driver is in the 2nd column |
| **Orders** | 2nd driver column | The driver in the **1st** driver column | Ready for return and a driver is in the 1st column |
| **Dispatch** | 1st driver column | The driver in the 1st column | Ready for return and a driver is in the 1st column |
| **Dispatch** | 2nd driver column | The driver in the 2nd column | Ready for the first signature and a driver is in the 2nd column |

Transfer orders have no 2nd driver column, so only the 1st column rows apply. On the **Orders** page, the 1st column icon of a Transfer copies the link of the order's delivery driver, who is not shown in the row. It only appears when the order has a delivery driver, so on most Transfers you will only see the icon on **Dispatch**.

What "ready" means for these order types (the order status must be **Dispatched** in every case, and no scanned POD may be attached):

| Order type | Ready for the first signature | Ready for return |
|------------|-------------------------------|------------------|
| **Container Export / International Export** | No signature collected yet, and container status is not **Dropped at customer**, **Returned to terminal** or **Full at yard** | **Sign PICKUP** not collected yet, and container status is not **Live load**, **Returned to terminal** or **Empty at yard** |
| **Dry Van** | No signature collected yet | **Sign DELIVERY** not collected yet |
| **Transfer** | No signature collected yet, and container status is not **Returned to terminal** | No signature collected yet, and container status is not **Live load**, **Returned to terminal** or **Empty at yard** |

!!! warning "Always check the name in the message"
    On the **Orders** page, for orders that are not Container Imports, the icon next to one driver copies the link of the driver in the **other** column. The blue message always names the driver whose link you copied. Read the name before you paste the link, and send it to that person.

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
    Anyone who has the link can open the driver's orders as that driver until it expires. Send it only to the driver. Disabling the mobile user or changing their Access Code does not cancel a link that was already sent. It keeps working until it expires. See [Mobile Users](mobile-users.md).

---

## :fontawesome-solid-comment-sms: SMS Notifications (currently unavailable)

!!! warning "SMS is not available right now"
    The **sms** add-on was designed to add an SMS icon next to the delivery driver so dispatch could text the driver the order and their Login Link. Because of a known issue, **the SMS icon is currently never shown**, even when the **sms** add-on is turned on. There is no other way to send the SMS from UTX Freight. Until this is fixed, use the [Login Link](#copying-and-sending-a-link) and send it from your own phone or email.

For reference, this is how the SMS feature is built to work once it is restored:

- It only texts the order's delivery driver, and only when the order is ready for the first signature.
- The driver must have a **Phone #** on their mobile user record. See [Mobile Users](mobile-users.md).
- The window is titled **Notify Driver via SMS** and previews the message: *Order# &lt;order number&gt; was assigned to you. View order: &lt;magic link here&gt;*. The real message contains the driver's Login Link, so sending it also renews the link for 24 hours.
- The window has **Close** and **Notify** buttons.

A successful send shows the title **Driver notified!**. Every failure shows the title **Driver not notified!** followed by one of the messages below.

| Result | Message |
|--------|---------|
| Sent | **Driver notified!** *The SMS message with order information was sent to delivery driver* |
| No driver or no phone number | *Order must have an assigned delivery driver with a valid phone number* |
| Invalid number | *Driver's phone number &lt;number&gt; is not valid* |
| Unreachable number | *Driver's phone number &lt;number&gt;, is not reachable* |
| International number | *Driver's phone number &lt;number&gt;, is international and service is not available for your account* |
| Blocked number | *Driver's phone number &lt;number&gt;, is blocked* |
| Not a mobile number | *Driver's phone number &lt;number&gt;, is not a mobile number* |
| Any other problem | *Unable to send the message at this moment. Reason: &lt;reason&gt;* |

The SMS icon colour shows the last attempt on the order:

| Colour | Tooltip |
|--------|---------|
| :fontawesome-solid-comment-sms:{ .text-primary } Blue | *Send SMS* (no SMS sent yet) |
| :fontawesome-solid-comment-sms:{ .text-success } Green | *Last SMS delivered* &lt;date&gt; *to* &lt;driver name&gt; |
| :fontawesome-solid-comment-sms:{ .text-danger } Red | *Last SMS failure* &lt;date&gt; *with:* &lt;error message&gt; |

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the share icon

!!! info "Solution"
    Check, in this order:

    1. The **magic_link** add-on is on for your account. See [Add-ons & Options](add-ons-and-options.md).
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
    The link signs in the driver named in the **Login Link copied for** message. On the **Orders** page, for orders that are not Container Imports, the icon in one driver column copies the link of the driver in the other column. Copy again, check the name, and send it to the right person.

### :fontawesome-solid-list: The driver opened the link but doesn't see an order

!!! info "Solution"
    The link opens the driver's order list, which only shows **Dispatched** orders where they are the driver for the waiting step, and not containers **Returned to terminal**. Check the order status and the driver assignment. See [Driver Workflow](driver-workflow.md).

### :fontawesome-solid-comment-sms: Where is the SMS button?

!!! info "Solution"
    SMS notifications are currently unavailable. The SMS icon is not shown even when the **sms** add-on is on. Copy the Login Link and send it yourself.

---

!!! tip "Best Practices"
    - **Read the name in the blue message** before you paste the link.
    - **Send the link close to the start of the driver's shift.** It lasts 24 hours from the last copy.
    - **Copy a fresh link** when a driver says the old one stopped working. Do not forward an old message.
    - **Send links only to the driver.** Anyone with the link can sign in as that driver until it expires.
