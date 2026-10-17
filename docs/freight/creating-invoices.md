# Creating & Editing Invoices

Build an invoice from a customer's completed orders, set its terms, status and tax, then print it, export it as EDI 210, edit it or delete it.

## :fontawesome-solid-file-invoice-dollar: Overview

An invoice in UTX Freight is a header (customer, terms, date, status, tax) plus the completed orders you tick in the **Invoice Orders** list. The money on the invoice always comes from those orders.

- :fontawesome-solid-building: **One customer per invoice** -- pick the **Company** first, then tick its orders
- :fontawesome-solid-circle-check: **Completed orders only** -- an order can be invoiced once it is **Completed**, is not already on an invoice, and its delivery date is on or after the **Order Start Date** in **Settings**
- :fontawesome-solid-calendar-days: **Due date is automatic** -- calculated from the **Invoice date** and the **Terms** every time you save
- :fontawesome-solid-calculator: **Totals are automatic** -- the sum of the order totals, plus GST and QST from the selected **Tax**
- :fontawesome-solid-print: **Print** opens a printable invoice; **EDI 210** downloads a CSV (if your account has EDI invoicing turned on -- ask UTX support)
- :fontawesome-solid-trash: **Delete** releases the orders so they can be invoiced again

!!! info "Related pages"
    This page covers building and maintaining an invoice. For the Invoices list, filters and exports see [Invoices](invoices.md). For emailing invoices and recording payments see [Invoice Email & Payments](invoice-email-and-payments.md). For how an order's total is built see [Order Rates, Charges & Expenses](order-charges-and-expenses.md).

<!-- TODO: Screenshot — The New Invoice form showing the Invoice Information section and the Invoice Orders picker -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Invoices** in the left menu.
2. Click **Add a new Invoice** (top right).
3. Choose the **Company**. Its name goes into the **Filter orders** box, so the order list below narrows to that company.
4. Check the **Terms**, **Invoice date**, **Invoice Status** and **Tax**.
5. In **Invoice Orders**, tick the orders to bill (or click **Select All**).
6. Click **Save Invoice**. You return to the Invoices list with the message *Invoice was successfully created.*

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Full access -- create, edit, print, EDI 210, delete |
| :fontawesome-solid-user-tie: **Manager** | Full access, for invoices of the offices they belong to |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | Full access, for invoices of the offices they belong to |
| :fontawesome-solid-headset: **Dispatch / Customer Service** | No access -- the **Invoices** menu is not shown |
| :fontawesome-solid-user: **Customers, drivers, warehouse and garage users** | No access |

**How to get there:**

- :fontawesome-solid-arrow-right: **Invoices** (left menu) > **Add a new Invoice** -- create an invoice (page title **New Invoice**)
- :fontawesome-solid-arrow-right: **Invoices** > :fontawesome-solid-gear: **Actions** menu on a row > **Edit** -- edit an invoice (page title **Edit Invoice**)

!!! info "Multi-office"
    An invoice belongs to the office you are working in, and the **Invoice Orders** list only shows that office's orders. Customers are shared between offices when the multi-office add-on is on, so the **Company** list shows every customer; without it, only the current office's customers are listed. Switch office first if you need to invoice another office's orders. See [Multi-Office](multi-office.md).

---

## :fontawesome-solid-pen-to-square: The Invoice Form

The New and Edit pages use the same form, in three parts: **Invoice Information**, **Payment Information** and **Invoice Orders**.

### :fontawesome-solid-circle-info: Invoice Information

