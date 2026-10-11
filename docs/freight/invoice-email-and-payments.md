# Sending Invoices & Recording Payments

Email an invoice to your customer with its proof of delivery attached, then record the payments you receive against it.

## :fontawesome-solid-envelope-open-text: Overview

Both tasks start from a row on the **Invoices** list (see [Invoices](invoices.md)):

- :fontawesome-solid-envelope: **Sending**: the envelope button on a row opens the **Send invoice to customer** window. The email carries the invoice PDF, the POD of each order that has one, and optionally the order documents.
- :fontawesome-solid-arrows-rotate: **Status on send**: a successful send of a **new** invoice changes its status to **Invoiced**. Any other status is left as it is.
- :fontawesome-solid-circle-check: **Delivery label**: every send attempt leaves an **OK** or **Failed!** label next to the status.
- :fontawesome-solid-file-pen: **REVISED**: once an invoice has been sent successfully, the next send is marked **REVISED** in the subject and the PDF file name.
- :fontawesome-solid-money-bill: **Payments**: **Record a payment** in the cog menu opens the invoice in a pop-up where you add payment lines (date, check number, amount) or click **Balance Paid In Full**.
- :fontawesome-solid-tag: **Status is yours to set**: adding payments never changes the status by itself. An invoice is treated as settled only when its status is **Paid**.

<!-- TODO: Screenshot — The Send invoice to customer window with To, Cc, Bcc, Subject, Include documents and the missing-POD warning -->

---

## :fontawesome-solid-bolt: Quick Start

**To email an invoice:**

1. Go to **Invoices** and find the invoice.
2. Click the :fontawesome-solid-envelope: envelope button on its row.
3. Check **To**, **Cc** and **Subject**, and tick or untick **Include documents**.
4. Click **Send**. A notification confirms the result, and the row shows **OK** or **Failed!**.

**To record a payment:**

1. On the invoice row, open the :fontawesome-solid-gear: cog menu and click **Record a payment**.
2. Click **Balance Paid In Full**, or click **(+) Add payment** and fill in the payment line.
3. Set **Invoice Status** if needed (for example **Partially Paid**).
4. Click **Update Invoice**.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Can send invoices, record payments and change status. Also has access to **Settings**, including **Test Email Configuration** |
| :fontawesome-solid-user-tie: **Manager** | Can send invoices, record payments and change status for invoices of the offices they belong to |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Can send invoices, record payments and change status for invoices of the offices they belong to |
| :fontawesome-solid-headset: **Dispatch**, **Customer Service** | No access to invoices |
| :fontawesome-solid-user: **Customer**, **Warehouse**, **Garage**, drivers | No access |

**How to get there:**

- :fontawesome-solid-arrow-right: **Invoices** > envelope button on a row (send)
- :fontawesome-solid-arrow-right: **Invoices** > cog menu on a row > **Record a payment** (payments)
- :fontawesome-solid-arrow-right: **Invoices** > click the status text on a row (change status inline)

---

## :fontawesome-solid-paper-plane: Sending an Invoice

### :fontawesome-solid-envelope: The envelope button

Each invoice row has an envelope button in the **Actions** column:

| Button | Tooltip | Meaning |
|--------|---------|---------|
| Blue envelope | **Email Invoice** | The invoice has never been sent successfully |
| Grey envelope | **Resend Invoice** | The invoice was sent successfully before |

Click it to open the **Send invoice to customer** window.

### :fontawesome-solid-list: Fields in the Send invoice to customer window

The window reminds you that *Starred (\*) fields are required.* Several fields are filled in for you when it opens. You can change any of them before sending.

| Field | Required | Pre-filled with |
|-------|----------|-----------------|
| **To** | Yes | The customer's **Accountant Email** (from the customer record) |
| **Cc** | No | The **Invoice Default CC Address** from **Settings**, followed by the customer's **Accountant Email (CC)**, separated by a comma. Either part is left out if it is empty |
| **Bcc** | No | Empty |
| **Subject** | Yes | Built from your company name and the invoice number (see below) |
| **Include documents** | No | Ticked |

**To**, **Cc** and **Bcc** accept several addresses separated by commas (`,`) or semicolons (`;`). Each address must be a valid email address, or the invoice is not sent.

!!! tip "Fix the source, not just the email"
    If **To** or **Cc** is wrong every time, correct the **Accountant Email** or **Accountant Email (CC)** on the customer. See [Managing Customers](managing-customers.md). The company-wide CC is the **Invoice Default CC Address** in [Application Settings](application-settings.md).

### :fontawesome-solid-heading: Subject line

