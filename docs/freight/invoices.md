# Invoices

Create invoices from completed orders, track payments, and export for accounting.

## :fontawesome-solid-file-invoice-dollar: Overview

The **Invoices** page is where you manage the billing cycle — from creating invoices for completed orders to tracking payments and exporting data for your accounting system.

- :fontawesome-solid-plus: **Create invoices** from completed orders
- :fontawesome-solid-envelope: **Email invoices** directly to customers
- :fontawesome-solid-filter: **Track payment status** — New, Invoiced, Paid, Partially Paid
- :fontawesome-solid-clock: **Monitor overdue invoices** — Past Due, 30+, 60+ day filters
- :fontawesome-solid-file-export: **Export** to CSV, Excel, or QuickBooks format

<!-- TODO: Screenshot — The Invoices list page showing filter tabs, search bar, and invoice rows with status badges -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Invoices** from the left menu.
2. Click **Create Invoice** (or create from a completed order).
3. Review the invoice details and charges.
4. Click **Send** to email it to the customer.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-tie: **Admin / Manager** | Full access — create, edit, send, delete |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Full access |
| :fontawesome-solid-headset: **Dispatch** | View only |

**How to get there:**

- :fontawesome-solid-arrow-right: From the left menu, click **Invoices**

---

## :fontawesome-solid-filter: Invoice Filters

The filter bar at the top helps you manage your invoice pipeline:

### Payment Status

| Filter | Shows |
|--------|-------|
| **All** | All invoices |
| **All Unpaid** | Everything that hasn't been fully paid |
| **New** | Invoices created but not yet sent |
| **Invoiced** | Sent to the customer, awaiting payment |
| **Paid** | Fully paid invoices |
| **Partially Paid** | Invoices with partial payments recorded |

### Overdue

| Filter | Shows |
|--------|-------|
| **Past Due** | Any invoice past its due date |
| **Past Due (30+ days)** | Invoices overdue by 30 or more days |
| **Past Due (60+ days)** | Invoices overdue by 60 or more days |

---

## :fontawesome-solid-table: Invoice List Columns

The invoice list shows:

| Column | Description |
|--------|-------------|
| **Invoice #** | Unique invoice number |
| **Invoice date** | Date the invoice was created |
| **Company** | Customer company name |
| **Invoice Total** | Total amount including taxes |
| **Due date** | Payment due date based on invoice terms |
| **Last Payment** | Date of the most recent payment |
| **Total Paid** | Amount paid so far |
| **Checks** | Associated check numbers |
| **Status** | New / Invoiced / Paid / Partially Paid |
| **Sent date** | Date the invoice was emailed |

The footer row shows the **total count** and **sum** of all invoices matching the current filter.

---

## :fontawesome-solid-envelope: Sending Invoices

To email an invoice to a customer:

1. Find the invoice in the list.
2. Click the **Email** action on the invoice row.
3. The invoice is sent to the customer's **Accountant Email** (configured on the customer profile).
4. The invoice status automatically changes to **Invoiced**.

!!! tip "Tip"
    If you send an invoice multiple times, subsequent emails are marked **REVISED** to indicate an updated version.

---

## :fontawesome-solid-money-bill: Recording Payments

### Pay in Full

Click the **Pay in Full** action on an invoice to record full payment. The **Paid Date** is set automatically.

### Partial Payments

Record partial payments against an invoice. The status changes to **Partially Paid** and the **Total Paid** column updates.

### Bulk Payment Updates

Use **Audit Payments** to review and update payments across multiple invoices at once.

<!-- TODO: Screenshot — The invoice detail showing the payment section with Pay in Full button -->

---

## :fontawesome-solid-file-export: Exporting Invoices

Click the **Export** dropdown on the Invoices page:

| Option | Format | Description |
|--------|--------|-------------|
| **CSV** | .csv | Comma-separated values for spreadsheets |
| **Excel** | .xlsx | Native Excel format |

Select the **year** and **format**, then click **Export**.

### QuickBooks Export

If your company uses QuickBooks, you can export invoices in a QuickBooks-compatible format for direct import into your accounting software.

---

## :fontawesome-solid-magnifying-glass: Invoice Discrepancies

The discrepancies feature helps identify payment mismatches — invoices where the amount paid doesn't match the invoice total. This is useful for reconciliation and month-end close.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### Customer didn't receive the invoice email

!!! info "Solution"
    Check the customer's **Accountant Email** field in their company profile (**Customers > Edit**). Also verify your email settings in **Settings** — the Invoice Mailer must be configured correctly. You can use the **Test Email Configuration** feature in Settings to verify.

### Can't create an invoice — no orders available

!!! info "Solution"
    Only **Completed** orders that are **not yet invoiced** can be added to an invoice. Check the order status on the **Orders** page. If the order is still Dispatched, it needs to be completed first.

### Invoice shows wrong charges

!!! info "Solution"
    Invoice charges come from the order. Edit the order to adjust the **base rate**, **terminal fees**, or **fuel surcharge**, then regenerate the invoice. Automatic charges (terminal fees, fuel surcharge) are recalculated based on the order's terminal and delivery date.

---

## Screenshots Needed

!!! info "Screenshots to capture"
    1. **Invoices list page** — showing filter tabs (All Unpaid / Past Due / New / Invoiced / Paid), a few invoice rows, and the total footer
    2. **Invoice detail** — showing the invoice with line items, charges, and payment section
    3. **Export dropdown** — showing the year selector and CSV/Excel format options
    4. **Bulk Audit Payments** — the audit payments view (if visually distinct)