| Field | Required | Default (new invoice) | Description |
|-------|----------|-----------------------|-------------|
| **Company** | Yes | Blank | The customer being billed. A new invoice lists **active** customers only; the Edit page also lists inactive (but not deleted) customers so older invoices still show theirs. Choosing a company also filters the order list to it (see below) |
| **Terms** | -- | **Default Terms** from **Settings** (Invoice group); on the Edit page, the invoice's saved terms | Payment terms, in two groups. **Most Common:** Due on Receipt, 30 Days, 10 Days, 45 Days. **Other:** 15 Days, 21 Days, 60 Days, 90 Days |
| **Invoice date** | Yes | Today | The date printed on the invoice. Pick it from the date picker |
| **Invoice Status** | -- | **new** | One of **new**, **Invoiced**, **Paid**, **Partially Paid**. If you save an invoice as **Paid** with no payment recorded, today's date is stored as its paid date |
| **Tax** | No | Blank | One of the taxes set up in UTX Freight (the same list in every office). Leave blank for no tax. See [Charge Types & Taxes](charge-types-and-taxes.md) |

Next to the date, an info note reads: *INFO: The due date is automatically calculated based on the invoice date and the terms.*

!!! tip "Status changes on its own when you email"
    You rarely set **Invoiced** by hand: emailing an invoice whose status is **new** switches it to **Invoiced** automatically. See [Invoice Email & Payments](invoice-email-and-payments.md).

### :fontawesome-solid-money-bill: Payment Information

Below the header fields, **Payment Information** lists the payments recorded on the invoice. Click **(+) Add payment** to add a line with **Paid date**, **Check number** and **Amount** (required), or **(-) Remove payment** to drop one. The same payments can be recorded from the **Record a payment** action on the Invoices list, which opens a smaller **Edit Invoice** window (status and payments only, plus a **Balance Paid In Full** button when the invoice is not already Paid) and does not change the invoice's orders. Payments are covered in [Invoice Email & Payments](invoice-email-and-payments.md).

### :fontawesome-solid-floppy-disk: Saving

- Click **Save Invoice**. The button reads **Please wait...** while the invoice saves.
- A new invoice returns you to the Invoices list with *Invoice was successfully created.*
- An edited invoice returns you to the list with *Invoice 00123 was successfully updated.* (with your invoice number).
- **Cancel** returns to the Invoices list without saving.

If **Company** or **Invoice date** is missing, the form stays open with the error, and the orders you had ticked stay ticked.

!!! info "An incomplete order never blocks the invoice"
    Orders are attached to the invoice without re-checking their own required fields. An order with, for example, a blank container number can still be invoiced.

---

## :fontawesome-solid-list-check: Picking Orders (Invoice Orders)

The **Invoice Orders** section lists every order you can put on this invoice, one checkbox per order, sorted by customer name, then delivery date, then order date.

<!-- TODO: Screenshot — The Invoice Orders section with the All / Selected Orders / Selected Company buttons, the Filter orders box, Select All and the selection counter -->

### :fontawesome-solid-circle-check: Which orders are listed

An order appears in the list when **all** of these are true:

- its status is **Completed**,
- it is not already on another invoice,
- its **delivery date** is on or after the **Order Start Date** in **Settings** (Invoice group),
- it belongs to the office you are working in.

On the Edit page, the orders already on this invoice are listed too.

!!! warning "Orders with no delivery date"
    An order with no delivery date is never listed, because it cannot be compared with the Order Start Date. Add the delivery date on the order, then come back to the invoice.

!!! tip "Find what still needs billing"
    On the **Orders** page, Admin and Manager users have two extra tabs. **Not Invoiced** lists Completed orders with no invoice and a delivery date on or after the **Order Start Date** -- the same rules as this list, except that orders created before the **Order Archive Cutoff Date** in **Settings** are also left out. **Late Invoicing** narrows that to orders delivered before the end of the week two weeks ago. See [Orders](orders.md).

### :fontawesome-solid-tag: How each order reads

Each checkbox label shows, separated by dashes:

**Order #** - **Customer** - **Container #** - **Reference #** - **Delivery date** - **Receiver** - **Status**

For a transfer, the **Receiver** part shows the customer's name.

If the order has no scanned signed POD and no driver signature (delivery or pickup), the label ends with **- MISSING PDF**. This is a warning only -- you can still invoice the order -- but there is no signed POD on file to send with the invoice. See [Order Documents & POD](order-documents-and-pod.md).