The subject is pre-filled in this format:

`<Your company name>[ REVISED] Invoice #<invoice number>[ - PO#<PO or reference>]`

| Part | When it appears |
|------|-----------------|
| **REVISED** | Only if the invoice's last send attempt succeeded (its row shows the green **OK** label). See [The REVISED rule](#the-revised-rule) |
| **- PO#…** | Only if the invoice has **exactly one order**. It shows that order's delivery PO number, or its reference number if there is no PO number |

Examples:

- `Acme Transport Invoice #01234 - PO#45-7781` (first send, one order)
- `Acme Transport REVISED Invoice #01234` (resend, several orders)

### :fontawesome-solid-triangle-exclamation: Warnings in the window

Two notices can appear under the fields. Neither one stops you from sending.

| Notice | When it appears |
|--------|-----------------|
| **WARNING**: *This order is missing (N) PODs in PDF format* (yellow) | One or more orders on the invoice have no signed POD and no scanned signed POD. *N* is the number of those orders. They are sent without a POD |
| *N additional documents will be attached if **Include Documents** is selected!* (blue) | The invoice has **one order** and that order has documents uploaded. *N* is the number of documents |

!!! info "Document count notice"
    The blue document count only appears on invoices with **one order**. On invoices with several orders it does not appear, even when the orders have documents. The documents are still attached if **Include documents** is ticked.

### :fontawesome-solid-check: Sending

1. Review the fields.
2. Click **Send** (or **Close** to cancel).
3. The window closes and a spinner replaces the envelope on the row while the email is built and sent.
4. When it finishes, the row refreshes and a notification appears at the top of the page:

| Result | Notification |
|--------|--------------|
| Sent | **Invoice Sent!** *The invoice was sent successfully.* |
| Sending failed | **Sending Invoice Failed!** *The invoice was not sent due to …error…. Please try again or contact the administrator.* |
| An address was rejected | **Sending Invoice Failed!** *The invoice was not sent. Please correct the email address and try again.* |

---

## :fontawesome-solid-paperclip: What the Customer Receives

### Email body

The email is headed **New invoice from** *your company name*. It says the invoice is attached as a PDF and that the attachments include the **invoice** and the **proof of delivery (if available)** for each order on the invoice. It ends with *Thank you for your business.* and your company name.

If your account is set up to link emails back to the app, the email also contains a **View your orders** link.

### Attachments

| Attachment | File name | When |
|------------|-----------|------|
| Invoice PDF | `<Your company name> Invoice <invoice number>.pdf`, or `<Your company name> Invoice REVISED <invoice number>.pdf` on a revised send | Always |
| Signed POD (one per order) | `<Your company name> POD Signed #<order ID>.pdf`. International export orders use **eBoL** instead of **POD** | When the order has a signature captured on the delivery or pickup |
| Scanned signed POD (one per order) | The scanned file's own name | When the order has no captured signature but has a scanned signed POD uploaded |
| Order documents | Each document's own file name | Only when **Include documents** is ticked. Every document of every order on the invoice is attached |

For each order, a captured signature takes priority: if the order has one, the signed POD PDF is generated and the scanned POD is not attached. Orders with neither get no POD attachment (this is what the yellow warning counts).

For how PODs and documents get onto an order, see [Order Documents & POD](order-documents-and-pod.md).

!!! warning "One failed attachment fails the whole email"
    The PODs and documents are downloaded from file storage while the email is built. If the download of any of them fails with an error, nothing is sent and the row shows **Failed!**. Hover over the label to read the error.

---

## :fontawesome-solid-arrows-rotate: What Changes After You Send

### On success

- **Sent date** is set to today. The row shows **sent** *date* under the status.
- The delivery label shows a green **OK**. Hovering over it shows *Email Delivered*.
- **Status** changes to **Invoiced**, but **only if it was new**. An invoice that is already **Invoiced**, **Partially Paid** or **Paid** keeps its status.
- The envelope turns grey (**Resend Invoice**).

### On failure

- The delivery label shows a red **Failed!**. Hover over it to see the error message.
- **Status** is not changed.
- **Sent date** is not changed: the row keeps showing the date of the last successful send, or **not sent**.

If the invoice was rejected because an address was invalid, the invoice is not touched at all: the label and status stay as they were.

### :fontawesome-solid-file-pen: The REVISED rule

**REVISED** is added to the subject and to the invoice PDF file name only when the invoice's **last send attempt succeeded**, meaning the row shows the green **OK** label.

