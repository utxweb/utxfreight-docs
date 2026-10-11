# Notifications & Emails

A reference of every email and on-screen notification UTX Freight sends: what triggers it, who receives it, the subject line, the sender, and which background jobs send things automatically.

## :fontawesome-solid-envelope: Overview

- :fontawesome-solid-bolt: **Automatic emails** are sent by the system when something happens (a new order is created, an order is dispatched or completed) or by a background job (invoicing reminder, automatic statements, container tracking digest, garage summaries and statements).
- :fontawesome-solid-hand-pointer: **User-triggered emails** are sent when someone clicks a button: invoices, statements, PODs, garage invoices, test emails, invitations, password resets and feedback.
- :fontawesome-solid-at: **Sender**: every email shows your company name as the display name. The address is either the **Admin Email** (notifications) or the **Accountant Email** (invoices, statements, PODs, garage emails) from [Application Settings](application-settings.md). Invitations and password resets are the exception: their sender is set by UTX for your system.
- :fontawesome-solid-server: **Mail account**: with **SMTP**, invoices and statements go through the **Invoice Mailer** account and order emails, PODs, reminders, digests and feedback go through the **Notification Mailer** account. With **Postmark**, everything goes through Postmark.
- :fontawesome-solid-bell: **Toasts** are the small notifications that slide in at the top of the screen after an action (for example **Invoice Sent!** or **Order Dispatched!**).
- :fontawesome-solid-share-from-square: **Driver sign-in links** are copied by dispatch and sent by you, by text message or email (see [Driver Login Links](driver-login-links.md)).

!!! info "One page for everything"
    This page lists every message in one place. The detailed how-to for each one lives on the feature page, linked in each section.

## :fontawesome-solid-bolt: Quick Start

1. An Admin checks the sender addresses in **Settings** (**Admin Email** and **Accountant Email**) and sends a test with **Test Email Configuration** > **Send Test**. See [Application Settings](application-settings.md).
2. Turn **Email Notifications** on or off for each person on **Edit Person**. It controls the new order, order dispatched and order completed emails only. See [Users, Contacts & Invitations](people-and-invitations.md).
3. Give each customer an **Accountant Email** so invoices and statements have a default recipient. See [Managing Customers](managing-customers.md).
4. If you have container tracking, choose who gets the digest in **Settings** > **Alert Email Subscriptions**. See [Container Alerts](container-alerts.md).
5. After sending an invoice or statement, watch the toast and the delivery status on the row (green **OK** / red **Failed!**). For a POD, watch the toast and the colour of the envelope.

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | What they can send or receive |
|------|-------------------------------|
| :fontawesome-solid-user-shield: **Admin** | Receives **New Order** emails (if Email Notifications is on) and the **Invoicing Reminder**. Sends invoices, statements and PODs. Sends test emails and manages alert subscriptions in **Settings**. |
| :fontawesome-solid-user-tie: **Manager** | Receives **New Order** emails in CC for orders of their office (if Email Notifications is on) and the **Invoicing Reminder**. Can send invoices, statements and PODs where their access allows it. |
| :fontawesome-solid-calculator: **Accountant** | Receives the **Invoicing Reminder**. Can send invoices. Sees the POD envelope, but can only send PODs if your system lets Accountants manage orders. |
| :fontawesome-solid-headset: **Dispatch** / **Customer Service** | Dispatching and completing orders triggers the customer emails. Can send PODs. |
| :fontawesome-solid-wrench: **Garage** (and Admins and Managers, with the Garage add-on) | Can send garage invoices, work summaries and statements. |
| :fontawesome-solid-user: **Customer** | Receives **Order #… is now dispatched** and **Order Completed for order #…** for their orders (if Email Notifications is on), and the invoices, statements and PODs you send them. |
| Any signed-in user | Can send **Feedback** to UTX from the top menu. Anyone can request a password reset from the sign-in page. |

See [User Roles](user-roles.md) for the full permission list.

