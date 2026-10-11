# Order Documents, POD & Signatures

Attach a scanned POD and other files to an order, open the printable POD, eBoL and confirmation sheets, email the POD to the client, and manage driver signatures.

## :fontawesome-solid-file-signature: Overview

Every order can carry proof of delivery and supporting paperwork. Office staff work with it from the **Orders** and **Dispatch** lists.

- :fontawesome-solid-file-pdf: **Scanned POD**: one PDF per order, uploaded in the **Documents** panel
- :fontawesome-solid-paperclip: **Additional documents**: any number of extra files per order, each tagged with a **Document Type**
- :fontawesome-solid-signature: **Signed POD**: built automatically from the signature the driver captures in the mobile app
- :fontawesome-solid-print: **Printable sheets**: **View POD** (or **View eBoL**), **View Internal POD** and **View Carrier Confirmation**
- :fontawesome-solid-envelope: **Send POD to client**: emails the signed or scanned POD to the delivery client
- :fontawesome-solid-eraser: **Remove Signature**: clears a delivery signature so the driver can sign again

<!-- TODO: Screenshot — Orders list showing the Email POD, POD and DOC columns with the envelope, red PDF, green signature and document icons -->

---

## :fontawesome-solid-bolt: Quick Start

**Attach a scanned POD or a document**

1. On the **Orders** list, open the order's action dropdown (the caret next to the status button) and click **Documents**.
2. Under **Order POD**, choose your file in **Signed POD file in .pdf format**.
3. To add other files, click **(+) Add document** under **Additional Documents**, choose the file and pick its type.
4. Click **Update Order**.

**Email the POD to the client**

1. In the **Email POD** column, click the envelope button on the order.
2. Check the **To** address, and add **Cc** or **Bcc** addresses if you need them.
3. Click **Send**.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Action | Admin | Manager | Dispatch / Customer Service | Accountant |
|--------|:-----:|:-------:|:---------------------------:|:----------:|
| Open the **Documents** panel, upload or delete files | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: ¹ |
| Open a document by its file name or icon | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: ¹ |
| Use the green **download** icon on a document | :fontawesome-solid-check: | — | — | — |
| See the **POD** and **DOC** columns on the Orders list | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: |
| **View POD** / **View eBoL** | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | — |
| **View Internal POD** (when enabled) | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | — |
| **View Carrier Confirmation** (Dry Van) | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | — |
| **Send POD to client** | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | — ² |
| **Remove Signature** | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: | :fontawesome-solid-check: ¹ |
| **Manage Document Types** | :fontawesome-solid-check: | :fontawesome-solid-check: | — | — |

¹ Accountants can work on orders in the standard setup. If your company has limited accountants to read-only access to orders, they cannot save changes in the **Documents** panel, cannot open the POD icons in the **POD** column, and do not see **Remove Signature**. The **Documents** link and the **DOC** icon are hidden from them, except on orders with the status **Dispatched**, where the panel opens but saving is refused.

² Accountants see the envelope in the **Email POD** column on the **Orders** list, but the send is refused and no email goes out. Sending runs through the **Dispatch** page, which only Admin, Manager, Dispatch and Customer Service can use. Ask one of them to send the POD.

Managers, dispatchers, customer service and accountants only see orders from their own office(s).

**How to get there:**

- **Documents panel**: **Orders** :fontawesome-solid-arrow-right: action dropdown on an order :fontawesome-solid-arrow-right: **Documents**. The **Dispatch** page has the same **Documents** link.
- **Document Types**: click your name at the top of the screen :fontawesome-solid-arrow-right: **Manage Document Types**.

---

## :fontawesome-solid-folder-open: The Documents Panel

Click **Documents** in an order's action dropdown. A window titled **Edit Order** *(order number - description - container)* opens with only the **Order Documents** section. It has two parts.

<!-- TODO: Screenshot — Edit Order window showing the Order Documents panel with Order POD and Additional Documents -->

### :fontawesome-solid-file-pdf: Order POD (scanned POD)

Use this for a POD that was signed on paper and scanned.

