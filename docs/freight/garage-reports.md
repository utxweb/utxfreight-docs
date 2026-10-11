# Garage Reports, Work Summaries & Statements

See how the garage is doing at a glance, check work order margins, and send customers a work summary or a statement of account, by hand or on a schedule.

## :fontawesome-solid-chart-bar: Overview

Garage **Reports** is the last item in the Garage sidebar menu, just above **Back to TMS**. It opens a **Dashboard** with links to three reports:

- :fontawesome-solid-gauge: **Dashboard**: four cards (**WOs Opened**, **WOs Completed**, **Revenue**, **Outstanding**) for **Today**, **This Week** or **This Month**, plus **Overdue Invoices**, **Low Stock Parts**, **Technician Hours** and **Recent Work Orders** panels.
- :fontawesome-solid-chart-line: **Profit Report**: revenue, parts cost and profit per work order for a date range (*Work order margins by date range*).
- :fontawesome-solid-clipboard-check: **Customer Work Summary**: the completed work orders of one customer for a week or a month, with what was invoiced and paid. Print it, email it, or schedule it (*Weekly/monthly summary by customer*).
- :fontawesome-solid-file-invoice-dollar: **Customer Statement**: a statement of account listing the customer's unpaid invoices, split into **Overdue** and **Not Yet Due**. Print it, email it, send yourself a test, or schedule it (*Due & overdue invoices by customer*).
- :fontawesome-solid-clock: **Automatic emails**: UTX Freight sends scheduled work summaries and statements for you, and shows the result (*Summary delivered*, *Statement delivered*, a skip message or an error) on the report page.

Garage reports only use garage data (garage work orders, garage invoices, garage customers). They are separate from the freight [Reports](reports.md), [Customer Statements](customer-statements.md) and [Automatic Statements](automatic-statements.md).

<!-- TODO: Screenshot — The Garage Reports Dashboard with the Today / This Week / This Month toggle, the four cards and the panels below -->

---

## :fontawesome-solid-bolt: Quick Start

**To email a customer their work for last week:**

1. Go to **Garage** > **Reports** and click **Customer Work Summary**.
2. Pick the **Customer**, pick any day of last week in **Date**, keep **Week** selected and click **View Report**.
3. Check the list, then click **Email to** *customer email* and confirm.

**To send a statement of account:**

1. Go to **Garage** > **Reports** and click **Customer Statement**.
2. Pick the **Customer** and click **View Statement**.
3. Click **Email to** *customer email* and confirm. Use **Send Test** first if you want to see the email yourself.

**To schedule either email:**

1. Open the customer on **Customer Work Summary** or **Customer Statement**.
2. In **Automatic Summary Emails** or **Automatic Statement Emails**, choose a **Frequency** and click **Save Schedule**.

---

## :fontawesome-solid-shield-halved: Access & Permissions

Garage reports are available only when the Garage add-on is enabled for your company (see [Add-ons & Options](add-ons-and-options.md)).

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Full access to all garage reports, emails and schedules, for the office they are working in |
| :fontawesome-solid-user-tie: **Manager** | Full access, for the office they are working in (they can switch between the offices they belong to) |
| :fontawesome-solid-screwdriver-wrench: **Garage** | Full access, for the first office on their user account (they cannot switch office) |
| :fontawesome-solid-headset: **Dispatch**, **Customer Service**, **Accountant**, **Customer**, **Warehouse**, drivers and yard workers | No access to the Garage area |

There are no separate permissions for reports: anyone who can open the Garage can view every report, send emails and change schedules.

The Dashboard, the Profit Report and the customer lists only cover the office you are currently working in (see [Multi-Office](multi-office.md)). The customer lists on **Customer Work Summary** and **Customer Statement** only show **active** customers.

**How to get there:**

- :fontawesome-solid-arrow-right: Main menu **Garage** > **Reports** in the Garage sidebar (opens the **Dashboard**)
- :fontawesome-solid-arrow-right: The cards at the bottom of the Dashboard: **Profit Report**, **Customer Work Summary**, **Customer Statement**, **All Work Orders**, **Invoices**
- :fontawesome-solid-arrow-right: Garage **Customers** list > the :fontawesome-solid-clipboard-check: clipboard button (*Work summary for (name)*) opens that customer's work summary for the current week
- :fontawesome-solid-arrow-left: Every report has a **Back to Reports** link at the bottom

