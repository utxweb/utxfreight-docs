# Warehouse Orders

Record the goods you store for a customer, the warehouse charges that apply, and the storage period, then let UTX Freight calculate the amount to bill.

## :fontawesome-solid-warehouse: Overview

- :fontawesome-solid-list: **Warehouse** > **Orders** opens the **Warehouse Orders** page. It shows three counters (**Open Orders**, **Completed**, **Total**), filter buttons, an **Orders** / **Products** view switch and a search box. The list shows 20 orders per page.
- :fontawesome-solid-file-pen: A warehouse order has a customer person (**Place the order on behalf of**), a **Storage Date**, an optional **Container Number**, a list of warehouse charges and a list of products (product, quantity, unit of measure, location).
- :fontawesome-solid-arrow-right: A warehouse order has two statuses: **New** (shown under **Open**) and **Completed**. You complete an order by entering its **Closing Date**. There is no way to reopen a completed order.
- :fontawesome-solid-calculator: The **Invoiced Rate** column calculates what the order is worth: **Fixed** charges are added once; each **Monthly** charge is billed per product row as months in storage × square feet of the unit of measure × quantity × rate.
- :fontawesome-solid-paperclip: Each order has a **Documents** window where you attach files.
- :fontawesome-solid-circle-info: Warehouse orders are separate from freight orders. They do not appear on the **Orders** or **Dispatch** pages, and no invoice is created from them automatically. The **Invoiced Rate** is a calculated figure you use for billing.

<!-- TODO: Screenshot — Warehouse Orders page with counters, filter buttons, Orders/Products switch and search box -->

---

## :fontawesome-solid-bolt: Quick Start

1. Click **Warehouse** in the left menu, then **Orders**.
2. Click **Create new Warehouse Order**.
3. In **Place the order on behalf of**, pick the customer's person.
4. Pick the **Storage Date** and, if there is one, type the **Container Number**.
5. Under **Order Charges for Invoice Breakdown**, click **(+) Add another** for each charge, pick it from the list and check the rate.
6. Under **Order Products**, click **(+) Add another** for each product and fill in the product, **Quantity**, unit of measure and location.
7. Click **Create Order**. The order appears under **Open**.
8. When the goods leave the warehouse, click **Complete** on the order row, pick the **Closing Date** and click **Submit**. The order moves to **Completed** and its **Invoiced Rate** stops growing month by month.

---

## :fontawesome-solid-shield-halved: Access & Permissions

Warehouse Orders are part of the **Warehouse** add-on. When the add-on is not turned on for your company, the **Warehouse** menu does not appear and opening the Warehouse Orders page redirects you away from it. See [Add-ons and Options](add-ons-and-options.md).

| Role | Warehouse Orders (view, create, edit, complete, documents) |
|------|------|
| :fontawesome-solid-user-tie: **Admin** | Yes |
| :fontawesome-solid-warehouse: **Warehouse** | Yes. Warehouse users land on the Warehouse Orders page when they sign in. |
| :fontawesome-solid-headset: **Manager**, **Dispatch**, **Accountant**, **Customer**, **Driver**, **Garage** and other roles | No |

**Where to find it:**

- :fontawesome-solid-arrow-right: Left menu :fontawesome-solid-warehouse: **Warehouse** > **Orders**

The other items of the **Warehouse** menu (**Product**, **Location**, **Charges**, **Unit of Measure**, **Building**) hold the lists the order form uses. See [Warehouse Setup](warehouse-setup.md) and [Warehouse Overview](warehouse-overview.md).

!!! info "Offices"
    Warehouse orders are not tied to an office. The list and counters show every warehouse order in your account, whatever office you are working in. See [User Roles](user-roles.md) for what each role can do elsewhere.

---

## :fontawesome-solid-list: The Warehouse Orders Page

### Counters

At the top right of the page:

| Counter | Counts |
|---------|--------|
| **Open Orders** | Orders with status **New** |
| **Completed** | Orders with status **Completed** |
| **Total** | All warehouse orders |

The counters always show the totals. They do not follow the filter or the search.

The **Create new Warehouse Order** button sits next to the counters.

### Filters

The filter buttons sit above the list. The selected one is green.

| Filter | Shows |
|--------|-------|
| **All** | Every warehouse order |
| **Open** | Orders with status **New**. This is the default when you open the page. |
| **Completed** | Orders with status **Completed** |
| **Not Invoiced** | Orders with status **Not Invoiced** |

