# Garage Invoices & Payments

Bill your garage customers for completed work orders, email the invoice as a PDF, and record the payments you receive.

## :fontawesome-solid-file-invoice: Overview

Garage invoices live in the Garage area under **Invoices** (subtitle *Manage garage invoices and payments*). They are kept completely separate from freight invoices: they have their own list, their own numbering and their own payments, and they never appear on the freight [Invoices](invoices.md) page.

- :fontawesome-solid-wrench: **Built from work orders**: an invoice bills one or more **Completed** work orders for a **single customer**. See [Garage Work Orders](garage-work-orders.md).
- :fontawesome-solid-file-invoice: **Single or bundled**: **Generate Single Invoice** bills one work order in one click. **Bundle with Other Work Orders** (or **New Invoice**) lets you pick several work orders for the same customer.
- :fontawesome-solid-hashtag: **Numbering**: every invoice gets a number like `GRG-00001` from the **Invoice Prefix** in Garage **Settings**. Numbers are never reused.
- :fontawesome-solid-calculator: **Totals**: subtotal of parts and labour, an optional discount (applied before taxes), shop supplies, GST and QST.
- :fontawesome-solid-arrows-rotate: **Lifecycle**: **Draft** > **Sent** > **Partially paid** > **Paid**, or **Void** at any point.
- :fontawesome-solid-envelope: **Email**: **Email Invoice** sends the invoice PDF to the customer, with the customer's accountant in CC.
- :fontawesome-solid-money-bill: **Payments**: record payments on the invoice page. The status moves to **Partially paid** or **Paid** automatically.

<!-- TODO: Screenshot — The garage Invoices list with the All / Draft / Sent / Unpaid / Paid / Void tabs and a few invoice rows -->

---

## :fontawesome-solid-bolt: Quick Start

**To invoice one completed work order:**

1. Open the work order (its status must be **Completed**).
2. Click **Generate Single Invoice** and confirm. A **Draft** invoice opens.
3. Check the totals, then click **Email Invoice** (which also marks it **Sent**) or **Mark Sent** if you deliver it another way.

**To bundle several work orders on one invoice:**

1. Go to **Invoices** and click **New Invoice**.
2. Pick the **Customer** and click **Continue**.
3. Tick the work orders to include, adjust the invoice fields, and click **Create Invoice**.

**To record a payment:**

1. Open a **Sent** or **Partially paid** invoice.
2. In **Record Payment**, check the **Amount** (it defaults to the balance due), pick a **Method**, and click **Record Payment**.

---

## :fontawesome-solid-shield-halved: Access & Permissions

Garage invoices are available only when the Garage add-on is enabled for your company (see [Add-ons & Options](add-ons-and-options.md)).

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Full access to garage invoices and payments |
| :fontawesome-solid-user-tie: **Manager** | Full access to garage invoices and payments for the offices they belong to |
| :fontawesome-solid-screwdriver-wrench: **Garage** | Full access to garage invoices and payments for the offices they belong to |
| :fontawesome-solid-file-invoice-dollar: **Accountant**, :fontawesome-solid-headset: **Dispatch**, **Warehouse**, **Customer**, drivers | No access to the Garage area |

Invoices belong to an office. The list, the counts on the tabs and the customers and work orders you can pick from only cover the office you are currently working in (see [Multi-Office](multi-office.md)).

**How to get there:**

- :fontawesome-solid-arrow-right: Main menu **Garage** > **Invoices** in the Garage sidebar
- :fontawesome-solid-arrow-right: A completed work order > **Generate Single Invoice** or **Bundle with Other Work Orders**
- :fontawesome-solid-arrow-right: The **Work Orders** list > row actions menu > **Generate invoice** or **Bundle with others**

---

## :fontawesome-solid-list: The Invoices List

The list shows the newest invoices first, 20 per page.

### :fontawesome-solid-filter: Tabs

Each tab shows a count of matching invoices.

| Tab | Shows |
|-----|-------|
| **All** | Every invoice, including void ones |
| **Draft** | Invoices with status **Draft** |
| **Sent** | Invoices with status **Sent** (no payment yet) |
| **Unpaid** | Invoices with status **Sent** or **Partially paid** |
| **Paid** | Invoices with status **Paid** |
| **Void** | Invoices with status **Void** |

