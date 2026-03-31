# Reports

Analyze your business performance with built-in reports covering income, deliveries, and driver activity.

## :fontawesome-solid-chart-bar: Overview

UTX Freight includes a suite of reports accessible from the **Reports** section in the left menu. Each report focuses on a different aspect of your business:

- :fontawesome-solid-dollar-sign: **Revenue reports** — Daily Income, Sales per Month, Income by Customer, Income by Shipper
- :fontawesome-solid-truck: **Operations reports** — Delivery by Zone, Drivers Delivery Report, Order Sales / Profit
- :fontawesome-solid-file-invoice-dollar: **Accounting reports** — Customer Reports (statements), Aged Receivables, AR Export

**How to get there:**

- :fontawesome-solid-arrow-right: From the left menu, expand **Reports** and select a report.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-tie: **Admin / Manager** | Full access to all reports |
| :fontawesome-solid-headset: **Dispatch** | Driver Delivery Report only |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Customer Reports, AR reports |

---

## :fontawesome-solid-dollar-sign: Daily Income

Shows daily revenue broken down by income source. Use this report to see how much money came in on any given day.

**How to use:**

1. Go to **Reports > Daily Income**.
2. Select the **date range** to analyze.
3. View the daily breakdown.

<!-- TODO: Screenshot — Daily Income report showing a date range with daily revenue figures -->

---

## :fontawesome-solid-calendar-days: Sales per Month

Monthly revenue trends displayed over time. Useful for spotting seasonal patterns and tracking growth.

**How to use:**

1. Go to **Reports > Sales per Month**.
2. The report shows monthly totals.

<!-- TODO: Screenshot — Sales per Month report showing monthly revenue bars or table -->

---

## :fontawesome-solid-building: Income by Customer

Revenue analysis grouped by customer company. See which customers generate the most income.

**How to use:**

1. Go to **Reports > Income by Customer**.
2. View the list of customers ranked by revenue.
3. Click **Export** to download as CSV for further analysis.

---

## :fontawesome-solid-warehouse: Income by Shipper

Revenue analysis grouped by shipper (pickup client). Helps you understand which pickup locations drive the most business.

**How to use:**

1. Go to **Reports > Income by Shipper**.
2. View shippers ranked by revenue.

---

## :fontawesome-solid-map-location-dot: Delivery by Zone

Delivery count and revenue grouped by delivery zone. Useful for territory planning and route optimization.

**How to use:**

1. Go to **Reports > Delivery by Zone**.
2. View deliveries and revenue per zone.
3. Toggle between **chart** and **table** views.

---

## :fontawesome-solid-chart-line: Order Sales / Profit

Detailed sales and profit breakdown per order. See the base rate, charges, and profit margin for each completed order.

**How to use:**

1. Go to **Reports > Order Sales / Profit**.
2. Filter by date range and company.
3. Review individual order profitability.

<!-- TODO: Screenshot — Order Sales / Profit report showing a few order rows with rate, charges, and profit columns -->

---

## :fontawesome-solid-user: Drivers Delivery Report

Track driver performance — number of deliveries, pickups, and legs completed per driver.

**How to use:**

1. Go to **Reports > Drivers Delivery Report**.
2. Select the **date range**.
3. View each driver's delivery count and activity.

This report is also available to dispatchers.

---

## :fontawesome-solid-file-invoice: Customer Reports

Manage and send customer **statements of account**. This is the hub for the automatic statements feature.

**How to use:**

1. Go to **Reports > Customer Reports**.
2. View each customer's balance and scheduled statement delivery day.
3. Edit the **Delivery Day** column to set or change the automatic schedule.
4. Click :fontawesome-solid-square-check: to save.

The **Next Date** column shows when the next automatic statement will be delivered.

For full details on setting up automatic statements, see [Automatic Statements](automatic-statements.md).

---

## :fontawesome-solid-file-invoice-dollar: Aged Receivables (AR)

Two distinct AR reports help you track outstanding payments:

- **Performance AR Report** — 12-month operational view with total income
- **Standard Aged Receivables** — GAAP-compliant snapshot for accounting

For full details, see [Aged Receivables](aged-receivables.md).

---

## :fontawesome-solid-file-export: AR Export

Generate and download aged receivables reports for external use:

1. Go to **Reports > AR Export**.
2. Select the **Month** and **Year**.
3. Click **Generate Report** or **Update Report**.
4. Download the data as an **Excel** file.

!!! info "Regenerating"
    Clicking **Regenerate** overwrites any previously saved file for that month/year. Use this if you've updated invoices since the last generation.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### Report shows no data

!!! info "Solution"
    Check the **date range** filter — make sure it covers the period you expect. Also verify that orders in that period have been **completed and invoiced**, as most reports pull from invoiced/completed order data.

### Numbers don't match my accounting software

!!! info "Solution"
    UTX Freight reports use the **invoice date** and **order completion date** for calculations. Your accounting software may use different date fields (payment date, posting date). Use the **AR Export** to download the raw data and reconcile.

---

## Screenshots Needed

!!! info "Screenshots to capture"
    1. **Reports menu** — the expanded Reports section in the left sidebar showing all report names
    2. **Daily Income report** — showing a date range with daily figures
    3. **Order Sales / Profit** — showing order rows with rate, charges, and profit columns
    4. **Customer Reports** — showing the statement scheduling table with Delivery Day and Next Date columns
    5. **Drivers Delivery Report** — showing driver names with delivery counts
