# Drivers, Brokers & Yard Workers (Mobile Users)

Set up the people who use UTX Freight from a phone (drivers, brokers and yard workers) and give each of them an Access Code to sign in.

## :fontawesome-solid-mobile-screen-button: Overview

A **mobile user** is someone who works in UTX Freight from a phone instead of the office screens. Mobile users are kept separate from office staff (who are added as people on your company, see [People & Invitations](people-and-invitations.md)). They don't have an email and password. They sign in with an **Access Code** or with a login link sent by dispatch.

- :fontawesome-solid-truck: **Driver**: is assigned to orders and completes them from the phone (signatures, delivered/returned). See [Driver Workflow](driver-workflow.md).
- :fontawesome-solid-handshake: **Broker**: has the same mobile rights as a Driver and appears in the same driver lists.
- :fontawesome-solid-warehouse: **Yard Worker**: works the yard from the phone. Searches containers by number. Is not offered in the order driver lists. See [Yard Management](yard-management.md).
- :fontawesome-solid-toggle-on: Each mobile user is either **active** or **disabled**. Only active users can sign in and be assigned.
- :fontawesome-solid-clock-rotate-left: Changes to mobile users are recorded in the audit history.

---

## :fontawesome-solid-bolt: Quick Start

1. In the left menu, open :fontawesome-solid-user: **Mobile Users** :fontawesome-solid-arrow-right: **Drivers, Brokers & Yard**.
2. Click **Add a new mobile user**.
3. Fill in **Firstname** and **Lastname**. Add the **Phone #** if you send SMS notifications.
4. Pick the **Role**: **Driver**, **Broker** or **Yard Worker**.
5. Type an **Access Code** of 5 to 16 characters. It must not be used by any other mobile user.
6. Leave **Active** checked and click **Save**.
7. Give the Access Code to the person. On their phone they tap **Mobile Login**, enter the code and tap **Sign in**.

---

## :fontawesome-solid-lock: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-gear: **Admin** | Full access: view, add, edit, enable and disable mobile users |
| :fontawesome-solid-user-tie: **Manager** | Full access |
| :fontawesome-solid-headset: **Dispatch** | Full access |
| :fontawesome-solid-phone: **Customer Service** | Full access (same rights as Dispatch) |
| :fontawesome-solid-calculator: **Accountant** | No access |
| :fontawesome-solid-warehouse: **Warehouse** / :fontawesome-solid-screwdriver-wrench: **Garage** | No access |
| :fontawesome-solid-building: **Customer** | No access |

**How to get there:**

- Left menu: :fontawesome-solid-user: **Mobile Users** :fontawesome-solid-arrow-right: **Drivers, Brokers & Yard**
- Or click your name in the top bar :fontawesome-solid-arrow-right: **Manage Drivers**

Both open the same page, titled **Drivers, Brokers and Yard Workers** (subtitle: *Management of Drivers, Brokers and Yard Workers with mobile access*).

!!! info "Which office's mobile users you see"
    Without the **Multi-Office** add-on, the list (and the driver drop-downs on orders) shows only the mobile users of the office you are currently working in. With the **Multi-Office** add-on, mobile users are shared: the list and the drop-downs show the mobile users of every office. See [Multi-Office](multi-office.md).

---

## :fontawesome-solid-list: The Mobile Users List

<!-- TODO: Screenshot — Drivers, Brokers and Yard Workers list showing the All Active / Disabled filter buttons, role labels in three colours, and the Actions menu open on one row -->

### Filters

Two buttons at the top left switch the list. The selected one is highlighted in green.

| Button | Shows |
|--------|-------|
| **All Active** | Mobile users who are active. This is the default when you open the page. |
| **Disabled** | Mobile users who have been disabled. |

There is no search box. The list is sorted by first name and shows 50 users per page, with page links at the bottom.

### Columns

| Column | What it shows |
|--------|---------------|
| **Role** | A coloured label with the role name (see the colour guide below). |
| **Name** | First and last name in bold. Green when the user is active, red when disabled. |
| **Phone #** | The phone number entered on the form. |
| **Email** | The email entered on the form. |
| **Truck #** | The truck number entered on the form. |
| **Active Deliveries** | Always shows **-**. This column is not filled in. |
| **Total Legs** | Always shows **-**. This column is not filled in. |
| **Active** | A green check icon when active, a red cross icon when disabled. |
| **Last Login** | Date and time of the user's previous sign-in (by Access Code or login link). Each time the user signs in, this column takes the time of the sign-in before it; after the very first sign-in it shows that sign-in. Empty if they have never signed in. |
| (Actions) | The **Actions** button with a drop-down menu: **Edit User**, and **Disable** or **Enable**. |

!!! info "Active Deliveries and Total Legs are always '-'"
    These two columns are placeholders. They always show **-** for every user, whatever work the user has done. To see a driver's work, use the [Dispatch](dispatch.md) board or [Reports](reports.md).

### :fontawesome-solid-palette: Color Guide