- First send of an invoice: no REVISED.
- Any send after a successful one: REVISED.
- If the last attempt **failed**, the next send has **no** REVISED, even if an earlier send had succeeded. Add the word to the subject yourself if you want it.

!!! tip "Resending after a correction"
    After you change an invoice that was already sent (orders, charges, terms), resend it from the envelope button. The REVISED marking tells the customer this copy replaces the previous one.

---

## :fontawesome-solid-money-bill: Recording a Payment

### Opening the payment window

On the invoice row, open the :fontawesome-solid-gear: cog menu and click **Record a payment**. A pop-up titled **Edit Invoice** *invoice number* **-** *customer name* opens.

<!-- TODO: Screenshot — The Record a payment pop-up showing the invoice summary, Invoice Status, Balance Paid In Full and a payment line -->

The top of the window summarizes the invoice (read-only):

| Item | Shows |
|------|-------|
| **Invoice Total** | Total of the orders including taxes |
| **Invoice Date** | Date on the invoice |
| **Invoiced Orders** | Reference numbers of the orders on the invoice |
| **Invoice Due Date** | Due date |

Below that:

- **Invoice Status**: a drop-down with **new**, **Invoiced**, **Paid**, **Partially Paid**.
- **Balance Paid In Full**: a button, shown only when the status is not **Paid**.
- **Payment Information**: the invoice's payment lines, with **(+) Add payment** to add another.

### :fontawesome-solid-circle-check: Balance Paid In Full

Click **Balance Paid In Full** when the customer has paid everything that is left. It:

1. Sets **Invoice Status** to **Paid**.
2. Adds a payment line with **Paid date** set to today and **Amount** set to the remaining balance.
3. Hides itself.

Fill in the **Check number** if you have one, then click **Update Invoice**.

!!! info "How the balance is worked out"
    The amount is the **Invoice Total** minus the payment lines **already saved** when you opened the window. Lines you added in this window before clicking the button are not deducted. If you add a partial payment and the rest in one go, save the partial payment first, or adjust the amount by hand.

!!! warning "Check the date"
    The **Paid date** is pre-filled from your computer's clock. Late in the evening it can come out as the next day. Correct it before saving if needed.

### :fontawesome-solid-list-ol: Payment lines

Click **(+) Add payment** to add a line. Each line has:

| Field | Required | Description |
|-------|----------|-------------|
| **Paid date** | No | Date of the payment (placeholder *Payment date*). Pick it from the calendar; dates are stored as YYYY-MM-DD |
| **Check number** | No | Cheque or reference number (placeholder *Check Number*) |
| **Amount** | Yes | Amount received (placeholder *Amount*). The window will not save while a line has no amount |
| **Action** | — | **(-) Remove payment** deletes the line when you click **Update Invoice** |

An invoice can have as many payment lines as you need. On the list, the number of lines shows as **N checks** under **Last payment**, and their sum shows as **paid $ …** under **Balance**.

### :fontawesome-solid-floppy-disk: Saving

Click **Update Invoice**. The window closes and the invoice row refreshes with the new balance, payments and status. Click **Close** to leave without saving.

!!! warning "Partial payments do not change the status"
    Adding payment lines never changes **Invoice Status** on its own. A part payment leaves the invoice as **new** or **Invoiced** until you pick **Partially Paid**. A payment that covers the whole total leaves it unpaid until you pick **Paid**. Set the status in the same window before clicking **Update Invoice**.

You can also manage payment lines and status from the full invoice form (cog menu > **Edit**). The **Balance Paid In Full** button is only in the **Record a payment** window. See [Creating Invoices](creating-invoices.md).

---

## :fontawesome-solid-tag: Changing the Status Inline

You can change an invoice's status straight from the list without opening anything:

1. Click the status text on the row (for example **Invoiced**).
2. A small editor titled *Enter new invoice status* opens.
3. Pick **new**, **Invoiced**, **Paid** or **Partially Paid** and confirm.

The change is saved immediately. This does not add or remove payment lines.

!!! warning "Avoid the blank option"
    The inline editor also offers an empty choice. An invoice with no status does not appear under any status tab except **All**, including **All Unpaid**. Use one of the four named statuses.

### Statuses

| Status | Meaning | Set by |
|--------|---------|--------|
| **new** | Created, not sent yet | Automatically when the invoice is created |
| **Invoiced** | Sent to the customer, waiting for payment | Automatically on the first successful send of a **new** invoice, or by you |
| **Partially Paid** | Some money received | You only |
| **Paid** | Fully settled | You only (directly, or with **Balance Paid In Full**) |

---

## :fontawesome-solid-scale-balanced: How Paid Affects Balances

