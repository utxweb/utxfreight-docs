# Reports

Analyze income, deliveries, profit and driver activity for the current office with the built-in reports under **Reports** in the left menu.

## :fontawesome-solid-chart-bar: Overview

The **Reports** menu groups every freight report in one place. Each page opens under the **Analytics** heading, with the page title underneath.

- :fontawesome-solid-dollar-sign: **Income reports**: **Income by Customer**, **Income by Shipper**, **Daily Income**, **Sales per Month**
- :fontawesome-solid-truck: **Operations reports**: **Delivery by Zone**, **Order Sales / Profit**, **Drivers Delivery Report**
- :fontawesome-solid-file-invoice-dollar: **Accounts receivable**: **Customer Reports** (statements), **Aged Receivables (AR)**, **AR Export**
- :fontawesome-solid-building: **Current office only**: every report shows data for the office you are working in. If your account has several offices, switch office to see another office's figures. See [Multi-Office](multi-office.md).
- :fontawesome-solid-eye: **View only**: reports never change your orders or invoices. Only **Customer Reports** (sending statements and, with automatic statements, changing a customer's statement schedule) and **AR Export** (saving monthly files) do anything beyond displaying data.

### :fontawesome-solid-list-ol: Menu order

The **Reports** menu lists the pages in this order, with these exact labels:

| # | Menu label | What it shows | Based on |
|---|------------|---------------|----------|
| 1 | **Income by Customer** | Invoiced income and payments per customer (Bill To) | Invoice date |
| 2 | **Income by Shipper** | Invoiced order income per delivery location | Invoice date |
| 3 | **Delivery by Zone** | Number of orders delivered per zone, per day (chart) | Order delivery date |
| 4 | **Daily Income** | Total of order amounts per day (bar chart) | Order delivery date |
| 5 | **Sales per Month** | Number of invoices and sales before tax per month | Invoice date |
| 6 | **Order Sales / Profit** | Sales, expenses and profit per order | Order delivery date |
| 7 | **Drivers Delivery Report** | The legs one driver moved | Order delivery date |
| 8 | **Customer Reports** | Customers with unpaid invoices, statements | Unpaid invoices (no date filter) |
| 9 | **Aged Receivables (AR)** | Standard aged receivables as of a date | Due date |
| 10 | **AR Export** | Saved monthly AR Excel files | Invoice date (12 months) |

<!-- TODO: Screenshot — Reports menu expanded in the left sidebar showing all ten report labels -->

---

## :fontawesome-solid-bolt: Quick Start

1. In the left menu, click :fontawesome-solid-chart-bar: **Reports** to expand it.
2. Click the report you need.
3. Set the filters at the top of the page (dates, customer, shipper or driver).
4. Click the page's button to run it: **Update Report**, **Filter** or **Report**.

!!! tip "Which date does a report use?"
    Income by Customer, Income by Shipper and Sales per Month count **invoices by invoice date**. Daily Income, Delivery by Zone, Order Sales / Profit and Drivers Delivery Report count **orders by delivery date**, whether or not they are invoiced. That is why the same week can show different totals in different reports.

---

## :fontawesome-solid-shield-halved: Access & Permissions

Access to reports is all or nothing: a user who can see the **Reports** menu can open every report in it, and a user who cannot see the menu cannot open any of them.

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | All reports, always |
| :fontawesome-solid-user-tie: **Manager** | All reports, but only when reports are enabled for managers on your account. Otherwise the **Reports** menu is not shown and no report can be opened |
| :fontawesome-solid-headset: **Dispatch** | No access, including the **Drivers Delivery Report** |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access, including **Customer Reports** and the AR pages |
| :fontawesome-solid-user: **Customer**, **Warehouse**, **Garage**, drivers | No access |

**How to get there:**

- :fontawesome-solid-arrow-right: Left menu :fontawesome-solid-chart-bar: **Reports** > the report name.

!!! info "Manager can't see Reports?"
    Whether Managers can see the **Reports** menu is an account-level option, not a setting you can change in the app or on a user's profile. Contact UTX support if your managers need it. There is no way to give access to only some reports. See [User Roles](user-roles.md).

---

## :fontawesome-solid-building: Income by Customer

Invoiced income and payments received, per customer (the company the invoice is billed to), for a range of invoice dates.

<!-- TODO: Screenshot — Income by Customer page with the filter panel and the Summary table -->

### Filters

| Field | Default | Notes |
|-------|---------|-------|
| **Customer** | **[ALL CUSTOMERS]** | Pick one customer to also see the **Invoices** detail panel |
| **Start date** | First day of the previous month | Compared with the invoice date |
| **End date** | Last day of the previous month | Compared with the invoice date (inclusive) |

When you first open the page it shows the whole previous month for all customers. Click **Update Report** after changing a filter.

### Summary table

One row per customer that has at least one invoice in the date range, sorted by **All Income**, highest first. A **TOTALS** row closes the table.

| Column | What it shows |
|--------|---------------|
| **Customer** | Customer name in capitals. Click it to drill down to that customer |
| **Invoices** | Number of invoices dated in the range |
| **Completed Orders** | Number of orders on those invoices |
| **All Income** | Total of those invoices, taxes included, followed by the customer's currency |
| **Paid Income** | Amount paid on those invoices. A fully paid invoice counts in full; otherwise the payments recorded on it are added up |

### Drill-down: Invoices panel

Click a customer name (or pick a customer in the **Customer** filter and click **Update Report**). An **Invoices** panel appears under the summary, listing each invoice in the range in invoice date order, with one line per order on it:

| Column | Order line | Invoice line |
|--------|------------|--------------|
| **Invoice** | Invoice number (greyed) | Invoice number |
| **Invoice Date** | | Invoice date |
| **Order** | Order number | |
| **Deliver To** | Delivery location name | |
| **Container#** | Container number | |
| **Order Income** | Order total (before tax) | |
| **All Income** | | Invoice total with taxes |
| **Paid Income** | | Amount paid on the invoice |

To go back to all customers, set **Customer** to **[ALL CUSTOMERS]** and click **Update Report**.

### Export Report

Click **Export Report** to download the current report as a CSV file. The file contains the **summary only**: one line per customer with **Customer**, **Invoices**, **Completed Orders**, **All Income** and **Paid Income**, plus a **TOTALS** line. It does not include the invoice and order detail, and amounts have no currency label.

---

## :fontawesome-solid-warehouse: Income by Shipper

Invoiced order income grouped by the **delivery location** of each order, for a range of invoice dates.

!!! info "Grouped by delivery company, not pickup"
    This report groups orders by their **Deliver To** company (the order's delivery location from [Shippers / Receivers](shippers-receivers.md)), not by the pickup location and not by the customer who is billed. Use **Income by Customer** for income per billed customer.

### Filters

| Field | Default | Notes |
|-------|---------|-------|
| **Shipper** | **[ALL SHIPPERS]** | Lists all shippers / receivers of the office. Pick one to see the **Invoices** detail panel |
| **Start date** | First day of the previous month | Compared with the invoice date of the order's invoice |
| **End date** | Last day of the previous month | Inclusive |

Only invoiced orders count: an order that is not on an invoice dated in the range is left out. Click **Update Report** after changing a filter.

### Summary table

One row per delivery location, sorted by **All Income**, highest first, with a **TOTALS** row.

| Column | What it shows |
|--------|---------------|
| **Shipper** | Delivery location name in capitals. Click it to drill down |
| **Invoices** | Number of different invoices those orders are on |
| **Completed Orders** | Number of invoiced orders delivered to that location |
| **All Income** | Sum of those orders' totals, **before tax** |

### Drill-down: Invoices panel

Click a shipper name (or pick one in the **Shipper** filter). The **Invoices** panel lists each invoice with its orders for that location:

| Column | Order line | Invoice line |
|--------|------------|--------------|
| **Invoice** | Invoice number (greyed) | Invoice number |
| **Date** | | Invoice date |
| **Order** | Order number | |
| **Bill To** | Customer billed for the order | |
| **Container#** | Container number | |
| **Order Income** | Order total (before tax) | |
| **All Income** | | Whole invoice total with taxes |
| **Paid Income** | | Amount paid on the whole invoice |

!!! info "Invoice lines cover the whole invoice"
    **All Income** and **Paid Income** on an invoice line are for the entire invoice, including orders delivered elsewhere. Only the order lines are limited to the selected location.

This report has no export button.

---

## :fontawesome-solid-map-location-dot: Delivery by Zone

A chart of how many orders were delivered in each zone, day by day. It counts orders only: it shows no revenue and has no table.

<!-- TODO: Screenshot — Delivery by Zone bar chart with several zones and a No Zone series -->

### Filters

| Field | Default | Options |
|-------|---------|---------|
| **Start date** | Monday of last week | Compared with the order delivery date |
| **End date** | Sunday of this week | Inclusive |
| **Chart type** | **Bar Chart** | **Bar Chart**, **Stacked Bar Chart**, **Line Chart** |

Click **Update Report** to redraw the chart.

### How orders are counted

- :fontawesome-solid-calendar-day: Each point is the number of orders with that **delivery date**, whatever their status (invoiced or not).
- :fontawesome-solid-location-dot: The zone comes from the city of the order's **delivery location**, using the zone assigned to that city in [Zones & Cities](zones-and-cities.md).
- :fontawesome-solid-circle-question: **No Zone** is a series of its own: orders whose delivery location's city has no zone.
- :fontawesome-solid-ban: Orders whose delivery location has no city, and orders with no delivery location picked from [Shippers / Receivers](shippers-receivers.md), are not counted in any series.
- Days with no deliveries in a zone have no point for that zone.
- :fontawesome-solid-download: Use the chart toolbar (top right of the chart) to download the chart as an image. There is no table or CSV export.

---

## :fontawesome-solid-dollar-sign: Daily Income

A bar chart with one bar per day: the total of order amounts for that day.

<!-- TODO: Screenshot — Daily Income chart for 7 days with the Start Date and Days fields -->

### Filters

| Field | Default | Notes |
|-------|---------|-------|
| **Start Date** | 7 days ago | First day of the chart |
| **Days** | **7** | Number of days to show, starting on **Start Date** |

Click **Filter** to redraw the chart. Hover a bar to see **Income for YYYY-MM-DD:** followed by the amount and **$**.

### How it is calculated

- :fontawesome-solid-calendar-day: Orders are placed on the day of their **delivery date**.
- :fontawesome-solid-calculator: Each day's value is the sum of those orders' **totals** (the order amount before tax).
- :fontawesome-solid-layer-group: All orders count, whatever their status, invoiced or not.
- :fontawesome-solid-chart-line: The page shows the chart only. There is no table and no export.

---

## :fontawesome-solid-calendar-days: Sales per Month

A table of invoiced sales per month for about the last 22 months (the current month and the 21 before it), newest first.

<!-- TODO: Screenshot — Sales per month table showing #, Month, Invoices # and Sales columns -->

| Column | What it shows |
|--------|---------------|
| **#** | Row number |
| **Month** | Month and year, for example **Mar 2026** |
| **Invoices #** | Number of invoices with an invoice date in that month |
| **Sales** | Sum of those invoices' subtotals, **before tax** |

There are no filters on this page.

!!! info "Figures are precomputed"
    The monthly figures are calculated regularly in the background, and the page shows the most recent calculation, so a change you just made may take a little while to appear. The current month is a month-to-date figure. Use **Income by Customer** for a period when you need live figures.

---

## :fontawesome-solid-chart-line: Order Sales / Profit

Sales, expenses and profit for each order delivered in a date range. The page heading reads **Order sales / profits**.

<!-- TODO: Screenshot — Order sales / profits table with a few order rows and the Totals and Average Per Order rows -->

### Filters

| Field | Default | Notes |
|-------|---------|-------|
| **Start Date** | 7 days ago | First delivery date included |
| **Days** | **7** | Number of days included. **0** is treated as **1** |

Click **Filter** to refresh. There is no customer or company filter, and all orders count whatever their status.

### Columns

| Column | What it shows |
|--------|---------------|
| **#** | Row number |
| **Delivery Date** | Order delivery date (rows are sorted by it) |
| **Order #** | Order number |
| **Container #** | Container number |
| **P/O #** | Delivery P/O number |
| **Booking #** | Booking number |
| **Client** | The order's delivery location (Deliver To company), not the billed customer. For a transfer order it shows the customer's company name |
| **Sales** | Order total, before tax |
| **Expenses** | Sum of the expense lines in the order's **Order Expenses** section |
| **Profits** | **Sales** minus **Expenses** |

Two rows close the table when there is at least one order: **Totals** (sum of each money column) and **Average Per Order** (each total divided by the number of orders).

!!! info "Profit is an amount, not a margin"
    **Profits** is a dollar amount. The report does not show a percentage margin. Expenses come from the **Order Expenses** panel on each order; an order with no expenses shows its whole total as profit. See [Order Rates, Charges & Expenses](order-charges-and-expenses.md).

---

## :fontawesome-solid-user: Drivers Delivery Report

The list of legs one driver moved, for orders delivered in a date range. The page heading reads **Driver Delivery Report**.

<!-- TODO: Screenshot — Driver Delivery Report results for one driver showing the leg list -->

### Running the report

1. Go to **Reports** > **Drivers Delivery Report**.
2. Pick the **Driver**. The list shows active drivers.
3. Set **Start Date** (default: 7 days ago) and **Days** (default: **7**; **0** is treated as **1**).
4. Click **Report**. The results appear below the filters without reloading the page.

The report covers one driver at a time. To compare drivers, run it once per driver.

### Results

The header shows **Driver Name:** and **Date:** (a single date, or **start to end** for a range). Then one row per leg:

| Column | What it shows |
|--------|---------------|
| **Leg** | Row number (#1, #2, ...) |
| **Date** | The order's delivery date |
| **Order #** | Order number |
| **Container #** | Container number |
| **Move** | **From => To** move locations of the leg; **N/A** when a location is missing |

- :fontawesome-solid-user-check: A leg is included when the selected driver is recorded as the driver who moved it.
- :fontawesome-solid-calendar-day: The date range filters on the **order's delivery date**, not on when the leg was moved. Legs are sorted by that date.
- :fontawesome-solid-ban: The report shows no counts, totals or pay. Count the rows if you need a number of moves. Driver pay is recorded in **Order Expenses** and on [Expenses & Checks](expenses-and-checks.md).

See [Order Legs & Move Locations](order-legs-and-move-locations.md) for how legs are recorded.

---

## :fontawesome-solid-file-invoice: Customer Reports

The statements page: one row per customer with unpaid invoices, where you email, print or download a **Statement of Account**. Full details are in [Customer Statements](customer-statements.md).

<!-- TODO: Screenshot — Customer Reports table showing the current columns (Past Due, Not Yet Due) and the Email, Print and Excel buttons -->

- :fontawesome-solid-filter: **Which customers appear**: only customers that have at least one invoice whose status is not **Paid**. Customers with everything paid are not listed. There is no date filter.
- :fontawesome-solid-user: **Customer** filter: **[ALL CUSTOMERS]** by default, or pick one customer and click **Update Report**.
- :fontawesome-solid-book-open: The list is paginated.

### Columns

| Column | What it shows |
|--------|---------------|
| **Status** | Red :fontawesome-solid-dollar-sign: when the customer has past due invoices, green :fontawesome-solid-check: otherwise |
| **Name** | Customer name, in red when the customer is inactive |
| **Orders** | Number of orders for the customer |
| **Invoices** | Number of invoices for the customer |
| **Income** | Total of all the customer's orders, all dates, before tax |
| **Past Due** | Unpaid balance (with taxes, minus payments) of invoices not marked **Paid** whose due date is before today |
| **Not Yet Due** | Unpaid balance of the other invoices not marked **Paid** (due today or later) |
| **Unpaid Invoices** | Number of past due invoices, as a red badge when above zero |
| **Sent date** | Date the last statement was emailed, or **-** |
| **Email** | Result of the last statement email (for example **OK** or **Failed!**) |
| **Delivery Day / Next Date** | Only when automatic statements are enabled on your account: the statement schedule (or **Not Scheduled**) and when the next one goes out. Click it to change the schedule |
| *(buttons)* | **Email**, **Print**, and the green Excel download |

When automatic statements are enabled, the top of the page also shows how many customers are scheduled on each day (**Sun** to **Sat**, **1st**, **15th**, **2nd & 16th**). See [Automatic Statements](automatic-statements.md).

---

## :fontawesome-solid-file-invoice-dollar: Aged Receivables (AR)

The **Aged Receivables (AR)** page shows unpaid balances per customer as of a date, aged by due date (**Not Yet Overdue**, **30 or Less**, **31 to 60**, **61 to 90**, **91 or More**, **Total Unpaid**). Pick the **As of Date**, click **Update Report**, and click **Download Excel** for the same figures as an `.xlsx` file.

For full details, see [Aged Receivables](aged-receivables.md).

---

## :fontawesome-solid-file-export: AR Export

**AR Export** generates and keeps monthly AR Excel files, so you can download a month's figures later. The page itself is headed **Aged Receivables (AR)** under **Analytics**, and the list of files is headed **AR Reports**. A note at the top explains that this is a business performance report covering the 12 months ending on the selected month.

1. Go to **Reports** > **AR Export**.
2. In **Report Period**, pick a quick selection (**This Month**, the default, **Last Month**, **2 Months Ago** or **3 Months Ago**, each shown with its month and year). To pick another month, choose **Custom Month/Year** and then select the **Month** and **Year** (from five years back to next year).
3. Click **Generate Report**. The file is built straight away.
4. In **Generated Reports**, click the green Excel button in the **Download** column once the **Status** is **Ready**.

The **Generated Reports** table shows **Month/Year**, **Status** (**Ready**, **Generating** or **Failed**), **Total Income**, **Duration**, **Generated At**, and the **Download**, **Regenerate** and **Delete** buttons. **Total Income** is the total of the invoices (with taxes) in the 12-month period. Only one report can exist per month and year: generating a month that already exists shows an error asking you to use **Regenerate**. **Regenerate** is available on **Ready** reports; a **Failed** report can only be deleted, then generated again.

!!! info "The export is aggregated, not raw data"
    The Excel file has **one row per customer** of the office (every customer that is not deleted, including those with no invoices), not one row per invoice. Columns: **Customer**, **Invoices**, **Completed Orders**, **All Income** (with taxes), **AR As Of YYYY-MM-DD** (the unpaid total as of the last day of the selected month), **30 days**, **60 days**, **90 days** and **90+ days**, plus a **TOTALS** row. It covers invoices dated in the 12 months ending on the last day of the selected month.

    Unlike **Aged Receivables (AR)**, the AR Export ages unpaid amounts by **invoice date** (days from the invoice date to the end of the month), not by due date, and counts only payments dated on or before the end of the month. To see individual invoices, use **Income by Customer** or the [Invoices](invoices.md) list.

!!! warning "Regenerating replaces the file"
    **Regenerate** deletes the saved file for that month and builds a new one from current data. Use it after you correct invoices or record payments.

---

## :fontawesome-solid-screwdriver-wrench: Garage Reports

If your account has the Garage add-on, garage reports are under **Reports** in the Garage sidebar, not in the freight **Reports** menu. See [Garage Reports](garage-reports.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see the Reports menu

!!! info "Solution"
    Only **Admin** users always see **Reports**. **Manager** users see it only when reports are enabled for managers on your account (contact UTX support). **Dispatch** and **Accountant** users never see it, and there is no per-report access.

### :fontawesome-solid-calendar-xmark: Report shows no data

!!! info "Solution"
    Check which date the report uses:

    - **Income by Customer**, **Income by Shipper**, **Sales per Month** and **AR Export** only count **invoices**, by **invoice date**. Orders that are not invoiced yet do not appear.
    - **Daily Income**, **Delivery by Zone**, **Order Sales / Profit** and **Drivers Delivery Report** count **orders** by **delivery date**, invoiced or not.

    Also check that you are in the right office: reports only show the current office.

### :fontawesome-solid-scale-unbalanced: Two reports show different totals for the same period

!!! info "Solution"
    This is expected. The reports use different dates and amounts:

    | Report | Date used | Amount |
    |--------|-----------|--------|
    | Income by Customer | Invoice date | Invoice total **with** taxes |
    | Income by Shipper | Invoice date | Order totals **before** tax |
    | Sales per Month | Invoice date | Invoice subtotal **before** tax |
    | Daily Income | Delivery date | Order totals **before** tax |
    | Order Sales / Profit | Delivery date | Order totals **before** tax |

    An order delivered at the end of one month and invoiced in the next falls in different months depending on the report.

### :fontawesome-solid-calendar-days: Sales per Month doesn't match Income by Customer

!!! info "Solution"
    **Sales per Month** is before tax and shows figures calculated regularly in the background, so a very recent change may not show yet. **Income by Customer** is live and includes taxes. Compare against **Income by Customer** for the same month to check live figures.

### :fontawesome-solid-file-csv: The Income by Customer export has no invoice detail

!!! info "Solution"
    **Export Report** only exports the summary (one line per customer plus **TOTALS**). For invoice and order detail, drill down on the page.

### :fontawesome-solid-map: Orders are missing from Delivery by Zone

!!! info "Solution"
    Orders count only when their delivery location has a city. Orders whose city has no zone appear under **No Zone**. Give the city a zone in [Zones & Cities](zones-and-cities.md).

### :fontawesome-solid-calculator: Numbers don't match my accounting software

!!! info "Solution"
    Accounting software often uses payment or posting dates, while UTX Freight reports use invoice dates or delivery dates (see the table above). For month-end reconciliation, use **Aged Receivables (AR)** (as of a date, by due date) or the **AR Export** file. Note that the AR Export is aggregated per customer; it is not a raw invoice list.

---

## :fontawesome-solid-star: Best Practices

!!! tip "Tips for reliable reports"
    - Use **Income by Customer** or **Sales per Month** for invoiced revenue, and **Daily Income** or **Order Sales / Profit** for work delivered but not necessarily billed yet.
    - Record **Order Expenses** on every order so **Order Sales / Profit** shows real profit.
    - Assign a zone to every city your customers deliver to, so **Delivery by Zone** has as few **No Zone** orders as possible.
    - Generate an **AR Export** at each month end and keep it as your record of that month.