| Colour | Meaning |
|--------|---------|
| :fontawesome-solid-square:{ style="color: #5cb85c" } Green **Role** label | Driver |
| :fontawesome-solid-square:{ style="color: #428bca" } Blue **Role** label | Broker |
| :fontawesome-solid-square:{ style="color: #f0ad4e" } Orange **Role** label | Yard Worker |
| Green **Name** | Active user |
| Red **Name** | Disabled user |
| Green check / red cross in **Active** | Active / disabled |

---

## :fontawesome-solid-user-plus: Adding a Mobile User

1. Open :fontawesome-solid-user: **Mobile Users** :fontawesome-solid-arrow-right: **Drivers, Brokers & Yard**.
2. Click **Add a new mobile user** at the top right. The **New Mobile User** page opens with the **Mobile User Information** form.
3. Fill in the fields (see the table below).
4. Click **Save**. You return to the list with the message **Driver was successfully created.**

Click **Cancel** to go back to the list without saving.

<!-- TODO: Screenshot — New Mobile User page with the Mobile User Information form filled in -->

### Form fields

Fields marked with * are required.

| Field | Required | Description |
|-------|----------|-------------|
| **Firstname** | * | First name. Shown in the list and in driver drop-downs. |
| **Lastname** | * | Last name. |
| **Phone #** | | The user's phone number. Needed if your system has the **SMS** add-on and you send order SMS to drivers. Enter it with the country code (for example `15145550123`); a `+` is added in front when the SMS is sent if you leave it out. See [Notifications & Emails](notifications-and-emails.md). |
| **Email** | | Email address, for your reference. It is not used to sign in. |
| **Truck #** | | The truck the user drives, for your reference. Shown in the list. |
| **Driver's License #** | | Licence number, for your reference. Not shown in the list. |
| **Role** | * | **Driver**, **Broker** or **Yard Worker**. See [Roles](#roles). |
| **Office** | * | The office the user belongs to. Hint: *Office to which the driver is assigned*. The list contains the offices you belong to, and starts on the office you are working in. See the warning below about new users. |
| **Access Code** | * | The code the user types to sign in on the phone. Hint: *Code used by the driver to access the application. The driver must be active!* See [Access Code rules](#access-code-rules). |
| **Active** | | Checked = the user can sign in and be assigned. Hint: *Only active drivers can access the system*. |

!!! warning "New users are saved in your current office"
    When you **add** a mobile user, the user is always saved in the office you are currently working in, whatever you pick in **Office**. To put the user in another office, either switch to that office before adding them, or save them and then edit them and change **Office**.

!!! info "No delete"
    Mobile users cannot be deleted from this page. When someone leaves, **disable** them instead. Their past orders and legs keep their name.

### :fontawesome-solid-key: Access Code rules

- It must be **5 to 16 characters** long. A blank code, or one shorter than 5 or longer than 16 characters, is refused when you save.
- It must be **unique**: no two mobile users can have the same code, even across roles and offices, and including disabled users. If the code is taken, the form shows an error and does not save.
- It is **case-sensitive**: `Truck-ABC` and `truck-abc` are different codes, and the person must type it exactly as saved.
- The system does not create the code for you. You choose it and give it to the person.
- The code only works while the user is **Active**.
- The code is shown on the edit form so you can look it up or change it. Changing it means the old code no longer works for new sign-ins.

!!! danger "Treat the Access Code like a password"
    Anyone who has the code can sign in as that user from a phone. Do not use easy codes like `12345` or the truck number, and change the code if it may have been shared.

---

## :fontawesome-solid-user-tag: Roles

| Role | On the phone | In office screens |
|------|--------------|-------------------|
| **Driver** | Sees the orders assigned to them. Can collect delivery and pickup signatures and mark orders as returned. See [Driver Workflow](driver-workflow.md). | Appears in the driver drop-downs on the **Orders** and **Dispatch** pages. |
| **Broker** | Exactly the same rights as a Driver. | Appears in the same driver drop-downs as Drivers. |
| **Yard Worker** | Lands on a screen with a **Container #** search box. Searches a container and grounds it in the yard. See [Yard Management](yard-management.md). | **Not** shown in the driver drop-downs on the **Orders** and **Dispatch** pages, so cannot be assigned as the order's driver. |

!!! info "Leg drivers"
    The driver picker on each **leg** of an order (see [Order Legs & Move Locations](order-legs-and-move-locations.md)) lists every active mobile user, whatever the role, including Yard Workers.

Only active users are offered in any of these drop-downs.

---

## :fontawesome-solid-pen-to-square: Editing a Mobile User

1. In the list, click the caret next to **Actions** on the user's row.
2. Click **Edit User**. The **Edit Mobile User** page opens.
3. Change the fields you need.
4. Click **Save**. You return to the list with the message **Driver was successfully updated.**

Every change (name, phone, role, office, Access Code, active status and so on) is recorded in the system's audit history with who made it and when.

---

## :fontawesome-solid-toggle-off: Disabling and Enabling

A disabled user cannot sign in with the Access Code and is removed from the driver drop-downs. Their history stays.

**From the list:**

1. Click the caret next to **Actions** on the user's row.
2. Click **Disable** (shown for active users) or **Enable** (shown for disabled users).
3. A notification appears at the top, for example *Driver: John Smith - Disabled*. The row updates in place: the name turns red and the **Active** icon becomes a red cross.

The user stays on screen until you reload the page or switch filter. Then they move to the **Disabled** list (or back to **All Active**).

**From the form:** uncheck or check **Active** on the **Edit Mobile User** page and click **Save**.

!!! warning "A login link sent earlier still works after disabling"
    Disabling stops the Access Code from working. But a login link that dispatch sent before you disabled the user keeps signing them in until that link expires. Changing the Access Code does not cancel the link either. See [Driver Login Links](driver-login-links.md).

---

## :fontawesome-solid-right-to-bracket: Signing In on a Phone (Access Code)

Mobile users sign in on their phone's web browser. No app download is needed.

1. Open UTX Freight in the phone's browser. The sign-in page shows the heading **Are you a driver or yard worker ?** under the normal email and password form.
2. Tap **Mobile Login**.
3. Type the code in the **Access code** field. The characters are hidden as you type.
4. Tap **Sign in**.

<!-- TODO: Screenshot — Phone sign-in page showing "Are you a driver or yard worker ?" and the Mobile Login button, then the Access Code screen -->

**What happens next:**

- **Drivers** and **Brokers** go to their list of assigned orders. See [Driver Workflow](driver-workflow.md).
- **Yard Workers** go to the **Container #** search screen. See [Yard Management](yard-management.md).

There is no "remember me" box on the Access Code screen.

Sign-in only works when the user is **Active**. Signing in with an Access Code (even with a wrong code) also signs out anyone who was signed in on that browser before.

!!! info "Use the phone's browser"
    The **Are you a driver or yard worker ?** heading and the **Mobile Login** button appear on the phone version of the sign-in page. The computer version of the sign-in page only shows the email and password form.

!!! info "Login link instead of a code"
    Dispatch can also send a driver a login link from the **Orders** or **Dispatch** page. Tapping the link signs the driver in without typing the code. See [Driver Login Links](driver-login-links.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-ban: The driver enters the code and the screen just comes back empty

!!! info "Solution"
    The sign-in page reloads without an error message when the code is not accepted. Check, on the **Edit Mobile User** page:

    - The **Access Code** is exactly what the driver types (5 to 16 characters, same upper and lower case, no extra spaces).
    - **Active** is checked. A disabled user cannot sign in.

    If both are right, set a new code, save, and give it to the driver.

### :fontawesome-solid-triangle-exclamation: The form won't save and shows an error on Access Code

!!! info "Solution"
    The code is either already used by another mobile user, or it is not between 5 and 16 characters. Access Codes must be unique across all mobile users. Pick a different code.

### :fontawesome-solid-user-slash: A driver doesn't appear in the Dispatch or Orders driver list

!!! info "Solution"
    Only **active** users with the **Driver** or **Broker** role appear there. Check that:

    - The user is in the **All Active** list, not **Disabled**.
    - The **Role** is **Driver** or **Broker**. Yard Workers are not offered there.
    - Without the **Multi-Office** add-on, the user belongs to the office you are working in.

### :fontawesome-solid-trash: How do I delete a mobile user?

!!! info "Solution"
    You can't delete them from this page. Use **Disable** in the **Actions** menu. They disappear from the active list and the drop-downs but keep their history.

### :fontawesome-solid-building: I created a driver for another office but they are in my office

!!! info "Solution"
    New mobile users are always saved in your current office. Open **Edit User**, change **Office**, and click **Save**. Or switch office first and then add the driver.

### :fontawesome-solid-comment-sms: The driver doesn't get SMS notifications

!!! info "Solution"
    SMS is only available when your system has the **SMS** add-on, and the order's delivery driver must have a **Phone #** (with the country code). Check the number on the **Edit Mobile User** page. See [Notifications & Emails](notifications-and-emails.md).

### :fontawesome-solid-chart-line: Why do Active Deliveries and Total Legs show "-"?

!!! info "Solution"
    These columns are not filled in. They always show **-**. Use the [Dispatch](dispatch.md) board or [Reports](reports.md) to see a driver's work.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Best Practices"
    - **Disable, don't reuse.** When someone leaves, disable their user and create a new one for the next person, so history stays correct.
    - **Change the code when a phone is lost or the code may have been shared.** Remember that an earlier login link still works until it expires, even after disabling.
    - **Fill in Phone # for every driver** (with the country code) if you use SMS notifications.
    - **Use the right role.** Pick **Yard Worker** for people who only work the yard, so they don't clutter the driver lists on Orders and Dispatch.
    - **Keep Access Codes private** and avoid guessable codes.