---

## :fontawesome-solid-gauge: The Dashboard

The page is titled **Dashboard**. Use the toggle at the top right to choose the period for the cards and the **Technician Hours** panel. The default is **Today**.

| Period | Covers |
|--------|--------|
| **Today** | Today |
| **This Week** | Monday of the current week up to now |
| **This Month** | The 1st of the current month up to now |

### :fontawesome-solid-square: Cards

| Card | What it counts | Uses the period? |
|------|----------------|------------------|
| **WOs Opened** | Work orders **created** in the period | Yes |
| **WOs Completed** | Work orders whose status is now **Completed** or **Invoiced** and that were **last updated** in the period | Yes |
| **Revenue** | The sum of the **Total** (taxes included) of all garage invoices **created** in the period, except **Void** ones. Drafts are included | Yes |
| **Outstanding** | What is still owed on all **Sent** and **Partially paid** invoices (total minus payments). Shown in red when above zero | No, always all unpaid invoices |

!!! info "WOs Completed uses the last update date"
    The card counts work orders by the date they were last updated. A work order completed last week and invoiced today counts as completed **Today**.

### :fontawesome-solid-table-list: Panels

| Panel | What it shows |
|-------|---------------|
| **Overdue Invoices** | Up to 10 **Sent** or **Partially paid** invoices whose due date is before today, oldest due date first: invoice number, customer, *Nd overdue* and balance due. **View all** opens the **Unpaid** tab of [Garage Invoices](garage-invoices.md). When there are none: *No overdue invoices* |
| **Low Stock Parts** | Up to 10 active parts whose quantity on hand is at or below their reorder point (parts with a reorder point of 0 or none are ignored), lowest quantity first: name, SKU and *quantity / reorder point*. The quantity is red at zero, yellow otherwise. **View all** opens the **Low Stock** tab of **Parts**. When there are none: *All parts above reorder point* |
| **Technician Hours** | Labour hours per technician, highest first, for work orders **last updated** in the period. Hours are credited to the work order's assigned technician, not to individual labour lines. Work orders with no one assigned are left out. When there are none: *No technician hours recorded* |
| **Recent Work Orders** | The 8 most recently created work orders, whatever the period: number, customer, status and total (parts, labour and shop supplies). **View all** opens **Work Orders**. When there are none: *No work orders yet* |

See [Garage Parts & Templates](garage-parts-and-templates.md) for reorder points and [Garage Work Orders](garage-work-orders.md) for assigning a technician.

---

## :fontawesome-solid-chart-line: Profit Report

The **Profit Report** shows the margin on each work order in a date range.

1. On the Dashboard, click **Profit Report**.
2. Set **From** and **To**. The defaults are the 1st of the current month and today.
3. Click **Filter**.

**Which work orders are included:** work orders whose **date in** falls between **From** and **To** (both days included), in any status except **Estimate** (so **Approved**, **In progress**, **Completed** and **Invoiced**). Newest date in first.

| Column | What it shows |
|--------|---------------|
| **WO #** | The work order number. Click it to open the work order |
| **Customer** | The customer name, followed by the company name in brackets when the customer has one |
| **Date** | The work order's date in |
| **Status** | The work order status |
| **Revenue** | Parts (quantity x charge price) + labour (hours x rate) + **Shop Supplies Fee** |
| **Parts Cost** | Parts at purchase price (quantity x purchase price) |
| **Profit** | Parts (charge price) - Parts Cost + labour. Green when zero or more, red when negative |

A **Totals** row adds up the three amount columns.

!!! info "Revenue includes shop supplies, Profit does not"
    The **Shop Supplies Fee** is part of **Revenue** but not of **Profit**, so **Revenue** - **Parts Cost** differs from **Profit** by the shop supplies amount. Labour is counted entirely as profit because labour lines have hours and a rate, with no cost.

!!! info "Work order amounts, not invoice amounts"
    The report uses the work order lines. Invoice discounts, GST and QST are not included, and the report does not check whether the work was invoiced or paid. For billed and paid amounts, use the **Customer Work Summary**, the **Customer Statement** or [Garage Invoices](garage-invoices.md).