### :fontawesome-solid-filter: Filtering the list

| Control | What it does |
|---------|--------------|
| **All** | Clears the filter and shows every listed order |
| **Selected Orders** | Shows only the ticked orders. The Edit page opens with this filter on, so you first see what is on the invoice |
| **Selected Company** | Puts the name of the customer chosen in **Company** into the **Filter orders** box, so the list shows orders whose label contains that name |
| **Filter orders** box | Type any text from the order label -- order number, customer, container number, reference, date, receiver -- to narrow the list |

The active button is highlighted. Choosing a **Company** puts its name into the **Filter orders** box automatically.

Under the box: *You can filter by entering any text included in the order name including the dates and container number. Regardless of your filter, the selected orders will always show up.*

!!! info "Ticked orders never hide"
    Whatever you type, ticked orders always stay visible. What goes on the invoice is every ticked order, not only the ones matching your filter.

### :fontawesome-solid-square-check: Select All and the selection counter

**Select All** ticks every order **currently shown** by the filter. Hidden orders are not touched.

- It is greyed out until you choose a **Company**, so you cannot select every customer's orders by accident.
- When every shown order is already ticked, the button changes to **Deselect All** and unticks them.
- On the Edit page, **Deselect All** asks first: *Deselect all N shown orders?* -- *They will be removed from this invoice when you click Save Invoice. You can click Select All to re-select them.* Click **Yes, deselect all** or **Cancel**.

The text next to the button tells you where you stand:

| Counter text | Meaning |
|--------------|---------|
| *Choose a company first to select its orders* | No **Company** chosen yet; **Select All** is disabled |
| *No orders to select* | The filter shows no orders |
| *3 of 5 shown orders selected* | Ticked vs shown, for the current filter |
| *3 of 5 shown orders selected — 7 selected in total, including hidden orders* | Other ticked orders are hidden by the filter. All 7 go on the invoice |

!!! tip "Review the selection before saving"
    An invoice is for one **Company**. The company filter matches text in the order label, so it can also show an order whose receiver or reference contains the same name. Click **Selected Orders** to review exactly what is ticked before you click **Save Invoice**.

---

## :fontawesome-solid-calendar-days: Due Date

The due date is recalculated from the **Invoice date** and **Terms** every time the invoice is saved:

| Terms | Due date |
|-------|----------|
| **Due on Receipt** (or no terms on an older invoice) | Same as the invoice date |
| **10 Days**, **15 Days**, **21 Days**, **30 Days**, **45 Days**, **60 Days**, **90 Days** | Invoice date plus that many days |

There is no separate due-date field. To change the due date, change the **Invoice date** or the **Terms** and save. The due date drives the aging shown on the Invoices list and the [Aged Receivables](aged-receivables.md) reports.

---

## :fontawesome-solid-hashtag: Invoice Numbers

Invoice numbers are assigned automatically when you save a new invoice. They are sequential and cannot be edited. Depending on how your account is configured, the number is shown in one of two formats:

| Format | Example | How it is built |
|--------|---------|-----------------|
| **Plain** | `00123` | The invoice number padded to 5 digits |
| **Decorated** | `A26 - 00123` | First letter of the customer's name, the last two digits of the invoice date's year, then the 5-digit number |

!!! info "Decorated numbers follow the invoice"
    In the decorated format, the letter and year are read from the current **Company** and **Invoice date**. If you change either on an existing invoice, the prefix changes too; the 5-digit part stays the same.

!!! tip "Searching by number"
    On the Invoices list, search with the digits only (for example `123`), not the decorated prefix.

---

## :fontawesome-solid-calculator: Totals and Taxes

The invoice has no line items of its own. Its amounts are calculated from the attached orders:

| Amount | Calculation |
|--------|-------------|
| **Subtotal** | Sum of the attached orders' totals (each order's **Base rate** plus its charges) |
| **GST** | Subtotal × the selected Tax's GST %, rounded to the cent |
| **QST** | Subtotal × the selected Tax's QST %, rounded to the cent |
| **Total** | Subtotal + GST + QST. With no **Tax** selected, the total is the subtotal |

