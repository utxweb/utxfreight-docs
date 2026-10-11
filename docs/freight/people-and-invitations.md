# Users, Contacts & Invitations

Add people to a company, send and resend their invitation, edit their details, and assign staff roles, offices and notification settings.

## :fontawesome-solid-users: Overview

In UTX Freight, every login is a **person** who belongs to a **company** on the **Customers** page. The same screens are used for customer contacts and for your own staff.

- :fontawesome-solid-user: **Customer contacts** are people under a customer company. Orders are placed on their behalf, and they can receive order emails and log in to see their orders.
- :fontawesome-solid-house: **Staff accounts** (Admin, Manager, Dispatch, Customer Service, Accountant, and Warehouse or Garage with those add-ons) are people under **your own company**, shown on the Customers page as **Your Company: <name>**.
- :fontawesome-solid-envelope: **Invitations**: when you add a person, UTX Freight immediately emails them an invitation. They click **Accept invitation**, choose a password, and their account is ready.
- :fontawesome-solid-user-tag: **Every new person starts with the Customer role** and is assigned to the office you are currently working in. An Admin changes the role afterwards for staff.
- :fontawesome-solid-bell: **Email Notifications** and **Active for orders** are per-person settings that control order emails and whether the person appears in the order form.

!!! info "Drivers are not added here"
    Drivers, yard workers and brokers use the mobile app and are managed separately. See [Mobile Users](mobile-users.md).

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Customers** from the left menu.
2. Find the company (for staff, your own company: **Your Company: <name>**).
3. Click :fontawesome-solid-plus: **Add Person**.
4. Enter **First Name**, **Last Name** and **Email** (required).
5. Click **Add this person**. You see **An invitation email has been sent to <email>.**
6. **For staff only:** an Admin clicks **Edit Person** on the new row, picks the **Role** (and **Offices**), and clicks **Save Changes**.

!!! warning "The invitation goes out immediately"
    The email is sent as soon as you click **Add this person**. Double-check the address first.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access Level |
|------|-------------|
| :fontawesome-solid-user-shield: **Admin** | Add, edit and delete any person. Only Admins see and can change **Company**, **Role**, **Offices** and **Can manage rates?** |
| :fontawesome-solid-user-tie: **Manager** | Add, edit and delete people in their own offices (see below), and edit their own details. Cannot change **Company**, **Role**, **Offices** or **Can manage rates?** |
| :fontawesome-solid-headset: **Dispatch / Customer Service** | Add and edit people in their own offices only when the edition option `dispatch_can_manage_customers` is on (off by default). Cannot delete people. Cannot change **Company**, **Role**, **Offices** or **Can manage rates?**. They can always edit their own details with **Edit Profile** |
| :fontawesome-solid-file-invoice-dollar: **Accountant, Customer** | No access to other people. They can edit their own details with **Edit Profile** |
| :fontawesome-solid-warehouse: **Warehouse, Garage** | No access to people, including their own profile. An Admin updates their details |

- Only **Admin** and **Manager** can delete a person. A dispatcher with `dispatch_can_manage_customers` on still sees the **Delete** button, but clicking it doesn't delete the person.
- Which people a Manager (or a dispatcher with the option on) can manage depends on [Multi-Office](multi-office.md):
    - **Multi-Office on**: any person who is assigned to at least one of their offices, including staff under your own company.
    - **Multi-Office off**: people whose company belongs to one of their offices. Your own company has no office, so staff accounts (other than their own) are managed only by Admins.
- If someone who isn't an Admin sends a role, company or office change anyway, UTX Freight ignores it.

**How to get there:**

- :fontawesome-solid-arrow-right: **Customers** > company box > **Add Person** (new person)
- :fontawesome-solid-arrow-right: **Customers** > company box > **Edit Person** on the person's row (existing person)
- :fontawesome-solid-arrow-right: Your name at the top of the screen > **Edit Profile** (your own details, for users who are not Admin or Manager)

---

## :fontawesome-solid-table: The People Table

Each company box on the **Customers** page lists its people. Deleted people are not shown.

