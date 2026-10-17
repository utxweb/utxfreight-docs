# Customer Statements

Email, print or download a **Statement of Account** that lists a customer's unpaid invoices, split into past due and not yet due, from the **Customer Reports** page.

## :fontawesome-solid-file-invoice-dollar: Overview

- :fontawesome-solid-list: **One row per customer**: **Reports** > **Customer Reports** lists every customer that has at least one invoice whose status is not **Paid**, with their balances and the result of the last statement email.
- :fontawesome-solid-envelope: **Email**: the blue **Email** button on a row opens the **Send statement to customer** window. The statement is attached as a PDF or an Excel file, depending on the customer's **Default Statement Format**.
- :fontawesome-solid-print: **Print**: opens the statement in a new browser tab, ready to print or save as PDF from your browser.
- :fontawesome-solid-file-excel: **Excel**: the green Excel button downloads the statement as an `.xlsx` file.
- :fontawesome-solid-circle-check: **Delivery tracking**: after each send, the row shows the **Sent date** and an **OK** or **Failed!** label in the **Email** column.
- :fontawesome-solid-scale-balanced: **Balances only count unpaid invoices**: every invoice whose status is not **Paid** is included. Amounts are the invoice total with taxes minus the payments recorded on it.

!!! info "Manual vs automatic statements"
    This page covers statements you send yourself. To have statements emailed on a fixed weekday, see [Automatic Statements](automatic-statements.md). A manual send always goes out when you click **Send**, even if the customer's balance is zero. The automatic schedule only sends when the balance is greater than zero.

<!-- TODO: Screenshot — Customer Reports page showing the customer table with the Email, Print and Excel buttons -->

---

## :fontawesome-solid-bolt: Quick Start

**To email a statement:**

1. Go to **Reports** > **Customer Reports**.
2. Find the customer and click the blue **Email** button on their row.
3. Check the **To** and **Cc** addresses, and add a **Bcc** if needed.
4. Check the format line at the bottom of the window (PDF or Excel icon).
5. Click **Send**. A notification confirms the result, and the row updates with today's **Sent date** and **OK** (or **Failed!**).

**To print or download a statement:**

1. Go to **Reports** > **Customer Reports**.
2. Click **Print** to open the statement in a new tab, or click the green Excel button to download the `.xlsx` file.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Full access: view **Customer Reports**, email, print and download statements |
| :fontawesome-solid-user-tie: **Manager** | Same as Admin, but only when reports are enabled for managers on your account. Otherwise the **Reports** menu is not shown |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access to the **Reports** menu, so cannot open **Customer Reports** |
| :fontawesome-solid-headset: **Dispatch** | No access to the **Reports** menu |
| :fontawesome-solid-user: **Customer**, **Warehouse**, **Garage**, drivers | No access |

Two permissions are involved:

- **Opening Customer Reports** requires access to **Reports** (the same access that shows the **Reports** menu in the left navigation).
- **Sending a statement** also requires permission to manage customers. Admins and Managers have it.

**How to get there:**

- :fontawesome-solid-arrow-right: Left menu :fontawesome-solid-chart-bar: **Reports** > **Customer Reports**

!!! tip "Manager can't see Reports?"
    Whether Managers can see the **Reports** menu is an account-level option. Contact UTX support if your managers need it.

---

## :fontawesome-solid-table: The Customer Reports Page

### :fontawesome-solid-filter: Choosing customers

At the top of the page, the **Customer** dropdown lets you pick one customer. Click **Update Report** to apply.

- **[ALL CUSTOMERS]** (the default) shows every customer that has at least one invoice whose status is not **Paid**. Customers whose invoices are all **Paid** do not appear.
- Picking a single customer shows only that customer, even if all their invoices are paid.
- The list shows 30 customers per page. Active customers come first, then inactive ones, each sorted by name. Use the page links at the bottom to see more.

### :fontawesome-solid-table-columns: Columns

| Column | What it shows |
|--------|---------------|
| **Status** | A red :fontawesome-solid-dollar-sign: label if the customer has at least one past due invoice, a green :fontawesome-solid-check: label if not |
| **Name** | Customer name. Inactive customers are shown in red |
| **Orders** | Number of orders for this customer |
| **Invoices** | Number of invoices for this customer, all statuses |
| **Income** | Total of all the customer's orders |
| **Past Due** | Unpaid balance of invoices whose due date is before today |
| **Not Yet Due** | Unpaid balance of invoices due today or later |
| **Unpaid Invoices** | Number of **past due** invoices (shown in a red label when above zero) |
| **Sent date** | Date of the last statement send, or **-** if none was recorded. A manual send only updates it when the email goes out. An [automatic statement](automatic-statements.md) run also updates it, including a run that skipped a zero balance or failed |
| **Email** | Result of the last statement send: **OK** (green) or **Failed!** (red), empty if no statement was ever sent. Hover the label to see the message: **Statement Delivered**, **Statement Not Sent (0.0$)** (an automatic run skipped a zero balance, still shown as **OK**), or the error |
| **Delivery Day / Next Date** | Only when automatic statements are enabled. See [Automatic Statements](automatic-statements.md) |
| *(buttons)* | **Email**, **Print** and the green Excel button |

