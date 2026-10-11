# Yard Worker Mobile Screen

Search a container by number on your phone, then ground it (take it off its chassis) or mark it **Full at yard** or **Empty at yard**.

## :fontawesome-solid-warehouse: Overview

Yard Workers use UTX Freight in their **phone's web browser**. There is no app to install. After signing in, a Yard Worker sees one screen: a container search.

- :fontawesome-solid-magnifying-glass: **Search a container** — type all or part of a container number in the **Container #** box and tap **Search**.
- :fontawesome-solid-list: **See the order** — each match shows the container number and order type, then **CUSTOMER**, **POD #**, **NOTE** (when there is one), **CONTAINER STATUS** and **CHASSIS NUMBER**.
- :fontawesome-solid-arrow-down: **Ground Container** — removes the chassis from the order. Only shown when a chassis is assigned.
- :fontawesome-solid-box: **Full at yard** / **Empty at yard** — sets the order's container status.
- :fontawesome-solid-arrows-rotate: **REFRESH** — reloads the order's status and chassis without changing anything.
- :fontawesome-solid-ban: **Nothing else** — Yard Workers cannot open the order list, sign PODs or change the order status.

!!! info "Changes go straight to the order"
    The buttons save to the order immediately. The office sees the new container status and chassis on the order.

---

## :fontawesome-solid-bolt: Quick Start

1. On your phone, open UTX Freight, tap **Mobile Login**, type your **Access Code** and tap **Sign in**.
2. Type the container number (or part of it) in the **Container #** box and tap **Search**.
3. Tap the container in **Search Results** to open it.
4. Tap **Ground Container**, **Full at yard** or **Empty at yard**. The card updates on the spot.

---

## :fontawesome-solid-lock: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-warehouse: **Yard Worker** (mobile user) | Container search and the yard buttons (**Ground Container**, **Full at yard**, **Empty at yard**, **REFRESH**). Nothing else. |
| :fontawesome-solid-truck: **Driver** / :fontawesome-solid-handshake: **Broker** | No access. They land on their own list of orders. See [Driver Mobile App](driver-workflow.md). |
| :fontawesome-solid-user-shield: **Admin**, :fontawesome-solid-user-tie: **Manager**, :fontawesome-solid-headset: **Dispatch**, other office roles | No container search screen. After sign-in they land on **Orders** (Warehouse users land on the warehouse orders). They change the container status and equipment from the order itself. See [Orders](orders.md) and [Order Form](order-form.md). |

**Who sets up Yard Workers:** an Admin, Manager, Dispatch or Customer Service user adds the person under :fontawesome-solid-user: **Mobile Users** :fontawesome-solid-arrow-right: **Drivers, Brokers & Yard**, picks the **Role** **Yard Worker**, and gives them an **Access Code**. See [Mobile Users](mobile-users.md).

**How to get there:** sign in on the phone. A Yard Worker always lands on the container search screen.

!!! warning "Yard Workers are mobile users, not office accounts"
    The **Yard Worker** role only exists under **Mobile Users** (with **Driver** and **Broker**). It is not in the **Role** list when you add a person with an email and password. The yard buttons are only allowed for a Yard Worker signed in with an **Access Code**.

!!! info "Phone layout only"
    The container search is part of the mobile layout, which UTX Freight uses automatically on a phone browser. On a desktop browser the page shows *Dashboard - Transportation orders coming soon* instead. Use a phone.

---

## :fontawesome-solid-right-to-bracket: Signing In

1. Open UTX Freight in the phone's browser. Under the email and password form, the page shows **Are you a driver or yard worker ?**
2. Tap **Mobile Login**.
3. Type your code in the **Access Code** field and tap **Sign in**.

You go straight to the container search. The phone remembers you, so you don't have to type the code every time. See [Mobile Users](mobile-users.md#signing-in-on-a-phone-access-code) for the sign-in rules.

<!-- TODO: Screenshot — Phone container search screen showing the Container # box and the Search button -->

---

## :fontawesome-solid-magnifying-glass: Searching for a Container

1. Type the container number in the **Container #** box. You can type only part of it (for example the last digits). Upper or lower case does not matter.
2. Tap **Search**.

The results appear under **Search Results**. If nothing matches, the screen shows **No Results Found**. The screen also shows **No Results Found** before your first search.

**Which orders are searched:**

| Included | Not included |
|----------|--------------|
| Orders with status **New**, **App. Made** or **Dispatched** | **Completed** orders |
| Every order whose container number contains what you typed | Orders created before the **Order Archive Cutoff Date** in **Settings** (see [Application Settings](application-settings.md)) |

!!! info "Several matches"
    A short search (for example 3 digits) can match several orders. Each one is listed as its own card. Check the container number and order type in the card title before you tap a button.

---

## :fontawesome-solid-id-card: What Each Result Shows

Tap a result to open it. The card title shows the **container number** followed by the order type code in brackets, for example `[CI]`.

| Type code | Order type |
|-----------|-----------|
| **CI** | Container Import |
| **CX** | Container Export |
| **TF** | Transfer |
| **DV** | Dry Van |
| **IX** | International Export |
| **WH** | Warehouse |