- An invoice with **no orders** shows a blank **Total** and **Balance** on the Invoices list, and **—** instead of an order count.
- There is no "regenerate" button. The invoice total always follows its orders: when an attached order's total changes (for example you edit its base rate or add a charge), the invoice total changes with it.
- Automatic charges are **not** recalculated on orders that are **Completed** or invoiced. A change to a terminal's default rate or to the fuel schedule does not reach orders that are already completed. To change their amounts, edit the order's charges by hand. See [Order Rates, Charges & Expenses](order-charges-and-expenses.md) and [Fuel Surcharge](fuel-surcharge.md).

---

## :fontawesome-solid-pen: Editing an Invoice

1. Go to **Invoices** and find the invoice.
2. Click the :fontawesome-solid-gear: **Actions** menu on its row > **Edit**.
3. The **Invoice Orders** list opens on **Selected Orders**. Click **All** or **Selected Company** to see orders you can add.
4. Change any field, tick orders to add them, untick orders to remove them.
5. Click **Save Invoice**.

What happens on save:

- **Ticked** orders not yet on the invoice are attached.
- **Unticked** orders are removed from the invoice and become available to invoice again.
- The due date, totals and taxes are recalculated.

!!! warning "Already-sent invoices"
    Editing does not re-send the invoice. If the customer already has it, email it again -- later sends are marked **REVISED**. See [Invoice Email & Payments](invoice-email-and-payments.md).

---

## :fontawesome-solid-print: Printing an Invoice

On the Invoices list, open the :fontawesome-solid-gear: **Actions** menu > :fontawesome-solid-print: **Print**. The printable invoice opens in a new browser tab; use your browser's print or save-as-PDF.

<!-- TODO: Screenshot — A printed invoice showing the header, FROM / BILL TO, the CONTAINER IMPORTS section and the GST / QST / TOTAL lines -->

Most accounts use this layout:

| Area | Contents |
|------|----------|
| **Header** | Your logo, **Invoice Number**, **Invoice Date**, **Payment Due** (the due date) |
| **FROM** | Your company name, address and **Tel** |
| **BILL TO** | The customer's name and address, followed by the **Message** from **Settings** (Invoice group) |
| **Order sections** | Orders grouped by order type, one section each: **CONTAINER IMPORTS**, **CONTAINER EXPORTS**, **CONTAINER TRANSFERS**, **DRY VAN MOVES**. Within a section, orders are sorted by delivery date, then order date |
| **Taxes** | When a Tax is selected: **GST (x%)** and **QST (x%)** lines, next to your **GST Number** and **QST Number** from **Settings** (Invoice group) |
| **Totals** | The **N.I.R** number (**NIR Number** from **Settings**, POD group) and **TOTAL**. If the invoice is not Paid but has payments: **Invoice Total**, **Paid to Date** and **Amount Due** |
| **Footer** | *THANK YOU FOR YOUR SUPPORT* |

Each order row shows the order number (with **PO:** underneath when the order has a delivery PO number), the container or trailer number (with **From:** / **To:** terminal for imports and exports), reference (plus booking and seal numbers for exports and transfers), the receiver (or the two terminals for transfers), the date (the delivery date; for dry van moves, the closing date), then one line for **Base rate** and one per charge, with their **Price**, and the order **Total**. Amounts are shown in the customer's default currency.

| Section | Columns |
|---------|---------|
| **CONTAINER IMPORTS** | POD · Cont.# · Reference# · Client · Delivery · Charge · Price · Total |
| **CONTAINER EXPORTS** | POD · Cont.# · Ref#/ Booking#/ Seal# · Client · Pickup · Charge · Price · Total |
| **CONTAINER TRANSFERS** | POD · Cont.# · Ref#/ Booking#/ Seal# · Terminals · Pickup · Charge · Price · Total |
| **DRY VAN MOVES** | POD · Trailer# · Reference# · Client · Pickup · Charge · Price · Total |