!!! warning "Not Invoiced is always empty"
    No screen or action in UTX Freight sets a warehouse order to **Not Invoiced**. Orders are either **New** or **Completed**, so the **Not Invoiced** filter shows no orders. Use **Completed** to find orders ready to bill.

Switching filters keeps your current search and view.

### Orders and Products views

Next to the filters, the **Orders** / **Products** switch changes what each row represents. **Orders** is the default.

**Orders view** — one row per warehouse order, 20 per page:

| Column | What it shows |
|--------|---------------|
| **Status** / **Order#** | A grey **WH** label (warehouse order), the status label and the order number. **New** shows a red star (hover text "New Order"); **Completed** shows a grey check mark (hover text "Order Completed"). |
| **Bill To** | The customer company of the person the order was placed for |
| **Storage Date** | The date the goods went into storage |
| **Closing Date** | The date entered when completing the order. Hidden under the **Open** filter. |
| **Container** | The **Container Number** |
| **Product Count** | Number of product rows on the order |
| **Invoiced Rate** | The calculated amount, in dollars. Hidden under the **Open** filter. See [How the Invoiced Rate is calculated](#how-the-invoiced-rate-is-calculated). |
| *(actions)* | **Complete** on open orders, **Edit** on completed orders, plus a drop-down arrow. See [Row actions](#row-actions). |
| **DOC** | A red file icon when the order has documents. Click it to open the **Documents** window. |

**Products view** — one row per product line, across all orders that match the filter, 25 per page:

| Column | What it shows |
|--------|---------------|
| **Status** / **Order#** | The order's **WH** label, status label and order number |
| **Bill To** | The order's customer company |
| **Storage** | The order's **Storage Date** |
| **Container** | The order's **Container Number** |
| **Product Name** | The warehouse product |
| **Sku** | The product's SKU |
| **Quantity** | The quantity on the line |
| **UoM** | The unit of measure on the line |
| **Location** | The warehouse location on the line |

The Products view has no action buttons. To change a line, switch back to **Orders** and edit the order.

In both views, click a column header with a link to sort by it. **Product Count**, **Invoiced Rate** and **DOC** cannot be sorted.

### Search

The search box (placeholder "Order #, product name, location and more") is at the right of the filters. Type one term and click the search button. The term is matched anywhere in the text (case-insensitive) against:

- the **Order #**
- the **Container Number**
- the **product name** and **SKU** of any product line
- the **location** name of any product line
- the customer **company name**

While a search is active, a green **Search:** tag with your term appears next to the view switch. The search stays applied when you change filters. Clicking **Orders** or **Products** clears it.

### Row actions { #row-actions }

| Order status | Main button | Drop-down arrow |
|--------------|-------------|-----------------|
| **New** (open) | **Complete** | **Edit**, **Documents** |
| **Completed** | **Edit** | **Documents** |

---

## :fontawesome-solid-file-pen: Creating and Editing a Warehouse Order

Click **Create new Warehouse Order**, or **Edit** on an order row. The **Warehouse Order** window opens.

When you edit an order, the top of the window shows the customer company's name and address, and the person's name and email.

<!-- TODO: Screenshot — Warehouse Order window with Customer, Storage Date, Container Number, charges and products -->

### Customer

The **Customer** section has one field, **Place the order on behalf of** (hint: "You can create an order on behalf of any customer."). Each entry shows the person's name in capitals followed by the company in brackets, for example `JANE SMITH [ Acme Imports ]`. The list is sorted by company name, then person name.

The list includes a person only when:

- the person belongs to the office you are currently working in,
- the person is active and not deleted,
- the person's company is active and not deleted, and
- the company's **Service** includes **Warehouse** (**Warehouse** or **Intermodal & Warehouse**).

See [Managing Customers](managing-customers.md) and [People and Invitations](people-and-invitations.md).

The person is required. The order's **Bill To** is that person's company.

### Storage Date and Container Number

The **Customer** section, these two fields and the charges all sit in the **Order Income & Billing** panel of the window.

| Field | Required | Notes |
|-------|----------|-------|
| **Storage Date** | Yes | The date the goods went into storage. The first month of billing is the month of this date. |
| **Container Number** | No | Free text. Shown in the **Container** column and searchable. |

### Charges

The **Order Charges for Invoice Breakdown** section (heading **Additional Charges**) holds the charges billed on the order. It starts empty.

1. Click **(+) Add another** to add a charge row.
2. Pick the charge in the drop-down. A new row starts on the first charge in the list (the list has no blank entry). Each entry reads the charge name followed by its rate and a dollar sign in brackets, for example `Storage (0.5$)`.
3. The rate box next to it fills in with the rate from the drop-down. Change it if needed. The rate is required and must be a number.
4. Click **(-) Remove** to delete a row.

The drop-down lists your **Income** charge types whose **Service** is **Warehouse**. Whether a charge is **Fixed** or **Monthly** comes from its **Value Type** on the charge type, and decides how it counts in the [Invoiced Rate](#how-the-invoiced-rate-is-calculated). See [Charge Types and Taxes](charge-types-and-taxes.md).

**Negotiated rates:** when the customer's company has a custom rate for a warehouse charge (**Custom rates for this customer**, **Warehouse** group, on the customer), the drop-down shows that rate instead of the default rate. See [Managing Customers](managing-customers.md#custom-rates).

- On a new order, the drop-down first shows default rates. As soon as you pick a person in **Place the order on behalf of**, the charge lists reload with that customer's rates.
- When editing an order, the drop-down shows the order customer's rates.

!!! warning "Changing the customer resets the rates"
    When you change **Place the order on behalf of**, every charge row keeps its selected charge but its rate box is overwritten with the rate shown in the drop-down for the new customer. Re-enter any rate you had typed by hand before you save.

### Products

The **Order Products** section lists what is stored. It starts empty.

1. Click **(+) Add another** to add a product row.
2. Fill in the row:

    | Field | Required | Notes |
    |-------|----------|-------|
    | Product | Always set | A warehouse product. The drop-down has no blank entry and starts on the first product. See [Warehouse Setup](warehouse-setup.md). |
    | **Quantity** | Yes | Number of units stored. Used in the monthly charge calculation. |
    | Unit of measure | Always set | No blank entry; starts on the first unit. Its **Length (inch)** and **Width (inch)** give the square footage for monthly charges. |
    | Location | Always set | No blank entry; starts on the first location. Where the product is stored. |

3. Click **(-) Remove** to delete a row.

Click **Create Order** (new order) or **Update Order** (existing order) to save, or **Close** to discard your changes.

!!! warning "Drop-downs list disabled and other-office records"
    In the current version, the product, unit of measure and location drop-downs on product rows list every record in your account, including disabled ones and those of other offices. The charge drop-down also lists disabled warehouse charge types and those of other offices. Check that you pick an active item. Rename an item you never want picked (for example add "DO NOT USE") if it keeps getting selected.

---

## :fontawesome-solid-circle-check: Completing an Order

1. On an open order row, click **Complete**.
2. The **Complete Order** window opens with a **Select closing date** section.
3. The **Closing Date** is filled in with today's date. Change it if the goods left on another day. It is required.
4. Click **Submit**.

The order's status changes to **Completed**. It leaves the **Open** filter and the **Open Orders** counter, and appears under **Completed** with its **Closing Date** and final **Invoiced Rate**.

!!! danger "Completing cannot be undone"
    There is no **Reopen** action, and the order form has no status field. A completed order stays completed. You can still click **Edit** to change its customer, dates, container, charges and products, but the **Closing Date** can only be set from the **Complete Order** window.

UTX Freight does not check that the **Closing Date** is after the **Storage Date**. If you pick an earlier date, the month count and the **Invoiced Rate** will be wrong.

---

## :fontawesome-solid-paperclip: Documents

Click the drop-down arrow on an order row and choose **Documents**, or click the red file icon in the **DOC** column. The **Documents** window opens with an **Order Documents** section.

- Each saved document shows a file icon and name (click to open), a download icon and the file size, plus a drop-down with its document type, which you can change.
- Click **(+) Add document** to add a row, choose the file under **Document** and pick its type in **- Select Type -**. The type list shows your active document types. A document saved without a type is saved as **Other**.
- Click **(-) Delete** on a row to remove that document.
- Click **Submit** to save your additions and deletions, or **Close** to discard them.

Documents can be added to both open and completed orders. See [Order Documents and POD](order-documents-and-pod.md) for how document types are used on freight orders.

---

## :fontawesome-solid-calculator: How the Invoiced Rate is calculated { #how-the-invoiced-rate-is-calculated }

The **Invoiced Rate** column (shown under **All**, **Completed** and **Not Invoiced**) is calculated from the order's charges and product rows when the row is drawn (rows are cached, see the [FAQ](#row-cache)):

1. **Months in storage** = calendar months from the **Storage Date** month to the closing month, counting both. The closing month is the **Closing Date**, or today's date for an order that is not completed. A storage date of January 30 and a closing date of February 1 count as **2** months. Storage and closing in the same month count as **1**.
2. **Fixed charges** — each charge whose charge type **Value Type** is **Fixed** is added **once**, at the rate on the order.
3. **Monthly charges** — for each product row, and for each charge whose **Value Type** is **Monthly**:

    **months in storage × square feet × quantity × rate**

    where **square feet** = (**Length (inch)** ÷ 12) × (**Width (inch)** ÷ 12) of the product row's unit of measure.

4. The **Invoiced Rate** is the sum of all of the above.

**Example:** an order has a **Fixed** "Handling" charge at 50, a **Monthly** "Storage" charge at 0.25, and one product row of quantity 10 on a 48 × 40 inch unit of measure. Storage Date March 15, Closing Date May 2 (3 months). Square feet = 4 × 3.33 = 13.33. Invoiced Rate = 50 + (3 × 13.33 × 10 × 0.25) = 50 + 100 = **$150**.

!!! warning "Units without dimensions are not billed monthly"
    If the product row's unit of measure has no **Length (inch)** or no **Width (inch)**, that row is skipped for monthly charges. Fixed charges still count. Set both dimensions on every unit of measure you use for storage. See [Warehouse Setup](warehouse-setup.md).

!!! info "Display format"
    The amount is shown with a **$** sign and is not rounded or formatted, for example `$150.0` or `$133.33333333333331`. The calculation does not include taxes.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-user-slash: The customer is not in "Place the order on behalf of"

!!! info "Solution"
    Check that the customer company's **Service** is **Warehouse** or **Intermodal & Warehouse**, that the company and the person are both active, and that the person belongs to the office you are working in. Customers set to **Intermodal** only do not appear. See [Managing Customers](managing-customers.md).

### :fontawesome-solid-filter: The Not Invoiced filter is empty

!!! info "Solution"
    This is expected. No action sets a warehouse order to **Not Invoiced**, so this filter never shows orders. Use **Completed**.

### :fontawesome-solid-eye-slash: I can't see the Closing Date or Invoiced Rate columns

!!! info "Solution"
    Those columns are hidden under the default **Open** filter. Click **All** or **Completed**.

### :fontawesome-solid-dollar-sign: The Invoiced Rate is $0.0 or too low

!!! info "Solution"
    - Check that the order has charges. Without charges the rate is 0.
    - Monthly charges need product rows. With no product rows, only Fixed charges count.
    - The unit of measure on each product row needs both **Length (inch)** and **Width (inch)**. Rows without them are skipped for monthly charges.
    - Check the **Value Type** of each charge type (**Fixed** or **Monthly**) under **Warehouse** > **Charges**.

### :fontawesome-solid-tag: The charge rate is not the customer's negotiated rate

!!! info "Solution"
    The drop-down shows the custom rate from the customer's **Custom rates for this customer** (**Warehouse** group). If none is set, it shows the charge type's default rate. The rate box is filled when you pick a charge or change the person; a rate typed by hand is kept until you change the person. Check the rate box before saving.

### :fontawesome-solid-rotate-left: I completed an order by mistake

!!! info "Solution"
    There is no reopen. You can click **Edit** to fix the order's other details, but it stays **Completed** with the closing date you entered. No screen lets you change the **Closing Date** afterwards.

### :fontawesome-solid-table-columns: Columns look shifted, or Product Count / Invoiced Rate looks out of date { #row-cache }

!!! info "Solution"
    Rows on the Orders view are saved (cached) per order and per user, and the saved row does not depend on the filter. A row first drawn under **Open** (without the **Closing Date** and **Invoiced Rate** cells) can be reused under **All**, and the reverse, so cells shift under the wrong headers. The **Invoiced Rate** of an open order shown under **All** is also not recalculated each month on its own.

    A saved row is refreshed only when the order record itself changes: completing it, changing **Place the order on behalf of**, **Storage Date** or **Container Number**, or adding or deleting a document. Changing only the charges or product rows does not refresh it, so **Product Count** and **Invoiced Rate** can stay out of date. To force a refresh, change one of the order's own fields or add a document. Rows on the Products view are saved the same way, per product line and per user.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Tips"
    - Set **Length (inch)** and **Width (inch)** on every unit of measure before using it on orders, or monthly charges will not count.
    - Set the **Value Type** of each warehouse charge type correctly: **Fixed** for one-time fees (handling, receiving), **Monthly** for storage priced per square foot.
    - Put negotiated prices in the customer's **Custom rates for this customer** instead of typing them on each order.
    - Pick the customer first, then add charges, so the rates fill in with the customer's prices.
    - Double-check the **Closing Date** before clicking **Submit**. Completing cannot be undone.
    - Attach receiving slips and photos in **Documents** so the order history stays with the order.