!!! info "There is no Partially paid tab"
    Partially paid invoices appear under **Unpaid** (and **All**). Drafts are not counted as unpaid because they have not been sent to the customer yet.

### :fontawesome-solid-table-columns: Columns

| Column | What it shows |
|--------|---------------|
| **Invoice #** | The invoice number. Click it to open the invoice |
| **Customer** | The customer name, with the company name in brackets when there is one |
| **WOs** | The number of work orders on the invoice. Hover over it to see their numbers (for example *Work orders: #12, #15*), or *No work orders linked* |
| **Status** | **Draft**, **Sent**, **Partially paid**, **Paid** or **Void** |
| **Date** | The invoice date |
| **Due** | The due date. Shown in red once it has passed and the invoice is not **Paid** |
| **Total** | The invoice total, taxes included |
| **Balance** | Total minus payments. Red while something is owed, green when nothing is |
| **Actions** | The :fontawesome-solid-eye: eye button opens the invoice |

When there are no invoices you see *No invoices yet* and *Create one from the New Invoice button, or generate from a completed work order.*

### :fontawesome-solid-palette: Status colours

| Status | Badge colour | Meaning |
|--------|--------------|---------|
| **Draft** | Grey | Created but not sent. Can be edited or deleted |
| **Sent** | Blue | Sent to the customer, no payment recorded |
| **Partially paid** | Yellow | At least one payment recorded, balance still owing |
| **Paid** | Green | Payments cover the full total |
| **Void** | Red | Cancelled. Excluded from all financial reports |

---

## :fontawesome-solid-file-circle-plus: Creating an Invoice

Only work orders that are **Completed** and not already on an invoice can be invoiced. One invoice always belongs to one customer, so you cannot bundle work orders of different customers.

### :fontawesome-solid-file-invoice: Generate Single Invoice

Use this when a work order is billed on its own.

1. Open a work order with status **Completed**.
2. Click **Generate Single Invoice** (on the **Work Orders** list, open the row actions menu and click **Generate invoice**).
3. Confirm *Generate a single-WO invoice for this work order only? You can still edit the work order while the invoice stays in Draft.*

The invoice is created as a **Draft** with these values, and the invoice page opens with *Invoice generated successfully.*

| Field | Value |
|-------|-------|
| **Customer** | The work order's customer |
| **Tax Rate** | The first active tax of your office |
| **Invoice Date** | Today |
| **Terms** | **Default Payment Terms** from Garage **Settings** |
| **Due Date** | Invoice date plus the terms (see [Terms and due date](#terms-and-due-date)) |
| **Shop Supplies Fee** | The work order's **Shop Supplies Fee** |
| **Discount** | None |

The work order's status changes to **Invoiced**. If the work order is already on an invoice, you are taken to that invoice instead (*Invoice already exists.*). If the work order is not **Completed**, you see *Work order must be completed before invoicing.*

### :fontawesome-solid-layer-group: Bundle work orders (New Invoice)

Use this to put several work orders for the same customer on one invoice. Clicking **Bundle with Other Work Orders** on a work order (or **Bundle with others** in the row actions menu) skips step 1 below and pre-ticks that work order.

**Step 1: pick the customer**

1. Go to **Invoices** and click **New Invoice**.
2. Choose the **Customer \*** (only active customers are listed). The form reminds you: *An invoice can only bundle work orders for a single customer.*
3. Click **Continue**.

**Step 2: pick the work orders and fill in the invoice**

The customer is now locked. Click **Change customer** to go back to step 1.

| Field | Default | Notes |
|-------|---------|-------|
| **Tax Rate** | The first active tax of your office | Choose another rate, or **No tax** |
| **Terms** | **Default Payment Terms** from Garage **Settings** (**Net 30** if none) | **Due on Receipt**, **Net 15**, **Net 30**, **Net 45** or **Net 60** |
| **Invoice Date** | Today | |
| **Shop Supplies Fee** | Empty (*Auto from WOs*) | Leave empty to use the sum of the selected work orders' shop supplies fees. Type an amount to override it |
| **Discount** | **No discount** | **Percent (%)** or **Fixed amount ($)** |
| **Discount Value** | Empty | For example `10` for 10% or `50` for $50. *Applied before taxes. One discount per invoice.* |
| **Notes** | Empty | Printed at the bottom of the invoice |

Under **Work Orders to Include \*** the table lists *only completed, uninvoiced work orders for this customer*, oldest first, with **WO #**, **Date**, **Equipment**, **Description** and **Subtotal** (parts plus labour). Tick the ones to bill and click **Create Invoice**.

If the customer has nothing to bill, you see *This customer has no completed work orders ready to invoice.*

The invoice is created as a **Draft**, the page shows *Invoice created.*, and every selected work order moves to **Invoiced**.

!!! warning "Someone else may have invoiced it first"
    If a selected work order was invoiced or reopened by someone else in the meantime, the invoice is not created and the form shows an error such as *Work orders #15 is not available for invoicing.* Untick it and try again. No invoice number is used up when this happens.

### :fontawesome-solid-calendar-days: Terms and due date {#terms-and-due-date}

The new invoice form has no due date field. The due date is the invoice date plus the terms:

| Terms | Due date |
|-------|----------|
| **Due on Receipt** | Same day as the invoice date |
| **Net 15** | Invoice date + 15 days |
| **Net 30** | Invoice date + 30 days |
| **Net 45** | Invoice date + 45 days |
| **Net 60** | Invoice date + 60 days |

When you edit a draft, the **Edit Invoice** page has a **Due Date** field:

- Changing **Terms** or **Invoice Date** on the page fills in the **Due Date** from the table above. You can then type a different date.
- When you save, if the **Terms** changed, the due date is always recalculated from the invoice date and the terms, so a date you typed by hand in the same save is replaced.
- If the **Terms** did not change, the **Due Date** shown in the field is saved as is.

---

## :fontawesome-solid-hashtag: Invoice Numbering

The number is assigned the moment the invoice is created, including drafts. It is built from two Garage **Settings**:

- **Invoice Prefix** (for example `GRG`)
- the next sequence number, padded to five digits

So the first invoice with prefix `GRG` is `GRG-00001`, the next `GRG-00002`, and so on. The prefix is `GRG` until you change it. The **Invoice Prefix** field in Garage **Settings** shows the number the next invoice will get (*Next invoice: GRG-00042*). See [Garage Settings & Taxes](garage-settings-and-taxes.md).

Garage **Settings** are kept per office, so each office has its own prefix and its own sequence. Give each office its own prefix so invoice numbers stay unique across your company.

!!! info "Numbers are never reused"
    The sequence only moves forward. Deleting a draft or voiding an invoice does not give its number back, so you will see a gap in the sequence. Changing the prefix affects new invoices only.

---

## :fontawesome-solid-calculator: How Totals Are Calculated

Totals are recalculated whenever the invoice is created, saved from **Edit Invoice**, or one of its work orders is edited while the invoice is a **Draft**.

| Line | How it is calculated |
|------|----------------------|
| **Subtotal** | Parts plus labour of all work orders on the invoice (quantity x charge price, hours x rate) |
| **Discount** | **Percent (%)**: that percentage of the subtotal. **Fixed amount ($)**: the amount, capped at the subtotal. Shown as *Discount (10%)* or *Discount* |
| **Shop Supplies** | The work orders' shop supplies fees added together, unless you typed an amount on the invoice |
| **GST** | GST rate of the selected **Tax Rate** x taxable amount |
| **QST** | QST rate of the selected **Tax Rate** x taxable amount |
| **Total** | Subtotal - Discount + Shop Supplies + GST + QST |
| **Paid** | Sum of recorded payments |
| **Balance Due** | Total - Paid |

**Taxable amount** = taxable parts + taxable labour + shop supplies - discount (never below zero). Parts and labour lines whose **Tax** box is unticked on the work order are left out of the taxable amount. Shop supplies are always taxed. With **No tax** selected, GST and QST are zero.

!!! tip "Discount is applied before taxes"
    The discount reduces the amount taxes are calculated on. Example: subtotal $1,000, 10% discount, all lines taxable, no shop supplies, GST 5% and QST 9.975%. Discount = $100, taxable amount = $900, GST = $45.00, QST = $89.78, total = $1,034.78.

!!! info "Percent discount limit"
    A **Percent (%)** discount cannot be more than 100. A **Fixed amount ($)** discount larger than the subtotal is reduced to the subtotal, so the invoice never goes negative.

Lines with a zero amount (discount, shop supplies, GST, QST) are hidden on the invoice page, the printout and the email.

---

## :fontawesome-solid-pen-to-square: Editing a Draft {#editing-a-draft}

Only **Draft** invoices can be edited. Open the invoice and click **Edit**.

The **Edit Invoice** page shows the customer (it cannot be changed) and these fields: **Tax Rate**, **Terms**, **Invoice Date**, **Due Date**, **Shop Supplies Fee**, **Discount**, **Discount Value** and **Notes**.

**Work Orders on this Invoice** lists the work orders already on the invoice (ticked) plus the customer's other completed, uninvoiced work orders (unticked):

- **Untick** a work order to remove it. It returns to **Completed**.
- **Tick** a work order to add it. It moves to **Invoiced**.

Click **Update Invoice** to save. The totals are recalculated and you see *Invoice updated successfully.*

!!! warning "Shop Supplies Fee on edit"
    The **Shop Supplies Fee** field shows the invoice's current fee. If you add or remove work orders and want the fee recalculated from the work orders, clear the field before saving. If you leave a number in it, that number is kept.

An invoice should always keep at least one work order. To drop a draft you no longer need, use **Delete**.

### :fontawesome-solid-wrench: Fixing a work order on a draft invoice

A work order on a **Draft** invoice can still be edited. On the invoice page, each work order section has an **Edit work order** link. Saving the work order updates the draft invoice's totals automatically, so there is no need to void the invoice. When you started from the invoice page you are taken back to it, with a message such as *Work order updated. Draft invoice GRG-00001 was recalculated to $1,034.78.* The work order page also reminds you with a banner (*...which is still a draft — you can still edit it...*) and an **Open draft invoice** link.

- If you change the work order's **Shop Supplies Fee**, the invoice's fee goes up or down by the same difference, so an amount you typed on the invoice is adjusted rather than replaced.
- The work order's customer cannot be changed while it is on an invoice. Remove it from the invoice first.

Once the invoice is **Sent**, **Partially paid** or **Paid**, its work orders are locked. To change them, reopen the invoice (see below) or void it.

---

## :fontawesome-solid-arrows-rotate: Invoice Lifecycle and Actions

The buttons at the top of the invoice page depend on its status.

| Button | Shown when | What it does | Confirmation |
|--------|-----------|--------------|--------------|
| **Edit** | **Draft** | Opens **Edit Invoice** | None |
| **Mark Sent** | **Draft** | Changes the status to **Sent** without emailing anything | *Mark this invoice as sent?* |
| **Reopen to Edit** | **Sent** with no payments | Returns the invoice to **Draft** so you can edit it | *Reopen this invoice for editing? It will go back to Draft status — remember to mark it as sent again afterwards.* |
| **Print** | Any status except **Void** | Opens the printable invoice in a new tab | None |
| **Email Invoice** | Any status except **Void** | Emails the PDF (see [Emailing an Invoice](#emailing-an-invoice)) | *Send invoice to:* followed by the customer and the addresses |
| **Delete** | **Draft** | Deletes the invoice. Its work orders return to **Completed** | *Delete invoice GRG-00001? The work order will return to Completed status. This cannot be undone.* |
| **Void** | Any status except **Void** | Voids the invoice. Its work orders return to **Completed** | *Void invoice GRG-00001? The work order will return to Completed status and you can generate a new invoice. The voided invoice will be excluded from reports.* |

After **Mark Sent** you see *Invoice marked as sent.* After **Delete** you are returned to the list with *Invoice GRG-00001 deleted.*

When **Edit** is not available, a greyed-out **Edit** button with a :fontawesome-solid-lock: lock is shown instead. Hover over it to see why:

| Situation | Tooltip |
|-----------|---------|
| **Paid** | *Paid invoices cannot be edited. Use Void if this invoice is wrong.* |
| Payments recorded (**Partially paid**) | *Remove the recorded payments below first, then you can reopen this invoice.* |

### :fontawesome-solid-rotate-left: Reopen to Edit

Use this when a sent invoice needs a correction (for example a forgotten discount) and you do not want to void it and lose the number.

1. Open the **Sent** invoice and click **Reopen to Edit**, then confirm.
2. The invoice is back in **Draft** (*Invoice reopened for editing. Mark it as sent again when you are done.*).
3. Edit the invoice or its work orders.
4. Click **Mark Sent** or **Email Invoice** again.

Reopen is blocked as soon as a payment is recorded (*Remove the recorded payments before reopening this invoice.*). Remove the payments first, then reopen.

### :fontawesome-solid-ban: Void

Void cancels an invoice that should not be collected, at any status including **Paid**.

- The status changes to **Void** and a red banner says *This invoice has been voided and is excluded from all financial reports.*
- All work orders are detached from the invoice and return to **Completed**, so you can invoice them again (**Generate Single Invoice** reappears on the work order). The confirmation tells you how many: *Invoice GRG-00001 voided. 2 work order(s) reverted to completed.*
- The voided invoice keeps its number and stays in the list under **Void**. Its page shows *No work orders are linked to this invoice (it may have been voided).*
- Payments already recorded stay listed on the voided invoice.
- No action buttons are shown on a void invoice. Voiding cannot be undone from the screen.

!!! danger "Delete vs Void"
    **Delete** is only for drafts and removes the invoice completely. For anything that has been sent or paid, use **Void**: the record stays for your audit trail. Trying to delete a non-draft invoice shows *Only draft invoices can be deleted. Use void for sent or paid invoices.*

### :fontawesome-solid-print: Print

**Print** opens the invoice in a new browser tab, ready to print or save as PDF. It is the same layout as the emailed PDF:

- Your logo, company name, *Garage Services*, and the **Company Address** and **Phone** from Garage **Settings**
- **INVOICE**, the invoice number and the number of work orders
- **Bill To**: customer name, phone and email
- **Invoice Date**, **Due Date** and **Terms**
- One section per work order: **Work Order #**, equipment and plate, **P/O** number, **Completed** date, then each part and labour line (**Description**, **Qty/Hours**, **Rate**, **Amount**) and a **Work Order Subtotal**
- **Subtotal**, discount, **Shop Supplies**, **GST** and **QST** (each with your registration number from Garage **Settings** when set), and **Total Due**
- **Notes**

!!! info "Total Due is the invoice total"
    The printout and PDF show the full invoice total. Payments and the remaining balance are not printed.

---

## :fontawesome-solid-envelope: Emailing an Invoice {#emailing-an-invoice}

1. Open the invoice and click **Email Invoice**.
2. The confirmation lists who will receive it: *Send invoice to:* the customer name, then each address.
3. Click **OK**. The page shows *Invoice emailed to customer@example.com, accounting@example.com.*

| Item | Value |
|------|-------|
| **To** | The garage customer's **Email** |
| **CC** | The garage customer's **Accountant Email**, when filled in |
| **From** | Your company name and the **Accountant Email** from the application settings (see [Application Settings](application-settings.md)) |
| **Subject** | *Invoice GRG-00001 from \<your company name\>* |
| **Body** | A summary of the invoice: your company name with *Garage Services* and your **Phone**, the customer name and phone, invoice date, due date and terms, the work order lines and the totals, then *Thank you for your business!* and your **Company Address** from Garage **Settings** |
| **Attachment** | *\<your company name\> Invoice GRG-00001.pdf* |

After sending:

- A **Draft** invoice is marked **Sent** automatically. Other statuses do not change.
- A purple **Emailed** badge with the date appears next to the status. It shows the most recent send.
- You can send the same invoice again at any time (for example as a reminder), except when it is **Void**.

**When you cannot email:**

| Situation | What you see |
|-----------|--------------|
| The customer has no **Email** | **Email Invoice** is greyed out with the tooltip *Customer has no email address* |
| The invoice is **Void** | The button is not shown |

Add the email on the customer record to fix the first case (see [Garage Customers & Equipment](garage-customers-and-equipment.md)).

---

## :fontawesome-solid-money-bill-wave: Payments

The **Payments** section at the bottom of the invoice page lists every payment recorded (**Date**, **Method**, **Reference**, **Amount**), newest first, or *No payments recorded*.

### :fontawesome-solid-plus: Recording a payment

The **Record Payment** form appears only when the invoice is **Sent** or **Partially paid** and has a balance due. You cannot record payments on a **Draft** (mark it sent first), a **Paid** or a **Void** invoice.

| Field | Required | Default | Notes |
|-------|----------|---------|-------|
| **Amount** | Yes | The balance due | Must be more than zero and cannot exceed the balance due |
| **Method** | No | *Select...* | **Cash**, **Check**, **Credit card**, **E transfer** or **Debit** |
| **Reference #** | No | Empty | Cheque number, transaction ID, etc. |
| **Date** | Yes | Today | The date you received the payment |

Click **Record Payment**. The page shows *Payment recorded successfully.*

If the amount is too high you see *Amount cannot exceed balance due of ...*. Overpayments cannot be recorded: the most you can enter is the balance due.

### :fontawesome-solid-arrows-rotate: Automatic status

You never set the payment status by hand. After each payment is recorded or removed:

| Result | New status |
|--------|-----------|
| Payments cover the total (balance zero) | **Paid** |
| Some payment recorded, balance still owing | **Partially paid** |
| All payments removed | **Sent** |

### :fontawesome-solid-xmark: Removing a payment {#removing-a-payment}

1. Click the :fontawesome-solid-xmark: on the payment row.
2. Confirm *Remove this payment?*. The page shows *Payment removed.* and the status and balance update.

Payments cannot be removed from a **Paid** invoice (*Cannot remove payments from a fully paid invoice.*). If a paid invoice is wrong, void it and invoice the work orders again.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: My work order does not appear in the New Invoice list

!!! info "Solution"
    Only work orders that are **Completed**, not already on an invoice, and belong to the selected customer are listed. Check the work order's status and customer. A work order still **In Progress** must be marked **Completed** first. A work order on a voided invoice is available again.

### :fontawesome-solid-users: Can I put work orders from two customers on one invoice?

!!! info "Solution"
    No. An invoice can only bundle work orders for a single customer. Create one invoice per customer.

### :fontawesome-solid-pen: I need to change an invoice I already sent

!!! info "Solution"
    If no payment is recorded, click **Reopen to Edit**, make the change, then **Mark Sent** or **Email Invoice** again. The invoice keeps its number. If payments are recorded, remove them first. If the invoice is **Paid**, use **Void** and create a new invoice.

### :fontawesome-solid-hashtag: There is a gap in my invoice numbers

!!! info "Solution"
    A number is taken as soon as an invoice is created, even as a draft. Deleting a draft does not give its number back. This is expected.

### :fontawesome-solid-envelope: The Email Invoice button is greyed out

!!! info "Solution"
    The customer has no email address. Add an **Email** to the garage customer and reload the invoice. Fill in **Accountant Email** too if their accountant should get a copy.

### :fontawesome-solid-ban: The Record Payment form is missing

!!! info "Solution"
    Payments can only be recorded on **Sent** or **Partially paid** invoices with a balance due. If the invoice is a **Draft**, click **Mark Sent** first.

### :fontawesome-solid-percent: Taxes look lower than expected

!!! info "Solution"
    Taxes are calculated after the discount and only on lines marked taxable on the work orders (plus shop supplies). Check the **Tax Rate** on the invoice and the taxable setting of the parts and labour lines.

### :fontawesome-solid-file-invoice-dollar: My garage invoices are not on the Invoices page

!!! info "Solution"
    Garage invoices are separate from freight invoices. Open **Garage** in the main menu, then **Invoices** in the Garage sidebar.

---

## :fontawesome-solid-star: Best Practices

!!! tip "Tips"
    - Fix work order lines while the invoice is still a **Draft**. Saving the work order updates the invoice totals without voiding anything.
    - Use **Reopen to Edit** rather than **Void** for corrections on unpaid sent invoices, so the invoice keeps its number.
    - Fill in the customer's **Accountant Email** so their accounting team is copied on every invoice.
    - Use **Email Invoice** instead of **Mark Sent** when you can: it sends the PDF and marks the invoice sent in one step.
    - Record the **Reference #** (cheque number or transfer ID) with each payment to make reconciliation easier.