!!! info "Layout can differ by account"
    The invoice layout is set per account by UTX. Some accounts use an older layout with the same orders, charges, taxes and totals, arranged differently: the header shows **Invoice #**, **Date** and **Client ID** (no **Payment Due**), the customer's **TERMS** appear in a box next to the **Message**, each section has an extra date column (**Return** or **Delivery**), amounts are shown with a `$` sign instead of the currency code, and the remaining amount is labelled **BALANCE**. A few accounts use a customised layout.

---

## :fontawesome-solid-file-csv: EDI 210 Export

When EDI invoicing is enabled for your account, the :fontawesome-solid-gear: **Actions** menu on each invoice has :fontawesome-solid-download: **EDI 210**. If you don't see it, EDI invoicing is not turned on for your account -- ask UTX support.

Clicking it downloads a CSV named `EDI210_<invoice number>_<YYYYMMDD>.csv` (the date is the download date). The file has a header row and **one row per order** on the invoice. Dates use the `dd/mm/yyyy` format and amounts have no thousands separator or currency sign.

| Column | Value |
|--------|-------|
| `DOC TYPE` | Always `INV` |
| `INVOICE-NUMBER` | Invoice number, as displayed |
| `ITEM NUMBER` | 1, 2, 3... one per order |
| `MSC PO` | The order's delivery PO number |
| `TERMS` | Terms in days (`0` for Due on Receipt) |
| `INVOICE-DATE` / `INVOICE-DUE DATE` | Invoice date and due date |
| `CURRENCY` | The customer's default currency |
| `BASE RATE` | The order's base rate |
| `PRE-PULL`, `STORAGE`, `FUEL` | Always `0.00` |
| `OTHER` | Sum of all the order's charges (including terminal fee and fuel surcharge) |
| `INVOICE TOTAL` | The whole invoice total with taxes (repeated on every row) |
| `WAYBILL-NUMBER` | The order's reference number |
| `WAYBILL-DATE` | The order's waybill date |
| `VESSEL` / `VOYAGE NUMBER` | From the order |
| `UNIQUE-SHIPMENT-ID` | Container number |
| `EQUIP-INITIAL` | First four characters of the container number |
| `DESTINATION  - UNLOC` | The receiver's UN/LOCODE, when set |
| `NOTES` | Always `*` |

These columns are present but always empty: `BOND CHARGES`, `CHASSIS DETENTION`, `DROP CHARGES`, `GENSET COST`, `OVERWEIGHT`, `SPECIAL PERMIT`, `WAITING TIME COST`, `DEAD RUN`, `OVERDIMENTION`, `SCALING`, `HAZMAT`, `RESERVATION FEE`, `EQUIP-NUMBER`, `ORIGIN-UNLOC`, `ORIGIN-PROV`, `DESTINATION-PROV`, `WEIGHT`, `UOM`, `EQUIP-SIZE`, `EQUIP-TYPE`.

!!! info "Charges are reported together"
    All of an order's charges are reported in `OTHER`, including the fuel surcharge. `FUEL`, `STORAGE` and `PRE-PULL` are always `0.00`.

---

## :fontawesome-solid-trash: Deleting an Invoice

1. On the Invoices list, open the :fontawesome-solid-gear: **Actions** menu > **Delete**.
2. Confirm **Are you sure?**.

The invoice disappears from the list. Its orders are **released**: they are no longer invoiced, appear again in **Not Invoiced** on the Orders page, and can be put on a new invoice.

!!! danger "Deleted invoices cannot be restored from the app"
    There is no undo button. If you deleted an invoice by mistake, contact UTX support. UTX support can restore a recently deleted invoice (within the last 12 months), provided its customer and office still exist. The invoice comes back with its original number, date, terms, status and tax, and its orders are re-attached if they have not been put on another invoice since. Check the restored invoice's orders afterwards.