| Column | What It Shows |
|--------|-------------|
| *(badge)* | **Owner** (green) for the account owner. For staff, the role name: **Dispatch** or **Customer Service** (blue), **Admin** or **Manager** (orange), other staff roles such as **Accountant** (light blue). Customer contacts have no role badge. A grey **Invited** badge is added while the person hasn't accepted their invitation |
| **Name** | First and last name |
| **Title** | Job title |
| **Email** | Email address (click to write to them) |
| **Phone** | Mobile # |
| **Notifs** | Whether **Email Notifications** is on |
| **Alerts** | Only with a container tracking add-on. Whether the person is subscribed to container tracking alerts. See [Container Alerts](container-alerts.md) |
| **Active** | Whether **Active for orders** is on |
| **Offices** | How many offices the person is assigned to |
| *(buttons)* | **Edit Person** and **Delete**, for users allowed to manage that person |

---

## :fontawesome-solid-user-plus: Adding a Person

1. On the **Customers** page, find the company.
2. Click :fontawesome-solid-plus: **Add Person**. The page **Add a person to <Company>** opens.
3. Fill in the fields below.
4. Click **Add this person** (or **Cancel** to go back to the Customers page).

![The Add Person form showing name, email, and contact fields](../images/customers-add-person.png)

**This person's name will be displayed next to their requests.**

| Field | Required | Description |
|-------|----------|-------------|
| **First Name** | Yes | Person's first name |
| **Last Name** | Yes | Person's last name |
| **Email** | Yes | Where the invitation is sent. This is also what they sign in with. Must not already be used by another person |

**The rest is optional. You can fill it in later if you'd like.**

| Field | Description |
|-------|-------------|
| **Title** | Job title |
| **Office #** | Office phone number |
| **Office Ext. #** | Office extension |
| **Mobile #** | Mobile number (shown in the **Phone** column) |
| **Fax #** | Fax number |

Below the fields, the **What happens now?** box says:

> *When you click the "Add this person" button below, we'll fire off a nice invitation to the email address you entered above. The email will contain a link to a web page where this person will complete the setup process by picking their own username and password. Plus, you can immediately start involving them in the system even before they've chosen their username and password.*

In practice, the person only chooses a password. Their username is the **Email** you entered.

### What happens when you click Add this person

- The person is created under the company and the invitation email is sent.
- You return to the **Customers** page with **An invitation email has been sent to <email>.**
- The person gets the **Customer** role, whatever company you added them to.
- The person is assigned to the office you are currently working in.
- **Email Notifications** and **Active for orders** are on.
- The person shows the **Invited** badge until they accept.
- You can place orders for them right away, before they accept.

If a required field is empty or the email is already in use, the form reloads with the error under the field and no invitation is sent.

!!! warning "Adding staff: set the role next"
    New people always start as **Customer**, even under your own company. Until an Admin sets their **Role** on **Edit Person**, a new staff member only has customer access.

---

## :fontawesome-solid-envelope-open-text: The Invitation Email

The email has the subject **Invitation instructions**. It contains:

- the heading *You're invited to join our tracking system.*
- *Hi <first name>, <your company> just set up an account for you.*
- *All you need to do is choose a password. It only takes a few seconds.*
- an **Accept invitation** link,
- a note that the account won't be created until they open the link and set a password,
- *Have questions? Contact <your company> at <admin email>*. The address is the admin email from your account settings.

### Accepting the invitation

1. The person clicks **Accept invitation** (signed out of UTX Freight).
2. The page *Hi there. Let's finish setting up your <your company> account!* opens.
3. They check their first and last name and enter a password twice. The hint reads *6 characters or longer with at least one number is safest.*
4. They click **Create your account**.

They are signed in straight away with **Your password was set successfully. You are now signed in.** and land on the dashboard. From then on they sign in with their email and that password. The **Invited** badge disappears and the resend box is no longer shown on **Edit Person**.

!!! info "Invitations don't expire"
    An invitation link stays valid until it is used or replaced by a resend. There's no time limit.

---

## :fontawesome-solid-paper-plane: Resending an Invitation

There's no resend button on the Customers page. Use the **Edit Person** page:

1. On the **Customers** page, click **Edit Person** on the row with the **Invited** badge.
2. At the top, a yellow box reads **<Name> hasn't accepted his invitation yet.** It shows when the last invitation was sent.
3. Choose one:
    - Click **resend the email**. You return to the Customers page with **Invitation email was successfully resend to <email>.**
    - Or copy the invite link shown in the box and send it to the person yourself (for example by text message or from your own email).

The yellow box is not shown to Customer users.

!!! warning "Resending replaces the link"
    **resend the email** creates a new invitation link. Links from earlier emails, and a link you copied before resending, stop working. If you copy the link, copy it again after any resend.

