# Auto Orders (Document Upload)

Upload a delivery order or cartage document and let UTX Freight read it for you, then review the extracted details and turn them into a new order.

## :fontawesome-solid-wand-magic-sparkles: Overview

**Auto Orders** is an optional add-on, currently in beta. It reads a document you upload, picks out the order details, and lets you check them before an order is created. Nothing is created automatically: every order is saved by a person from the review window.

- :fontawesome-solid-upload: **Upload**: a button in the header of the **Orders** page opens the **Upload a Document** window.
- :fontawesome-solid-cogs: **Background processing**: the document is read in the background. While this happens it sits in the **Processing** tab.
- :fontawesome-solid-eye: **Need Review**: once the details are extracted, the document moves to the **Need Review** tab with the extracted values in the table.
- :fontawesome-solid-file-pen: **Review window**: shows the document on the left and a **Create Order** form on the right, pre-filled with what was found. Click a field label to highlight where the value was read on the document.
- :fontawesome-solid-check: **Completed**: once you save, the order is created with status **New** and the document moves to the **Completed** tab, with a **View Order** button.
- :fontawesome-solid-building: **Recognised layouts**: FedEx Cartage, FedEx In-Bond, Delmar, Kerry Logistics and Kuehne+Nagel documents are read field by field (each layout fills a different set of fields). Any other document gets a generic read that only looks for the container number.

!!! warning "Beta feature"
    Auto Orders is in beta. Always check every value in the review window before you save. The text recognition can misread characters, and fields it cannot find are left empty.

<!-- TODO: Screenshot — The Orders page with the AUTO ORDERS card (Processing / Need Review / Completed) and the Upload button in the header. Use demo data only. -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Orders** and click **Upload** in the header (next to **Create a new order**).
2. In **Upload a Document**, choose the file and click **Submit**. You land on the **Processing** tab.
3. Wait for the document to be read. Then open the **Need Review** tab in the **AUTO ORDERS** card.
4. Click **Review** on the document's row.
5. Check and correct the fields in the **Create Order** tab. Make sure **Place the order on behalf of** has a customer.
6. Click **Save and Next** to create the order and open the next document, or **Save and Close** to create the order and close the window.
7. Open the new order and complete it (dates, locations and other details).

---

## :fontawesome-solid-shield-halved: Access & Permissions

The add-on must be enabled on your account by UTX. When it is off, the **Upload** button and the **AUTO ORDERS** card are not shown.

| Role | Upload, tabs and review window | Save an order from the review window |
|------|--------|--------|
| :fontawesome-solid-user-shield: **Admin** | Yes | Yes |
| :fontawesome-solid-user-tie: **Manager** | Yes | Yes |
| :fontawesome-solid-headset: **Dispatch** | Yes | Yes |
| :fontawesome-solid-file-invoice-dollar: **Accountant**, **Customer**, **Driver**, **Garage**, **Warehouse** | No | No |

**Refresh**, **Reprocess All**, **Reprocess** and the **Debug** tab in the review window are UTX support tools. They are only visible to UTX support, not to your users.

!!! danger "Account suspension"
    When your account is suspended, the **Upload** button turns red with a :fontawesome-solid-ban: icon. Clicking it opens **Account Suspended - Action Blocked** (**Order Creation Disabled**) instead of the upload window. **Create a new order** is blocked the same way. See [Orders](orders.md).

---

## :fontawesome-solid-upload: Uploading a Document

1. Go to :fontawesome-solid-arrow-right: **Orders**.
2. Click **Upload** (:fontawesome-solid-upload:) in the header, to the right of **Create a new order**.
3. The **Upload a Document** window opens. Click the **File** field and choose your document.
4. Click **Submit**. Click **Close** to cancel.

When the upload succeeds, the window closes and the **Orders** page opens on the **Processing** tab, where your document now appears.

**Files:** use a PDF, JPG or PNG file of up to 20 MB. A file larger than 20 MB is not accepted. Only the **first page** of the document is read and shown in the review window, so put the delivery order on page 1.

### Upload messages

| Message (under **File**) | What it means | What to do |
|------|------|------|
| **File required** | You clicked **Submit** without choosing a file. | Choose a file and submit again. |
| **This document has already been uploaded** | The exact same file was uploaded to Auto Orders before. Each file can only be uploaded once. | Look for it in **Processing**, **Need Review** or **Completed**. A re-scanned or edited copy counts as a different file. |
| A message ending in **submission failed.** | The file was saved but could not be sent for reading. No document is added to the tabs. | Try again later. If it keeps failing, contact UTX support. |

---

## :fontawesome-solid-table-list: The AUTO ORDERS Card