!!! info "Unpaid means not Paid"
    An invoice counts as unpaid as long as its status is not **Paid**, whatever payments are recorded on it. Its amount is the invoice total with taxes minus the payments recorded. To remove an invoice from statements, set its status to **Paid** (see [Sending Invoices & Recording Payments](invoice-email-and-payments.md)).

---

## :fontawesome-solid-envelope: Emailing a Statement

### :fontawesome-solid-window-maximize: The Send statement to customer window

Click the blue **Email** button on a customer's row. The **Send statement to customer** window opens. Starred (\*) fields are required.

| Field | Prefilled with | Notes |
|-------|----------------|-------|
| **To** \* | The customer's **Accountant Email** | Required. You can enter several addresses separated by commas |
| **Cc** | The customer's **Accountant Email (CC)** | Optional. Several addresses allowed, separated by commas |
| **Bcc** | Empty | Optional. Several addresses allowed, separated by commas |

Both prefilled addresses come from the customer's record. To change them for future sends, edit the customer (see [Managing Customers](managing-customers.md)).

Below the fields, the window reads **The customer will receive the statement in [icon] format**:

- a red :fontawesome-solid-file-pdf: PDF icon means the statement is attached as a PDF
- a green :fontawesome-solid-file-excel: Excel icon means the statement is attached as an Excel (`.xlsx`) file

The format follows the customer's **Default Statement Format**. You cannot change it in this window.

Click **Send** to send, or **Close** to cancel. While the email is being sent, the row shows a wait indicator in place of the **Email** button. When it finishes, the row refreshes.

### :fontawesome-solid-bell: Notifications

| Result | Notification | Row after send |
|--------|--------------|----------------|
| Sent | **Statement Sent!** — *The statement was sent successfully.* | **Sent date** set to today, **Email** shows **OK** (hover: *Statement Delivered*) |
| Sending error | **Sending Statement Failed!** — *The statement was not sent due to [error]. Please try again or contact the administrator.* | **Sent date** unchanged, **Email** shows **Failed!** (hover shows the error) |

!!! warning "Zero balance statements are still sent"
    A manual send does not check the balance. If the customer owes nothing, they still receive a statement showing zero amounts. Check the **Past Due** and **Not Yet Due** columns before you click **Send**.

### :fontawesome-solid-at: The email the customer receives

| Part | Content |
|------|---------|
| **Subject** | `<Your company> Statement of Account as of <YYYY-MM-DD>` |
| **Subject (multi-office)** | `<Your company> Statement of Account as of <YYYY-MM-DD> - <Office name>`, where the office is the one you are currently working in |
| **Attachment (PDF)** | `Statement of account as of <YYYY-MM-DD>.pdf` |
| **Attachment (Excel)** | `Statement of account as of <YYYY-MM-DD>.xlsx` |
| **Body** | A **Statement of Account for <date>** heading, a note that the attachment contains the current statement of the account as a PDF (or XLSX), **Thank you!**, and your company name |

The date is the day the statement is sent. The email is sent through your invoice email settings.

!!! info "Multi-office"
    When your account uses [multiple offices](multi-office.md), the emailed statement only includes the customer's invoices from the office you are currently working in, and the office name is added to the subject. Switch office before sending if you need another office's statement.

---

## :fontawesome-solid-file-pdf: PDF vs Excel Format

Each customer has a **Default Statement Format** on their customer record (in the **Rate to apply for new orders** section of the customer form):

| Option | What the customer receives |
|--------|----------------------------|
| **PDF Format** (default) | The statement as a PDF attachment |
| **Excel (.xlsx)** | The statement as an Excel attachment |

1. Go to **Customers**, find the customer and edit them.
2. Choose **Default Statement Format**.
3. Save the customer.

This setting only controls the emailed attachment. The **Print** and Excel buttons on **Customer Reports** are available for every customer.

---

## :fontawesome-solid-file-lines: What the Statement Contains

### :fontawesome-solid-file-pdf: PDF and Print version

The **Print** page and the PDF attachment use the same layout.

**Left side:**