<!-- TODO: Screenshot — The Profit Report with the From / To filter and the Totals row -->

---

## :fontawesome-solid-clipboard-check: Customer Work Summary

The **Customer Work Summary** lists one customer's finished work for a week or a month, with what was invoiced, what was paid and the balance.

### :fontawesome-solid-sliders: Choosing the customer and period

| Field | What to enter |
|-------|---------------|
| **Customer** | Choose from *-- Select customer --*. Only active customers are listed |
| **Date** | **Week**: any day of the week you want (defaults to today). The hint says *Report snaps to Monday of selected week*: the report always covers Monday to Sunday of that week. **Month**: a month picker (defaults to the current month); the report covers the whole month |
| **Week** / **Month** | The period type. **Week** is the default. Clicking **Week** or **Month** reloads the report straight away, switching the **Date** field between a day picker and a month picker |

Click **View Report**.

### :fontawesome-solid-filter: Which work orders are included

A work order is included when:

- it belongs to the selected customer,
- its status is **Completed** or **Invoiced**, and
- its **date out** falls in the period, or, if it has no date out, it was last updated in the period.

Work orders that are still **Estimate**, **Approved** or **In progress** never appear. They are listed by date out, oldest first.

### :fontawesome-solid-table: What the report shows

Under the customer name you see the period (for example *Oct 05 - Oct 11, 2026*, or *October 2026* for a month) and the number of work orders.

| Card | What it shows |
|------|---------------|
| **Work Orders** | How many work orders are included |
| **Total Invoiced** | The sum of the **Total** of the invoices linked to those work orders (each invoice counted once, **Void** invoices excluded) |
| **Total Paid** | Payments recorded on those invoices |
| **Balance Due** | **Total Invoiced** - **Total Paid**. Red when above zero |

| Column | What it shows |
|--------|---------------|
| **WO #** | The work order number. Click it to open the work order |
| **Equipment** | The work order's equipment, or *-* |
| **Description** | The work order description, shortened |
| **Completed** | The date out, or *-* |
| **Invoice** | The invoice number (click to open it), or *-* if not invoiced yet |
| **Amount** | Parts + labour of the work order (no shop supplies, discount or taxes) |
| **Status** | The status of the linked invoice: **Draft**, **Sent**, **Partially paid** or **Paid**, or *-* |

The **Totals** row shows **Total Invoiced**, not the sum of the **Amount** column. When nothing matches you see *No completed work orders in this period.*

!!! info "Why Total Invoiced can differ from the Amount column"
    **Amount** is the work order's parts and labour only. **Total Invoiced** uses the full invoice totals, which include shop supplies, discounts and taxes. If an invoice bundles work orders from outside the period, its whole total is still counted.

<!-- TODO: Screenshot — Customer Work Summary for one customer, week view, with the four cards, the table and the Print / Email buttons -->

### :fontawesome-solid-print: Print

Click **Print** to open the summary in a new tab, ready to print or save as PDF. It shows your logo and company name, the **Company Address** and **Phone** from Garage **Settings**, the title **WORK SUMMARY** with the period, **Prepared For** (customer name, phone and email), the work order table, **Total Invoiced**, **Total Paid** and **Balance Due**, and *Generated on (date)*. The emailed PDF uses the same layout.

### :fontawesome-solid-envelope: Email the summary

1. Click **Email to** *customer email*.
2. Confirm *Email work summary to:* followed by the customer name and each address.
3. The page shows *Work summary emailed to (addresses).*

