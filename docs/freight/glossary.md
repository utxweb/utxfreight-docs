# Glossary

An A–Z list of the terms, screen labels, abbreviations and status names used in UTX Freight, each with a short definition and a link to the page that explains it in full.

## :fontawesome-solid-book: Overview

UTX Freight uses trucking, port and rail vocabulary, and some things have more than one name: one name in exports and order history, another on a filter tab, and a third in a tooltip. This page puts all of those names side by side.

- :fontawesome-solid-font: **Labels are written exactly as the screen shows them**, in **bold**. Status names keep their capitals and punctuation (for example **App. Taken**, **Arrived - Awaiting delivery**).
- :fontawesome-solid-shuffle: **Synonyms are grouped.** When two names mean the same thing, both are listed and point to the same definition. See [Synonyms & Alternate Names](#synonyms-alternate-names).
- :fontawesome-solid-link: **Every entry links to its page.** The glossary only gives the short version; the linked page has the details, steps and permissions.
- :fontawesome-solid-puzzle-piece: **Some terms only exist on some accounts.** Add-ons (for example **Garage**, **Warehouse**, **Fuel Surcharge**, container tracking) and the shipment mode (**intermodal** or **ground**) decide which screens you see. Entries say so when it matters. See [Add-ons & Options](add-ons-and-options.md).

---

## :fontawesome-solid-bolt: Quick Start

1. Use your browser's search (**Ctrl+F**, or **Cmd+F** on a Mac) and type the word, label or abbreviation you are looking for.
2. If the word is a nickname or an older name (for example *Canned Jobs* or *App. Made*), start with the [Synonyms & Alternate Names](#synonyms-alternate-names) table.
3. For a short code on the **Orders** page (**CI**, **LFD**, **B#** …), see [Order Type Codes](#order-type-codes) and [Abbreviations](#abbreviations).
4. Click the link in the **See** column to open the full page.

---

## :fontawesome-solid-shield-halved: Access & Permissions

The glossary is a reference page. Everyone can read it. The terms it defines are used by the roles below; each user has exactly one role.

| Role | Who it is for |
|------|---------------|
| :fontawesome-solid-user-shield: **Admin** | Full access to everything, including **Settings** and role changes |
| :fontawesome-solid-user-tie: **Manager** | Close to Admin, but cannot open **Settings**, change roles or use some admin-only pages |
| :fontawesome-solid-headset: **Dispatch** | Creates and dispatches orders. Sees rates only with **Can manage rates?** |
| :fontawesome-solid-headset: **Customer Service** | Same permissions as **Dispatch**; the only difference is the **Invoiced / Rate** column on the Orders list |
| :fontawesome-solid-calculator: **Accountant** | Invoicing, payments and statements; order and check rights depend on edition options |
| :fontawesome-solid-user: **Customer** | A customer contact using the [Customer & Consignee Portal](customer-portal.md) |
| :fontawesome-solid-warehouse: **Warehouse** | Warehouse add-on users |
| :fontawesome-solid-wrench: **Garage** | Garage add-on users |
| :fontawesome-solid-truck: **Driver** / :fontawesome-solid-handshake: **Broker** / **Yard Worker** | Mobile users who sign in on a phone with an **Access Code** or a **Login Link** |

See [User Roles & Permissions](user-roles.md) for the full permission matrix.

---

## :fontawesome-solid-shuffle: Synonyms & Alternate Names

Use this table when someone uses a different word for the same thing.

| You may hear or see | Same as | Where each name appears | See |
|---------------------|---------|-------------------------|-----|
| **App. Taken**, **App. Made**, **Appointment Made** | One order status: an appointment has been made | **App. Taken** is the name in exports and order history. **App. Made** is the filter tab on **Orders**, **Dispatch** and the customer portal. **Appointment Made** is the status label tooltip and the Legend | [Order Status Workflow](order-workflow.md) |
| **Make App.** | The button that moves a **New** order to **App. Taken** | Row action button on **Orders** and **Dispatch** | [Order Status Workflow](order-workflow.md) |
| **New**, **New Order** | The first order status | **new** in exports and history; **New Order** is the tooltip; **New** is the tab | [Order Status Workflow](order-workflow.md) |
| **Shipper / Receiver**, **Client**, **Manage Clients** | The address book of pickup and delivery locations | **Manage Clients** in the user menu opens the same list as **Shipper / Receiver**. "Send POD to client" means the delivery location | [Shippers & Receivers](shippers-receivers.md) |
| **Customer** vs. **Client** | Not the same | A **Customer** is the company you bill. A **Client** (Shipper / Receiver) is a pickup or delivery location | [Customers](managing-customers.md) |
| **Charge Types**, **Order Charges** | The list of charges you bill (and expense charge types) | **Charge Types** in the user menu; the page it opens is titled **Order Charges** | [Charge Types & Taxes](charge-types-and-taxes.md) |
| **Order Charges for Invoice Breakdown**, **Rate** | The rate and charges section of an order | **Order Charges for Invoice Breakdown** in the **Quick Edit**, **Dispatch** and **Complete** windows; **Rate** on the full order form | [Order Rates, Charges & Expenses](order-charges-and-expenses.md) |
| **Expense Types**, **Expense Categories**, **Other Expense** | The "other" payees for order expenses | **Expense Types** in the user menu; the page it opens is titled **Expense Categories**; the payee group in **Order Expenses** is **Other Expense** | [Charge Types & Taxes](charge-types-and-taxes.md) |
| **Templates**, **Job Templates**, **Canned Jobs** | Garage job templates: pre-filled parts and labor | **Templates** in the Garage sidebar opens **Job Templates**. *Canned jobs* is an older name, still used in some release notes | [Garage Parts & Templates](garage-parts-and-templates.md) |
| **MGT**, **Racine / Cast** | One container tracking source: Montreal Gateway Terminals (Racine and Cast) | Shown as **MGT (Racine/Cast)** on screens | [Container Tracking](container-tracking.md) |
| **Termont**, **Port of Montreal** | One container tracking source (Port of Montreal terminals) | Shown as **Termont** on Container Alerts; the **Port Tracking** window on **Dispatch** is titled **Port of Montreal** (it also lists MGT containers) | [Container Tracking](container-tracking.md) |
| **CN**, **CN Rail**, **Canadian National** | The CN rail tracking source | **CN Rail** on Container Alerts; **CN Tracking** button on **Dispatch** | [Container Tracking](container-tracking.md) |
| **Login Link**, **driver login link** | A one-tap sign-in link for a driver | **Login Link** in the copy message (tooltip **Click to copy** on the share icon) | [Driver Login Links](driver-login-links.md) |
| **Mobile Users**, **Drivers, Brokers & Yard**, **Drivers, Brokers and Yard Workers**, **Manage Drivers** | People who use UTX Freight from a phone, and the page that lists them | Left menu **Mobile Users** > **Drivers, Brokers & Yard**, or **Manage Drivers** in the user menu; the page title is **Drivers, Brokers and Yard Workers** | [Mobile Users](mobile-users.md) |
| **Order Start Date**, **Invoice order start date** | One setting | **Order Start Date** on the Settings page; **Invoice order start date** on the edit form | [Application Settings](application-settings.md) |
| **Order Archive Cutoff Date**, **Order archived at**, archive cutoff | One setting | **Order Archive Cutoff Date** on the Settings page; **Order archived at** on the edit form | [Application Settings](application-settings.md) |
| **Job type**, **Order type** | The kind of order (Import, Export …) | **Job type** on the order form; **Order Type** filter card | [Orders](orders.md#order-types) |
| **Container status**, **C.Status** | The container's current location label | **C.Status** column on Orders and Dispatch | [Container Statuses](container-statuses.md) |
| **Dry Van**, **Dry Van Move**, **DV**, **LCL** (driver phone) | Dry Van orders | **DV** badge; on the driver's phone Dry Van steps are titled **LCL: Pickup** and **LCL: Delivery** | [Driver Workflow](driver-workflow.md) |
| **International Export**, **IX**, **eBoL** | International Export orders use an eBoL instead of a POD | **View eBoL** replaces **View POD** | [Order Documents & POD](order-documents-and-pod.md) |
| **Equipments**, **Equipment** | Chassis, trailers and trucks | Left menu **Equipments** | [Equipment](equipment.md) |
| **Your Company: &lt;name&gt;** | Your own company on the Customers page; your staff are its people | **Customers** page | [Users, Contacts & Invitations](people-and-invitations.md) |
| **Auto Orders** | Order creation from an uploaded document (beta) | **AUTO ORDERS** section of the **Orders** filters | [Auto Orders](auto-orders.md) |
| **Broker** | Three different things | See [Broker](#b) | [Lookup Lists](lookup-lists.md) |

---

## :fontawesome-solid-tags: Order Type Codes

Each order row on the **Orders** page starts with a short code badge. The **Orders Page Legend** lists the same codes.

| Code | Full name (Legend) | Job type on the form | Filter card name |
|------|--------------------|----------------------|------------------|
| **CI** | **Container Import** | **Container Import** | **Import** |
| **CX** | **Container Export** | **Container Export** | **Export** |
| **TF** | **Container Transfer** | **Container Transfer** | **Transfer** |
| **DV** | **Dry Van Move** | **Dry Van Move** | **Dry Van** |
| **IX** | **International Export** | **International Export** | **International Export** |
| **WH** | **Warehouse** | Warehouse orders (separate list) | Listed in the Legend only when warehouse orders are enabled |

Order types are switched on per account by UTX. By default only **Import** and **Export** are enabled. See [Orders](orders.md#order-types).

---

## :fontawesome-solid-flag: Order Status Names

| Exports / history | Tooltip / Legend | Filter tab | Icon and colour | Next button |
|--------------|------------------|------------|-----------------|-------------|
| **new** | **New Order** | **New** | :fontawesome-solid-star: red | **Make App.** |
| **App. Taken** | **Appointment Made** | **App. Made** | :fontawesome-solid-clock: orange | **Dispatch** |
| **Dispatched** | **Order Dispatched** (Legend: **Dispatched**) | **Dispatched** | :fontawesome-solid-road: green | **Complete** |
| **Completed** | **Order Completed** (Legend: **Completed**) | **Completed** | :fontawesome-solid-check: grey | **Actions** |

Other tabs on the **Orders** page group statuses:

- **In Progress** (the default tab): **New** + **App. Taken** + **Dispatched**.
- **Not Invoiced**: **Completed** orders not on an invoice, delivered on or after the **Order Start Date** (Admin / Manager).
- **Late Invoicing**: like **Not Invoiced**, but only orders delivered before the end of the week two weeks ago (Admin / Manager).

!!! info "Invoiced is not an order status"
    Putting an order on an invoice does not change its status. It stays **Completed**. Invoices have their own statuses (**new**, **Invoiced**, **Paid**, **Partially Paid**). See [Creating Invoices](creating-invoices.md).

See [Order Status Workflow](order-workflow.md).

---

## :fontawesome-solid-boxes-stacked: Container Status Names

A **container status** says where the container is. It is separate from the order status. These are the **built-in** statuses that come with UTX Freight. Your company can add **custom** statuses with its own names and colours; those are not listed here. Statuses can be shown in any colour you configure; the colours below are the defaults.

| Container status | Default colour | Short meaning |
|------------------|----------------|---------------|
| **Arrived - Awaiting delivery** | Green | Import: the container has arrived at the terminal and is ready for pickup |
| **Arrived - Missing customs** | Red | Import: arrived, but customs clearance is missing |
| **Arrived - On hold** | Red | Import: arrived, but on hold |
| **At customer** | Grey | The container is at the customer (no default job type description) |
| **Driver at terminal** | Light green | The driver is at the terminal for the pickup |
| **Dropped at customer** | Red | Delivered to the customer. Set automatically on an import's delivery signature and an export's drop signature |
| **Empty at customer** | Yellow | An empty container is at the customer (waiting for pickup, or for loading) |
| **Empty at yard** | Blue | An empty container is stored at your yard. Set by the yard worker's **Empty at yard** button |
| **Export** | Orange | The container is processed for export |
| **Full at customer** | Orange | Loaded at the customer and ready for pickup |
| **Full at yard** | Purple | A full container is stored at your yard. Set by the yard worker's **Full at yard** button |
| **Live load** | Red | The container is being loaded or unloaded live |
| **On rail** | Pink | The container is on rail transport |
| **On route to customer** | Yellow | Being moved to the customer |
| **On route to terminal** | Yellow | Being moved to the terminal (empty return on imports, loaded on exports) |
| **On route to yard** | Yellow | Being moved to the yard (no default job type description) |
| **On vessel** | Dark blue | The container is on the vessel |
| **Ready for 2nd stop** | Grey | Ready for a second stop (no default job type description) |
| **Returned to terminal** | Green | Returned to the terminal; the order leaves the driver app. Set automatically by **Drop Completed** (import) and **Transfer Completed** |
| **Reused for export** | Orange | Export: the container is reused for another export shipment |

When an order has no container status, **N/A** is shown in grey. See [Container Statuses](container-statuses.md).

---

## :fontawesome-solid-calculator: Abbreviations

| Abbreviation | Stands for | Meaning in UTX Freight | See |
|--------------|-----------|------------------------|-----|
| **B#** | Booking Number | The **Booking number** of an Export, Transfer or International Export order | [Order Form](order-form.md) |
| **CI / CX / TF / DV / IX / WH** | Order type codes | See [Order Type Codes](#order-type-codes) | [Orders](orders.md) |
| **CLM** | Car Location Message | The CN rail event status shown in CN tracking (**CLM Status**, **CLM Code**). "De-ramped" means the container is off the train | [Container Tracking](container-tracking.md) |
| **CTQ** | Commission des transports du Québec | Printed with your **NIR Number** on the POD (**NIR - CTQ#:**) | [Application Settings](application-settings.md) |
| **CUT** | Cutoff Date | The **Cutoff date** of an Export order | [Order Form](order-form.md) |
| **DEM** | Demurrage | The **Demurrage date** of an Import order | [Order Form](order-form.md) |
| **eBoL** | Electronic Bill of Lading | The International Export version of the POD (**View eBoL**) | [Order Documents & POD](order-documents-and-pod.md) |
| **EDI 210** | Freight invoice (EDI) | A CSV download of an invoice, in the invoice **Actions** menu, when EDI invoicing is enabled | [Creating Invoices](creating-invoices.md) |
| **EDI 214** | Shipment status message (EDI) | A CN tracking field under **Technical Details** | [Container Tracking](container-tracking.md) |
| **EDI 322** | Terminal / intermodal ramp activity (EDI) | A CN tracking field under **Technical Details** | [Container Tracking](container-tracking.md) |
| **ERD** | Earliest Return Date | The **Earliest Return Date (ERD)** of an Export order | [Order Form](order-form.md) |
| **ETA** | Estimated Time of Arrival | The **ETA date** of an Import order | [Order Form](order-form.md) |
| **GST** | Goods and Services Tax | Your **GST Number** (printed on invoices as **G.S.T / T.P.S**) and the federal tax on invoices | [Application Settings](application-settings.md), [Charge Types & Taxes](charge-types-and-taxes.md) |
| **LCL** | Less-than-Container Load | On the driver's phone, Dry Van steps are titled **LCL: Pickup** and **LCL: Delivery**. On the order list, a container size containing "LCL" (or "DRY", "20" or "45") is shown in red | [Driver Workflow](driver-workflow.md) |
| **LFD** | Last Free Day | The **Last Free Day (LFD)** of an Import, Export or International Export order: the last day before storage or demurrage charges start | [Order Form](order-form.md), [Container Alerts](container-alerts.md) |
| **NIR** | Quebec carrier registration number | Your **NIR Number**, printed on the POD (**NIR - CTQ#:**) and on the invoice (**N.I.R**) | [Application Settings](application-settings.md) |
| **P/O#**, **P.O.** | Purchase Order Number | The pickup or delivery **P.O.** on an order. **P/O#:** under the order number shows the delivery P.O., or **N/A** | [Order Form](order-form.md) |
| **POD** | Proof of Delivery | The scanned POD (uploaded PDF) or signed POD (built from the driver's signature) | [Order Documents & POD](order-documents-and-pod.md) |
| **QST** | Quebec Sales Tax (TVQ) | Your **QST Number** (printed as **Q.S.T / T.V.Q.**) and the Quebec tax on invoices | [Application Settings](application-settings.md) |
| **S#** | Seal Number | The **Seal number** of a container | [Order Form](order-form.md) |
| **SKU / Sku** | Stock keeping unit | Part code in the Garage parts catalogue, product code in the Warehouse | [Garage Parts & Templates](garage-parts-and-templates.md), [Warehouse Setup](warehouse-setup.md) |
| **STO** | Storage | The **Storage date** of an Import order | [Order Form](order-form.md) |
| **UoM** | Unit of Measure | The unit on a warehouse product line | [Warehouse Setup](warehouse-setup.md) |
| **WO** | Work Order | A Garage repair or service job | [Garage Work Orders](garage-work-orders.md) |

---

## :fontawesome-solid-arrow-down-a-z: A–Z

### A

| Term | Definition | See |
|------|-----------|-----|
| **Access Code** | The code a mobile user (Driver, Broker, Yard Worker) types after tapping **Mobile Login** to sign in on a phone | [Mobile Users](mobile-users.md) |
| **Active for orders** | A per-person setting that decides whether a customer contact appears in the order form | [Users, Contacts & Invitations](people-and-invitations.md) |
| **Add-on** | An optional feature that UTX turns on for your account (for example Garage, Warehouse, Fuel Surcharge, Multi-Office, container tracking, Driver Login Links). When it is off, its menus and buttons are hidden. You cannot switch add-ons on yourself | [Add-ons & Options](add-ons-and-options.md) |
| **Additional Charges** | The charge lines of an order on top of the **Base rate**: the ones you add with **(+) Add another**, plus computed lines such as the terminal fee and fuel surcharge | [Order Rates, Charges & Expenses](order-charges-and-expenses.md) |
| **Aged Receivables** | The AR report of unpaid invoices by age. The **Standard** report ages by days past due (**Not Yet Overdue**, **30 or Less**, **31 to 60**, **61 to 90**, **91 or More**); the **Performance** report ages by invoice date (**30 days**, **60 days**, **90 days**, **90+ days**) | [Aged Receivables](aged-receivables.md) |
| **Aging buckets** | The age bands unpaid invoices are grouped into. On the **Invoices** page: rollups **Past due**, **30+ days**, **60+ days** and exact bands **Not Due**, **0-30**, **31-60**, **61-90**, **91+** | [Invoices](invoices.md#ar-aging-days-past-due), [Aged Receivables](aged-receivables.md) |
| **App. Made** / **App. Taken** / **Appointment Made** | The second order status: an appointment has been made. Once it is set, a customer can no longer edit the order | [Order Status Workflow](order-workflow.md) |
| **Archive cutoff** | See **Order Archive Cutoff Date** | [Application Settings](application-settings.md) |
| **Arrived - Awaiting delivery** | Built-in container status: the import container is at the terminal and ready for pickup. Set it yourself; dispatching does not set it | [Container Statuses](container-statuses.md) |
| **Assign Equipment** | The window used to put a **Chassis** or **Trailer** on an order from **Orders** or **Dispatch** | [Equipment](equipment.md) |
| **Auto compute fuel surcharges for this order** | Order setting. When **Yes**, the fuel surcharge is added automatically (Import, Export and Transfer orders, Fuel Surcharge add-on) | [Fuel Surcharge](fuel-surcharge.md) |
| **Auto Orders** | Beta add-on that reads an uploaded document and pre-fills a new order for review (**Processing**, **Need Review**, **Completed** tabs) | [Auto Orders](auto-orders.md) |
| **Automatic statements** | Customer statements emailed on a schedule (a day of the week, the 1st or 15th of the month, or the 2nd and 16th), only when the customer has unpaid invoices | [Automatic Statements](automatic-statements.md) |

### B

| Term | Definition | See |
|------|-----------|-----|
| **Base rate** | The main price of an order, filled from the customer's custom zone rate or else from the delivery city's zone rate | [Order Rates, Charges & Expenses](order-charges-and-expenses.md) |
| **Borrowed equipment** | A chassis you do not own (for example borrowed from another carrier). Assign the special unit named **Borrowed** and type the real chassis number on the order (**Enter chassis number**) | [Equipment](equipment.md#borrowed-equipment) |
| **Broker** (three meanings) | 1. **Broker records**: names on **Manage Brokers**, used in the **Broker** field of Dry Van orders and the **Broker** payee group in **Order Expenses**. 2. **Customer companies flagged Broker**: the **Broker** checkbox on a customer, offered in **Transport Company ( broker )** on Dry Van orders. 3. **Broker mobile users**: phone users with exactly the same rights as a Driver. The three are not linked | [Lookup Lists](lookup-lists.md), [Customers](managing-customers.md), [Mobile Users](mobile-users.md) |
| **Building** | Warehouse add-on: a warehouse site with an address and contact. Every warehouse **Location** belongs to one building | [Warehouse Setup](warehouse-setup.md) |
| **Built-in status** | A container status that comes with UTX Freight. It cannot be edited or deleted | [Container Statuses](container-statuses.md) |

### C

| Term | Definition | See |
|------|-----------|-----|
| **C.Status** | The container status column on **Orders** and **Dispatch** (intermodal accounts) | [Container Statuses](container-statuses.md) |
| **Can manage rates?** | Per-user checkbox on a Dispatch person's profile. Only an Admin can change it. When checked (the default), the dispatcher sees rates, charges and expenses and can open **Charge Types**, **Expense Types** and **Manage Cities** | [User Roles](user-roles.md), [Users, Contacts & Invitations](people-and-invitations.md) |
| **Canned Jobs** | Older name for Garage **Job Templates** | [Garage Parts & Templates](garage-parts-and-templates.md) |
| **Charge Types** | The list of charges, opened from **Charge Types** in the user menu (page title **Order Charges**). **Income** types are billed; **Expense** types are costs. One can be the **Terminal Fee** | [Charge Types & Taxes](charge-types-and-taxes.md) |
| **Chassis** | Equipment sub category for container chassis. Assigned to orders with **Assign Equipment** | [Equipment](equipment.md) |
| **Checks** | The checks you issue to pay order expenses. Saving a check marks its expense lines as **Paid** (when **Check Expenses** is enabled) | [Expenses & Checks](expenses-and-checks.md) |
| **City** | A location (UN location) that Shippers / Receivers are linked to. Each city belongs to at most one **zone** | [Zones & Cities](zones-and-cities.md) |
| **Client** | Another name for **Shipper / Receiver** (pickup or delivery location). **Manage Clients** opens the Shipper / Receiver list. Not the billed customer | [Shippers & Receivers](shippers-receivers.md) |
| **Closing Date** | Warehouse add-on: the date entered when you **Complete** a warehouse order. It stops the storage month count | [Warehouse Orders](warehouse-orders.md) |
| **Completed** | Final order status: the order is delivered and ready to invoice. Also a Garage work order status (before **Invoiced**) and a warehouse order status | [Order Status Workflow](order-workflow.md) |
| **Computed Terminal Fee** | The terminal fee charge added automatically to Import and Export orders | [Terminals](managing-terminals.md) |
| **Consignee** | A customer whose company is linked to one or more Shipper / Receiver records. Its users get read-only visibility of orders delivered to those locations, even orders placed by another freight forwarder | [Customer & Consignee Portal](customer-portal.md), [Shippers & Receivers](shippers-receivers.md) |
| **Container Alerts** | Container tracking page of alerts: **Pickup Ready**, **Customs Released**, **LFD Approaching**, **Departed** | [Container Alerts](container-alerts.md) |
| **Container status** | Label for where the container is now (for example **Full at yard**). Separate from the order status. See [Container Status Names](#container-status-names) | [Container Statuses](container-statuses.md) |
| **Container tracking** | Add-ons that check the container's terminal status at CN Rail, Termont (Port of Montreal) or MGT (Racine/Cast) | [Container Tracking](container-tracking.md) |
| **Custom rate** | A customer-specific rate for a zone, a terminal or a warehouse charge. It replaces the standard rate for that customer | [Customers](managing-customers.md) |
| **Custom status** | A container status your company created. You choose its name, colour and order types | [Container Statuses](container-statuses.md) |
| **Customer** | A company you bill, with its people (contacts). Every order is placed on behalf of a customer person. Also the role of customer contacts who log in | [Customers](managing-customers.md), [Customer & Consignee Portal](customer-portal.md) |
| **Customer Reports** | The **Reports** page for sending customer statements by email, print or Excel | [Customer Statements](customer-statements.md) |
| **Customer Service** | A staff role with exactly the same permissions as **Dispatch**. The only difference: it sees the **Invoiced / Rate** column on Orders (without the invoice button) | [User Roles](user-roles.md) |
| **Cutoff date (CUT)** | The **Cutoff date** field of a Container Export order (Legend: **CUT** - Cutoff Date) | [Order Form](order-form.md) |

### D

| Term | Definition | See |
|------|-----------|-----|
| **Default Rate** | A terminal's terminal fee, used for the **Computed Terminal Fee** unless the customer has its own rate | [Terminals](managing-terminals.md) |
| **Default tag** | A tag pre-selected on new staff orders for a customer | [Order Tagging](order-tagging.md) |
| **Demurrage (DEM)** | Charges for a container left at the terminal past its free time. The **Demurrage date** is on Import orders | [Order Form](order-form.md) |
| **Dispatch** | The order status after **App. Taken**, the button that sets it, the role, and the **Dispatch** board page | [Dispatch](dispatch.md), [Order Status Workflow](order-workflow.md) |
| **Document Type** | The category you give each additional document attached to an order | [Order Documents & POD](order-documents-and-pod.md) |
| **Driver** | A mobile user who is assigned to orders and completes them from the phone (signatures, delivered, returned) | [Driver Workflow](driver-workflow.md) |
| **Dry Van Move (DV)** | A ground move from a pickup company to a delivery company. Its legs are built automatically | [Orders](orders.md#order-types) |

### E

| Term | Definition | See |
|------|-----------|-----|
| **Edition** / **edition options** | Account options set by UTX that widen or narrow what some roles can do (for example letting Managers view reports, letting Dispatch manage customers, or letting customers enter their own orders). They cannot be changed in the app; ask UTX support | [User Roles](user-roles.md#edition-options-set-by-utx), [Add-ons & Options](add-ons-and-options.md) |
| **Equipment** | Your chassis, trailers and trucks (left menu **Equipments**). Each unit has an **Equipment Type** in one of three sub categories: **Chassis**, **Truck**, **Trailer**. Garage equipment is a separate list | [Equipment](equipment.md) |
| **Estimate** | First status of a Garage work order. **Print Estimate** prints it for the customer | [Garage Work Orders](garage-work-orders.md) |
| **Expenses** | What an order costs you (driver pay, broker fees, other costs), entered in **Order Expenses**. They never change the order total | [Expenses & Checks](expenses-and-checks.md) |

### F – G

| Term | Definition | See |
|------|-----------|-----|
| **Fuel surcharge** | A monthly percentage of the base rate, added automatically to qualifying Import, Export and Transfer orders (Fuel Surcharge add-on). Set on the **Fuel Schedule** page, with customer overrides and exemptions | [Fuel Surcharge](fuel-surcharge.md) |
| **Full at yard** / **Empty at yard** | Container statuses for containers stored at your yard, set by the yard worker or the office | [Yard Management](yard-management.md) |
| **Garage** | Add-on for repair shops: work orders, invoices (numbered `GRG-00001` by default), parts, templates, customers and equipment, all per office | [Garage Overview](garage-overview.md) |
| **Ground** (shipment mode) | Account mode with trailer-based screens (**Trailer#**, **Equipment #**). The other mode is **intermodal** | [Add-ons & Options](add-ons-and-options.md) |
| **Ground Container** | Yard Worker button that takes the container off its chassis (removes the chassis from the order) | [Yard Management](yard-management.md) |
| **GST / QST** | Federal and Quebec sales taxes. Your numbers are entered in **Settings**; tax rates in **Manage Taxes**; the Garage has its own taxes | [Application Settings](application-settings.md), [Garage Settings & Taxes](garage-settings-and-taxes.md) |

### I – L

| Term | Definition | See |
|------|-----------|-----|
| **In Progress** | Default **Orders** tab: **New** + **App. Taken** + **Dispatched** orders | [Orders](orders.md) |
| **Income** / **Expense** | The two kinds of charge type: billed to the customer, or a cost you track | [Charge Types & Taxes](charge-types-and-taxes.md) |
| **Intermodal** (shipment mode) | Account mode for containers, terminals and steamship lines. Container statuses and terminals only exist in this mode | [Add-ons & Options](add-ons-and-options.md) |
| **International Export (IX)** | An export order that uses an eBoL instead of a POD | [Orders](orders.md#order-types) |
| **Invoice Status** | Freight invoice status: **new**, **Invoiced**, **Paid**, **Partially Paid**. Emailing a **new** invoice sets **Invoiced** | [Creating Invoices](creating-invoices.md) |
| **Job Templates** | Garage: named jobs with parts and labor lines, applied to a work order with **Apply Template**. Opened from **Templates** in the Garage sidebar | [Garage Parts & Templates](garage-parts-and-templates.md) |
| **Late Invoicing** | **Orders** tab of completed, uninvoiced orders delivered before the end of the week two weeks ago | [Orders](orders.md) |
| **Leg** | One move of an order: **Move From** a place, by a driver, **Move To** another place. Dry Van and Transfer legs are built automatically | [Order Legs & Move Locations](order-legs-and-move-locations.md) |
| **Legend** | Button on the **Orders** page that opens the **Orders Page Legend** (codes, badges, abbreviations, icons, colours) | [Orders](orders.md) |
| **Location** | Warehouse add-on: a storage spot (aisle, bay, room) inside a **Building** | [Warehouse Setup](warehouse-setup.md) |
| **Login Link** | One-tap sign-in link for a driver, copied from the :fontawesome-solid-share-from-square: icon (Driver Login Links add-on). Valid 24 hours; you send it yourself | [Driver Login Links](driver-login-links.md) |

### M – O

| Term | Definition | See |
|------|-----------|-----|
| **Make App.** | Button that records the appointment and moves a **New** order to **App. Taken** | [Order Status Workflow](order-workflow.md) |
| **Mobile Login** | Button on the phone sign-in page for drivers, brokers and yard workers. It opens the **Access Code** field | [Driver Workflow](driver-workflow.md) |
| **Mobile user** | A Driver, Broker or Yard Worker. Set up under **Mobile Users**, not on the Customers page | [Mobile Users](mobile-users.md) |
| **Move Locations** | The places (besides terminals) that order legs can move from and to, managed from **Manage Move Locations** in the user menu (page title **Leg Move Locations**) | [Order Legs & Move Locations](order-legs-and-move-locations.md) |
| **Multi-Office** | Add-on to run several offices in one account. Orders, invoices and checks belong to one office; master data is shared | [Multi-Office](multi-office.md) |
| **Not Invoiced** | **Orders** tab of completed orders not yet on an invoice, delivered on or after the **Order Start Date** | [Orders](orders.md) |
| **Office** | The branch an order, invoice or check belongs to. You work in one office at a time (office switcher in the top bar). Garage and lookup list records also belong to an office | [Multi-Office](multi-office.md) |
| **Off-Hire** | Import order field for equipment off-hire; shown as a red **OFF-HIRE** badge in the size column | [Orders](orders.md) |
| **Order Archive Cutoff Date** | Setting (form label **Order archived at**). Only orders created on or after this date appear on the **Orders** page and in its searches | [Application Settings](application-settings.md) |
| **Order Charges** | Title of the page opened by **Charge Types** in the user menu | [Charge Types & Taxes](charge-types-and-taxes.md) |
| **Order Expenses** | The order section where you record costs. The payee list is grouped into **Driver**, **Broker** and **Other Expense** | [Order Rates, Charges & Expenses](order-charges-and-expenses.md) |
| **Order Start Date** | Setting (form label **Invoice order start date**). Only completed orders delivered on or after it are offered for invoicing and listed in **Not Invoiced** / **Late Invoicing**; the Standard aged receivables report also starts there | [Application Settings](application-settings.md) |

### P – R

| Term | Definition | See |
|------|-----------|-----|
| **Parts** | Garage parts catalogue (**Parts Inventory**) with cost, charge price and stock. Stock goes down when a work order moves to **In progress** | [Garage Parts & Templates](garage-parts-and-templates.md) |
| **Pickup Ready** | Container alert: the container is off the train (CN) or cleared for pickup at the terminal (Termont / MGT) | [Container Alerts](container-alerts.md) |
| **Port Tracking** | Button on the **Dispatch** page for Termont and MGT container tracking | [Container Tracking](container-tracking.md) |
| **POD** | Proof of Delivery: the **Scanned POD** (uploaded PDF) or **Signed POD** (from the driver's signature). **View Internal POD** is a staff version | [Order Documents & POD](order-documents-and-pod.md) |
| **Product** | Warehouse add-on: a stored item with a **Name**, a **Sku** and optional default location and unit of measure | [Warehouse Setup](warehouse-setup.md) |
| **Rate manager** | A user who can see and change rates: Admin, Manager, and Dispatch with **Can manage rates?** | [Order Rates, Charges & Expenses](order-charges-and-expenses.md) |
| **Return Address** | The terminal the container goes back to (**Terminal Name**, **Instructions**, and **Return Date** on Imports or **Last Return Date** on Exports). Shown for Import, Export and Transfer. The order details page calls it **Return Address**; on the order form it is titled **Empty container return terminal** (Import, Transfer) or **Full container return terminal** (Export) | [Order Form](order-form.md) |
| **Returned to terminal** | Container status that closes the container cycle and removes the order from the driver app | [Container Statuses](container-statuses.md) |

### S

| Term | Definition | See |
|------|-----------|-----|
| **Service** (customer) | What a customer uses: **Intermodal**, **Warehouse**, **Intermodal & Warehouse** or **Garage** (the last three with their add-ons) | [Customers](managing-customers.md) |
| **Shipment mode** | **intermodal** or **ground**, set by UTX. Shapes the whole application | [Add-ons & Options](add-ons-and-options.md) |
| **Shipper / Receiver** | A pickup or delivery location (company name, address, city, contacts). Not the billed customer. Also called **Client** | [Shippers & Receivers](shippers-receivers.md) |
| **Shop Supplies Fee** | Garage: a fee for shop consumables on a work order, added to the invoice (summed from the work orders unless overridden) | [Garage Work Orders](garage-work-orders.md), [Garage Invoices](garage-invoices.md) |
| **Signed POD** | The POD built from the driver's captured signature | [Order Documents & POD](order-documents-and-pod.md) |
| **Special Note** | Short staff comment shown in bold red under the order's status and on the driver's phone. Hidden from customers | [Order Form](order-form.md) |
| **Statement** | A summary of a customer's unpaid invoices, sent by email (PDF or Excel), printed, or sent automatically | [Customer Statements](customer-statements.md) |
| **Steamship line** | The shipping line on a container order, chosen from **Manage Steamship Lines** | [Lookup Lists](lookup-lists.md) |
| **Storage Date** | On Import orders (**Storage date**, **STO**): the container storage date. On warehouse orders: the date storage starts | [Order Form](order-form.md), [Warehouse Orders](warehouse-orders.md) |
| **Suspension** | Account status set by UTX. While suspended, no one can create, duplicate or upload orders; existing orders stay visible | [Add-ons & Options](add-ons-and-options.md) |

### T

| Term | Definition | See |
|------|-----------|-----|
| **Tag / Group** | A label on an order, used to colour and filter orders. The tag list is set up by UTX | [Order Tagging](order-tagging.md) |
| **Templates** | Garage sidebar item that opens **Job Templates** | [Garage Parts & Templates](garage-parts-and-templates.md) |
| **Terminal** | A rail yard, port terminal or other place where containers are picked up and returned. Some names (CN, CP, Termont, Racine, Cast) drive filters and tracking | [Terminals](managing-terminals.md) |
| **Terminal fee** | Charge added automatically to Import and Export orders (**Computed Terminal Fee**) from the terminal's **Default Rate** or the customer's terminal rate. Needs one charge type set as the **Terminal Fee** | [Terminals](managing-terminals.md), [Charge Types & Taxes](charge-types-and-taxes.md) |
| **Termont** | The Port of Montreal container tracking source | [Container Tracking](container-tracking.md) |
| **Trailer** | Equipment sub category. Assigned to orders like a chassis | [Equipment](equipment.md) |
| **Transfer (TF)** | A container move to the **Return To** location, with no second driver. Its legs are built automatically | [Orders](orders.md#order-types) |
| **Transfer to Office** | Moves an order that is not invoiced to another office (Multi-Office) | [Multi-Office](multi-office.md) |

### U – Z

| Term | Definition | See |
|------|-----------|-----|
| **Unit of Measure (UoM)** | Warehouse add-on: the footprint of a stored item. Its **Length (inch)** and **Width (inch)** give the square feet that **Monthly** charges are billed on | [Warehouse Setup](warehouse-setup.md) |
| **Warehouse** | Add-on for storage orders, billed by space and time, with their own list, numbering and statuses (**New** shown under **Open**, and **Completed**). Also a user role | [Warehouse Overview](warehouse-overview.md) |
| **Work Order** | Garage repair or service job. Statuses: **Estimate** → **Approved** → **In progress** → **Completed** → **Invoiced**; an estimate can go straight to **In progress** | [Garage Work Orders](garage-work-orders.md) |
| **Yard Worker** | A mobile user who searches containers by number and can **Ground Container** or set **Full at yard** / **Empty at yard**. Has no order list | [Yard Management](yard-management.md) |
| **Your Company** | Your own company on the **Customers** page; your staff are its people | [Customers](managing-customers.md) |
| **Zone** | A group of cities with one rate. The delivery city's zone gives the order's **Base rate**. A red **Zone Not Set** badge means no zone was found | [Zones & Cities](zones-and-cities.md) |

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-clock: Are App. Taken and App. Made different statuses?

!!! info "Solution"
    No. It is one status. **App. Taken** is the name in exports and order history, **App. Made** is the filter tab, and **Appointment Made** is the tooltip. See [Order Status Workflow](order-workflow.md).

### :fontawesome-solid-building: Is a Client the same as a Customer?

!!! info "Solution"
    No. A **Customer** is the company you bill. A **Client** is a **Shipper / Receiver**: a pickup or delivery location. **Manage Clients** opens the Shipper / Receiver list. A customer only sees a Shipper / Receiver's deliveries when it is linked to it as a **consignee**. See [Shippers & Receivers](shippers-receivers.md).

### :fontawesome-solid-handshake: Someone mentioned a "broker". Which one?

!!! info "Solution"
    Check where they saw it. On a Dry Van order's **Broker** field or in **Order Expenses**, it is a name from **Manage Brokers**. In **Transport Company ( broker )** or on the Customers list, it is a customer flagged **Broker**. On a phone, it is a mobile user with the Broker role. See [Lookup Lists](lookup-lists.md).

### :fontawesome-solid-ship: What is MGT?

!!! info "Solution"
    **MGT** is Montreal Gateway Terminals, the container tracking source for the Racine and Cast terminals. On screens it is shown as **MGT (Racine/Cast)**. See [Container Tracking](container-tracking.md).

### :fontawesome-solid-eye-slash: A term in this glossary does not appear in my account

!!! info "Solution"
    Many terms belong to an add-on (Garage, Warehouse, Fuel Surcharge, Multi-Office, container tracking, Driver Login Links, tags) or to one shipment mode (intermodal or ground). If the add-on is off, its screens are hidden. Contact UTX support to ask about turning it on. See [Add-ons & Options](add-ons-and-options.md).

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Speaking the same language"
    - When you report a problem to UTX support, use the label exactly as the screen shows it (for example **App. Made** tab, **C.Status** column), and the order number.
    - Use **Special Note** for instructions drivers must see, and **Comments** for internal notes.
    - Name custom container statuses clearly so they do not look like built-in ones.
    - Open the **Legend** on the **Orders** page when you see a code or icon you do not recognise.

## Related Pages

- [Orders](orders.md)
- [Order Status Workflow](order-workflow.md)
- [Container Statuses](container-statuses.md)
- [User Roles & Permissions](user-roles.md)
- [Add-ons & Options](add-ons-and-options.md)
- [Navigation & Account](navigation-and-account.md)