1. **Customer Statement** heading and the customer name.
2. A summary box **Customer Statement as of <date>**:

    | Line | Amount |
    |------|--------|
    | **Past Due** | Unpaid balance of invoices whose due date is before today |
    | **Not Yet Due** | Unpaid balance of invoices due today or later |
    | **Total Billed** | Unpaid balance of all invoices that are not **Paid** |

3. A **Detailed Summary** with two tables, **Past Due** and **Not Yet Due**. Each lists **Invoice** (invoice number), **Issue Date**, **Due Date** and **Amount** (the remaining balance of that invoice).
4. A **Total Billed** line at the bottom.

All amounts are followed by the customer's **Default Currency** (CAD or USD).

**Right side (your company block):** your logo, address, city and province/state, postal code, **Tel:**, **Fax:**, website, and the line **THANK YOU FOR YOUR BUSINESS!**

!!! info "Per-order detail"
    On accounts where detailed statements are enabled, each invoice in the detailed tables is followed by one line per order on it, showing the container number, the order reference number and the order total. This is an account-level option. Contact UTX support to turn it on or off.

### :fontawesome-solid-file-excel: Excel version

The Excel file has one sheet named **Statement**. The download from the green button is named `<Customer name> Statement of Account as of <YYYY-MM-DD>.xlsx`. The emailed attachment uses the name shown in the email table above.

| Rows | Content |
|------|---------|
| 1–2 | **Invoice Statement**, then the customer name |
| 4 | **Invoice Statement as of <date>** |
| 5 | **Past Due Invoices** and the past due balance (column D), currency (column E) |
| 6 | **Due Invoices** and the not yet due balance |
| 7 | **Total Billed** and the total unpaid balance |
| 9 | **Detailed Summary** |
| 10 onward | **Past Due Invoices** table with **Invoice**, **Issue Date**, **Due Date**, **Amount** columns |
| Next | **Due Invoices** table with the same columns |
| Last | **Total Billed** |

Your company block (company name in capitals, address, city and province/state, postal code, **Tel:**, **Fax:**, website and **THANK YOU FOR YOUR BUSINESS!**) is in column H, rows 4 to 11. When detailed statements are enabled, per-order lines (container number, reference number, order total) appear under each invoice, as in the PDF.

!!! info "Section names in the Excel file"
    In the Excel file, the **Due Invoices** section holds the invoices due today or later, the same invoices as the **Not Yet Due** section of the PDF. Past due invoices are under **Past Due Invoices**.

!!! info "Print and Excel buttons are not filtered by office"
    The **Print** and Excel buttons, and the balance columns on the **Customer Reports** page, include all of the customer's unpaid invoices from every office. Only the emailed statement is limited to the current office on multi-office accounts.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-user-slash: A customer is missing from Customer Reports

!!! info "Solution"
    With **[ALL CUSTOMERS]** selected, only customers with at least one invoice that is not **Paid** are listed. If all of a customer's invoices are **Paid**, select the customer by name in the **Customer** dropdown and click **Update Report**. Also check the other pages of the list (30 customers per page).

### :fontawesome-solid-circle-xmark: The Email column shows Failed!

!!! info "Solution"
    Hover the **Failed!** label to read the error. Check the addresses in **To**, **Cc** and **Bcc**, then send again. If the error is about the mail server or authentication, ask your administrator to check the invoice email settings in [Application Settings](application-settings.md).

### :fontawesome-solid-envelope-open: The To field is empty when I open the window

!!! info "Solution"
    **To** is prefilled from the customer's **Accountant Email**. If the customer has none, type the address in the window, or edit the customer and fill in **Accountant Email** (and **Accountant Email (CC)**) so it is prefilled next time.

### :fontawesome-solid-file-excel: The customer received Excel but wanted a PDF (or the reverse)

!!! info "Solution"
    Edit the customer and change **Default Statement Format** to **PDF Format** or **Excel (.xlsx)**, save, then send the statement again.

### :fontawesome-solid-money-bill: A paid invoice still appears on the statement

!!! info "Solution"
    Statements include every invoice whose status is not **Paid**, even if payments cover the full amount. Set the invoice status to **Paid** (see [Sending Invoices & Recording Payments](invoice-email-and-payments.md)).

---

## :fontawesome-solid-star: Best Practices

!!! tip "Tips"
    - Fill in **Accountant Email**, **Accountant Email (CC)** and **Default Statement Format** on each customer so statements go to the right people in the right format without retyping.
    - Mark invoices **Paid** as soon as payment is complete so statements only show what is really owed.
    - Check the **Past Due** and **Not Yet Due** columns before sending: a manual send goes out even when the balance is zero.
    - Use **Print** to preview the statement layout before emailing it (on multi-office accounts, remember the email only includes the current office's invoices).
    - For regular statements, set up [Automatic Statements](automatic-statements.md) instead of sending each one by hand.