---

## :fontawesome-solid-table-list: All Emails at a Glance

| Email | Subject | Trigger | To | From | Mail account (SMTP) |
|-------|---------|---------|----|------|---------------------|
| [New order](#new-order) | `New Order #<order number> from <customer company>` | An order is created | Admins with Email Notifications on; CC: Managers of the order's office with Email Notifications on | Admin Email | Notification |
| [Order dispatched](#order-dispatched-and-order-completed) | `Order #<order number> is now dispatched` | **Dispatch Order** | The person the order is placed for, if Email Notifications is on | Admin Email | Notification |
| [Order completed](#order-dispatched-and-order-completed) | `Order Completed for order #<order number>` | **Complete Order** | The person the order is placed for, if Email Notifications is on | Admin Email | Notification |
| [Invoicing reminder](#invoicing-reminder) | `Invoicing Reminder - <Weekday, Mon. DD>` (multi-office: `Invoicing Reminder (All Offices) - …`) | Background job, Monday / Wednesday / Friday | Active Admins, Accountants and Managers | Admin Email | Notification |
| [Invoice](#invoice-email) | What you type (pre-filled `<Your company> Invoice #<number>`) | **Send** in *Send invoice to customer* | What you type in To / Cc / Bcc | Accountant Email | Invoice |
| [Statement of account](#statement-of-account) | `<Your company> Statement of Account as of <YYYY-MM-DD>` (+ ` - <Office>` with multi-office) | **Send** in *Send statement to customer*, or the automatic statement job | Manual: what you type. Automatic: customer's Accountant Email | Accountant Email | Invoice |
| [POD](#pod-email) | `<Your company> Order #<order number> Delivered` | **Send** in *Send POD to client* | What you type in To / Cc / Bcc | Accountant Email | Notification |
| [Container tracking digest](#container-tracking-digest) | `Container Tracking — <N> alert(s)` | Background job | Each subscriber | Admin Email | Notification |
| [Invitation](#invitation-and-password-reset) | `Invitation instructions` | Adding or re-inviting a person | The invited person | Set by UTX | Not chosen (see below) |
| [Password reset](#invitation-and-password-reset) | `Reset password instructions` | **I forgot my password** | The person who asked | Set by UTX | Not chosen (see below) |
| [Feedback](#feedback) | `[<Category>] Feedback from <name> on <page>` | **Feedback** in the top menu | UTX support | Admin Email | Notification |
| [Test emails](#test-emails) | `Test <Your company> notification configuration` and `Test <Your company> invoice configuration` | **Send Test** in **Settings** | The address you type | Admin Email / Accountant Email | Notification / Invoice |
| [Garage invoice](#garage-emails) | `Invoice <number> from <Your company>` | **Email Invoice** | Garage customer's Email; CC: their Accountant Email | Accountant Email | Not chosen (see below) |
| [Garage work summary](#garage-emails) | `Work Summary <period> - <Your company>` | **Email to** button, or the automatic summary job | Garage customer's Email; CC: their Accountant Email | Accountant Email | Not chosen |
| [Garage statement](#garage-emails) | `Statement of Account as of <Mon DD, YYYY> - <Your company>` | **Email to** button, or the automatic statement job | Garage customer's Email; CC: Accountant Email; BCC: Admin Email | Accountant Email | Not chosen |

!!! info "\"Not chosen\" mail account"
    Garage emails, invitations and password resets do not have their own mail account setting. They normally go out through the **Notification Mailer** account. If you use SMTP, make sure **both** accounts are allowed to send as your **Accountant Email**. With Postmark this does not matter.

<!-- TODO: Screenshot — Settings page, Administrative Emails rows (Admin Email, Accountant Email) -->

---

## :fontawesome-solid-truck-fast: Order Emails

### New order {#new-order}

| Item | Value |
|------|-------|
| **Subject** | `New Order #<order number> from <customer company>` |
| **Trigger** | An order is created, whoever creates it (customer, dispatcher or admin). |
| **To** | Every active Admin (company and person not deleted, **Active for orders** on) who has **Email Notifications** on. |
| **CC** | The Managers of the order's office who have **Email Notifications** on. |
| **From** | Your company name and the **Admin Email**. |
| **Body** | *New order notification*, *<contact> from <customer company> submitted a new order* (the contact is the person the order is placed for, even if staff created it), the order number, client name (or *Container Transfer*), reference number, container number and terminals (import, export, transfer) or pickup and delivery addresses, and a **View new orders** link. |

**Not sent when** the order is a copy made with **Duplicate** (see [Order Duplication](order-duplication.md)).

!!! warning "Nobody gets the email?"
    The email only reaches Admins and Managers who have **Email Notifications** on. Make sure at least one Admin has it on. The order is always saved, even if the email cannot be sent.

### Order dispatched and order completed {#order-dispatched-and-order-completed}

| Item | Order dispatched | Order completed |
|------|------------------|-----------------|
| **Subject** | `Order #<order number> is now dispatched` | `Order Completed for order #<order number>` |
| **Trigger** | **Dispatch Order** in the dispatch window | **Complete Order** in the complete window |
| **To** | The person the order is placed for (the customer contact) | Same |
| **Condition** | That person has **Email Notifications** on | Same |
| **From** | Your company name and the **Admin Email** | Same |
| **Body** | *Status change notification for order #…*, the new status, **Appointment Date** and **Appointment Time**, then order details | The new status, **Empty container return date** (when set), then order details |

- **Make App.** never sends an email to the customer.
- The *View your orders* link at the bottom is only included when your system is set up to link emails back to the app (ask UTX support).
- After dispatching, the toast reads *The order was dispatched and a notification was sent to the customer with the appointment information.* (or the completed version). If the email cannot be sent, the message ends with **Sending email failed!** instead. See [Order Workflow](order-workflow.md).

### Invoicing reminder {#invoicing-reminder}

A reminder of completed orders that are still not invoiced.

| Item | Value |
|------|-------|
| **Subject** | `Invoicing Reminder - <Weekday, Mon. DD>`, for example *Invoicing Reminder - Friday, Oct. 09*. With [Multi-Office](multi-office.md): `Invoicing Reminder (All Offices) - <Weekday, Mon. DD>` |
| **Trigger** | A background job. It only sends on **Monday, Wednesday and Friday**. |
| **To** | Every active user with the **Admin**, **Accountant** or **Manager** role. **Email Notifications** does not apply: they get it either way. |
| **From** | Your company name and the **Admin Email**. |
| **Sent only when** | There is at least one completed, not-invoiced order delivered **2 weeks ago or earlier**, or with **no delivery date**. Orders from this week and last week alone do not trigger it. |

The table *Completed Orders waiting to be invoiced* has these columns:

| Column | Counts |
|--------|--------|
| **Over 2 Weeks ago** (red) | Not-invoiced completed orders delivered more than 2 weeks ago |
| **2 Weeks ago** (orange) | Delivered in the week two weeks back |
| **This Week** (green) | Delivered this week or last week |
| **Missing Date** (red) | No delivery date |
| **Total** | All not-invoiced orders |

With multi-office, there is one section per office, and only offices with something to report are included. The counts respect the **Order Archive Cutoff Date** and **Order Start Date** in [Application Settings](application-settings.md).

!!! tip "Seeing the late orders"
    The full list of orders waiting to be invoiced is on the **Late Invoicing** tab of the **Orders** page. That tab is shown to Admins and Managers.

---

## :fontawesome-solid-file-invoice-dollar: Billing Emails

### Invoice email {#invoice-email}

Sent from the envelope button on the **Invoices** list. The full procedure is in [Sending Invoices & Recording Payments](invoice-email-and-payments.md).

| Item | Value |
|------|-------|
| **Window** | *Send invoice to customer*: **To**, **Cc**, **Bcc**, **Subject**, **Include documents** |
| **Subject** | What is in **Subject**. Pre-filled as `<Your company> Invoice #<invoice number>`, with ` - PO#<PO or reference>` when the invoice has one order, and **REVISED** after the company name when the last send succeeded. |
| **To / Cc** | **To** is pre-filled with the customer's **Accountant Email**. **Cc** is pre-filled with the **Accountant Email (CC)** of your own company and of the customer. You can edit them. |
| **From** | Your company name and the **Accountant Email**. |
| **Attachments** | The invoice PDF, the signed or scanned POD of each order, and the order documents when **Include documents** is ticked. |
| **Mail account** | Invoice Mailer |

**Delivery status:** shown on the invoice row in the **Invoices** list. Success sets the sent date and **OK**, and a **new** invoice becomes **Invoiced**. A failure shows **Failed!** with the error.

!!! warning "Invoice 'From' Override must be valid"
    Sending invoices and statements (manual and automatic) needs a valid address in **Settings** > **Invoice 'From' Override** (or the UTX default if yours is blank). Otherwise sending is refused with **Sending Invoice Failed!** / **Sending Statement Failed!** and *…Please correct the email address and try again.* See [Application Settings](application-settings.md#administrative-email-addresses).

### Statement of account {#statement-of-account}

| | Manual | Automatic |
|---|--------|-----------|
| **How** | **Reports** > **Customer Reports**, **Email** button, window *Send statement to customer* (**To**, **Cc**, **Bcc**) | A background job on each customer's schedule. See [Automatic Statements](automatic-statements.md). |
| **To** | What you type (pre-filled with the customer's **Accountant Email**) | The customer's **Accountant Email** |
| **CC** | What you type (pre-filled with the **Accountant Email (CC)** of your company and of the customer) | The customer's **Accountant Email (CC)** and the **Invoice Default CC** |
| **Subject** | `<Your company> Statement of Account as of <YYYY-MM-DD>` | Same |
| **Multi-office** | Only the current office's invoices, and ` - <Office name>` is added to the subject | One statement per office with unpaid invoices |
| **Skipped when** | Never | No unpaid balance (status *Statement Not Sent (0.0$)*; with multi-office the office is simply skipped), customer inactive, or no valid **Accountant Email** or **Invoice 'From' Override** (nothing is sent and the status is not updated) |

- **From:** your company name and the **Accountant Email**. **Mail account:** Invoice Mailer.
- **Attachment:** *Statement of account as of <date>.pdf* or *.xlsx*, following the customer's **Default Statement Format**.
- **Delivery status:** the **Email** column on **Customer Reports** (green **OK** or red **Failed!**) and the sent date. See [Customer Statements](customer-statements.md).

### POD email {#pod-email}

Sent from the envelope in the **Email POD** column on **Orders** or **Dispatch** (shown to Admins, Managers, Accountants, Dispatch and Customer Service). The envelope only appears once the order has a signature or a scanned POD (or has been emailed before). See [Order Documents & POD](order-documents-and-pod.md).

| Item | Value |
|------|-------|
| **Window** | *Send POD to client*: **To**, **Cc**, **Bcc**, **Subject** |
| **To** | Pre-filled with the email of the order's delivery company (or the order's delivery email) |
| **Subject** | `<Your company> Order #<order number> Delivered` |
| **From** | Your company name and the **Accountant Email** |
| **Attachment** | The signed POD PDF, or the scanned POD if there is no signature |
| **Mail account** | Notification Mailer |

!!! warning "POD needs a valid Invoice Default CC"
    Sending a POD needs a valid address in **Settings** > **Invoice Default CC** (or the UTX default if yours is blank). Otherwise sending is refused with **Sending POD Failed!** and *The POD was not sent. Please correct the email address and try again.* See [Application Settings](application-settings.md#administrative-email-addresses).

**Delivery status:** the envelope colour and the toast. Blue: not delivered yet (tooltip *Send POD to client*). Green: last send delivered (tooltip *Last email delivered …*). Red: the last attempt failed.

---

## :fontawesome-solid-satellite-dish: Container Tracking Digest {#container-tracking-digest}

Only on systems with a container tracking add-on. Full details in [Container Alerts](container-alerts.md).

| Item | Value |
|------|-------|
| **Subject** | `Container Tracking — <N> alert` or `… alerts`, for example *Container Tracking — 3 alerts* |
| **Trigger** | A background job. |
| **To** | Each user in **Settings** > **Alert Email Subscriptions** > **Container Tracking Alerts**, one email each. |
| **From** | Your company name and the **Admin Email**. |
| **Content** | All alerts not emailed yet, with action items (pickup available, LFD approaching) first, and a **View Alerts Dashboard** link. With multi-office, grouped by office. |

- No email when there are no new alerts or no subscribers.
- Each alert is emailed once. If delivery fails for every subscriber, the alerts are kept for the next digest.

---

## :fontawesome-solid-user-plus: Account Emails

### Invitation and password reset {#invitation-and-password-reset}

| | Invitation | Password reset |
|---|-----------|----------------|
| **Subject** | `Invitation instructions` | `Reset password instructions` |
| **Trigger** | Inviting a new person, or **resend the email** on a person whose invitation is not accepted yet. See [Users, Contacts & Invitations](people-and-invitations.md). | **I forgot my password** on the sign-in page, then **Send me reset instructions** |
| **To** | The invited person | The email address entered |
| **Link** | **Accept invitation**, no expiry until used or replaced | **Change my password**, valid for **6 hours** |
| **From** | A sender address set by UTX for your system, **not** the Admin Email setting | Same |

- **Email Notifications** does not affect these emails.
- The invitation ends with *Have questions? Contact <Your company> at <Admin Email>*.
- The password does not change until the person opens the link and sets a new one. If they did not ask for it, they can ignore the email.
- After requesting a reset the screen says *You will receive an email with instructions about how to reset your password in a few minutes.*

### Feedback {#feedback}

1. Click :fontawesome-solid-comment-dots: **Feedback** in the top menu. The window *We'd love your feedback* opens.
2. Choose the type of feedback (**General**, **Bug Report** or **Suggestion**) and how important it is.
3. Type your message in **Your Feedback** (at least 10 characters) and click **Send Feedback**. A *Thank you!* message confirms it.

| Item | Value |
|------|-------|
| **Subject** | `[<Category>] Feedback from <your name> on <page>`, where the category is the type you chose and the page is the address (path) of the screen you were on |
| **To** | UTX support (not your company) |
| **From** | Your company name and the **Admin Email** |

The email is sent in the background a moment after you submit.

### Test emails {#test-emails}

In **Settings**, the **Test Email Configuration** box (Admins only) sends two emails to the address you type, using the **saved** settings:

| Subject | Mail account | From |
|---------|-------------|------|
| `Test <Your company> notification configuration` | Notification Mailer | Admin Email |
| `Test <Your company> invoice configuration` | Invoice Mailer | Accountant Email |

The page then shows *Test emails sent successfully to …* or *Email test failed.* followed by *Notification Failed: …* and/or *Invoicing Failed: …*. See [Application Settings](application-settings.md#testing-your-email-configuration).

---

## :fontawesome-solid-wrench: Garage Emails {#garage-emails}

Only with the Garage add-on. All of them are sent **from** your company name and the **Accountant Email**. The invoice, work summary and statement go **to** the garage customer's **Email**, with the customer's **Accountant Email** in CC when filled in; the test statement goes only to the address you type.

| Email | Subject | Sent by | Attachment | Extra |
|-------|---------|---------|------------|-------|
| **Invoice** | `Invoice <number> from <Your company>` | **Email Invoice** on the invoice | *<Your company> Invoice <number>.pdf* | Sent in the background. A **Draft** invoice becomes **Sent** and a purple **Emailed** badge shows the date. Void invoices and customers with no **Email** are refused. See [Garage Invoices](garage-invoices.md). |
| **Work summary** | `Work Summary <Mon DD - Mon DD, YYYY> - <Your company>` | **Email to <customer email>** on the **Customer Work Summary**, or the automatic summary job | *<Your company> Work Summary <period>.pdf* | Manual sends go out in the background and are not recorded. |
| **Statement of account** | `Statement of Account as of <Mon DD, YYYY> - <Your company>` | **Email to <customer email>** on the **Customer Statement**, or the automatic statement job | *<Your company> Statement of Account <YYYY-MM-DD>.pdf* | BCC to the **Admin Email**. Only offered when the customer has outstanding invoices. |
| **Test statement** | `[TEST] Statement of Account as of <date> - <Your company> (<customer>)` | **Send Test** in the **Send Test Email** box | Same PDF | Only to the **Recipient**: no CC, no BCC, no status change. |

The automatic work summary and statement jobs skip customers with no **Email**, no work orders in the period (*No work orders in period - skipped*), or nothing outstanding (*No outstanding invoices - skipped*). Their result (*Summary delivered*, *Statement delivered*, or the skip or error message) is shown in the customer's schedule box. See [Garage Reports](garage-reports.md).

---

## :fontawesome-solid-bell: On-Screen Notifications (Toasts)

Toasts appear at the top centre of the screen. Success toasts disappear after about 2 seconds; most failure toasts stay about 5 seconds. Hover over a toast to keep it open.

| Action | Success | Failure |
|--------|---------|---------|
| Send invoice | **Invoice Sent!** — *The invoice was sent successfully.* | **Sending Invoice Failed!** — *The invoice was not sent due to <error>…* or *…Please correct the email address and try again.* |
| Send statement | **Statement Sent!** — *The statement was sent successfully.* | **Sending Statement Failed!** — *The statement was not sent due to <error>…* or *…Please correct the email address and try again.* |
| Send POD | **POD Sent!** — *The pod was sent successfully.* | **Sending POD Failed!** — *The POD was not sent due to <error>…* or *…Please correct the email address and try again.* |
| Make App. | **Appointment Made!** | **Appointment not made!** |
| Dispatch Order | **Order Dispatched!** | **Dispatching failed!** |
| Complete Order | **Order Completed!** | **Completing order failed!** |
| Edit order (edit window or a quick field edit on the row) | **Order Updated!** | **Update failed!** |
| Reset order to new | **Order Reset!** | **Order not updated!** |
| Move status back one step | **Order status changed!** | **Order not updated!** |
| Remove signature | **Order Signature Reset!** | **Order not updated!** |
| Container tracking bulk update | **Updated** — *Orders were updated!* | **Update Failed** |
| Enable a list item or driver | **Update** — *<item> <name> - Enabled* (green) | — |
| Disable a list item or driver | **Update** — *<item> <name> - Disabled* (red, but the change worked) | — |

The **Thank you!** pop-up after sending feedback is a separate confirmation window, not a toast.

---

## :fontawesome-solid-clock: Background Jobs

These jobs run automatically on a schedule managed by UTX outside the app. The times can change, so don't count on a specific hour.

| Job | What it does | Runs only when |
|-----|-------------|----------------|
| **Container tracking update** | Pulls container status from CN Rail, Termont and MGT (Racine/Cast), creates alerts, then checks for approaching Last Free Days. See [Container Tracking](container-tracking.md). | The matching tracking add-on is on |
| **Container tracking digest** | Emails the new alerts to subscribers ([above](#container-tracking-digest)). | A tracking add-on is on |
| **Automatic customer statements** | Emails statements to customers whose scheduled date is today, about 20 per run. See [Automatic Statements](automatic-statements.md). | At least one customer has a statement schedule (the schedule is only offered when automatic statements are enabled for your system) |
| **Garage work summaries** | Emails scheduled work summaries. | Garage add-on is on |
| **Garage statements** | Emails scheduled garage statements. | Garage add-on is on |
| **Invoicing reminder** | Emails the late-invoicing summary ([above](#invoicing-reminder)). | Monday, Wednesday or Friday, and there is something late |
| **Aged receivables processing** | Builds the Aged Receivables (AR) reports you requested that are still being generated. See [Aged Receivables](aged-receivables.md). | A report is waiting |
| **Auto-order document check** | Checks whether uploaded documents for [Auto Orders](auto-orders.md) have finished being read, and fills in the order data. | Documents are waiting |
| **Report data** | Recalculates the figures behind **Sales per Month**. See [Reports](reports.md). | Always |

!!! info "Batch limits"
    The automatic statement jobs (Freight and Garage) send at most about 20 emails per run, with a short pause between each. Spread customer schedules over different days.

---

## :fontawesome-solid-paper-plane: Postmark Delivery

When **Email Delivery Method** is **Postmark** (set up by UTX):

- Every email above goes through Postmark, including invitations and password resets. The Invoice and Notification SMTP accounts are not used.
- The **From** address is rewritten to a UTX sending address for your system. The display name (your company name) is kept.
- The original sender (for example your **Accountant Email**) is put in **Reply-To**, so customer replies reach your real mailbox.
- Recipients therefore see your company name, but the address after it is not yours. This is expected.

See [Application Settings](application-settings.md#email-delivery-method).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-envelope-circle-check: A customer didn't get the dispatched or completed email

!!! info "Solution"
    The email goes only to the person the order is placed for, and only if their **Email Notifications** is on. Check their **Edit Person** page. **Make App.** never sends an email.

### :fontawesome-solid-bell-slash: No one gets the New Order email

!!! info "Solution"
    Make sure at least one Admin has **Email Notifications** and **Active for orders** on. Duplicated orders never trigger it.

### :fontawesome-solid-user-slash: I want to stop the Invoicing Reminder for one person

!!! info "Solution"
    **Email Notifications** does not control it. Every active Admin, Accountant and Manager receives it. The only way to stop it for a person is to change their role or turn off **Active for orders**.

### :fontawesome-solid-list-check: Where do I see the orders from the Invoicing Reminder?

!!! info "Solution"
    Open **Orders** and click the **Late Invoicing** tab (Admins and Managers).

### :fontawesome-solid-reply: Customers reply to an address that isn't ours

!!! info "Solution"
    With Postmark, the From address is a UTX sending address, but **Reply-To** is your real address, so normal replies reach you. If replies go elsewhere, check **Admin Email** and **Accountant Email** in **Settings**.

### :fontawesome-solid-ban: Garage emails are rejected with "Sender is not allowed"

!!! info "Solution"
    Garage emails are sent from the **Accountant Email** and may go through the Notification Mailer account. With SMTP, allow both accounts to send as that address, or use the same mailbox for both. Contact UTX support if unsure.

### :fontawesome-solid-key: The password reset link doesn't work

!!! info "Solution"
    Reset links expire after 6 hours, and only the newest one works. Request a new one with **I forgot my password**.

### :fontawesome-solid-flask: How do I check that email works?

!!! info "Solution"
    An Admin can use **Settings** > **Test Email Configuration** > **Send Test**. Both test emails should arrive. If one fails, the message shows the mail server's error.

---

!!! tip "Best Practices"
    - Send a test email after any change to the email settings.
    - Keep **Email Notifications** on for at least one Admin so new orders are never missed.
    - Fill in each customer's **Accountant Email** before you send invoices or schedule statements.
    - Check the toast and the delivery status (green **OK** / red **Failed!**, or the envelope colour for PODs) after every invoice, statement or POD send.
    - Make sure **Invoice 'From' Override** and **Invoice Default CC** hold valid addresses, or invoice, statement and POD sends are refused.
    - Subscribe at least one dispatcher to the container tracking digest.