Inside the card:

| Field | What it shows |
|-------|---------------|
| **CUSTOMER** | The delivery company on the order. For a Transfer order, it shows the name of the customer company that owns the order. |
| **POD #** | The order's **Reference number**. |
| **NOTE** | The order's **Special Note**, in red. Only shown when the order has one. See [Order Form](order-form.md#special-note). |
| **CONTAINER STATUS** | The order's current container status, for example *Full at yard*. Empty when no status is set. |
| **CHASSIS NUMBER** | The **Equipment** assigned to the order. When the equipment is **Borrowed**, the borrowed chassis number is shown instead. Shows **-- no chassis --** in red when no equipment is assigned. |

Below the fields are the yard buttons.

<!-- TODO: Screenshot — An open search result card showing CUSTOMER, POD #, NOTE, CONTAINER STATUS, CHASSIS NUMBER and the Ground Container / Full at yard / Empty at yard / REFRESH buttons -->

---

## :fontawesome-solid-hand-pointer: Yard Buttons

Each button saves right away. There is no confirmation and no **Save** button. The card updates on the spot without reloading the page.

| Button | Shown when | What it does |
|--------|-----------|--------------|
| **Ground Container** | The order has a chassis (equipment) assigned | Removes the equipment from the order. **CHASSIS NUMBER** changes to **-- no chassis --** and the button disappears. |
| **Full at yard** | The container status is not already *Full at yard* | Sets the order's container status to *Full at yard*. **CONTAINER STATUS** turns green and the button disappears. |
| **Empty at yard** | The container status is not already *Empty at yard* | Sets the order's container status to *Empty at yard*. **CONTAINER STATUS** turns green and the button disappears. |
| **REFRESH** | Always | Reloads **CONTAINER STATUS** and **CHASSIS NUMBER** from the order, so you see changes made by the office. Changes nothing. |

### :fontawesome-solid-arrow-down: Grounding a container

1. Search for the container and open its card.
2. Check that **CHASSIS NUMBER** shows the chassis you are taking it off.
3. Tap **Ground Container**.

The chassis is taken off the order, so the office sees the order without **Equipment**. Grounding does not change the container status. If the container is now sitting in the yard, also tap **Full at yard** or **Empty at yard**.

!!! warning "Grounding cannot be undone from the phone"
    There is no button to put a chassis back on the order. The office must pick the **Equipment** again on the order. See [Order Form](order-form.md).

### :fontawesome-solid-box: Setting Full at yard or Empty at yard

1. Search for the container and open its card.
2. Tap **Full at yard** if the container is loaded, or **Empty at yard** if it is empty.

Only the container status changes. The order status (**New**, **App. Made**, **Dispatched**) stays the same. Switching from one to the other is allowed: after you tap **Full at yard**, the **Empty at yard** button is still there, and the other way around.

On the office side, these statuses feed the **Full at Yard** and **Empty at Yard** counters on the **Orders** page (intermodal accounts). See [Orders](orders.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-magnifying-glass: The search shows No Results Found but the container exists

!!! info "Solution"
    The search only finds orders that are **New**, **App. Made** or **Dispatched**. It does not find **Completed** orders or orders created before the **Order Archive Cutoff Date**. Check the order's status with the office. Also check the number: try typing only the last few digits.

### :fontawesome-solid-eye-slash: The Ground Container button is missing

!!! info "Solution"
    **Ground Container** only shows when the order has a chassis. If **CHASSIS NUMBER** shows **-- no chassis --**, there is nothing to remove. Tap **REFRESH** if the office has just assigned a chassis.

### :fontawesome-solid-eye-slash: The Full at yard (or Empty at yard) button is missing

!!! info "Solution"
    The button is hidden when the container status already has that value. Look at **CONTAINER STATUS**.

### :fontawesome-solid-list: I can't see the list of orders or sign a POD

!!! info "Solution"
    That is expected. Yard Workers only have the container search and the yard buttons. POD signatures are collected by **Drivers** and **Brokers** in the [Driver Mobile App](driver-workflow.md). If this person also drives, they need a separate mobile user with the **Driver** role.

### :fontawesome-solid-desktop: I only see "Dashboard - Transportation orders coming soon"

!!! info "Solution"
    You opened UTX Freight on a desktop browser. The container search only appears in the phone layout. Sign in from a phone.

### :fontawesome-solid-ban: The buttons don't do anything

!!! info "Solution"
    Make sure you signed in with an **Access Code** as a Yard Worker set up under **Mobile Users**. Only a Yard Worker signed in this way is allowed to use the yard buttons. Also check that the phone has a data connection, then tap **REFRESH**.

---

## :fontawesome-solid-star: Best Practices

!!! tip "Tips for yard work"
    - Search with enough digits to get one match. With several matches, check the container number and type code before tapping.
    - Tap **REFRESH** before you act if the card has been open for a while, so you see the office's latest changes.
    - After **Ground Container**, set **Full at yard** or **Empty at yard** so the office knows the container is in the yard and in what state.
    - Give each Yard Worker their own Access Code. See [Mobile Users](mobile-users.md).