| Item | Value |
|------|-------|
| **To** | The garage customer's **Email** |
| **CC** | The garage customer's **Accountant Email**, when filled in |
| **From** | Your company name and the **Accountant Email** from [Application Settings](application-settings.md) |
| **Subject** | *Work Summary (period) - (your company name)*, for example *Work Summary Oct 05 - Oct 11, 2026 - (your company name)* |
| **Body** | *Dear (customer name)*, *Here is a summary of work completed on your vehicles during this period.*, a work order table (**WO #**, **Equipment**, **Completed**, **Invoice**, **Amount**, **Status**) and **Total Invoiced**, **Total Paid** and **Balance Due**, ending with *Thank you for your business!* In the email body, **Amount** is the total of the linked invoice (or *-* if not invoiced), not the work order's parts and labour |
| **Attachment** | *(your company name) Work Summary (period).pdf* |

The period in the subject and file name always uses the first and last day, also for a month (for example *Oct 01 - Oct 31, 2026*).

If the customer has no **Email**, the button is replaced by a greyed-out **No email on file** (*Add an email address to this customer first*). See [Garage Customers & Equipment](garage-customers-and-equipment.md).

!!! info "Manual sends and the schedule are independent"
    Sending a summary by hand does not change **Next send** or the delivery status, and a scheduled summary due the same day is still sent.

### :fontawesome-solid-clock: Automatic Summary Emails {#automatic-summary-emails}

The **Automatic Summary Emails** box (*Schedule recurring summary emails to this customer*) sits below the buttons.

1. Choose a **Frequency**.
2. Click **Save Schedule**. The page shows *Automatic summary set to Weekly on Monday.* (or the option you chose), or *Automatic summary disabled.*

| Frequency | Sends on | Period covered |
|-----------|----------|----------------|
| **Disabled** | Never | |
| **Weekly on Sunday** ... **Weekly on Saturday** | That weekday, every week | Monday of the week that contains yesterday, through yesterday |
| **Monthly on the 1st** | The 1st of each month | The whole previous month |
| **Monthly on the 15th** | The 15th of each month | The whole previous month |

Examples of the weekly period:

| Schedule | Sent on | Covers |
|----------|---------|--------|
| **Weekly on Monday** | Monday | The previous Monday to Sunday (a full week) |
| **Weekly on Saturday** | Saturday | Monday to Friday of the same week |
| **Weekly on Sunday** | Sunday | Monday to Saturday of the same week |

!!! tip "Use Weekly on Monday for full weeks"
    Any other weekday sends a partial week (Monday up to the day before the send day).

When a schedule is active the box also shows:

- **Next send:** the next date the summary is due. For a weekly schedule this is the next occurrence of that weekday (today if it is that weekday and nothing was sent today). For a monthly schedule it is the 1st or 15th of this month, or of next month once that day has passed or the summary was already sent on it.
- The result of the last automatic send, in green or red:

| Message | Meaning |
|---------|---------|
| *Summary delivered* | The email was sent |
| *No work orders in period - skipped* | No completed or invoiced work orders in the period, so nothing was sent |
| An error message (red) | The email could not be sent. It is not retried that day |

---

## :fontawesome-solid-file-invoice-dollar: Customer Statement

The **Customer Statement** (*Outstanding invoices — overdue and not yet due — ready to print or email.*) lists what a customer still owes.

1. On the Dashboard, click **Customer Statement**.
2. Choose the **Customer** (only active customers are listed) and click **View Statement**.

### :fontawesome-solid-filter: Which invoices are included

Only invoices with status **Sent** or **Partially paid**. **Draft**, **Paid** and **Void** invoices never appear. Each invoice shows its **balance due** (total minus payments), not its full total.

| Section | Invoices |
|---------|----------|
| **Overdue** | Due date before today |
| **Not Yet Due** | Due date today or later, or no due date |

Within each section, invoices are sorted by due date, earliest first (invoices with no due date last). The statement is always as of today: there is no date to choose.

### :fontawesome-solid-table: What the statement shows

Under the customer name: *Statement of account as of (today's date)* and the number of outstanding invoices.

| Card | What it shows |
|------|---------------|
| **Overdue** | Total balance due of the overdue invoices. Red when above zero |
| **Not Yet Due** | Total balance due of the invoices not yet due |
| **Total Outstanding** | **Overdue** + **Not Yet Due** |

| Table | Columns | Empty message |
|-------|---------|---------------|
| **Overdue (n)** | **Invoice**, **Issued**, **Due**, **Days Overdue** (for example *12 days*), **Balance Due**, and an **Overdue Subtotal** row | *No overdue invoices.* |
| **Not Yet Due (n)** | **Invoice**, **Issued**, **Due**, **Terms**, **Balance Due**, and a **Not Yet Due Subtotal** row | *No upcoming invoices.* |

Click an invoice number to open the invoice.

<!-- TODO: Screenshot — Customer Statement for one customer with the Overdue / Not Yet Due / Total Outstanding cards, both tables and the Send Test Email and Automatic Statement Emails boxes -->

### :fontawesome-solid-print: Print / PDF

Click **Print / PDF** to open the statement in a new tab. It shows your logo and company name, the **Company Address** and **Phone** from Garage **Settings**, the title **STATEMENT OF ACCOUNT** *As of (date)*, **Statement For** (customer name, phone and email), the **Overdue**, **Not Yet Due** and **Total Outstanding** amounts, both tables (with **Issue Date** and **Due Date** columns), *THANK YOU FOR YOUR BUSINESS!* and *Generated on (date)*. The emailed PDF uses the same layout.

### :fontawesome-solid-envelope: Email the statement

1. Click **Email to** *customer email*.
2. Confirm *Email statement of account to:* followed by the customer name and each address.
3. The page shows *Statement of account emailed to (addresses).*

| Item | Value |
|------|-------|
| **To** | The garage customer's **Email** |
| **CC** | The garage customer's **Accountant Email**, when filled in |
| **BCC** | The **Admin Email** from [Application Settings](application-settings.md), when filled in, so you keep a copy of every statement (manual and automatic) |
| **From** | Your company name and the **Accountant Email** from Application Settings |
| **Subject** | *Statement of Account as of (date) - (your company name)*, for example *Statement of Account as of Oct 10, 2026 - (your company name)* |
| **Body** | The overdue, not yet due and total outstanding amounts. When something is overdue it adds *A balance of (amount) is past due. We kindly ask that you arrange payment at your earliest convenience.* It ends with *Thank you for your business!* |
| **Attachment** | *(your company name) Statement of Account (date).pdf*, with the date as year-month-day (for example *2026-10-10*) |

The email is sent immediately, so the result is known right away:

- **Success:** the delivery status becomes *Statement delivered* and today is recorded as the statement's sent date.
- **Failure:** you see *Statement could not be sent: (reason)* and the delivery status shows the error in red.

**When you cannot email:**

| Situation | What you see |
|-----------|--------------|
| The customer has no **Email** | A greyed-out **No email on file** (*Add an email address to this customer first*) |
| Nothing is outstanding | A greyed-out **Nothing to send** (*This customer has no outstanding invoices to send*). If you get there another way: *This customer has no outstanding invoices — nothing to send.* |

!!! warning "A manual send replaces today's automatic send"
    Sending a statement by hand records today as the sent date. If the same customer's automatic statement is due today, it is skipped, and **Next send** moves to the following scheduled date. This avoids the customer getting two statements on the same day.

### :fontawesome-solid-flask: Send Test Email

The **Send Test Email** box (*Preview exactly what the customer receives — sent to you, not to them.*) sends the same statement and PDF to an address you choose.

1. Check **Recipient**. It is prefilled with your own user email.
2. Click **Send Test**. The page shows *Test statement sent to (address).*

- The subject starts with **[TEST]** and ends with the customer name: *[TEST] Statement of Account as of (date) - (your company name) (customer name)*.
- It goes only to the **Recipient**: no CC to the customer's accountant and no BCC to the admin.
- It does not change the delivery status, the sent date or **Next send**.
- It works even when the customer has no email or nothing outstanding.

If **Recipient** is empty you see *Please enter a recipient email address.* If sending fails: *Could not send test email: (reason)*.

### :fontawesome-solid-clock: Automatic Statement Emails

The **Automatic Statement Emails** box (*Schedule recurring statements of account to this customer*) works like the summary schedule.

1. Choose a **Frequency**: **Disabled**, **Weekly on Sunday** to **Weekly on Saturday**, **Monthly on the 1st** or **Monthly on the 15th**.
2. Click **Save Schedule**. The page shows *Automatic statement set to (frequency).* or *Automatic statement disabled.*

A statement has no period: each automatic statement lists the invoices outstanding on the day it is sent.

When a schedule is active the box shows **Next send:** (calculated as for the work summary) and the result of the last send:

| Message | Meaning |
|---------|---------|
| *Statement delivered* | The statement was sent (automatically or with the email button) |
| *No outstanding invoices - skipped* | Nothing was owed on the scheduled day, so nothing was sent |
| An error message (red) | The email could not be sent. It is not retried that day |

---

## :fontawesome-solid-gears: How Automatic Emails Are Sent

UTX Freight sends the scheduled emails automatically: work summaries and statements are sent separately. Sending times are managed by UTX, so don't count on a specific time of day. Nothing is sent when the Garage add-on is off.

A scheduled email is sent to a customer only when:

- the customer is **active**,
- a **Frequency** other than **Disabled** is saved,
- **Next send** is today,
- the customer has an **Email** (customers without one are not sent anything and no status message is shown), and
- nothing was already sent (or attempted) for that customer today.

| | Work summary | Statement |
|---|------------------|---------------|
| **Content** | Work orders completed in the period (see [the periods above](#automatic-summary-emails)) | Invoices outstanding today |
| **Skipped when** | No work orders in the period: *No work orders in period - skipped* | Nothing outstanding: *No outstanding invoices - skipped* |
| **Recipients** | To customer **Email**, CC **Accountant Email** | To customer **Email**, CC **Accountant Email**, BCC **Admin Email** |
| **Success message** | *Summary delivered* | *Statement delivered* |

Skips and errors also count as "done for today": the customer is not tried again until their next scheduled date.

!!! tip "Spread your schedules"
    Spread customers across different weekdays and the 1st and 15th to keep each day light.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-calendar-week: I picked a Wednesday but the summary starts on Monday

!!! info "Solution"
    That is expected. In **Week** view the report always covers Monday to Sunday of the week that contains the date you picked (*Report snaps to Monday of selected week*). Switch to **Month** for a calendar month.

### :fontawesome-solid-eye-slash: A work order is missing from the work summary

!!! info "Solution"
    Only **Completed** and **Invoiced** work orders appear, and only when their **date out** is in the period (or, with no date out, when they were last updated in the period). Check the work order's status and date out. Also check that it belongs to this customer.

### :fontawesome-solid-envelope-circle-check: The automatic summary says "No work orders in period - skipped"

!!! info "Solution"
    No completed or invoiced work orders matched the period, so no email was sent. Remember that a weekly schedule only covers Monday up to the day before the send day. Schedule **Weekly on Monday** to cover full weeks.

### :fontawesome-solid-file-circle-xmark: An invoice is missing from the statement

!!! info "Solution"
    Statements only list **Sent** and **Partially paid** invoices. A **Draft** invoice must be marked sent or emailed first (see [Garage Invoices](garage-invoices.md)). **Paid** and **Void** invoices are never listed.

### :fontawesome-solid-envelope: The Email button says "Nothing to send" or "No email on file"

!!! info "Solution"
    **No email on file**: add an **Email** to the garage customer. **Nothing to send** (statement only): the customer has no outstanding balance. You can still use **Print / PDF** or **Send Test**.

### :fontawesome-solid-clock-rotate-left: The scheduled statement did not go out today

!!! info "Solution"
    Check the message next to **Next send**. If someone emailed the statement by hand today, the automatic send is skipped on purpose. If the customer has no **Email**, nothing is sent: add one, then send the statement with the email button.

### :fontawesome-solid-scale-unbalanced: Revenue minus Parts Cost does not equal Profit

!!! info "Solution"
    **Revenue** includes the **Shop Supplies Fee**; **Profit** does not. The difference is the shop supplies amount.

### :fontawesome-solid-chart-column: The Dashboard numbers do not match my invoices for the month

!!! info "Solution"
    **Revenue** uses the date the invoice was created in UTX Freight (not its invoice date), includes drafts and taxes, and excludes void invoices. **Outstanding** is always the total of all unpaid invoices, whatever period is selected.

---

## :fontawesome-solid-star: Best Practices

!!! tip "Tips"
    - Fill in each customer's **Email** and **Accountant Email** so summaries and statements reach both the customer and their bookkeeper.
    - Use **Send Test** before the first statement to a new customer, so you see exactly what they will receive.
    - Schedule weekly summaries on **Monday** so each email covers a full week.
    - Spread automatic schedules across weekdays and the 1st and 15th to keep each day light.
    - Check the delivery message next to **Next send** now and then to catch failed emails.
    - Mark invoices **Sent** (or email them) promptly: drafts never appear on statements.