**Paid** is the status that settles an invoice. Whatever the payment lines say, an invoice with status **Paid**:

- Shows a **Balance** of **$ 0.00**, and **paid $ …** equal to the full invoice total.
- Has no aging badge and is left out of every **AR Aging** filter and the **All Unpaid** tab.
- Gets a **paid date** of today if it has no payment line with a date and no paid date yet. This date appears under **Last payment** when there are no payment lines.

Any other status (**new**, **Invoiced**, **Partially Paid**) is treated as unpaid. Its **Balance** is the invoice total minus the sum of its payment lines, and it stays on **All Unpaid** and in aging, even when the payments cover the total. An invoice with a blank status also keeps its balance and aging badge, but it is only listed under **All**.

!!! tip "Find mismatches"
    Because **Paid** overrides the payment lines, a Paid invoice can have payment lines that don't add up to its total. **Audit Payments** on the Invoices page lists those. See [Invoices](invoices.md#audit-payments).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-circle-xmark: The row shows Failed! after sending

!!! info "Solution"
    Hover over **Failed!** to read the error. Common causes:

    - The email settings for invoices are wrong or the mail server refused the message. An admin can check with **Settings** > **Test Email Configuration**: enter an address in the *Enter recipient email* box and click **Send Test**. It sends one test email with the Notification settings and one with the Invoice settings. On success it reports *Test emails sent successfully to …*; otherwise it reports *Email test failed.* followed by which one failed (for example *Invoicing Failed: …*).
    - A POD or document could not be fetched. Check the order's documents, then send again.

    The status was not changed, so you can simply click the envelope and send again once the cause is fixed.

### :fontawesome-solid-at: "Please correct the email address and try again"

!!! info "Solution"
    One of the addresses in **To**, **Cc** or **Bcc** is not a valid email address. Separate several addresses with commas or semicolons, and check for typos. If the addresses look right, ask an admin to check the **Invoice 'From' Address Override** in **Settings**: if it holds something that is not a valid email address, every invoice send is rejected with this message. When it is left empty, your account's default sender address is used instead.

### :fontawesome-solid-file-circle-xmark: The customer didn't get a POD for one of the orders

!!! info "Solution"
    That order had no captured signature and no scanned signed POD when you sent. The yellow **WARNING** in the send window shows how many orders are missing one. Upload the POD to the order (see [Order Documents & POD](order-documents-and-pod.md)) and resend the invoice.

### :fontawesome-solid-file-pen: Why does the subject say REVISED?

!!! info "Solution"
    The invoice was already sent successfully once, so the new copy is marked as revised. Delete the word from **Subject** if you don't want it. The invoice PDF's file name will still include REVISED.

### :fontawesome-solid-file-pen: I resent an invoice but it wasn't marked REVISED

!!! info "Solution"
    The previous attempt failed. REVISED is only added when the last send succeeded. Type it into the subject yourself if needed.

### :fontawesome-solid-money-bill: I recorded the full payment but the invoice is still on All Unpaid

!!! info "Solution"
    Payments don't change the status. Set the status to **Paid**: click the status text on the row, or open **Record a payment** and change **Invoice Status**.

### :fontawesome-solid-arrows-rotate: I sent an invoice and its status didn't change to Invoiced

!!! info "Solution"
    The automatic change only happens when the status was **new**. An invoice already **Invoiced**, **Partially Paid** or **Paid** keeps its status when sent. If the row shows **Failed!**, the email was not sent.

### :fontawesome-solid-eye-slash: I can't find Balance Paid In Full

!!! info "Solution"
    The button is hidden when the invoice is already **Paid**, and it disappears after you click it once. It is only in the **Record a payment** window, not on the full **Edit** page.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips"
    - Keep every customer's **Accountant Email** and **Accountant Email (CC)** up to date so the send window fills itself correctly.
    - Look at the yellow POD warning before sending. Upload missing PODs first so the customer gets everything in one email.
    - Untick **Include documents** when the orders carry large or internal files the customer doesn't need.
    - Record every payment as its own line with the check number. It keeps **Audit Payments** and your reconciliation clean.
    - Set the status as you record money: **Partially Paid** for part payments, **Paid** once settled.

---

## Screenshots Needed

!!! info "Screenshots to capture"
    1. **Send invoice to customer** window with pre-filled fields, the yellow POD warning and the blue documents notice
    2. **Invoice row** after sending, showing the green **OK** label and **sent** date, and one with **Failed!** and its tooltip
    3. **Record a payment** window with **Balance Paid In Full** and two payment lines
    4. **Inline status editor** open on a row