| Field | What it does |
|-------|--------------|
| **Signed POD file in .pdf format** | Choose the scanned POD file. Only a PDF is accepted. If you pick another file type the form shows *"Please select a file with a PDF extension."* |
| Hint under the field | Shown only when a PDF is already attached: *"Uploading a new file will replace the existing PDF: (file name)"*. An order holds one scanned POD, so a new upload replaces the old one. |
| **Check to remove the existing PDF** | Shown only when a PDF is already attached. Tick it and click **Update Order** to delete the scanned POD. |

Files can be up to 20 MB. A larger file is rejected and the update fails.

You can also attach or replace the scanned POD with the same **Signed POD file in .pdf format** field in two other places: the **Order Documents** section of the **Complete** window, and the **Administrative information** section of the full **Edit Order** page.

!!! warning "A scanned POD takes the order off the driver's list"
    Once a scanned POD is attached, the order is treated as signed and no longer shows as ready for signature in the driver app.

### :fontawesome-solid-paperclip: Additional Documents

Use this for anything else that belongs to the order: work orders, customs papers, photos, and so on.

1. Click **(+) Add document**. A new row appears.
2. In **Document**, choose the file.
3. In the type list (**- Select Type -**), pick a document type. Only **active** document types are listed.
4. Add more rows if needed, then click **Update Order**.

Any file type can be attached, up to 20 MB per file. A new row where no file was chosen is ignored when you save.

Saved documents show as a row with:

| Item | What it does |
|------|--------------|
| File icon | A PDF icon for `.pdf`, an image icon for `.jpg`, `.jpeg`, `.png` or `.gif`, and a plain file icon for anything else. Click it to open the file in a new tab. |
| File name | Click to open the file in a new tab. |
| Green download icon | Downloads the file. **Admin only**, see the warning below. |
| Size | The file size. |
| Type list | Change the document type, then click **Update Order**. |
| **(-) Delete** | Removes the row. The document is deleted when you click **Update Order**. |

!!! info "No type selected"
    If you save a document without choosing a type, it is saved with the type **Other**. If no **Other** type exists yet, UTX Freight creates it.

!!! warning "The download icon only works for Admins"
    The green download icon checks for document-management rights that only the **Admin** role has. Anyone else who clicks it is sent back to the dashboard with an access message. Click the **file name** or the **file icon** instead: those links open the file for everyone who can open the Documents panel.

---

## :fontawesome-solid-table-columns: POD, DOC and Email POD Columns

At the right end of each row, the **Orders** list has an **Email POD** column, then the order's action button, then the **POD** and **DOC** columns. The **Dispatch** page has only the **Email POD** column. The **Legend** button on the **Orders** list opens the **Orders Page Legend**, which also explains these icons under **Document Icons**.

### :fontawesome-solid-palette: Icon Guide

| Column | Icon | Meaning | Click to |
|--------|------|---------|----------|
| **POD** | :fontawesome-solid-file-pdf:{ .text-danger } Red PDF | A scanned POD is attached | Open the scanned PDF in a new tab |
| **POD** | :fontawesome-solid-file-signature:{ .text-success } Green signature | The order has a driver signature (delivery, pickup, or both) | Open the signed POD (tooltip *"Open signed POD"*) |
| **DOC** | :fontawesome-solid-file-lines:{ .text-danger } Red document | The order has at least one additional document | Open the **Documents** panel |
| **Email POD** | :fontawesome-solid-envelope: Envelope button | A POD can be sent, or was already sent | Open **Send POD to client** |

Both POD icons can show at once when an order has a scanned POD and a signature.

The **DOC** icon only shows to users who can edit the order. The **Email POD** column shows to Admin, Manager, Dispatch, Customer Service and Accountant (accountants cannot actually send, see **Send POD to Client** below).

---

## :fontawesome-solid-print: View POD, eBoL, Internal POD and Carrier Confirmation

These links are in the order's action dropdown and open in a new tab.

