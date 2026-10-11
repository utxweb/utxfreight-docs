# Application Settings

The **Settings** page holds the company-wide values UTX Freight uses on invoices, PODs and outgoing emails: tax and NIR numbers, invoice terms and message, date limits for orders and invoicing, how email is delivered, and the sender addresses.

## :fontawesome-solid-circle-info: Overview

- There are **two screens**: a read-only **Settings** page (a table of every value with a short description) and an **Edit Setting** form where you change them. See [The two screens](#the-two-screens).
- There is one set of settings for the whole system. It is not per office or per customer.
- The settings are grouped as **Order**, **Invoice**, **POD**, **Email Delivery Method**, the SMTP mailer sections, and **Administrative Email Addresses**.
- Emails leave the system through one of two **delivery methods**: **SMTP** (your own mail server) or **Postmark** (an email service managed by UTX).
- With SMTP, two mail accounts are used: the **Invoice Mailer** account sends invoices and statements, and the **Notification Mailer** account sends order emails, PODs, invoicing reminders, alert digests and feedback. A few emails (Garage emails, password-reset and invitation emails) do not pick an account themselves, see [Which account sends which email](#administrative-email-addresses).
- Every email field has a fallback: if you leave it blank, UTX Freight uses the default UTX configured for your system.
- The **Settings** page also has a **Test Email Configuration** box and, if you have container tracking, an **Alert Email Subscriptions** box.
- Every change to the settings is recorded with who made it and what changed.

## :fontawesome-solid-bolt: Quick Start

1. Click your **name** at the top of the screen :fontawesome-solid-arrow-right: :fontawesome-solid-gear: **Settings**.
2. Click **Edit settings** (top right).
3. Change the values you need, for example **GST Number**, **QST Number** and **NIR Number**.
4. Click **Save Changes**. You are returned to the **Settings** page with the message *Settings were successfully updated.*
5. If you changed anything email-related, type your own address in **Test Email Configuration** and click **Send Test**.

## :fontawesome-solid-lock: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Full access: view the **Settings** page, edit settings, send test emails, manage alert subscriptions. |
| :fontawesome-solid-user-tie: **Manager** | The **Settings** item appears in the user menu, but opening it is refused: you are sent back to the dashboard with a "not authorized" message. Ask an Admin to make the change. |
| :fontawesome-solid-headset: **Dispatch** / :fontawesome-solid-calculator: **Accountant** / **Customer Service** | No menu item and no access. |
| :fontawesome-solid-warehouse: **Warehouse** / :fontawesome-solid-wrench: **Garage** | No access. Garage has its own settings page (see [Garage Settings & Taxes](garage-settings-and-taxes.md)). |
| :fontawesome-solid-user: **Customer / Driver** | No access. |

**To navigate:** click your **name** at the top of the screen to open the user menu :fontawesome-solid-arrow-right: :fontawesome-solid-gear: **Settings**. See [Navigation & Account](navigation-and-account.md).

!!! info "Super User menu"
    Some people see an extra :fontawesome-solid-user-shield: **Super User** item under **Settings** in the user menu. That menu is for UTX staff only (system monitoring, audit trail, account maintenance). It is not part of your company's settings and is not described in these docs.

The **Manage …** items (cities, zones, terminals and so on), **Charge Types**, **Expense Types** and **Manage Taxes** are in the same user menu but are **not** on the Settings page. See [User Roles](user-roles.md) for how roles work.

## :fontawesome-solid-table-columns: The Two Screens

### Settings page (read-only)

The page titled **Settings** (*Application global settings*) shows, from top to bottom:

1. **Alert Email Subscriptions**: only if your system has a container tracking add-on. See [Alert Email Subscriptions](#alert-email-subscriptions).
2. **Test Email Configuration**: see [Testing your email configuration](#testing-your-email-configuration).
3. A table with the columns **Group**, **Setting**, **Value** and **Description**.

What the table shows for email:

- The **Delivery Method** row shows the active method as a badge: **SMTP** or **POSTMARK**.
- With **SMTP**, the **General SMTP**, **Invoice Mailer** and **Notification Mailer** rows are shown. Passwords are always shown as `********`.
- With **Postmark**, those SMTP rows are replaced by a **Postmark** group showing **API Token** (*Configured* or *Not configured*) and **Message Stream**.
- The SMTP and **Administrative Emails** rows show the value **actually in use**. If a field is blank in the form, you see the UTX default here instead of an empty cell.

!!! warning "Some on-screen descriptions are out of date"
    The **Description** column is short and in a few places not accurate. Rely on this page instead:

    - **Order Archive Cutoff Date** says it applies to the "Orders / Search and Dispatch pages". It does **not** affect the **Dispatch** board.
    - **Order Start Date** says "orders completed after this date". The filter is actually on the order's **delivery date**, on or after the date.
    - **Admin Email** says "Devise sender". It does **not** set the sender of password-reset or invitation emails.
    - **Invoice 'From' Override** says it "overrides accountant email". It does not change the sender of invoices.
    - **Message** says it shows "in the header of each invoice". Where it appears depends on your invoice layout.

### Edit Setting form

Click **Edit settings** on the Settings page to open the **Edit Setting** form. It is split into sections: **Order Settings**, **Invoice Settings**, **POD Settings**, **Email Delivery Method**, **General SMTP Settings**, **Invoice Mailer Settings**, **Notification Mailer Settings** and **Administrative Email Addresses**.

- Click **Save Changes** to save (the button reads *Please wait...* while saving), or **Cancel** to go back without saving.
- When **Postmark** is selected, the three SMTP sections are hidden.
- Date fields open a date picker.

### Label differences between the two screens

Several fields have a different name on each screen:

| Settings page (Group / Setting) | Edit Setting form (Section / Field) |
|--------------------------------|--------------------------------------|
| Order / **Order Archive Cutoff Date** | Order Settings / **Order archived at** |
| Invoice / **Default Terms** | Invoice Settings / **Default Terms for all companies** |
| Invoice / **Order Start Date** | Invoice Settings / **Invoice order start date** |
| Invoice / **Message** | Invoice Settings / **Invoice Message** |
| POD / **POD Footer** | POD Settings / **POD Message** |
| Invoice Mailer / **Domain**, **Username**, **Password** | Invoice Mailer Settings / **Invoice Domain**, **Invoice Username**, **Invoice Password** |
| Notification Mailer / **Domain**, **Username**, **Password** | Notification Mailer Settings / **Notification Domain**, **Notification Username**, **Notification Password** |
| Administrative Emails / **Invoice 'From' Override** | Administrative Email Addresses / **Invoice 'From' Address Override** |
| Administrative Emails / **Invoice Default CC** | Administrative Email Addresses / **Invoice Default CC Address** |

The other labels (**GST Number**, **QST Number**, **NIR Number**, **Email Delivery Method**, **SMTP Address**, **SMTP Port**, **SMTP Authentication**, **Admin Email**, **Accountant Email**) are the same on both.

<!-- TODO: Screenshot — Settings page (read-only table) with the Test Email Configuration box -->
<!-- TODO: Screenshot — Edit Setting form, Order / Invoice / POD sections -->

## :fontawesome-solid-box: Order Settings

| Field | What it does |
|-------|--------------|
| **Order Archive Cutoff Date** (form: **Order archived at**) | Only orders **created** on or after this date appear on the **Orders** page: every tab (**All**, **In Progress**, **New**, **App. Made**, **Dispatched**, **Completed**, **Not Invoiced**, **Late Invoicing**) and order searches. Older orders are not deleted, they are just left out of these lists. It also limits the orders counted in the invoicing reminder email. It does **not** affect the **Dispatch** board, invoices or reports. New systems start at 2010-01-01. |

!!! tip "Use it for speed"
    If your Orders page is slow because of years of history, move the archive cutoff forward (for example to the start of last year). You can move it back at any time to see older orders again.

## :fontawesome-solid-file-invoice-dollar: Invoice Settings

| Field | What it does |
|-------|--------------|
| **GST Number** | Your GST registration number. Printed in the totals area of the invoice, on the line **G.S.T / T.P.S** followed by the number. Depending on the invoice layout UTX set up for your system, the line is printed on every invoice or only on invoices that have a tax. Suggested format: `#00000000RT0001`. |
| **QST Number** | Your QST registration number. Printed on the invoice on the line **Q.S.T / T.V.Q.** followed by the number, under the same rule as **GST Number**. Suggested format: `#0000000000TQ0001`. |
| **Default Terms** (form: **Default Terms for all companies**) | The terms pre-selected when you create a **new** invoice. The dropdown is grouped: **Most Common** (Due on Receipt, 30 Days, 10 Days, 45 Days) and **Other** (15 Days, 21 Days, 60 Days, 90 Days). New systems start at **15 Days**. You can still change the terms on each invoice. Changing this setting does **not** change existing invoices. |
| **Order Start Date** (form: **Invoice order start date**) | Only completed orders with a **delivery date** on or after this date are offered when you create or edit an invoice. The same limit applies to the **Not Invoiced** and **Late Invoicing** tabs on the Orders page, the invoicing reminder email, and the **Standard** aged receivables report (invoices dated before it are left out, see [Aged Receivables](aged-receivables.md)). Use it if you invoiced outside UTX Freight before. New systems start at 2010-01-01. |
| **Message** (form: **Invoice Message**) | Free text printed near the top of every invoice. Depending on your invoice layout it appears in red bold next to **TERMS**, or in small text under the **BILL TO** customer address. Use it for payment instructions or other accounting information. Line breaks are kept. |

!!! warning "Keep a date in Order Start Date"
    If you clear **Order Start Date**, no completed orders are offered on new invoices. Set it to an early date (for example 2010-01-01) instead of leaving it blank.

## :fontawesome-solid-file-signature: POD Settings

| Field | What it does |
|-------|--------------|
| **NIR Number** | Your NIR (CTQ) number. Printed on the POD as **NIR - CTQ#:** followed by the number, and also on every invoice as **N.I.R** followed by the number. Suggested format: `R-000000-0`. |
| **POD Footer** (form: **POD Message**) | Free text printed at the bottom of every POD document. Line breaks are kept. |

See [Order Documents & POD](order-documents-and-pod.md) for the POD itself.

!!! info "Setup checklist"
    The [Setup Checklist](setup-checklist.md) step **Add your GST, QST and NIR numbers** is done once **GST Number**, **QST Number** and **NIR Number** are all filled in. Its **Open Settings** button opens the **Edit Setting** form. These are your own registration numbers, not tax rates; tax rates are under **Manage Taxes** (see [Charge Types & Taxes](charge-types-and-taxes.md)).

## :fontawesome-solid-paper-plane: Email Delivery Method

In the **Email Delivery Method** section, choose one:

| Option | Meaning |
|--------|---------|
| **SMTP — Use your own SMTP server credentials** | Emails are sent through the SMTP server and accounts in the three SMTP sections below. This is the default. |
| **Postmark — Use the Postmark email API** | Emails are sent through Postmark, an email service set up and managed by UTX. The SMTP sections are hidden and ignored. |

### How Postmark works

- The Postmark access token is managed by UTX, not entered in Settings. Once Postmark is the saved method, the form shows a **Postmark Status** line (**API Token:** **Configured** or **Not set**) and the Settings page shows an **API Token** row (**Configured** or **Not configured**). If it is not configured, emails cannot be sent: contact UTX support before switching.
- **Message Stream** is set by UTX for your system and is shown for information only.
- The **From** address of each email is rewritten to a UTX sending address for your system. The display name (for example your company name) is kept.
- The original From address (for example your **Accountant Email**) is put in **Reply-To**, so when a customer clicks Reply, the answer goes to your real mailbox.

!!! tip "Talk to UTX before switching"
    Switch to Postmark only when UTX support has confirmed it is set up for your system. You can switch back to SMTP at any time; your saved SMTP values are kept.

## :fontawesome-solid-server: SMTP Settings (SMTP only)

These three sections only apply when **Email Delivery Method** is **SMTP**.

### General SMTP Settings

Shared by both mail accounts.

| Field | What it does |
|-------|--------------|
| **SMTP Address** | Your mail server's host name, for example `smtp.example.com`. |
| **SMTP Port** | The server port, for example `587`. Port **465** uses an encrypted (SSL/TLS) connection from the start. Any other port (such as 587) starts unencrypted and upgrades with STARTTLS when the server offers it. |
| **SMTP Authentication** | How the account logs in: `plain`, `login` or `cram_md5`. |

### Invoice Mailer Settings

The account used to send **invoice** emails and **statement of account** emails (manual and automatic).

| Field | What it does |
|-------|--------------|
| **Invoice Domain** | The domain announced to the mail server, usually your email domain (for example `example.com`). |
| **Invoice Username** | The login of the mail account, usually a full email address. |
| **Invoice Password** | The password of that account. |

### Notification Mailer Settings

The account used for every other email from UTX Freight.

| Field | What it does |
|-------|--------------|
| **Notification Domain** | The domain announced to the mail server. |
| **Notification Username** | The login of the mail account. |
| **Notification Password** | The password of that account. |

### Password handling

- The password fields are always empty when you open the form (placeholder *Leave blank to keep current*). Leave them blank to keep the saved password.
- Type a new value only when you want to change it. Saving a blank field never erases the saved password.
- Passwords are never shown: the Settings page always displays `********`.
- If no password was ever saved, the UTX default for your system is used.

## :fontawesome-solid-at: Administrative Email Addresses

| Field | What it really does |
|-------|---------------------|
| **Admin Email** | The **From** address (with your company name as display name) of notification emails: new order, order dispatched, order completed, invoicing reminders, the container tracking alert digest, and feedback sent to UTX. It is also the contact address printed in invitation emails (*Have questions? Contact … at …*) and receives a BCC copy of every Garage statement of account. It does **not** set the sender of password-reset or invitation emails; those come from the UTX configuration of your system. |
| **Accountant Email** | The **From** address of all invoice, statement of account and POD emails, and of Garage invoices, statements and work summaries. |
| **Invoice 'From' Override** (form: **Invoice 'From' Address Override**) | Pre-fills a hidden **From** field on the **Send invoice to customer** and **Send statement to customer** windows, and is checked for **automatic statements**. It does **not** change the sender of the email: invoices and statements always go out from **Accountant Email**. The value (yours, or the UTX default if yours is blank) must be a valid address (`accounting@example.com` or `Accounting Dept <accounting@example.com>`). If it is missing or invalid, sending an invoice or statement is refused with *Please correct the email address and try again.*, and automatic statements are not sent. |
| **Invoice Default CC** (form: **Invoice Default CC Address**) | Pre-fills the **CC** field when you email an invoice or a statement. You can edit or remove it in the window before sending. For **automatic statements** it is added to the customer's own statement CC. It is also used as the hidden **From** field of the POD send window, so if it is blank (and there is no UTX default), sending a POD fails with *Sending POD Failed!* The POD itself is still sent from **Accountant Email**. |

!!! info "Which account sends which email (SMTP)"
    | Email | Mail account | From address |
    |-------|-------------|--------------|
    | Invoice (with PODs and documents) | Invoice Mailer | Accountant Email |
    | Statement of account (manual or automatic) | Invoice Mailer | Accountant Email |
    | POD email to customer | Notification Mailer | Accountant Email |
    | New order, order dispatched, order completed | Notification Mailer | Admin Email |
    | Invoicing reminder | Notification Mailer | Admin Email |
    | Container tracking alert digest | Notification Mailer | Admin Email |
    | Feedback sent to UTX | Notification Mailer | Admin Email |
    | Test invoice / Test notification | Invoice Mailer / Notification Mailer | Accountant Email / Admin Email |
    | Garage invoice, statement of account, work summary | Not chosen (see below) | Accountant Email |
    | Password reset, invitation | Not chosen (see below) | Sender set by UTX for your system |

    Emails marked *Not chosen* do not select a mail account themselves: they go through whichever of the two accounts the application used last (normally the Notification Mailer). So that they always go out, make sure both accounts are allowed to send as **Accountant Email** (Garage emails) and that the UTX sender for password-reset and invitation emails is accepted by your server.

    With **Postmark**, all of them go through Postmark, and the From is rewritten as described above.

!!! warning "POD emails mix the two"
    PODs are sent through the **Notification Mailer** account but **from** the **Accountant Email**. If your mail server only lets an account send as its own address, POD emails can be rejected ("sender not allowed"). Either use the same mailbox for both, or allow the notification account to send as the accountant address.

!!! warning "Sender changes and restarts"
    For most emails sent while people work in the app (order emails, invoices, statements, PODs, feedback), the **From** address is read when the application starts. After changing **Admin Email** or **Accountant Email**, the test emails and Garage emails use the new address right away, but those other emails may keep the old one until the application is restarted. Scheduled emails (automatic statements, invoicing reminders, alert digests) pick up the change on their next run. Ask UTX support if the old sender keeps appearing.

See [Notifications & Emails](notifications-and-emails.md) for who receives each email, and [Invoice Email & Payments](invoice-email-and-payments.md) for the send window.

## :fontawesome-solid-life-ring: Blank Fields and UTX Defaults

All email-related fields fall back to a default that UTX set when your system was built, if you leave them blank:

**SMTP Address**, **SMTP Port**, **SMTP Authentication**, the Invoice and Notification **Domain**, **Username** and **Password**, **Admin Email**, **Accountant Email**, **Invoice 'From' Override**, **Invoice Default CC**.

- The Settings page shows the effective value, so a blank field shows the UTX default there.
- To go back to the UTX default, clear the field and save (this does not work for passwords, which can only be replaced).
- The non-email fields (dates, GST, QST, NIR, messages) have no UTX fallback.

!!! info "Setup checklist"
    The [Setup Checklist](setup-checklist.md) step **Your email is configured** is always marked done, because sending was set up by UTX when your system was built. Its **Open Settings** button lets you check the sender addresses customer replies go to.

## :fontawesome-solid-envelope-circle-check: Testing Your Email Configuration

The **Test Email Configuration** box is at the top of the Settings page.

1. Type an email address in the box (placeholder *Enter recipient email*).
2. Click **Send Test** (it reads *Sending...* while it works).
3. Two emails are sent with the **saved** settings:
    - **Test *Company* notification configuration**: through the Notification Mailer, from **Admin Email**.
    - **Test *Company* invoice configuration**: through the Invoice Mailer, from **Accountant Email**.
4. Check the inbox (and spam folder) for both.

Save your changes before testing: the test uses what is saved, not what is typed in an open form.

| Message | Meaning |
|---------|---------|
| *Test emails sent successfully to …* | Both emails were accepted by the mail server (or Postmark). |
| *Email test failed. Notification Failed: …* | The notification email could not be sent. The text after it is the mail server's error. |
| *Email test failed. … Invoicing Failed: …* | The invoice email could not be sent. Both failures can appear in the same message. |
| *Invalid or missing recipient email address.* | The address box was empty or had no `@`. |

## :fontawesome-solid-bell: Alert Email Subscriptions

This box only appears if your system has a container tracking add-on. Under **Container Tracking Alerts** you choose which users receive the daily container tracking alert digest email.

1. Pick a user in **— Select a user —**. Only active users of your own company are listed, and users already subscribed are left out.
2. Click **Add Subscriber**.
3. To stop the emails for someone, click **Remove** on their row and confirm.

The list shows **Name**, **Email** and **Role** of each subscriber. The digest is sent from **Admin Email** through the Notification Mailer. See [Container Alerts](container-alerts.md) for what the digest contains.

## :fontawesome-solid-clock-rotate-left: Change History

Every save of the settings is recorded: who made the change, when, and the old and new values. The history is not shown on the Settings page; UTX support can look it up for you (for example to find out who changed the **Accountant Email**).

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-ban: I changed Admin Email but password-reset emails still come from another address

!!! info "Solution"
    Password-reset and invitation emails do not use **Admin Email**. Their sender is part of the UTX configuration of your system. Contact UTX support to change it.

### :fontawesome-solid-ban: I set Invoice 'From' Override but invoices still come from the accountant address

!!! info "Solution"
    That is expected. Invoices, statements and PODs are always sent from **Accountant Email**. Change **Accountant Email** instead.

### :fontawesome-solid-ban: Sending an invoice or statement fails with "Please correct the email address and try again"

!!! info "Solution"
    First check the **To**, **CC** and **BCC** addresses in the window. If they are correct, check **Invoice 'From' Override** on the Settings page: it must show a valid address. Fill it in (for example with your **Accountant Email**) and save.

### :fontawesome-solid-ban: Sending a POD always fails

!!! info "Solution"
    Check that **Invoice Default CC** has a valid address (or that the UTX default is used). The POD window uses it as a hidden From value and refuses to send without it. If the error mentions the sender, see [POD emails mix the two](#administrative-email-addresses).

### :fontawesome-solid-ban: Orders are missing from the Orders page

!!! info "Solution"
    Check **Order Archive Cutoff Date**. Orders created before it do not appear on the Orders page or in searches. Move the date back and save.

### :fontawesome-solid-ban: A completed order does not appear when I create an invoice

!!! info "Solution"
    Check the order's **delivery date** against **Order Start Date**. Orders delivered before that date are not offered on invoices and do not appear in **Not Invoiced** or **Late Invoicing**. Also check that the order is **Completed** and not already on another invoice.

### :fontawesome-solid-ban: The test email fails with a timeout or connection error

!!! info "Solution"
    Check **SMTP Address** and **SMTP Port**. Use **465** only if your server expects SSL from the start; use **587** for STARTTLS. If the error is about authentication, re-type the password in the right mailer section (blank keeps the old one) and check **SMTP Authentication**.

### :fontawesome-solid-ban: Only one of the two test emails arrives

!!! info "Solution"
    The two tests use different accounts. If the invoice test fails, check **Invoice Mailer Settings**; if the notification test fails, check **Notification Mailer Settings**. The error after *Invoicing Failed:* or *Notification Failed:* tells you why.

### :fontawesome-solid-ban: I'm a Manager and Settings sends me back to the dashboard

!!! info "Solution"
    Managers see the **Settings** menu item but cannot open the page. Ask an Admin to make the change.

## :fontawesome-solid-star: Best Practices

!!! tip "Best Practices"
    - Fill in **GST Number**, **QST Number** and **NIR Number** before sending your first invoice.
    - After any email change, save and then use **Send Test** with your own address.
    - Use a mailbox you actually read for **Accountant Email** and **Admin Email**: with Postmark, customer replies go there.
    - Keep **Invoice 'From' Override** and **Invoice Default CC** filled in with valid addresses, so invoices, statements and POD emails can be sent and you keep a copy of invoices and statements.
    - Never clear **Order Start Date** or **Order Archive Cutoff Date**; move them instead. A blank **Order Start Date** stops completed orders from being offered on new invoices.
