# Integrations

Every outside service UTX Freight connects to, what data goes back and forth, which add-on turns it on, and where you see it in the app.

## :fontawesome-solid-plug: Overview

UTX Freight connects to a small number of outside services. All of them are set up and run by UTX: you never enter API keys or terminal passwords yourself, and most integrations only need an add-on turned on for your account.

| Integration | What it does for you | Add-on / option | Where you see it |
|-------------|----------------------|-----------------|------------------|
| :fontawesome-solid-train: **CN Rail** | Container status, ETA, Last Free Day, customs, GPS and bill of lading from CN | CN tracking | Tracking icon on **Orders** / **Dispatch**, **CN Tracking** and **Alerts** on **Dispatch** |
| :fontawesome-solid-ship: **Port of Montreal (Termont)** | Container availability, holds, customs, vessel and carrier data from Termont / Viau | Port of Montreal tracking | Tracking icon on **Orders** / **Dispatch**, **Port Tracking** and **Alerts** on **Dispatch** |
| :fontawesome-solid-ship: **MGT (Racine/Cast)** | Container availability, holds, customs, vessel and carrier data from MGT | MGT tracking | Tracking icon on **Orders** / **Dispatch**, **Port Tracking** and **Alerts** on **Dispatch** |
| :fontawesome-solid-wand-magic-sparkles: **AWS Textract** | Reads uploaded delivery orders and pre-fills a new order | Auto Orders (beta) | **Upload** button and **AUTO ORDERS** card on **Orders** |
| :fontawesome-solid-envelope: **Postmark** | Sends all outgoing emails through a UTX-managed email service | **Email Delivery Method** = Postmark in **Settings** | **Settings** page, the *From* line of every email |
| :fontawesome-solid-file-csv: **EDI 210 invoice CSV** | Downloads one invoice as an EDI 210 CSV file | EDI invoicing (account option set by UTX) | **Invoices** > :fontawesome-solid-gear: **Actions** > **EDI 210** |
| :fontawesome-solid-file-excel: **QuickBooks-ready export** | Exports the listed invoices in a QuickBooks import layout | None (standard) | **Invoices** > **Export** panel |
| :fontawesome-solid-barcode: **NHTSA VIN decoder** | Fills **Year**, **Make** and **Model** from a VIN | Garage | Garage **Equipment** form > **Decode** |

