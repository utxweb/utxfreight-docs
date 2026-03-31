# Managing Customers

Create and manage the companies and contacts that place orders in UTX Freight.

## :fontawesome-solid-building: Overview

Every order in UTX Freight is placed on behalf of a **contact person** from a **customer company**. Before you can create orders, you need at least one customer with one contact.

- :fontawesome-solid-building: **Companies** are the billing entities — each has an address, default rate, and statement settings.
- :fontawesome-solid-user: **Contacts** (People) belong to a company — they receive notifications and can log in to place orders.
- :fontawesome-solid-tag: **Default tags** can be set per customer to automatically organize new orders.
- :fontawesome-solid-gas-pump: **Fuel surcharge exemptions** can be configured per customer.
- :fontawesome-solid-envelope: **Automatic statements** can be scheduled per customer.

<!-- TODO: Screenshot — The Customers list page showing the sidebar filters, search bar, and company list -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-arrow-right: **Customers** from the left menu.
2. Click **Add a new customer** at the top right.
3. Enter the **company name** (the only required field).
4. Click **Save Changes**.
5. Back on the list, find the company and click :fontawesome-solid-plus: **Add Person** to create a contact.

!!! tip "Tip"
    The contact will automatically receive an **invitation email**. If you don't want that yet, use a placeholder email like `name+1@utxfreight.ca` — you can change it later.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access Level |
|------|-------------|
| :fontawesome-solid-user-tie: **Admin / Manager** | Full access — create, edit, disable customers |
| :fontawesome-solid-headset: **Dispatch** | View customers, limited editing (if configured) |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | View customers |

**How to get there:**

- :fontawesome-solid-arrow-right: From the left menu, click **Customers**

---

## :fontawesome-solid-plus: Creating a Customer

1. Navigate to :fontawesome-solid-arrow-right: **Customers**.
2. Click **Add a new customer**.
3. Fill in the company details.
4. Click **Save Changes**.

### Company Information

| Field | Description |
|-------|-------------|
| **Name** | Company name (required) |
| **Web Address** | Company website |
| **Address 1 / Address 2** | Street address |
| **City** | City name |
| **State / Province** | Select from dropdown |
| **ZIP / Postal Code** | Postal or ZIP code |
| **Country** | Canada (CA) or United States (US) |
| **Office #** | Phone number |
| **Fax #** | Fax number |

<!-- TODO: Screenshot — The customer creation form showing the company information fields -->

### Email Settings

| Field | Description |
|-------|-------------|
| **Accountant Email** | Primary email for invoices and statements |
| **Accountant Email (CC)** | CC address for invoice emails (comma-separated for multiple) |

### Rate & Billing

| Field | Description |
|-------|-------------|
| **Service** | Service type for this customer |
| **Default Order Rate** | The default base rate applied to new orders for this customer |
| **Default Currency** | CAD or USD |
| **Default Statement Format** | Format for automatic statement emails |

---

## :fontawesome-solid-user-plus: Adding Contact People

Once a company exists, add contacts who will be associated with orders:

1. On the **Customers** list, find the company.
2. Click :fontawesome-solid-plus: **Add Person**.
3. Fill in **First name**, **Last name**, and **Email**.
4. Click **Save Changes**.

!!! warning "Invitation email"
    Adding a person triggers an automatic invitation email. The contact can then log in and place orders. Use a placeholder email if you want to delay this.

<!-- TODO: Screenshot — The Add Person form showing name and email fields -->

---

## :fontawesome-solid-pencil: Editing a Customer

1. On the **Customers** list, click the company name to expand it.
2. Click the **Edit customer** button.
3. Update the fields as needed.
4. Click **Save Changes**.

### Default Tag

If the **Tagging** addon is enabled, you can set a **Default Tag** for the customer. This tag is automatically applied to every new order created for this customer.

### Fuel Surcharge Exemption

If the **Fuel Surcharge** addon is enabled, you will see a **Fuel Surcharge** section on the edit form:

- Check **Exempt from Fuel Surcharge** to exclude this customer from all fuel charges.
- After saving, go to **Fuel Schedule** and click **Recalculate** on affected months to remove existing charges.

For full details, see [Fuel Surcharge — Exempting a Customer](fuel-surcharge.md#exempting-a-customer-from-fuel-surcharges).

### Automatic Statement Schedule

If the **Automatic Statements** addon is enabled, you can set the delivery day:

- On the customer edit form, select a day from the **Send statement on** dropdown.
- The statement email is sent automatically on that day if the customer has an outstanding balance.

For full details, see [Automatic Statements](automatic-statements.md).

---

## :fontawesome-solid-filter: Filtering the Customer List

The sidebar on the Customers page provides quick filters:

| Filter | What It Shows |
|--------|-------------|
| **All Active** | All enabled customer companies |
| **Disabled** | Deactivated companies (hidden from order forms) |
| **Brokers** | Companies flagged as brokers |

Use the **search box** at the top to filter by company name or contact name.

---

## :fontawesome-solid-file-export: Exporting Customers

Click the **Export** button to download the customer list as a **CSV** file. The export includes all active companies with their contact information.

---

## :fontawesome-solid-ban: Disabling a Customer

Disabled customers no longer appear in dropdown menus when creating orders. To disable:

1. Edit the customer.
2. Uncheck the **Active** checkbox.
3. Click **Save Changes**.

The customer and all their historical orders remain in the system — they are just hidden from new order forms.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### Customer doesn't appear in the order form dropdown

!!! info "Solution"
    The customer may be **disabled**. Go to **Customers**, use the **Disabled** filter in the sidebar, find the company, and re-enable it.

### Contact didn't receive the invitation email

!!! info "Solution"
    You can resend the invitation from the customer list. Find the contact and click the **Resend Invitation** link.

---

## Screenshots Needed

!!! info "Screenshots to capture"
    1. **Customers list page** — showing sidebar filters (All Active / Disabled / Brokers), search bar, and a few companies listed
    2. **Customer creation form** — showing company info fields, email settings, and rate section
    3. **Add Person form** — showing first name, last name, email fields
    4. **Customer edit form** — showing the Default Tag dropdown and Fuel Surcharge exemption checkbox (if visible)