| Link | Shown when | Who sees it | What you get |
|------|-----------|-------------|--------------|
| **View POD** | Every order type except International Export | Admin, Manager, Dispatch, Customer Service | A PDF of the POD for printing, named *(Your company) POD #(order number).pdf*. The signature images and signature dates are left off. See [The POD sheet](#the-pod-sheet). |
| **View eBoL** | International Export orders (replaces **View POD**) | Admin, Manager, Dispatch, Customer Service | A PDF of the bill of lading for printing, named *(Your company) eBoL #(order number).pdf*. See [The eBoL sheet](#the-ebol-sheet-international-export). |
| **View Internal POD** | Only when the Internal POD option is turned on for your company. **Orders** list only. | Admin, Manager, Dispatch, Customer Service | A web page with the POD's order details plus blank boxes for internal billing notes. No signature boxes. See [The Internal POD](#the-internal-pod). |
| **View Carrier Confirmation** | Dry Van orders only. **Orders** list only. | Admin, Manager, Dispatch, Customer Service | A web page with the booking, package, pickup and delivery details to send to the carrier. See [The Carrier Confirmation sheet](#the-carrier-confirmation-sheet-dry-van). |

**View Internal POD** and **View Carrier Confirmation** open as web pages, not PDFs. Use your browser's print command to print them or save them as PDF.

!!! tip "Blank POD vs. signed POD"
    **View POD** gives you a sheet to print and take on the road, without signature images or signature dates. The green signature icon in the **POD** column opens the same layout as a web page, with the captured signature images and dates filled in.

<!-- TODO: Screenshot — View POD PDF for a Container Import order, showing the header, order blocks, container block and signature boxes -->

### :fontawesome-solid-file-lines: The POD sheet

The POD (from **View POD**, the green signature icon and the **Send POD to client** email) uses the same layout for Container Import, Container Export, Transfer and Dry Van orders. The bilingual French / English labels below are printed exactly as shown. Which blocks appear depends on the order type.

**Header**

- Your company logo, and your company address, **Tel:**, **Fax:** and web address.
- The title **Proof of delivery - Order #:** followed by the order number.

**Order blocks**

| Label on the sheet | What is printed | Order types |
|--------------------|-----------------|-------------|
| **DATE:** | The order date | All |
| **Customs Release** | **YES** or **NO** | Container Import only |
| *(top right)* | The order type in capitals, for example **IMPORT** or **DRY VAN** | All |
| **CONSIGNATAIRE / CONSIGNED TO:** | The order's customer | All |
| **REFERENCE NUMBER** | The order's reference number | All |
| **PICKUP FROM:** | The pickup company name | Dry Van only |
| **PICKUP DATE:** | The pickup date | Dry Van only |
| **ADRESSE / ADDRESS:**, **CONTACT PERSON:** | The pickup address (a **-** when empty) and pickup contact | Dry Van only |
| **VILLE / CITY:**, **CODE POSTAL / POSTAL CODE:** | The pickup city and postal code (a **-** when the postal code is empty) | Dry Van only |
| **SPECIAL INSTRUCTIONS**, **PO #** | The pickup comments and pickup P.O. number | Dry Van only |
| **LIVRE A / DELIVERY TO:** | The delivery company name | All |
| **DELIVERY DATE** | The delivery date | Dry Van only |
| **HAZARDOUS** | **YES** or **NO** | All types except Dry Van |
| **ADRESSE / ADDRESS:** | The delivery address (a **-** when empty) | All |
| **CONTACT PERSON:** | The delivery contact, plus the delivery email address when there is one | All |
| **ZONE** | The order's zone | All |
| **VILLE / CITY:**, **CODE POSTAL / POSTAL CODE:** | The delivery city and postal code (a **-** when the postal code is empty) | All |
| **SPECIAL INSTRUCTIONS** | The delivery comments | All |
| **PO #** | The delivery P.O. number | All |

**Container block**

| Label on the sheet | What is printed | Order types |
|--------------------|-----------------|-------------|
| **CONTAINER NUMBER / NUMERO DU CONTAINEUR** | The container number, in large capitals | Container Import, Container Export. On Transfer orders the heading shows as **Container Number** only. |
| **TRAILER NUMBER / NUMERO DE LA REMORQUE** | The trailer number, in large capitals | Dry Van |
| **EQUIPMENT TYPE** | The order's equipment type | Dry Van only |
| **PICK-UP LOCATION** | The pickup terminal | All types except Dry Van |
| **NUMERO DE PICK-UP** | The pickup number | Container Import |
| **BOOKING NUMBER** | The booking number | All types except Container Import and Dry Van |
| **RETURN** | The return terminal | Import and Export only |
| **INSTRUCTIONS FOR CONTAINER** | The return instructions | Import and Export only |
| **CHASSIS #** | The chassis (equipment) name. When the equipment is **Borrowed**, the chassis number is printed instead. | Import and Export only |
| **SIZE** | The container size | Import and Export only |
| **RV NUMBER** | The reservation number | Import and Export only |
| **POIDS / WEIGHT** | The weight (a **-** when empty) | Import and Export only |
| **VOLUME / CBM** | The volume | Import and Export only |
| **STEAMSHIP LINE** | The steamship line | Import and Export only |
| **OFF-HIRE** | **YES** or **NO** (blank when not set) | Container Import only |
| **SCALE** | The scale value (for example *Full*, *Empty* or *Both*) | Container Export only |
| **NUMERO DE SEAL / SEAL NUMBER** | The seal number | Import and Export only |
| **No DE COLIS / PKGS.** | The packages | Import and Export only |
| **TIME IN**, **TIME OUT** | The order's time in and time out when they are recorded, otherwise blank | All types except Dry Van |

**Signature boxes**

The signature area depends on the order type. On Dry Van, Container Export and Transfer orders, each signature box is followed by a row of labels: **SIGNATURE (AU COMPLET / IN FULL)** under the signature itself, **SIGNED BY** under the signee name, and a **DATE** label under the date. On Container Import orders the label row has only **SIGNATURE (AU COMPLET / IN FULL)** and the date label.

| Order type | Boxes, top to bottom |
|------------|----------------------|
| **Dry Van** | **PICKUP SIGNATURE (Shipper)** with **DATE ( PICKUP )**, then **DELIVERY SIGNATURE (Receiver)** with **DATE ( DELIVERY )**. The pickup signature and the delivery signature from the driver app fill these two boxes. |
| **Container Import** | One box: **DRIVER'S SIGNATURE** with **DATE ( RECU / RECEIVED )**. It holds the delivery signature. On the signed POD a **SIGNED BY** line with the signee name is added below. |
| **Container Export** and **Transfer** | **DROP SIGNATURE (Empty)** with **DATE ( DROP )**, then **PICKUP SIGNATURE (Full)** with **DATE ( PICKUP )**. The first box holds the pickup signature from the driver app, the second holds the delivery signature. |

On the blank **View POD** the signature images and dates are empty. The signee names still print on Dry Van, Container Export and Transfer orders if a signature was already captured.

**NIR line and footer**

- **NIR - CTQ#:** followed by your **NIR Number** is printed at the right of the first signature box. Set it in **Settings** (see [Application Settings](application-settings.md)). If **NIR Number** is empty, the label prints with nothing after it.
- The **POD Message** from **Settings** (shown as **POD Footer** on the Settings page) is printed in small text at the bottom of the sheet. Line breaks are kept.

!!! info "Remove Signature and the Export layout"
    **Remove Signature** clears the delivery signature. On a Dry Van POD that is the **DELIVERY SIGNATURE (Receiver)** box, on an Import POD the **DRIVER'S SIGNATURE** box, and on an Export or Transfer POD the **PICKUP SIGNATURE (Full)** box.

### :fontawesome-solid-file-shield: The Internal POD

**View Internal POD** is an office copy of the POD for recording extra charges by hand. It is only available when the Internal POD option is turned on for your company (see [Add-ons & Options](add-ons-and-options.md)).

What is the same as the POD:

- The title **Proof of delivery - Order #:** with the order number.
- The same order blocks (**DATE:**, **Customs Release**, **CONSIGNATAIRE / CONSIGNED TO:**, **REFERENCE NUMBER**, the Dry Van pickup blocks, **LIVRE A / DELIVERY TO:** and the delivery blocks).
- The same container block (container or trailer number, **PICK-UP LOCATION**, booking or pickup number, and for Import and Export, **RETURN**, **INSTRUCTIONS FOR CONTAINER**, **CHASSIS #**, **SIZE**, **RV NUMBER**, **POIDS / WEIGHT**, **VOLUME / CBM**, **STEAMSHIP LINE**, **OFF-HIRE** or **SCALE**, **NUMERO DE SEAL / SEAL NUMBER** and **No DE COLIS / PKGS.**).

What is different:

| Internal POD | Details |
|--------------|---------|
| Header | Your logo only. Your company address, phone, fax and web address are not printed. |
| **INTERNAL INFORMATION** and **RATE** | A block labelled **INTERNAL INFORMATION** with an empty **RATE** box. Not shown on Dry Van orders. |
| Blank boxes | Empty boxes to fill in by hand: **TIME IN**, **TIME OUT**, **TOTAL FOR TIME IN/OUT**, **EXTRA LEG / DEAD RUN**, **LIFT ON**, **LIFT OFF**, **CHASSIS DETENTION**, **STORAGE**, **HAZMAT**, **PORT FEE**, **REMANIFEST**, **EXTRA** and **TOTAL**. These are always blank, even when the order has a time in or time out recorded. |
| No signatures | No signature boxes, no **SIGNED BY** and no date boxes. |
| No NIR, no footer | The **NIR - CTQ#:** line and the **POD Message** footer are not printed. |

International Export orders also get this POD-style layout from **View Internal POD**, not the eBoL layout.

!!! warning "Keep the Internal POD in the office"
    The Internal POD is meant for internal billing notes. Do not give it to the receiver or email it to the client: use **View POD** or **Send POD to client** for that.

<!-- TODO: Screenshot — View Internal POD page showing the INTERNAL INFORMATION block and the blank charge boxes -->

### :fontawesome-solid-file-invoice: The eBoL sheet (International Export)

On International Export orders, **View eBoL** replaces **View POD**. It prints a bill of lading layout, not the POD layout. The green signature icon and the **Send POD to client** email use the same layout.

| Section on the sheet | What is printed |
|----------------------|-----------------|
| Heading | Your logo and the title **Bill of Landing** (spelled this way on the sheet). |
| **SHIPPER** | The order's customer: name, address, city, province and postal code, country, **Tel:**, and the email address of the customer user on the order. |
| **FREIGHT FORWARDER** | Your company: name, address, city, province and postal code, **Tel:** and **Fax:**. |
| **CONTRACT** | **Order** (the order number) and **Booking** (the booking number). |
| **CONSIGNEE** | The delivery company name, address, postal code and city, country and contact. |
| **OVERSEAS AGENT** | Empty. |
| **NOTIFY** | The word *CONSIGNEE*. |
| **INSURED VALUE** | Empty **WORDS:**, **FIGURES:** and **INSURANCE TYPE:** lines. |
| **OCEAN FREIGHT: PREPAID** | The labels **CLOSING**, **SAILING** and **ETA**, with no dates filled in. |
| **OCEAN VESSEL:** | The vessel name, then **ORIGIN:** and **PORT OF LOADING:** (the customer's city and country) and **PORT OF DISCHARGE:** and **DESTINATION:** (the delivery city and country), in capitals. |
| **MARKS AND NUMBERS** | The container number, and **SN#** with the seal number when there is one. |
| **NO.of PKGS.** | The packages. |
| **DESCRIPTION OF GOODS** | The goods description. |
| **GROSS WEIGHT** | The weight. |
| **VOLUME** | The volume (CBM). |
| Terms | Fixed bill of lading terms text. |
| **SPECIAL INSTRUCTIONS** | The order's **Comments**. |
| **AUTHORIZED SIGNATURE** | A fixed "dated in" place line, the date the order was created (YYYY-MM-DD), and a blank **SIGNATURE:** line. |
| Footer | A fixed disclaimer that you act as agents only. |

The eBoL has no driver signature boxes, no **NIR - CTQ#:** line and no **POD Message** footer.

!!! warning "The signed eBoL has no signature on it"
    The eBoL layout never shows the driver's signature image, signee name or signature date. The signed version (green signature icon) and the *eBoL Signed* PDF attached to the POD email look the same as **View eBoL**.

<!-- TODO: Screenshot — View eBoL PDF for an International Export order -->

### :fontawesome-solid-truck-ramp-box: The Carrier Confirmation sheet (Dry Van)

**View Carrier Confirmation** prints the delivery instructions for the carrier that moves a Dry Van order.

| Section on the sheet | What is printed |
|----------------------|-----------------|
| Header (left) | Your logo, your company name in capitals, address and **Tel:**. |
| Header (right) | **Shipment:** (the order's reference number), **Transport Booking:** (the trailer / container number) and **Delivery Date:** (the delivery date). |
| **DELIVERY INSTRUCTIONS** | The sheet title. |
| **BOOKING DETAILS** | Two columns: **TRANSPORT COMPANY** and **ROAD CARRIER REGISTRATION**. |
| **TRANSPORT COMPANY** | The order's transport company (the **Transport Company ( broker )** field, **Transport Company / Broker** in Quick Edit) in capitals, with address and **Tel:**. If the order has no transport company, your own company is printed. |
| **ROAD CARRIER REGISTRATION** | Empty. |
| **CHARGES** | One line, **Delivery Cartage**, with the order total in your company's default currency. |
| **CONSIGNEE** | The order's customer name. |
| **PACKAGES DETAILS** | **PACKAGES** and **WEIGHT**, then a **Goods Description:** line. |
| **INSTRUCTIONS DETAILS** | **1- PICKUP**: the pickup company, address, city and postal code (a **-** when the address or postal code is empty), then **Contact:** and **Notes:** (the pickup comments). **2- DELIVERY**: the same for the delivery address, with the delivery comments as **Notes:**. |
| **SPECIAL INSTRUCTIONS** | The order's **Special Note** (see [Special Note](order-form.md#special-note)). |
| Footer | **THANK YOU FOR YOUR SUPPORT**. |

!!! info "Fixed text on some accounts"
    On some accounts, UTX has set up the Carrier Confirmation with fixed text: the header logo and company name, and the footer (for example payment terms and a contact name and email), can show fixed wording set up by UTX for the account instead of your own company details. Contact UTX support if your sheet shows text you want changed.

!!! warning "The order total is printed"
    The **CHARGES** section shows the order total as **Delivery Cartage**. Check that this is the amount you want the carrier to see before you send the sheet.

<!-- TODO: Screenshot — View Carrier Confirmation page for a Dry Van order -->


---

## :fontawesome-solid-envelope: Send POD to Client

**Who:** Admin, Manager, Dispatch and Customer Service. Accountants see the envelope on the **Orders** list, but their send is refused and no email goes out.

### When the envelope appears

The envelope button shows in the **Email POD** column when the order has at least one of:

- a delivery signature
- a pickup signature
- a scanned POD
- a previous POD email attempt

### Sending

1. Click the envelope. The **Send POD to client** window opens.
2. Review the fields:

    | Field | Prefilled with | Required |
    |-------|----------------|:--------:|
    | **To** | The delivery client's email address | Yes |
    | **Cc** | Empty | No |
    | **Bcc** | Empty | No |
    | **Subject** | *(Your company) Order # (order number) Completed* | Yes |

    **To**, **Cc** and **Bcc** accept several addresses separated by commas or semicolons.

3. Click **Send**. A spinner replaces the envelope while the email goes out, then a message confirms **POD Sent!** or explains the failure.

<!-- TODO: Screenshot — Send POD to client window with To, Cc, Bcc and Subject -->

!!! warning "Known issue: the Subject field is ignored"
    Whatever you type in **Subject**, the email always goes out with the subject **(Your company) Order #(order number) Delivered**. The field still has to be filled in for the form to submit.

!!! info "Cc and Bcc are not cleared between sends"
    The window keeps what you typed in **Cc** and **Bcc** until you reload the page. Check them before sending the next order's POD.

### What the client receives

- **From:** your company name and the **Accountant Email** from **Settings**.
- **Attachment** (one file):
    - If the order has a delivery or pickup signature: a signed POD PDF named *(Your company) POD Signed #(order number).pdf* (*eBoL Signed* for International Export).
    - Otherwise: the scanned POD PDF, under its original file name.
    - If the order has neither (for example, the scanned POD was removed after an earlier send), the email goes out with no attachment.
- **Body:** the heading *New proof of delivery from (your company)*, followed by the order number, order type, client name and reference number. Import and Export orders also show the container number and pickup terminal; other order types show the pickup company, pickup address and delivery address.

### Envelope colours

| Colour | Meaning | Tooltip |
|--------|---------|---------|
| :fontawesome-solid-circle:{ .text-primary } **Blue** | Never sent successfully | *Send POD to client* |
| :fontawesome-solid-circle:{ .text-success } **Green** | The last attempt was delivered | *Last email delivered (date and time)* |
| :fontawesome-solid-circle:{ .text-danger } **Red** | A send succeeded before, but the latest attempt failed | *Last email delivered (date and time)*, the date of the last **successful** send |

!!! info "A failed first send stays blue"
    The date only updates on a successful send. If the very first attempt fails, the button stays blue with the tooltip *Send POD to client*. Watch for the **Sending POD Failed!** message.

You can send the POD again at any time. Each successful send updates the date in the tooltip.

---

## :fontawesome-solid-signature: Signatures in the Office

Drivers capture signatures in the mobile app (see [Driver Workflow](driver-workflow.md)). Office staff see them in these places:

- **Driver name colour**: the **Orders** list has two driver columns (**Delivery Driver** and **Return Driver** when your company runs container work, **Pickup Driver** and **Delivery Driver** otherwise). In the first one, a **green** driver name means the order is ready for its first signature in the driver app. In the second one, green means it is ready for the next step (the return or the delivery). **Red** means it is not ready, for example because it is already signed, has a scanned POD, or its status or container status does not allow it.
- **Signature date**: shown in grey under the driver's name once that signature is captured.
- **POD column**: the green signature icon opens the signed POD with the signature image, signee name and date.
- **Email POD column**: the envelope appears as soon as a signature exists.

Some order types, such as Dry Van, can have two signatures: one at pickup and one at delivery.

### :fontawesome-solid-eraser: Remove Signature

Use this when a driver collected the wrong signature, or the signature must be taken again.

**Remove Signature** shows in the action dropdown on both the **Orders** and **Dispatch** pages only when **all** of these are true:

- the order has a **delivery** signature
- the order status is **not Completed**
- you can manage the order

To remove it:

1. Open the order's action dropdown and click **Remove Signature**.
2. In the warning *"Are you sure you want to remove the signature, this is a destructive action and cannot be undone!"*, click **CLEAR THE SIGNATURE**.
3. The message **Order Signature Reset!** confirms it.

What it clears:

- the delivery signature image
- the signee name
- the signature date

What it does **not** touch:

- the **pickup** signature
- a scanned POD
- the order status

Once cleared, the driver can capture the delivery signature again, as long as nothing else blocks it: no scanned POD is attached and the order's status and container status still allow it. Check the driver name colour on the **Orders** list to confirm.

!!! danger "This cannot be undone"
    The signature image is deleted permanently. The only way to get a signature back is to have the driver sign again.

!!! info "Completed orders"
    **Remove Signature** is hidden on Completed orders. Move the order back first with **Go Back 1 Step** or **Reset Order to New** (see [Order Workflow](order-workflow.md)).

---

## :fontawesome-solid-tags: Document Types

Document types label the files in **Additional Documents** (for example *Work Order* or *Customs*).

**Who:** Admin and Manager.
**Where:** click your name at the top of the screen :fontawesome-solid-arrow-right: **Manage Document Types**.

The list shows **Name**, **Orders** and **Active** for the current office. Use **Add a new Document Type** to create one, or **Actions** :fontawesome-solid-arrow-right: **Edit** to change one. **View History** shows past changes.

| Field | Description |
|-------|-------------|
| **Name** | The name shown in the type list on the Documents panel. Required. |
| **Office** | The office the document type belongs to. Required. |
| **Active** | *"Only active document types will be visible for new documents."* Untick it to retire a type without losing it on documents that already use it. |

Click **Save Changes** to save, or **Cancel** to go back.

!!! info "Document types cannot be deleted"
    There is no working **Delete** option for document types. To stop using one, untick **Active**. The **Orders** column always shows **-**; it does not count documents.

!!! tip "The type list on the Documents panel"
    The Documents panel lists all **active** document types, sorted by name. It is not limited to the current office: active types from every office appear.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-envelope: I don't see the envelope button on an order

!!! info "Solution"
    The envelope only shows once the order has a signature, a scanned POD, or a previous email attempt. Upload the scanned POD in **Documents**, or wait for the driver to sign. Also check your role: the **Email POD** column is for Admin, Manager, Dispatch, Customer Service and Accountant.

### :fontawesome-solid-user-lock: I'm an accountant and the POD email never goes out

!!! info "Solution"
    Sending the POD is limited to Admin, Manager, Dispatch and Customer Service. Accountants see the envelope, but the send is refused. Ask one of those users to send it.

### :fontawesome-solid-heading: The client received a different subject than the one I typed

!!! info "Solution"
    This is a known issue. The subject is always *(Your company) Order #(order number) Delivered*, whatever is in the **Subject** field.

### :fontawesome-solid-triangle-exclamation: "The POD was not sent. Please correct the email address and try again."

!!! info "Solution"
    One of the addresses is not valid. Check **To**, **Cc** and **Bcc**: separate several addresses with commas or semicolons. If the addresses are correct, ask an Admin to check that **Invoice Default CC Address** is filled in on the **Settings** page; the POD form also needs it to validate.

### :fontawesome-solid-download: Clicking the green download icon sends me to the dashboard

!!! info "Solution"
    The download icon works for Admins only. Click the document's **file name** or **file icon** instead to open it.

### :fontawesome-solid-file-pdf: The client got the signed POD, not the scanned one

!!! info "Solution"
    When an order has both a signature and a scanned POD, the email attaches only the signed POD. To send the scanned copy, attach it to your own email from the **POD** column (red PDF icon).

### :fontawesome-solid-eraser: Remove Signature is missing from the dropdown

!!! info "Solution"
    It only shows when the order has a **delivery** signature and is not **Completed**. A pickup-only signature cannot be removed this way.

### :fontawesome-solid-list: My new document type is not in the list

!!! info "Solution"
    Make sure **Active** is ticked on the document type, then reopen the Documents panel.

### :fontawesome-solid-hashtag: The POD shows "NIR - CTQ#:" with no number

!!! info "Solution"
    The number comes from **NIR Number** on the **Settings** page. Ask an Admin to fill it in (see [Application Settings](application-settings.md)). The same page holds the **POD Message** printed at the bottom of the POD.

### :fontawesome-solid-file-shield: I don't see View Internal POD

!!! info "Solution"
    **View Internal POD** only appears when the Internal POD option is turned on for your company, and only on the **Orders** list for Admin, Manager, Dispatch and Customer Service. Contact UTX to turn the option on (see [Add-ons & Options](add-ons-and-options.md)).

### :fontawesome-solid-signature: The signed eBoL has no signature

!!! info "Solution"
    This is how the eBoL layout works: it has no driver signature boxes, so the signed version looks the same as **View eBoL**. The signature is still stored on the order and shows as the green signature icon in the **POD** column.

---

## :fontawesome-solid-lightbulb: Best Practices

!!! tip "Keep POD paperwork tidy"
    - Upload scanned PODs as soon as the paper comes back, so the order leaves the driver's list and the envelope becomes available.
    - Always pick a document type. Untyped files all end up as **Other**.
    - Retire old document types with **Active** rather than renaming them.
    - Check **Cc** and **Bcc** before each POD email. They carry over from the previous send.
    - Check the envelope colour after sending: green means delivered, red means the last attempt failed.