- :fontawesome-solid-puzzle-piece: **Add-ons** are turned on per account by UTX. If a button or icon described here is missing, the add-on is probably off. See [Add-ons and Options](add-ons-and-options.md).
- :fontawesome-solid-arrows-rotate: **Automatic vs. on demand** -- container tracking and Auto Orders run in the background on a schedule. EDI, QuickBooks export and VIN decoding happen only when you click the button.
- :fontawesome-solid-key: **Credentials** -- the CN, MGT, AWS and Postmark accounts belong to UTX and are stored on the server. They are never shown in the app.
- :fontawesome-solid-ban: **No public API** -- UTX Freight does not offer an API for customers. See [Is there an API?](#is-there-an-api).

---

## :fontawesome-solid-bolt: Quick Start

- **Track containers:** ask UTX to turn on the tracking add-on for your terminal (CN, Port of Montreal, MGT). Make sure your pickup terminals are named as in [Which terminal triggers which source](#which-terminal-triggers-which-source). Then click the tracking icon in the **Container#** column on **Orders** or **Dispatch**.
- **Create orders from documents:** with the Auto Orders add-on, click **Upload** on **Orders**, wait for the document to reach **Need Review**, then click **Review**.
- **Send an invoice as EDI 210:** on **Invoices**, open the :fontawesome-solid-gear: **Actions** menu of the invoice and click **EDI 210**.
- **Export invoices for QuickBooks:** on **Invoices**, filter the list, choose **Layout** **QuickBooks columns** in the **Export** panel and click **Export**.
- **Decode a VIN:** in the Garage, on the equipment form, type the **VIN** and click **Decode**.

---

## :fontawesome-solid-shield-halved: Access & Permissions

Each integration follows the permissions of the feature it lives in.

| Integration | Who can use it |
|-------------|----------------|
| **Container tracking popup** (CN, Termont, MGT) | Admin, Manager, Dispatch, Customer Service. Accountant on **Orders** only when your account lets accountants manage orders (an option set by UTX -- ask UTX support). Customers, drivers, warehouse and garage users don't see it. See [Container Tracking](container-tracking.md#access-permissions) |
| **Container Alerts** page | Opened with the **Alerts** button on **Dispatch**, so Admin, Manager, Dispatch and Customer Service. Only Admins can mark alerts read or unread. See [Container Alerts](container-alerts.md) |
| **Auto Orders** | Admin, Manager, Dispatch and Customer Service can upload and review. See [Auto Orders](auto-orders.md) |
| **Email Delivery Method** (Postmark) | Admin only (**Settings**). See [Application Settings](application-settings.md) |
| **EDI 210** and **QuickBooks** export | Admin, Manager and Accountant (the roles that can open **Invoices**). Dispatch and Customer Service have no access |
| **VIN Decode** | Admin, Manager and Garage users (the roles that can edit Garage equipment) |

---

## :fontawesome-solid-satellite-dish: Container Tracking (CN, Termont, MGT)

The three tracking integrations work the same way from your point of view: the system checks containers in the background, stores the latest terminal data, and shows it in a popup. The full guide is [Container Tracking](container-tracking.md).

### Which terminal triggers which source

The source is chosen from the order's **pickup terminal** name (upper or lower case does not matter), not from the container number.

| Source | Pickup terminal name | Icon in **Container#** |
|--------|----------------------|------------------------|
| :fontawesome-solid-train: **CN Rail** | Exactly **CN** (nothing else in the name) | Red train |
| :fontawesome-solid-ship: **Termont (Port of Montreal)** | Contains **TERMONT** or **VIAU** | Blue ship |
| :fontawesome-solid-ship: **MGT (Racine/Cast)** | Contains **RACINE** or **CAST** | Orange ship |

!!! tip "Start the terminal name with the keyword"
    The tracking popup picks its source from the **first word** of the terminal name (**CN**, **TERMONT**, **VIAU**, **RACINE** or **CAST**). Name tracked terminals so the keyword comes first, for example *CAST Montreal* rather than *Montreal CAST*.

!!! info "New or renamed terminals"
    If tracking does not start for a terminal you have just added or renamed, contact UTX support.

See [Managing Terminals](managing-terminals.md) to set up your terminals.

### What each source sends

| Source | How UTX gets the data | Data you see |
|--------|-----------------------|--------------|
| **CN Rail** | CN's intermodal tracking service, using UTX's CN account. Each check combines five CN data sets: shipment tracking, ETA, bill of lading, GPS position and shipment status | CLM status (for example **De-ramped**), event location, destination, lot location, customs status, equipment type, size, empty/full, weights, waybill status, GPS position, BOL number, shipper, consignee, commodity, **Destination ETA**, **Last Free Day** |
| **Termont** | The terminal operator's public container lookup web page (no login needed) | Terminal section, hold message, available for pickup (yes/no), visit and transit state, customs status, shipping line, vessel, voyage, origin, size/type, seal, gross weight, carrier IN / OUT timeline, ETA, Last Free Day |
| **MGT (Racine/Cast)** | MGT's container inquiry web page, signed in with UTX's MGT account. Containers no longer in the yard are looked up in MGT's history | Same layout as Termont |

If one of CN's supplementary data sets (ETA, BOL, GPS or status) fails, the rest of the check still goes through: you simply see fewer sections in the popup.

### Refresh behaviour

- :fontawesome-solid-clock: **Stored data is refreshed automatically.** A scheduled job run by UTX checks the containers and stores the result. You cannot trigger that check from the app. The refresh interval is set by UTX. The **Updated ... ago** line in the popup tells you when that container was last refreshed.
- :fontawesome-solid-train: **One live lookup:** the **CN Tracking** button on **Dispatch** asks CN live (basic tracking data only) each time you open it. It does not refresh the stored data that the popup, alerts and **Port Tracking** use. **Port Tracking** shows stored data only. See [Tracking Bulk Update](tracking-bulk-update.md).
- :fontawesome-solid-filter: **Only in-progress orders** (status **New**, **App. Taken** or **Dispatched**) created after the **Order Archive Cutoff Date** are checked. A container stops being checked once it has left the terminal (CN: **Departed** or **Completed**; Termont / MGT: transit state **Out**).
- :fontawesome-solid-layer-group: **Batches:** orders are processed in groups of 200 for CN, 50 for MGT and 10 for Termont. Within a group, a container number that appears on several orders is checked once. Blank container numbers and **N/A** are skipped.
- :fontawesome-solid-pen: **What changes on your orders:** for Termont and MGT only, when a container's terminal data changes, blank fields on the in-progress orders with that container number (**Seal Number**, **Weight** in KG, **Steamship Line** and **Container Size** when a matching list entry exists, and **Customs released** set to yes when the customs description contains "release") are filled in. Existing values are never overwritten. CN data never changes order fields. **ETA** and **Last Free Day** are never copied automatically -- use the **CN Tracking** and **Port Tracking** buttons on **Dispatch** ([Tracking Bulk Update](tracking-bulk-update.md)).
- :fontawesome-solid-bell: **Alerts:** status changes (pickup ready, customs released, departed) and approaching Last Free Days create alerts on the **Container Alerts** page and in the daily digest email. See [Container Alerts](container-alerts.md).
- :fontawesome-solid-heart-pulse: **Health:** the **Integration Health** cards at the top of **Container Alerts** show, per source, whether the last pull worked and returned containers. See [Container Alerts](container-alerts.md#integration-health).

!!! warning "Terminal websites can change"
    Termont and MGT data is read from the terminals' own web lookups. When a terminal changes its website or is down, tracking for that source can stop until UTX adapts. Check **Integration Health** on Container Alerts, and contact UTX support if a source stays stale.

---

## :fontawesome-solid-wand-magic-sparkles: Auto Orders (AWS Textract)

**Add-on:** Auto Orders (beta). **Where:** **Orders** > **Upload** button and the **AUTO ORDERS** card (**Processing**, **Need Review**, **Completed**).

**Data flow:**

1. You upload a document in **Upload a Document**.
2. UTX Freight sends the file to Amazon Web Services (AWS) Textract, a text-recognition service, through UTX's AWS account. The document shows in **Processing**.
3. A scheduled background check collects the recognised text, extracts the order details (container number, reference, seal, terminal, size, weight and so on, depending on the document layout) and moves the document to **Need Review**.
4. You check the values in the review window and save. Nothing becomes an order until a person saves it.

**Refresh:** the move from **Processing** to **Need Review** waits for the next scheduled check, so there is a delay. Reload the **Need Review** tab after a while.

Full guide, including recognised document layouts and error messages: [Auto Orders](auto-orders.md).

---

## :fontawesome-solid-envelope: Postmark Email

**Option:** **Settings** > **Edit settings** > **Email Delivery Method** > **Postmark — Use the Postmark email API**. The other choice is **SMTP — Use your own SMTP server credentials** (the default).

**What happens when Postmark is selected:**

- UTX Freight's outgoing emails (for example invoices, PODs, notifications and alert digests) go through Postmark, an email delivery service managed by UTX, instead of your SMTP server. The SMTP sections of the settings are not used.
- The **From** address is replaced by a UTX sending address. The sender **name** is kept.
- The **Reply-To** is set to your original From address (unless the email already has its own Reply-To), so replies from customers still reach your mailbox.
- The Postmark access token is managed by UTX. When Postmark is selected, the **Settings** page shows **API Token** as **Configured** or **Not configured**, and the **Message Stream** used for your system.

!!! warning "Check with UTX before switching"
    If the Postmark token is not configured, emails cannot be sent. Switch to Postmark only when UTX support confirms it is ready, then use **Test Email Configuration** > **Send Test** on the **Settings** page. See [Application Settings](application-settings.md#email-delivery-method).

---

## :fontawesome-solid-file-csv: EDI 210 Invoice CSV

**Option:** EDI invoicing, an account option turned on by UTX. **Where:** **Invoices** > :fontawesome-solid-gear: **Actions** menu on a row > :fontawesome-solid-download: **EDI 210**.

**Data flow:** one way, on demand. Clicking **EDI 210** downloads a CSV file named `EDI210_<invoice number>_<YYYYMMDD>.csv` (the date is the download date). UTX Freight does not send the file anywhere: you upload or email it to your customer's EDI system yourself.

**What is in the file:**

- One header row, then **one row per order** on the invoice.
- Dates in `dd/mm/yyyy`, amounts without thousands separator or currency sign.
- Invoice number, item number (1, 2, 3... per order), the order's delivery PO number (`MSC PO`), terms in days (`0` for **Due on Receipt**), invoice and due dates, currency (the customer's default currency), the order's base rate, the order's reference number as `WAYBILL-NUMBER`, waybill date, vessel, voyage, container number, the first four characters of the container number, the receiver's UN code and the invoice total (with taxes when the invoice is taxed), repeated on every row.
- Many other columns (bond, chassis detention, hazmat, weight, size and so on) are always empty.

!!! warning "FUEL is always 0 -- fuel goes under OTHER"
    The `FUEL`, `PRE-PULL` and `STORAGE` columns are always `0.00`. All of an order's charges, **including the fuel surcharge**, are added together in the `OTHER` column. Charges are not split by type.

!!! tip "Fill in UN codes"
    The `DESTINATION  - UNLOC` column is the **UN Code** of the receiver's city. Set it in the **Un Location Information (EDI Compatible)** form for each city (see [Zones & Cities](zones-and-cities.md)) so the column is not empty.

Full column list: [Creating Invoices](creating-invoices.md#edi-210-export).

---

## :fontawesome-solid-file-excel: QuickBooks-Ready Invoice Export

**Add-on:** none. **Where:** **Invoices** > **Export** panel in the filter bar.

**Data flow:** one way, on demand. UTX Freight does **not** connect to QuickBooks. It builds a file that you import into QuickBooks yourself.

1. Filter the **Invoices** list (status tab, search, invoice date range).
2. In the **EXPORT** panel, choose **QuickBooks columns** in the first drop-down (the other choice, **AR aging detail**, is not a QuickBooks layout) and **Excel** (.xlsx) or **CSV** (.csv) in the second.
3. Click **Export**. The panel tells you how many invoices are currently listed; only those are exported.

The file has one row per listed invoice, sorted by invoice date, with the columns **Invoice**, **Invoice Date** (YYYY-MM-DD), **Customer**, **Details** (`<type> - <container>` per order, separated by commas; the type is `CI` import, `EX` export, `DV` dry van, `TF` transfer or `IX` international export), **Amount before sales taxes**, **GST Charged**, **QST Charged** (both `0.00` when the invoice is not taxed) and **Amount after sales taxes**. An export is limited to 20,000 invoices; above that you see a message and nothing is downloaded.

Full guide: [Invoices](invoices.md#exporting-invoices).

---

## :fontawesome-solid-barcode: NHTSA VIN Decoder (Garage)

**Add-on:** Garage. **Where:** Garage > **Equipment** > new or edit form > **Decode** button next to **VIN**.

**Data flow:** when you click **Decode**, your browser sends the VIN directly to the free public VIN decoder of the U.S. National Highway Traffic Safety Administration (NHTSA). Nothing goes through UTX's servers and nothing is saved until you save the equipment form.

- The VIN must be at least 11 characters, otherwise you see *Please enter a valid VIN (at least 11 characters).*
- If NHTSA returns at least one of make, model or model year, **Year**, **Make** and **Model** are all replaced with what NHTSA returned (a value NHTSA did not return is cleared), and a short **VIN Decoded** message shows the result.
- If NHTSA knows the VIN but returns no make, model or year: *VIN was found but no make/model/year data returned. Please enter manually.*
- If NHTSA does not answer within 10 seconds or cannot be reached: *Could not reach NHTSA VIN decoder. Please enter vehicle details manually.*

Full guide: [Garage Customers & Equipment](garage-customers-and-equipment.md).

---

## :fontawesome-solid-code: Is There an API?

**No.** UTX Freight has **no public API** for customers. You cannot connect your own software to read or create orders, invoices or tracking data.

UTX Freight has a few internal endpoints that UTX uses to monitor and support your system. They are protected, not documented, and not available to customers.

To get data out of UTX Freight, use the built-in exports (for example the invoice **Export** panel and **EDI 210**). See [Data Exports](data-exports.md).

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see a tracking icon, Upload button or EDI 210 option

!!! info "Solution"
    Each of these needs its own add-on or account option. Check [Add-ons and Options](add-ons-and-options.md) and contact UTX support to turn it on. For tracking, also check that the order's pickup terminal is named as in [Which terminal triggers which source](#which-terminal-triggers-which-source).

### :fontawesome-solid-arrows-rotate: Can I force a container to refresh now?

!!! info "Solution"
    No. The stored tracking data is refreshed on UTX's schedule. For CN, the **CN Tracking** button on **Dispatch** shows a live answer from CN, but it does not update the popup. Look at **Updated ... ago** in the popup and the **Integration Health** cards on Container Alerts. If a source has not updated for a long time, contact UTX support.

### :fontawesome-solid-gas-pump: The EDI file shows FUEL 0.00 but the order has a fuel surcharge

!!! info "Solution"
    This is expected. The fuel surcharge is included in the `OTHER` column together with all other charges. `FUEL` is always `0.00`.

### :fontawesome-solid-file-import: Does UTX Freight sync with QuickBooks automatically?

!!! info "Solution"
    No. The QuickBooks columns export is a file you import into QuickBooks yourself. Nothing is sent to QuickBooks.

### :fontawesome-solid-reply: Customers say our emails come from a different address

!!! info "Solution"
    With **Postmark** selected, the From address is a UTX sending address, while the sender name stays yours and Reply-To points to your original address. Replies still reach you. If you need your own From address, switch **Email Delivery Method** back to **SMTP**.

### :fontawesome-solid-key: Can I get an API token?

!!! info "Solution"
    No. There is no customer API. Use the exports described in [Data Exports](data-exports.md).

---

!!! tip "Best Practices"
    - Name the CN pickup terminal exactly **CN**, and start other tracked terminal names with **TERMONT**, **VIAU**, **RACINE** or **CAST**, so tracking and the popup pick the right source.
    - Check **Integration Health** on Container Alerts before trusting a status that hasn't changed in a while.
    - Always review Auto Orders values before saving -- text recognition can misread characters.
    - Set the **UN Code** on your receivers' cities before sending EDI 210 files.
    - Send a test email from **Settings** after any change to **Email Delivery Method**.