---

## :fontawesome-solid-link: What Invoicing Does to Orders

Once an order is on an invoice:

| Effect | Details |
|--------|---------|
| **Cannot be deleted** | **Delete Order** is greyed out. Remove the order from the invoice first (Edit the invoice and untick it) |
| **Cannot be transferred** | In multi-office accounts, **Transfer to Office** is greyed out as **Transfer (Invoiced)** |
| **No automatic charge updates** | Terminal fee and fuel surcharge are no longer recalculated (this already applies once the order is Completed) |
| **Total still flows to the invoice** | Editing the order's base rate or charges by hand updates the invoice total |
| **Invoice icon on Orders** | Admin, Manager and Accountant see a :fontawesome-solid-file-invoice: **Get order invoice** button in the order's invoice column. It opens the Invoices list searched to that invoice. Customer Service sees the order total but not the button |
| **Status unchanged** | The order stays **Completed** -- being invoiced is not an order status |

Removing an order from an invoice (untick and save, or delete the invoice) undoes all of this.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-ban: Can't create an invoice -- the order isn't in the list

!!! info "Solution"
    The order must be **Completed**, not already on an invoice, and have a **delivery date on or after** the **Order Start Date** in **Settings** (Invoice group). It is the delivery date that counts, not the date the order was completed. Also check that you are in the right office, and that the filter (**Filter orders** box, **Selected Orders**, **Selected Company**) is not hiding it -- click **All**.

### :fontawesome-solid-hand: Select All is greyed out

!!! info "Solution"
    Choose a **Company** first. **Select All** is also disabled when the current filter shows no orders (*No orders to select*).

### :fontawesome-solid-triangle-exclamation: An order shows MISSING PDF

!!! info "Solution"
    The order has no scanned signed POD and no driver signature. You can still invoice it, but there is no signed POD on file for it. Upload the signed POD on the order first if the customer needs it. See [Order Documents & POD](order-documents-and-pod.md).

### :fontawesome-solid-calculator: Invoice shows wrong amounts

!!! info "Solution"
    Invoice amounts come from the orders. Edit the order's **Base rate** or charges; the invoice total updates by itself. Completed and invoiced orders do not recalculate the Terminal Fee or fuel surcharge automatically, so adjust those charges by hand. If taxes are wrong, edit the invoice and check the **Tax** selected.

### :fontawesome-solid-file-circle-question: The invoice total is blank in the list

!!! info "Solution"
    The invoice has no orders. Edit it and tick its orders, or delete it.

### :fontawesome-solid-calendar-xmark: The due date is wrong

!!! info "Solution"
    The due date is calculated from the **Invoice date** and **Terms**. Edit the invoice, correct either one, and click **Save Invoice**.

### :fontawesome-solid-trash-can: I can't delete an order

!!! info "Solution"
    The order is on an invoice. Use **Get order invoice** on the order row to find the invoice, edit it, untick the order and save. Then delete the order.

### :fontawesome-solid-rotate-left: I deleted an invoice by mistake

!!! info "Solution"
    Contact UTX support with the invoice number and customer. UTX support can restore invoices deleted within the last 12 months, with the same number and, where they can still be found, its orders. Check the orders on the restored invoice afterwards.

### :fontawesome-solid-download: There is no EDI 210 option

!!! info "Solution"
    EDI invoicing is an account option that UTX turns on. Ask UTX support if you need it.

---

!!! tip "Best Practices"
    - Set the **Order Start Date** in **Settings** to the day you started invoicing in UTX Freight, so older work doesn't clutter the order list.
    - Always pick the **Company** first, then use **Select All** -- it only works on the shown orders of that company.
    - Watch the counter: if it says *including hidden orders*, click **Selected Orders** to see everything that will be billed.
    - Resolve MISSING PDF orders before invoicing, so a signed POD is on file for every order you bill.
    - Check rates on the order before invoicing -- completed orders do not recalculate automatic charges.