On the **Orders** page, the filter area shows an **AUTO ORDERS** card with three tabs. Each tab lists documents, newest first, with page numbers at the bottom when there are many.

| Tab | Icon | Shows documents that are | Row action |
|-----|------|------|------|
| **Processing** | :fontawesome-solid-cogs: (red) | Uploaded and still being read | A moving progress bar. No action yet. |
| **Need Review** | :fontawesome-solid-eye: (blue) | Read and waiting for someone to check them | **Review** |
| **Completed** | :fontawesome-solid-check: (green) | Saved as an order | **View** and **View Order** |

The same icon appears in the **Status** column of each row.

### Table columns

| Column | What it shows |
|------|------|
| **Status** | The tab icon for the document's current stage |
| **File** | The uploaded file's name |
| **Customer** | The customer recognised from the document layout (see [Recognised Document Layouts](#recognised-document-layouts)). **N/A** when no customer was recognised. |
| **Reference #** | The reference number read from the document |
| **Client** | The shipper/receiver matched from the delivery address |
| **Container #** | The container number read from the document. A red **!** (:fontawesome-solid-exclamation:) appears on **Need Review** rows when the number has an invalid format, when no container number was found, or when the number already exists on an order. |
| **Seal #** | The seal number read from the document |
| **Pickup Terminal** | The pickup terminal matched from the document |
| **Container Size** | The container size matched from the document |
| **Steamship Line** | The carrier read from the document (FedEx Cartage and Delmar layouts only). Shown for information only, it is not copied to the order. |
| **Weight** | The weight read from the document |

Empty cells mean the value was not found.

**View Order** on a **Completed** row opens the **Orders** list searched by the new order's number (Order#).

<!-- TODO: Screenshot — The Need Review tab with a few demo rows, including one with the red ! next to the container number. No real customer or container data. -->

---

## :fontawesome-solid-clock: Background Processing

Reading a document is not instant. After you upload:

1. The document is sent for text recognition and appears in **Processing**.
2. A scheduled check runs in the background at regular intervals. When it finds that the document has been read, it extracts the order details and moves the document to **Need Review**.

Because the move to **Need Review** waits for the next scheduled check, there is a delay between the upload and the moment the document is ready. Reload the **Need Review** tab after a while to see it.

!!! info "Nothing to do in Processing"
    While a document is in **Processing** you cannot open or edit it. If a document stays in **Processing** for a long time, contact UTX support.

---

## :fontawesome-solid-file-pen: Reviewing a Document

On the **Need Review** tab, click **Review** on a row. On the **Completed** tab, the same button is labelled **View**. The **Review** window opens full screen.

### The document image

The left side shows the first page of the uploaded document. On the right, each field in the form has a grey label (**Ref #**, **Cont #**, **Terminal**, **Seal #**, **Weight**, **Cont Size**, **Delivery**). Click a label and the place on the document where that value was found is highlighted in yellow. If the value was not found on the document, no new highlight is drawn. The highlight shows where the original value was read; it does not follow your edits.

### The Create Order tab

The form is pre-filled with the extracted values. Correct anything that is wrong or missing.

| Field | Pre-filled from | Notes |
|------|------|------|
| **Job type** (radio buttons) | Always **Import** | The order types enabled on your account (**Import**, **Export**, **Transfer**, **Dry Van**, **International Export**). Change it if needed. |
| **Place the order on behalf of** | The recognised customer's **Default user** | Required. Lists the active logins of the recognised customer. If no customer was recognised, or that customer has no active logins, it lists all active logins of active intermodal customers. Unless your account uses multiple offices, the list is limited to your current office. Hint: *You can create an order on behalf of any customer.* |
| **Ref #** | The document's reference number | Reference Number |
| **Cont #** | The container number found on the document | Container Number. Required to save. Checked for format and duplicates (see below). |
| **Terminal** | The pickup location on the document | Pickup terminal. Required to save an **Import** or **Export** order. Recognised automatically only when the pickup text contains **CN** (or **CANADIAN NATIONAL**), **CP**, **Racine** or **Termont**. Otherwise pick it from the list of your office's active terminals. |
| **Seal #** | The document's seal number | Seal Number |
| **Weight** | The document's weight | Weight |
| **Cont Size** | The container size on the document (Delmar and Kuehne+Nagel layouts only) | Container size. Only a fixed list of spellings is translated to a container size name (for example `40 REEFER` to **40RE**, `20 STD` to **20**, `53 VAN` to **53**, `45 HQ` to **45HC**), and that container size must exist in your account. Any other spelling leaves the field empty. |
| **Delivery** | The delivery address's postal code | The delivery shipper/receiver. It is matched by **postal code** against your [Shippers & Receivers](shippers-receivers.md). If none matches, it stays empty. |

The **New Client** button below **Delivery** lets you add a missing shipper/receiver without leaving the window (see [New Client](#new-client-quick-create)).

### Container number warnings

When a **Need Review** document opens, the container number is checked. It is checked again each time you change **Cont #**. A red message appears under the field:

| Message | Meaning |
|------|------|
| **Invalid container number format** | The number is not 4 letters followed by 6 or 7 digits, or no container number was found. |
| **Duplicate container number** | An order with this container number already exists (in any status). |

If a warning is showing when you save, a confirmation asks *Invalid container number format, are you sure you want to create the order?* or *Duplicate container number, are you sure you want to create the order?*. Click **OK** to create the order anyway, or **Cancel** to go back and fix it.

!!! tip "Common misreads"
    For generic documents and the FedEx Cartage and Kerry Logistics layouts, the reader corrects `0` read in place of `O` in the 4-letter prefix and `?` read in place of `3` in the digits. Other mix-ups (for example `1` and `I`) can still happen, and the Delmar and FedEx In-Bond layouts are not corrected at all, so always compare the container number with the document.

### Buttons

| Button | What it does |
|------|------|
| **Save and Next** | Creates the order and opens the next document waiting in **Need Review**. If no other document is waiting, the window closes. |
| **Skip** | Does not save anything. Opens the next document waiting in **Need Review** (the next one uploaded after the current document). The skipped document stays in **Need Review**. After the newest document, it starts again from the oldest one, so if only one document is waiting, the same document opens again. |
| **Save and Close** | Creates the order and closes the window. The row moves to **Completed**. |
| **Close** | Closes the window without saving. |

**Save and Next** and **Save and Close** work the same way: **Save and Next** opens the next document waiting in **Need Review** after the current one, starting again from the oldest when it reaches the newest.

When you open a document from the **Completed** tab (**View**), **Save and Next** and **Save and Close** are hidden, since it already has an order. **Skip** and **Close** are still shown; **Skip** opens a document waiting in **Need Review**.

When you save:

- The order is created in your current office with status **New**, using the values in the form. As with any new order, the order date is set to today, the customer's default order rate and the terminal fee charge are applied when they are set up, and the new order notification is sent (see [Notifications & Emails](notifications-and-emails.md)). Continue with it as with any other order (see [Order Workflow](order-workflow.md)).
- The document moves to **Completed** and is linked to the order (**View Order**).
- If **Place the order on behalf of** is empty, the form shows **User required** and nothing is saved. Other missing values (an empty **Cont #**, or an empty **Terminal** on an **Import** or **Export** order) are shown on the form the same way.

!!! info "The uploaded file is not attached to the order"
    The document you uploaded stays with Auto Orders. It is not added to the new order's documents. If you need it on the order, upload it there (see [Order Documents & POD](order-documents-and-pod.md)).

!!! warning "Only these fields are copied"
    The new order only gets **Job type**, **Place the order on behalf of**, **Ref #**, **Cont #**, **Terminal**, **Seal #**, **Weight** and **Cont Size**. Dates, delivery and return locations and everything else are not filled in. Open the order afterwards to complete it (see [Order Form](order-form.md)).

<!-- TODO: Screenshot — The Review window with a demo document on the left, a yellow highlight on the container number, and the Create Order tab on the right showing the Duplicate container number warning and the Save and Next / Skip / Save and Close / Close buttons. Demo data only. -->

---

## :fontawesome-solid-user-plus: New Client (Quick Create)

If the delivery shipper/receiver does not exist yet:

1. In the review window, click **New Client** under **Delivery**.
2. The **Shipper / Receiver Information** window opens. Fill in:

    | Field | Notes |
    |------|------|
    | **Company Name** | Required |
    | **Office** | Required. One of your offices |
    | **Address** | Street address |
    | **City (Must exist)** | Pick from the active cities of your current office. Add missing cities first (see [Zones & Cities](zones-and-cities.md)). |
    | **Postal Code** | Enter it so future documents with this postal code are matched automatically |
    | **Contact Info** | Optional |
    | **Email** | Optional |

3. Click **Create**. The window closes and the new shipper/receiver is selected in **Delivery**.

If something is missing or wrong, the window stays open and shows the error. Click **Close** to cancel.

---

## :fontawesome-solid-building: Recognised Document Layouts

UTX Freight recognises some document layouts by lines of text on page 1 and reads them field by field. For each one, the **Customer** is the first customer in your account whose company name contains the provider's name (not case-sensitive).

| Layout | Recognised by | Customer matched by name containing |
|------|------|------|
| **FedEx Cartage** | FedEx Trade Networks cartage slip (French company heading plus the line **CARTAGE SLIP**) | `FEDEX` |
| **FedEx In-Bond** | FedEx Trade Networks in-bond document (English company heading plus the line **IN BOND / EN DOUANE**) | `FEDEX` |
| **Delmar** | The line **DELIVERY INSTRUCTIONS** plus the Delmar web address | `DELMAR` |
| **Kerry Logistics** | Kerry Logistics (Canada) company heading plus the Kerry Logistics web address | `KERRY LOGISTICS` |
| **Kuehne+Nagel** | **KUEHNE** and **NAGEL** each on its own line | `KUEHNE` followed by `NAGEL` |
| **Generic** | Any other document | No customer |

Each layout fills a different set of fields. Fields left blank in this table start empty for that layout.

| Layout | Ref # | Cont # | Terminal | Seal # | Weight | Cont Size | Delivery | Steamship Line |
|------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **FedEx Cartage** | Yes | Yes | Yes | | | | Yes (importer) | Yes |
| **FedEx In-Bond** | Yes | Yes | Yes | Yes | Yes | | Yes (consignee) | |
| **Delmar** | Yes | Yes | Yes | Yes | Yes | Yes | Yes (deliver to) | Yes |
| **Kerry Logistics** | | Yes | Yes | | Yes | | Yes (client) | |
| **Kuehne+Nagel** | Yes | Yes | Yes | | Yes | Yes | Yes | |
| **Generic** | | Yes | | | | | | |

**Delivery** is only filled when a postal code is found in the delivery address and a shipper/receiver with that postal code exists.

For a recognised layout, **Place the order on behalf of** is pre-filled with that customer's **Default user**.

!!! tip "Set the Default user"
    For recognised providers, open the customer in **Customers**, edit it, and choose a login in **Default user**. The field appears on the edit form of existing intermodal customers and lists that customer's active logins. Without it, **Place the order on behalf of** starts empty and you pick the login yourself. See [Managing Customers](managing-customers.md).

**Generic documents:** only the container number is looked for (the first word shaped like a container number: 4 letters followed by 7 digits). All other fields start empty. **Customer** shows **N/A**, and **Place the order on behalf of** lists all active customer logins.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-hourglass-half: My document is still in Processing

!!! info "Solution"
    Documents move to **Need Review** at the next scheduled background check, so a short wait is normal. Reload the **Need Review** tab later. If a document stays in **Processing** for a long time, contact UTX support. They can re-run the check.

### :fontawesome-solid-copy: "This document has already been uploaded"

!!! info "Solution"
    The same file was uploaded before. Find it in **Processing** (still being read), **Need Review** (not yet saved) or **Completed** (already an order). Each file can only be uploaded once.

### :fontawesome-solid-ban: I clicked Save and Next but no order was created

!!! info "Solution"
    Check that **Place the order on behalf of** is filled in: when it is empty, the form shows **User required**. **Cont #** must also be filled in, and **Terminal** is required on an **Import** or **Export** order.

### :fontawesome-solid-user-slash: Place the order on behalf of is empty

!!! info "Solution"
    The document was not a recognised layout, or the recognised customer has no **Default user**. Pick the customer login from the list. To pre-fill it next time, set **Default user** on the customer.

### :fontawesome-solid-location-dot: Delivery is empty

!!! info "Solution"
    No shipper/receiver in your account has the postal code read from the document, or the layout is not recognised. Pick the shipper/receiver from the list, or click **New Client** to create it with the correct **Postal Code**.

### :fontawesome-solid-exclamation: Why is there a red ! next to the container number?

!!! info "Solution"
    The container number is either missing, not in a valid format (4 letters followed by 6 or 7 digits), or already used on an existing order. Open the document with **Review** and compare **Cont #** with the document. You can still save after confirming the warning, but **Cont #** cannot be empty.

### :fontawesome-solid-file: Only part of my document was read

!!! info "Solution"
    Only the first page is read. Make sure the delivery order is on page 1 of the file.

### :fontawesome-solid-eye-slash: I don't see the Upload button or the AUTO ORDERS card

!!! info "Solution"
    The Auto Orders add-on is not enabled on your account, or your role is not Admin, Manager or Dispatch. Contact UTX to enable the add-on (see [Add-ons & Options](add-ons-and-options.md)).

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Getting the most out of Auto Orders"
    - Set a **Default user** on each recognised provider's customer so the customer is pre-filled.
    - Keep postal codes on your [Shippers & Receivers](shippers-receivers.md) up to date. That is how **Delivery** is matched.
    - Click each field label in the review window to check the value against the document before saving.
    - Never ignore a **Duplicate container number** warning without checking the existing order first.
    - After saving, open the new order and complete the dates, rates and locations.
