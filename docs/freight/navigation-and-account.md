# Signing In, Navigation & Your Profile

This page covers how you sign in to UTX Freight on the web, where you land after signing in, the left sidebar and top bar for each role, how to edit your own profile, how to use UTX Freight from a phone as an office or customer user, and how to send feedback to the UTX team.

## :fontawesome-solid-circle-info: Overview

- You sign in with your **Email** and **Password**. Tick **Remember me** to stay signed in on that browser.
- Forgot your password? Click **I forgot my password**, then **Send me reset instructions**. The reset link in the email is valid for **6 hours**.
- After you sign in, UTX Freight takes you to the page that fits your role: **Orders** for most users and **Warehouse** :fontawesome-solid-arrow-right: **Orders** for the Warehouse role. Garage users need to open the Garage screens directly (see [Where You Land](#where-you-land-after-signing-in)).
- The **left sidebar** lists the main sections. Each item appears only when your role is allowed to use it, so different users see different menus.
- The **top bar** shows your company and current office name on the left. On the right are the office switcher (multi-office only), **Feedback**, **Online Documentation**, and your **user menu** (your name). The user menu contains **Edit Profile** or **Settings**, the **Manage ...** lists, and **Logout**.
- If you open a page your role can't use, you are sent back to your starting page. Nothing is changed.
- On a phone, UTX Freight switches to a simplified layout built for drivers. Office and customer users should tap **View normal site** at the bottom of the page to get the full site (see [Using UTX Freight on a Phone](#using-utx-freight-on-a-phone-office-and-customer-users)).

## :fontawesome-solid-bolt: Quick Start

1. Open your UTX Freight address and enter your **Email** and **Password**.
2. Tick **Remember me** if you are on your own computer, then click **Sign in**.
3. Use the left sidebar to move between sections (**Orders**, **Dispatch**, **Invoices**, and so on).
4. Click your name in the top bar :fontawesome-solid-arrow-right: **Edit Profile** to update your phone numbers or email notifications.
5. Click **Feedback** in the top bar any time to report a bug or suggest an improvement.

## :fontawesome-solid-lock: Access & Permissions

Every web user (Admin, Manager, Dispatch, Customer Service, Accountant, Customer, and, when those add-ons are enabled, Warehouse and Garage) signs in on the same sign-in page. What you see afterwards depends on your role. See [User Roles](user-roles.md) for the full permission list.

| Role | Lands on after sign-in | Edit Profile in user menu |
|------|------------------------|---------------------------|
| :fontawesome-solid-user-shield: **Admin** | **Orders** | No (Admins see **Settings** instead) |
| :fontawesome-solid-user-tie: **Manager** | **Orders** | No |
| :fontawesome-solid-headset: **Dispatch** / **Customer Service** | **Orders** | Yes |
| :fontawesome-solid-calculator: **Accountant** | **Orders** | Yes |
| :fontawesome-solid-user: **Customer** | **Orders** | Yes |
| :fontawesome-solid-warehouse: **Warehouse** | **Warehouse** :fontawesome-solid-arrow-right: **Orders** (when the Warehouse add-on is enabled) | Shown, but the role can't open it |
| :fontawesome-solid-screwdriver-wrench: **Garage** | No Garage starting page. Open the Garage screens directly (see below) | Shown, but the role can't open it |

!!! info "Drivers and mobile users sign in differently"
    Drivers, brokers and yard workers are set up under **Mobile Users** and don't sign in with an email and password. On a phone, the sign-in screen shows **Are you a driver or yard worker ?** with a **Mobile Login** button, which asks for an **Access Code**. See [Mobile Users](mobile-users.md) and [Driver Login Links](driver-login-links.md).

## :fontawesome-solid-right-to-bracket: Signing In

<!-- TODO: Screenshot — Sign-in page with Email, Password, Remember me and Sign in -->

1. Go to your UTX Freight sign-in page.
2. Enter your **Email** and **Password**.
3. Optionally tick **Remember me**.
4. Click **Sign in**.

If the email or password is wrong, you'll see **Invalid email or password.** Check for typos and caps lock, or reset your password (below).

### Remember me

When **Remember me** is ticked, the browser keeps you signed in, even after you close it, for up to two weeks. Leave it unticked on shared or public computers. Clicking **Logout** always ends your session.

### Resetting your password

1. On the sign-in page, under **Help:**, click **I forgot my password**.
2. The page **Can't sign in? Forget your password?** opens. Enter your **Email**.
3. Click **Send me reset instructions**. You'll see: *You will receive an email with instructions about how to reset your password in a few minutes.*
4. Open the email (subject **Reset password instructions**) and click **Change my password**.
5. On the **Change your password** page, enter your new **Password** and type it again in **Confirm new password**.
6. Click **Reset my password**. You're signed in with your new password.

To go back without resetting, click the **send me back to the sign in screen** link (after "Nevermind,").

!!! warning "The reset link expires after 6 hours"
    If you open the link more than 6 hours after requesting it, the reset fails with a message that the token has expired. Request a new link with **I forgot my password**. Only the most recent link works.

!!! info "Password rules"
    Passwords must be at least **6 characters** long (maximum 128). Your password does not change until you complete the **Change your password** page, so you can ignore a reset email you didn't request.

## :fontawesome-solid-house: Where You Land After Signing In

UTX Freight sends you to a starting page based on your role:

| Role | Starting page |
|------|---------------|
| **Warehouse** | **Warehouse** :fontawesome-solid-arrow-right: **Orders**. If the Warehouse add-on isn't enabled, you are sent to the public home page instead. |
| **Garage** | There is no Garage starting page: the redirect after sign-in points to **Orders**, which the Garage role can't open. Open the Garage **Work Orders** page directly (the `/garage/work_orders` address on your UTX Freight site) and bookmark it. |
| Everyone else | **Orders** |

Yard workers who sign in with **Mobile Login** land on a container search: a **Container #** box with a **Search** button, with results under **Search Results** (or **No Results Found**). Drivers who sign in with **Mobile Login** land on **Orders**. See [Yard Management](yard-management.md) and [Mobile Users](mobile-users.md).

## :fontawesome-solid-bars: The Left Sidebar

The sidebar lists the sections you can open. Items appear in the order below. An item is shown only when your role (and, for add-ons, your account) allows it.

| Sidebar item | Who sees it | Notes |
|--------------|-------------|-------|
| :fontawesome-solid-clipboard-check: **Getting started** | Admin, Manager | Shows your setup checklist. The label changes to **Setup check** on an account that is already running, and to **Setup complete** once everything is done. An alert icon means steps remain. See [Setup Checklist](setup-checklist.md). |
| :fontawesome-solid-truck: **Orders** | Every role except Warehouse | The Garage role sees the item but can't open Orders. See [Orders](orders.md). |
| :fontawesome-solid-road: **Dispatch** | Admin, Manager, Dispatch, Customer Service | Opens the dispatched orders. See [Dispatch](dispatch.md). |
| :fontawesome-solid-warehouse: **Warehouse** | Admin, Warehouse, when the Warehouse add-on is enabled | Expands to **Orders**, **Product**, **Location**, **Charges**, **Unit of Measure**, **Building**. See [Warehouse Overview](warehouse-overview.md). |
| :fontawesome-solid-screwdriver-wrench: **Garage** | Admin, Manager, Garage, when the Garage add-on is enabled | Opens Garage work orders. The Garage screens have their own sidebar (with **Back to TMS** at the bottom) and no **Feedback** button. See [Garage Overview](garage-overview.md). |
| :fontawesome-solid-file-invoice: **Invoices** | Admin, Manager, Accountant | See [Invoices](invoices.md). |
| :fontawesome-solid-gas-pump: **Fuel Schedule** | Users who can manage charge types (Admin, Manager, Accountant, Warehouse, and Dispatch with **Can manage rates?**), when the Fuel Surcharge add-on is enabled | See [Fuel Surcharge](fuel-surcharge.md). |
| :fontawesome-solid-money-bill: **Expenses** | Admin | See [Expenses & Checks](expenses-and-checks.md). |
| :fontawesome-solid-money-bill: **Checks** | Admin. Manager and Accountant when check management is turned on for your account. | See [Expenses & Checks](expenses-and-checks.md). |
| :fontawesome-solid-building: **Customers** | Admin, Manager. Dispatch when customer management is turned on for your account. | See [Managing Customers](managing-customers.md). |
| :fontawesome-solid-building: **Shipper / Receiver** | Admin, Manager, Dispatch | See [Shippers & Receivers](shippers-receivers.md). |
| :fontawesome-solid-truck: **Equipments** | Admin, Manager, Dispatch | See [Equipment](equipment.md). |
| :fontawesome-solid-user: **Mobile Users** | Admin, Manager, Dispatch | Expands to **Drivers, Brokers & Yard**. See [Mobile Users](mobile-users.md). |
| :fontawesome-solid-chart-bar: **Reports** | Admin. Manager when reports are turned on for your account. | Expands to the report list below. See [Reports](reports.md). |

The **Reports** submenu contains, in order:

1. **Income by Customer**
2. **Income by Shipper**
3. **Delivery by Zone**
4. **Daily Income**
5. **Sales per Month**
6. **Order Sales / Profit**
7. **Drivers Delivery Report**
8. **Customer Reports**
9. **Aged Receivables (AR)** (see [Aged Receivables](aged-receivables.md))
10. **AR Export**

At the bottom of the sidebar (on wider screens) you'll find **UTX Freight TMS** and **Release** followed by the version number you are running, for example **Release 3.12.19**. Quote this version when you report a problem. The [Changelog](changelog.md) lists what changed in each release.

!!! info "Settings that depend on your account"
    Some items depend on how UTX has configured your account: whether Managers can manage checks or view reports, and whether Dispatch can manage customers or terminals. If you expect to see an item and don't, ask your Admin or UTX support.

## :fontawesome-solid-window-maximize: The Top Bar

On the left, the top bar shows your company name followed by **|** and your current office name. Clicking it takes you to your starting page. On the right, from left to right, it contains:

| Item | What it does |
|------|--------------|
| :fontawesome-solid-building: **Office switcher** (your current office name) | Only shown when multi-office is enabled **and** you belong to more than one office. See [Switching offices](#switching-offices). |
| :fontawesome-solid-comment-dots: **Feedback** | Opens the feedback form. See [Sending Feedback](#sending-feedback). |
| :fontawesome-solid-book: **Online Documentation** | Opens this documentation site in a new tab. |
| :fontawesome-solid-user: **Your name** | Opens your user menu (below). |

### Switching offices

When multi-office is enabled and you are assigned to two or more offices:

1. Click the office name in the top bar.
2. Pick an office from the list. Your current office has a green check mark.
3. The page reloads with **Switched to the <office name> office**.

Orders, invoices and checks are shown for the office you have selected. When multi-office is enabled, each office also gets its own top bar color (there are six colors, so they repeat after the sixth office), so you can see at a glance which one you're working in. The Warehouse and Garage roles can't switch offices: choosing an office sends them back to their starting page. See [Multi-Office](multi-office.md).

### The user menu

Click your name in the top bar to open the user menu. Items are grouped by dividers and appear in this order. An item is shown only when your role allows it.

| Menu item | Who sees it | Notes |
|-----------|-------------|-------|
| :fontawesome-solid-user: **Edit Profile** | Everyone **except** Admin and Manager | Warehouse and Garage users see it but can't open it. See [Editing Your Profile](#editing-your-profile). |
| :fontawesome-solid-gear: **Settings** | Admin and Manager | Only Admins can open it. A Manager who clicks it is sent back to their starting page. See [Application Settings](application-settings.md). |
| :fontawesome-solid-user-shield: **Super User** | UTX staff only | Not used by customers. |
| **Manage Brokers** | Admin, Manager | |
| **Manage Cities** | Admin, Manager, Dispatch with **Can manage rates?** | See [Zones & Cities](zones-and-cities.md). |
| **Manage Clients** | Admin, Manager, Dispatch | Same list as **Shipper / Receiver**. |
| **Manage Container Sizes** | Admin | Intermodal accounts only. See [Lookup Lists](lookup-lists.md). |
| **Manage Container Statuses** | Admin, Manager, Dispatch | Intermodal accounts only. Dispatch can view but not change statuses. See [Container Statuses](container-statuses.md). |
| **Manage Document Types** | Admin, Manager | See [Lookup Lists](lookup-lists.md). |
| **Manage Drivers** | Admin, Manager, Dispatch | Opens **Mobile Users**. |
| **Manage Equipment Types** | Admin, Manager, Dispatch | See [Equipment](equipment.md). |
| **Manage Move Locations** | Admin, Manager, Dispatch | See [Order Legs & Move Locations](order-legs-and-move-locations.md). |
| **Manage Steamship Lines** | Admin | Intermodal accounts only. |
| **Manage Terminals** | Admin, Manager. Dispatch when terminal management is turned on for your account. | Intermodal accounts only. See [Managing Terminals](managing-terminals.md). |
| **Manage Zones** | Admin, Manager | See [Zones & Cities](zones-and-cities.md). |
| :fontawesome-solid-dollar-sign: **Charge Types** | Admin, Manager, Accountant, Warehouse, Dispatch with **Can manage rates?** | See [Charge Types & Taxes](charge-types-and-taxes.md). |
| :fontawesome-solid-dollar-sign: **Expense Types** | Admin, Manager, Accountant, Dispatch with **Can manage rates?** | |
| :fontawesome-solid-dollar-sign: **Manage Taxes** | Admin, Manager, Accountant | See [Charge Types & Taxes](charge-types-and-taxes.md). |
| **Manage Content** | Admin | See [Website Content](website-content.md). |
| **Manage Offices** | Admin | See [Multi-Office](multi-office.md). |
| :fontawesome-solid-power-off: **Logout** | Everyone | Signs you out and returns you to the home page. |

!!! tip "Customers see a short menu"
    A Customer user typically sees only **Edit Profile** and **Logout** in the user menu, and only **Orders** in the sidebar.

## :fontawesome-solid-user-pen: Editing Your Profile

<!-- TODO: Screenshot — Edit Profile page (Personal Information) with Save Changes button -->

1. Click your name in the top bar :fontawesome-solid-arrow-right: **Edit Profile**.
2. The **Personal Information** page opens. Update the fields you need.
3. Click **Save Changes**.

| Field | Description |
|-------|-------------|
| **First Name** | Your first name. Your name is displayed next to your requests. |
| **Last Name** | Your last name. |
| **Email** | The address you sign in with, and where UTX Freight sends your emails. |
| **Title** | Your job title. |
| **Office #** / **Office Ext. #** | Your office phone number and extension. |
| **Mobile #** | Your mobile phone number. |
| **Fax #** | Your fax number. |
| **Email Notifications** | When ticked, you receive the **Order #... is now dispatched** and **Order Completed for order #...** emails for orders placed under your name. For Admins, and for Managers of the order's office, it also controls whether they get the **New Order #...** email sent whenever an order is created. Untick it to stop these emails. See [Notifications & Emails](notifications-and-emails.md). |
| **Active for orders** | The form says "Only active users will be available as the order suppliers". When unticked, this person no longer appears in **Place the order on behalf of** on new orders. An Admin with this unticked also stops getting the **New Order** email. |

!!! info "Fields only an Admin can change"
    **Company** appears only when an Admin is editing. **Role** and **Offices** appear only when an Admin edits a staff user (a user of your own company) who isn't the account owner, and **Can manage rates?** appears only for Dispatch and Customer Service users in that same case. You can't change your own role or offices. See [People & Invitations](people-and-invitations.md).

!!! info "Admins and Managers"
    Admins and Managers don't have **Edit Profile** in their menu. They update their own details the same way they update other users, from the people listed under **Customers**. See [People & Invitations](people-and-invitations.md).

After you click **Save Changes**, you are taken to the **Customers** page with **User was successfully updated.** If your role can't open **Customers** (Accountant, Customer, and Dispatch unless customer management is turned on for your account), you end up on your starting page instead, usually without a confirmation message. Your changes are still saved. **Cancel** discards your changes and also goes to **Customers** (or your starting page if your role can't open it).

## :fontawesome-solid-mobile-screen: Using UTX Freight on a Phone (Office and Customer Users)

UTX Freight has a separate phone layout. It was built for drivers and yard workers, but it is also shown to office staff (Admin, Manager, Dispatch, Customer Service, Accountant, and so on) and to Customer users when they open UTX Freight on a phone. For an office or customer user, the phone layout is not useful: switch to the normal site as described below.

### When you get the phone layout

You get the phone layout when any of these is true:

| Situation | Notes |
|-----------|-------|
| Your browser identifies itself as a mobile browser | Browsers whose identification (user agent) contains "Mobile" or "webOS", which covers most phones. A browser that doesn't include either word (for example, many tablets) gets the normal site. |
| The address you opened ends with `?mobile=1` | The choice is remembered for the rest of your browser session, on any device. |
| Your UTX Freight address starts with `mobile.` | The phone layout is always used on that address. **View normal site** and `?mobile=0` have no effect there. Use your regular UTX Freight address instead. |

Adding `?mobile=0` to the address (or tapping **View normal site**) turns the phone layout off for the rest of your browser session, even on a phone. The choice is stored in your session, so after you **Logout** (or when your browser ends the session) you get the phone layout again on a phone.

### What you see in the phone layout

<!-- TODO: Screenshot — Phone layout for an office user: header with Home, company name and Logout, empty Orders list with Refresh button and View normal site link -->

- **Sign-in page:** the same **Email**, **Password**, **Remember me** and **Sign in** fields, plus the **Are you a driver or yard worker ?** box with the **Mobile Login** button. Office and customer users sign in with their email and password as usual. **Mobile Login** is only for drivers, brokers and yard workers.
- **Header:** **Home** on the left (opens your company's public home page), your company name in the middle (followed by **-** and your current office name when multi-office is enabled), and, once you are signed in (for example on **Orders**), **Logout** on the right. The sign-in page header has no **Logout**.
- **Not available:** there is no left sidebar, no user menu (so no **Edit Profile** or **Settings**), no office switcher, no **Feedback** and no **Online Documentation** link.
- **Bottom of the page (once signed in, for example on Orders):** a **View normal site** link. It is shown to office and customer users only, not to drivers, brokers or yard workers (they see **Delivered by** followed by their name instead). The sign-in page doesn't have this link.

### The Orders page in the phone layout

After you sign in, you land on **Orders** as usual, but the page shows the **driver's** order list instead of the normal orders table. It groups orders under headings such as **Import: Deliver to client**, **Import: Return empty**, **Export: Drop Empty**, **Export: Pickup Full**, **LCL: Pickup**, **LCL: Delivery** and transfer headings (**TF:** followed by the pickup and return terminals), with buttons such as **Sign DELIVERY**, **Sign DROP**, **Sign PICKUP**, **Drop Completed** and **Transfer Completed**, and a **Refresh** button at the bottom. See [Driver Workflow](driver-workflow.md) for what these mean for drivers.

This list only shows in-progress orders (from the first page of results) that are ready for a signature or a return and where the **assigned driver** matches the person signed in. It compares the driver assigned on the order with your own user number, but drivers and web users are numbered separately. As a result:

- For an office or customer user the list is **usually empty**: you see only the **Refresh** button and the **View normal site** link.
- It **can show orders that have nothing to do with you**, when the driver assigned to an order happens to have the same number as your user account.

!!! warning "Don't use the Sign or Completed buttons as an office or customer user"
    Orders that appear in your phone list are not "your" orders. The **Sign ...**, **Drop Completed** and **Transfer Completed** buttons are meant for the assigned driver. Tap **View normal site** and work from the normal **Orders** page instead.

### Switching to the normal site

1. Sign in, then scroll to the bottom of the **Orders** page in the phone layout.
2. Tap **View normal site**.
3. UTX Freight opens the normal **Orders** page, with the left sidebar, top bar and user menu described above. It stays on the normal site for the rest of your browser session.

To go back to the phone layout, add `?mobile=1` to the end of the address (for example, after `/orders`) and open it. The normal UTX Freight screens have no link back to the phone layout. On a phone, your company's public home page (the **Home** link) shows a **View mobile site** link at the bottom, which also switches the phone layout back on.

!!! tip "Bookmark the normal site on your phone"
    Add `?mobile=0` to the end of your UTX Freight address (for example, the sign-in page or `/orders`) and bookmark it. Opening that bookmark turns the phone layout off right away, even after you have logged out.

!!! info "Drivers, brokers and yard workers"
    Drivers, brokers and yard workers should stay on the phone layout. Their order list, signatures and container search only exist there. See [Driver Workflow](driver-workflow.md), [Yard Management](yard-management.md) and [Mobile Users](mobile-users.md).

## :fontawesome-solid-ban: When You Don't Have Access

- If you open a page or link your role isn't allowed to use (for example, a bookmarked URL), UTX Freight sends you back to your starting page. Nothing is changed. Because the starting page is itself reached through a redirect (to **Orders** or **Warehouse** :fontawesome-solid-arrow-right: **Orders**), you usually don't see an error message: you simply land on your starting page.
- If you open **Dispatch** without Dispatch access (anyone other than Admin, Manager, Dispatch or Customer Service), you are sent to **Orders**.
- Most sidebar and user-menu items you can't use are hidden. The exceptions are **Settings** for Managers, **Edit Profile** for Warehouse and Garage users, and **Orders** for Garage users: these are shown but send you back to your starting page.

## :fontawesome-solid-comment-dots: Sending Feedback

Use **Feedback** in the top bar to send a bug report, suggestion or general comment straight to the UTX team.

<!-- TODO: Screenshot — "We'd love your feedback" modal with type and importance buttons -->

1. Click :fontawesome-solid-comment-dots: **Feedback** in the top bar. The **We'd love your feedback** window opens.
2. Under **What type of feedback?**, choose **General** (default), **Bug Report** or **Suggestion**.
3. Under **How important is this?**, choose **Low**, **Normal** (default) or **Urgent**.
4. Type your message in **Your Feedback** (the hint text changes with the type you picked). You can type up to **2000 characters**. Under the box you see **Please enter at least 10 characters**, then **N more characters needed**, then a counter such as **42 / 2000**. Leading and trailing spaces don't count.
5. Click **Send Feedback**. The button stays disabled until you have typed at least 10 characters. Click **Cancel** to close without sending.
6. A **Thank you!** confirmation appears and the window closes.

As the form says, your feedback is sent to the development team along with the current page for context. The page address (including any filters in it) and your browser details (browser and window size) are attached automatically, so you don't need to describe where you were.

!!! tip "Writing a useful bug report"
    Choose **Bug Report**, open the feedback form from the page where the problem happens, and describe what you clicked, what you expected and what happened instead. Include order or invoice numbers if relevant.

!!! warning "Where Feedback is not available"
    The **Feedback** button is not on the Garage screens or on the mobile (phone) screens. Drivers and other mobile users can't send feedback this way. Contact your dispatcher or Admin instead.

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-key: I never received the password reset email

!!! info "Solution"
    Check your spam folder and make sure you typed the same email you sign in with. If the address isn't registered, the form shows **Email not found** instead of sending anything. If it still doesn't arrive, ask your Admin to check your email address under **Customers**. Remember that the link only works for 6 hours.

### :fontawesome-solid-clock: My reset link says the token has expired

!!! info "Solution"
    The message reads "Reset password token has expired, please request a new one". Reset links are valid for 6 hours. Click **I forgot my password** again and use the newest email.

### :fontawesome-solid-eye-slash: A menu item my colleague has is missing for me

!!! info "Solution"
    Menu items depend on your role, on add-ons (Warehouse, Garage, Fuel Surcharge), on whether your account is intermodal, and on some account settings. Ask your Admin to check your role. See [User Roles](user-roles.md) and [Add-ons & Options](add-ons-and-options.md).

### :fontawesome-solid-gear: I'm a Manager and Settings sends me back

!!! info "Solution"
    Managers see **Settings** in the user menu, but only Admins can open it. A Manager who clicks it lands back on their starting page. Ask an Admin to make the change.

### :fontawesome-solid-building: I don't see the office switcher

!!! info "Solution"
    The switcher only appears when multi-office is enabled and you are assigned to more than one office. An Admin can add offices to your user. See [Multi-Office](multi-office.md).

### :fontawesome-solid-envelope: I'm getting too many order emails

!!! info "Solution"
    Go to **Edit Profile**, untick **Email Notifications**, and click **Save Changes**.

### :fontawesome-solid-screwdriver-wrench: I have the Garage role and signing in doesn't open the Garage

!!! info "Solution"
    The sign-in redirect has no Garage destination. Go straight to the Garage **Work Orders** page (`/garage/work_orders` on your UTX Freight site) and bookmark it.

### :fontawesome-solid-mobile-screen-button: I opened UTX Freight on my phone and my orders list is empty / looks wrong

!!! info "Solution"
    On a phone, office and customer users get the phone layout, which shows the drivers' order list (headings such as **Import: Deliver to client** or **Import: Return empty**). That list matches orders against the assigned driver, so for you it is usually empty, or it shows orders that aren't yours. Scroll to the bottom and tap **View normal site** to get the normal **Orders** page. If your address starts with `mobile.`, use your regular UTX Freight address instead. See [Using UTX Freight on a Phone](#using-utx-freight-on-a-phone-office-and-customer-users).

### :fontawesome-solid-mobile-screen: I'm a driver. Where do I sign in?

!!! info "Solution"
    Drivers use **Mobile Login** or the login link sent by dispatch, not the email and password sign-in. See [Mobile Users](mobile-users.md) and [Driver Login Links](driver-login-links.md).

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips"
    - Only tick **Remember me** on your own device, and always **Logout** on shared computers.
    - Keep your **Mobile #** and **Email** up to date so dispatch and customers can reach you.
    - In multi-office accounts, check the office name in the top bar before creating orders or invoices.
    - Use **Feedback** from the page where something went wrong. The page is attached for you.
    - Note the **Release** number at the bottom of the sidebar when you contact support.
    - On a phone, tap **View normal site** right after signing in, or bookmark your address with `?mobile=0` at the end.