---

## :fontawesome-solid-user-pen: Editing a Person

1. On the **Customers** page, click **Edit Person** on the person's row.
2. Change the fields.
3. Click **Save Changes**. You return to the Customers page with **User was successfully updated.**

Click **Cancel** to leave without saving.

### Fields everyone can edit

| Field | Description |
|-------|-------------|
| **First Name** / **Last Name** | Required |
| **Email** | Required. Changing it changes the address the person signs in with |
| **Title** | Job title |
| **Office #**, **Office Ext. #**, **Mobile #**, **Fax #** | Phone numbers |
| **Email Notifications** | Checkbox. See [Email Notifications](#email-notifications) |
| **Active for orders** | Checkbox, with the note *Only active users will be available as the order suppliers*. See [Active for orders](#active-for-orders) |

### Admin-only fields

| Field | When it appears | Description |
|-------|-----------------|-------------|
| **Company** | Always, for Admins | The company the person belongs to. Change it to move a person to another customer or to your own company |
| **Role** | Admins, for people under your own company, except the **Owner** | The person's role. See [Assigning staff roles](#assigning-staff-roles-and-offices) |
| **Offices** | Same as **Role** | Checkboxes, one per office. Hint: **Do NOT assign more than one office to customers.** |
| **Can manage rates?** | Same as **Role**, and only when the saved role is **Dispatch** or **Customer Service** | See [Can manage rates?](#can-manage-rates) |

**Role** and **Offices** are never shown for people under a customer company, so people added to a customer company keep the **Customer** role and the office they were added in.

### :fontawesome-solid-user: Edit Profile (your own details)

Users who are not Admin or Manager edit their own details from the menu under their name at the top of the screen: **Edit Profile**. It opens the same form for their own account, without the admin-only fields. Warehouse and Garage users see the menu item but are not allowed to open their profile; an Admin edits their details instead.

Admins and Managers don't have **Edit Profile** in that menu. They edit their own details from **Customers**, under **Your Company**, with **Edit Person** on their own row.

---

## :fontawesome-solid-user-gear: Assigning Staff Roles and Offices

Staff accounts live under your own company on the Customers page. To set up a staff member:

1. Go to **Customers** and select your own company (the default filter).
2. Click **Add Person** in the **Your Company: <name>** box and add the person as described above.
3. As an Admin, click **Edit Person** on the new row.
4. Pick the **Role**.
5. Check the **Offices** the person works in.
6. Click **Save Changes**.

The **Role** list contains **Admin**, **Customer**, **Accountant**, **Dispatch**, **Manager** and **Customer Service**, plus **Warehouse** with the Warehouse add-on and **Garage** with the Garage add-on. See [User Roles](user-roles.md) for what each role can do.

To turn an existing person into a staff member, an Admin first changes their **Company** to your own company and saves. **Role** and **Offices** appear the next time you open **Edit Person**.

The **Owner** of the account has no **Role** or **Offices** fields.

!!! info "Offices"
    Staff in several offices can have several **Offices** checked. Customer contacts should stay in a single office. See [Multi-Office](multi-office.md).

### :fontawesome-solid-dollar-sign: Can manage rates?

**Can manage rates?** appears for **Dispatch** and **Customer Service** users, with the note *Specifies if this Dispatch can manage rates and charges across the app*. It is **on by default**.

- **On**: the user can manage rates and charges, including the rate and charge controls on orders that are reserved for users who can manage rates.
- **Off**: those order rate controls are not available to the user, and they can't manage **Charge Types**, **Expense Types** or **Manage Cities**, or view an order's audit history.

The checkbox only appears after the role has been saved as **Dispatch** or **Customer Service**. If you just changed the role, save first, then open **Edit Person** again. The setting only applies to Dispatch and Customer Service: Admins and Managers can always manage rates, and other roles don't use it. See [User Roles](user-roles.md).

---

## :fontawesome-solid-bell: Email Notifications

**Email Notifications** (the **Notifs** column) is on by default. It controls these emails:

| Email | Who gets it when Email Notifications is on |
|-------|--------------------------------------------|
| **New Order #<number> from <company>** (sent when an order is created) | **To:** every Admin with Email Notifications on and Active for orders on. **CC:** the Managers of the order's office with Email Notifications on |
| **Order #<number> is now dispatched** | The person the order is placed for (customer contact), when the order is dispatched |
| **Order Completed for order #<number>** | The person the order is placed for, when the order is completed |

Turn it off for a customer contact who doesn't want dispatched and completed emails, or for an Admin or Manager who doesn't want new-order emails.

Email Notifications doesn't control invitations, password resets, invoices, statements, container alerts or the **Invoicing Reminder**. See [Notifications & Emails](notifications-and-emails.md).

---

## :fontawesome-solid-toggle-on: Active for orders

**Active for orders** (the **Active** column) is on by default. The form note reads *Only active users will be available as the order suppliers*.

- **Off**: the person no longer appears in the order form's person list (**Place the order on behalf of**), in the warehouse order form, or in the **Default user** list on the customer form. Existing orders placed for them are not changed.
- It does **not** block login. A person with **Active for orders** off can still sign in. To remove someone's access, delete the person.
- For Admins, turning it off also stops the **New Order** email. Admin, Manager and Accountant users with it off also don't get the **Invoicing Reminder** email (a reminder about orders not yet invoiced, sent on Mondays, Wednesdays and Fridays when needed).

---

## :fontawesome-solid-trash: Deleting a Person

1. On the **Customers** page, click **Delete** on the person's row.
2. Confirm **Are you sure - this action cannot be reverted?**

The row disappears from the table right away.

!!! danger "This cannot be reverted"
    There's no way to restore a deleted person from the app.

What deleting does:

- The person disappears from the Customers page and from order forms.
- Their **Email Notifications** setting is turned off.
- Their stored email address is changed (a random prefix is added), so they can no longer sign in with it and the original address can be used for a new person.
- It's a soft delete: their record stays in the database, and orders placed for them keep their history.
- A company that has ever had people, including deleted ones, can't be deleted. See [Customers](managing-customers.md#deleting-a-customer).

Only **Admin** and **Manager** can delete people.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-envelope: The person never received the invitation

!!! info "Solution"
    Open **Edit Person** and check the email address. Then click **resend the email** in the yellow box, or copy the invite link from the box and send it yourself. Also ask the person to check their spam folder.

### :fontawesome-solid-link-slash: The invitation link says "The invitation token provided is not valid!"

!!! info "Solution"
    The link was replaced by a newer one (someone clicked **resend the email**), or the invitation was already accepted. Use the link from the most recent email, or copy it again from **Edit Person**. If the person already set their password, they just sign in with their email.

### :fontawesome-solid-user-lock: My new dispatcher only sees customer screens

!!! info "Solution"
    Every new person starts as **Customer**. An Admin must open **Edit Person** on their row under your own company, set the **Role** (and **Offices**), and save.

### :fontawesome-solid-eye-slash: I don't see the Role or Offices fields

!!! info "Solution"
    They are shown only to Admins, only for people under your own company, and never for the account **Owner**. To make a customer contact a staff member, change their **Company** to your own company, save, then edit them again.

### :fontawesome-solid-dollar-sign: I don't see Can manage rates?

!!! info "Solution"
    It appears only when the saved role is **Dispatch** or **Customer Service**. Save the role first, then reopen **Edit Person**.

### :fontawesome-solid-ban: A person doesn't appear in the order form

!!! info "Solution"
    Check that **Active for orders** is on for the person, that they aren't deleted, and that their company is active with a service that includes Intermodal (Warehouse for the warehouse order form). Unless [Multi-Office](multi-office.md) is on, the person must also be assigned to the office you are working in. See [Customers](managing-customers.md).

### :fontawesome-solid-right-to-bracket: I unchecked Active for orders but the person can still log in

!!! info "Solution"
    That's expected. **Active for orders** only controls the order lists. To remove access, delete the person.

### :fontawesome-solid-bell-slash: A customer gets dispatched/completed emails they don't want

!!! info "Solution"
    Open **Edit Person** and uncheck **Email Notifications**. Customers can also do this themselves from **Edit Profile**.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips for managing people"
    - Check the email address before clicking **Add this person**. The invitation goes out immediately.
    - Add staff under **Your Company**, then set their **Role** and **Offices** right away.
    - Give customer contacts a single office.
    - Turn off **Can manage rates?** for dispatchers who shouldn't see or change pricing.
    - Uncheck **Active for orders** for contacts who no longer place orders but whose history you want to keep. Delete only people who should lose access.
    - If you copy an invite link, copy it again after any resend.
