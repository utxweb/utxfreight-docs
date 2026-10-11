# Expenses & Checks

Review what you owe drivers, brokers and other payees, and record the checks you write to pay them.

## :fontawesome-solid-money-bill: Overview

Expenses and checks are the "money out" side of UTX Freight. Each one has its own page in the left sidebar:

- :fontawesome-solid-list: **Expenses** -- a list of every expense line entered in the **Order Expenses** panel of your orders (driver pay, broker fees, other costs). You can filter by payee, order status and payment status, and see which check paid each line.
- :fontawesome-solid-money-check: **Checks** -- a list of the checks you issued. Each check records a vendor invoice (amount, number, date) and the payee's name and address.
- :fontawesome-solid-link: **Linking** -- when **Check Expenses** is enabled for your edition, you tick expense lines on a check. Saving the check marks those lines as **Paid** on the Expenses page.
- :fontawesome-solid-print: **Printing** -- each check has a **Print** button that opens a printable check layout in a new tab.
- :fontawesome-solid-address-book: **Vendors** -- every time you save a check, the payee's name and address are saved as a vendor, so you can pick them again on the next check. There is no separate vendor page.

Expenses are entered on the orders themselves, not on these pages. See [Order Rates, Charges & Expenses](order-charges-and-expenses.md#order-expenses).

<!-- TODO: Screenshot — The Expenses page with the Filters box, the list of expense lines, Paid icons and the TOTAL row -->

---

## :fontawesome-solid-bolt: Quick Start

Already familiar with the feature? Here is the fastest path to pay a driver or broker:

1. Add the expense on the order, in **Order Expenses**, and complete the order.
2. Click **Expenses** in the left sidebar. Unpaid lines are shown by default.
3. Pick the payee in **Select a filter** and click **Search** to see what you owe them.
4. Click **Checks** in the left sidebar, then **Add a new Check**.
5. Fill in **Issue date**, **Check Number**, the **Vendor Invoice Information** and the payee under **Vendor Information** (type a few letters in **Search for a vendor** to reuse a saved one).
6. Under **Check Expenses**, tick the expense lines this check pays.
7. Click **Save Changes**, then click **Print** on the check's row.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Expenses page | Checks |
| ---- | ---- | ---- |
| :fontawesome-solid-user-shield: **Admin** | Yes | Yes (view, add, edit, delete, print, history) |
| :fontawesome-solid-user-tie: **Manager** | No sidebar link | Yes, when your edition allows managers to manage checks |
| :fontawesome-solid-calculator: **Accountant** | No sidebar link | Yes, when your edition allows accountants to manage checks |
| :fontawesome-solid-user: **All other roles** | No sidebar link | No |

- The **Expenses** link appears in the left sidebar for **Admin** users only.
- The **Checks** link appears for anyone who can manage checks. For Managers and Accountants this depends on your UTX Freight edition (the **manager can manage checks** and **accountant can manage checks** options). If you are a Manager or Accountant and you do not see **Checks**, contact UTX support to ask whether it can be enabled for your edition.
- Managers and Accountants only see and manage checks belonging to the offices they are assigned to.
- Expense lines are added on orders by users who can manage rates (**Admin**, **Manager**, and **Dispatch** or **Customer Service** users with **Can manage rates?** checked). See [Order Rates, Charges & Expenses](order-charges-and-expenses.md#access-permissions) and [User Roles](user-roles.md).

### Offices

| Page | Office behaviour |
| ---- | ---- |
| **Expenses** | Not limited to the current office. It lists expense lines from orders in **all** offices. |
| **Checks** list | Shows only the checks of the office you are currently working in. |
| **Check Expenses** on the check form | Offers only expense lines from orders in the current office. |

If you work with several offices, switch to the right office before creating a check. See [Multi-Office](multi-office.md).

---

## :fontawesome-solid-list: The Expenses Page

Click **Expenses** in the left sidebar. The page title is **Expenses** (subtitle *Tracking of expenses for brokers*). There is no "add" button here: expenses are created from the order forms.

### Filters

The **Filters** box at the top has three dropdowns and a **Search** button. The list refreshes in place when you click **Search**.

| Filter | Options | Default |
| ---- | ---- | ---- |
| **Select a filter** | **No Filter**, or one payee. The list contains all your brokers, drivers and expense categories, grouped as **Broker**, **DriverUser** (drivers) and **ExpenseCategory** (other expense categories). | **No Filter** |
| **Order status** | **All statuses**, or one order status (for example **Completed**). Only statuses that exist on your orders are listed. | **All statuses** |
| **Expense payment status** | **Paid and Unpaid**, **Paid Only**, **Unpaid Only** | **Unpaid Only** |

- **Paid Only** shows lines that are linked to a check. **Unpaid Only** shows lines that are not linked to any check.
- When you first open the page, it shows **Unpaid Only** for all payees and all order statuses.

### Columns

The list is sorted by order, newest first, and is split into pages.

| Column | What It Shows |
| ---- | ---- |
| **Type** | **Driver**, **Broker** or **Expense** (an other-expense category) |
| **Name** | The payee's name |
| **Category** | The expense type picked on the expense line, if any (your **Expense** charge types) |
| **Order** | The order reference |
| **Order Status** | The order's status, shown as an icon. Hover over it to see the status (for example *Order Completed*). |
| **Delivery Date** | The order's delivery date |
| **Paid** | :fontawesome-solid-circle-check:{ .text-success } green check when the line is linked to a check; :fontawesome-solid-circle-xmark:{ .text-danger } red cross when it is not |
| **Check Info** | For paid lines, the check's payee name and number (for example `Company XYZ #1042`). Click it to open the check. |
| **Amount** | The expense amount (the **Rate** entered on the order) |
| *(button)* | :fontawesome-solid-dollar-sign: **View Check** on paid lines -- opens the check's edit form |

### TOTAL row

The last row of the table shows **TOTAL**, the sum of the **Amount** column. It adds up the lines shown on the current page of results only, not every page.

!!! tip "Find what you owe one payee"
    Pick the payee in **Select a filter**, set **Order status** to **Completed** and keep **Unpaid Only**. The **TOTAL** row then shows what you still owe them for completed orders (on the current page of results).

---

## :fontawesome-solid-money-check: The Checks List

Click **Checks** in the left sidebar. The page title is **Checks** (subtitle *Management of Checks*). Checks are listed newest first, 50 per page.

<!-- TODO: Screenshot — The Checks list with the search box, Print buttons and the Actions menu open -->

### Columns

| Column | What It Shows |
| ---- | ---- |
| **Check #** | The check number |
| **Vendor Invoice Date** | Date of the vendor's invoice |
| **Vendor Invoice Number** | The vendor's invoice number |
| **Vendor Invoice Amount** | The invoice amount, shown as currency |
| **Vendor** | The payee name |
| **Issue Date** | The date the check was issued |
| :fontawesome-solid-print: **Print** | Opens the printable check in a new tab. See [Printing a Check](#printing-a-check). |
| :fontawesome-solid-gear: **Actions** | **View History**, **Edit**, **Delete** |

### Search

Use the search box at the top right (placeholder *Check #, Vendor or Invoice Number*) and click **Search**. It matches any part of the **check number**, the **vendor name** or the **vendor invoice number**, ignoring upper/lower case.

### Actions menu

| Action | What It Does |
| ---- | ---- |
| **View History** | Opens a **History** window listing each change to the check: the **User** who made it, the **Changes** (field and old/new values) and **When**. If there is nothing to show, it reads *No history found for this item.* |
| **Edit** | Opens the **Edit Check** form. |
| **Delete** | Deletes the check after an **Are you sure?** confirmation. |

---

## :fontawesome-solid-pen-to-square: Creating or Editing a Check

Click **Add a new Check** at the top right of the Checks list (or **Edit** in a check's **Actions** menu). The form opens in a box titled **Check Information**.

<!-- TODO: Screenshot — The New Check form showing Vendor Invoice Information, Vendor Information with the vendor search, and Check Expenses -->

### Check fields

| Field | Required | Notes |
| ---- | ---- | ---- |
| **Issue date** | Yes | Date picker. Printed as the check date. |
| **Check Number** | No | Free text. Shown in the list and in **Check Info** on the Expenses page. It is not printed on the check. |

### Vendor Invoice Information

| Field | Required | Notes |
| ---- | ---- | ---- |
| **Vendor invoice amount** | Yes | The amount of the check. This is the amount printed on the check, in figures and in words. |
| **Vendor invoice number** | No | Printed on the check stubs. |
| **Vendor invoice date** | No | Date picker. Printed on the check stubs. |

!!! warning "The check amount is not calculated from expenses"
    Ticking expense lines under **Check Expenses** does not fill or change **Vendor invoice amount**. Enter the amount yourself. Use the Expenses page and its **TOTAL** row to work out what you owe.

### Vendor Information

| Field | Required | Notes |
| ---- | ---- | ---- |
| **Search for a vendor** | No | Type at least 2 letters of a saved vendor's name and pick it from the suggestions. The fields below fill in automatically. See [Vendors](#vendors). |
| **Name** | Yes | The payee, printed on the check. |
| **Address 1** | No | Street address. |
| **City** | No | |
| **State** | No | State or province. |
| **ZIP/Postal Code** | No | |
| **Country** | No | **Canada** or **United States**. |

You can change any of the filled-in fields after picking a vendor.

!!! warning "Fill in the full address before printing"
    The printed check shows the payee's name, address, city, state, ZIP/postal code and country. Complete these fields before you click **Print**.

### Check Expenses

This section appears only when check expenses are enabled for your edition. It lists expense lines as checkboxes, each written like:

`DriverUser: John Smith for order #12345 - $ 150.00`

(payee type, payee name, order reference, amount). The payee type reads **DriverUser**, **Broker** or **ExpenseCategory**.

| Form | Expense lines offered |
| ---- | ---- |
| **New Check** | Unpaid lines (not on any check) from **Completed** orders in the current office. |
| **Edit Check** | The same, plus the lines already linked to this check (ticked). |

- :fontawesome-solid-square-check: **Tick** a line and save: the line is linked to this check. On the Expenses page it shows the green **Paid** icon, the check in **Check Info** and a **View Check** button.
- :fontawesome-solid-square-minus: **Untick** a line on an existing check and save: the line is released and shows as unpaid again.
- Expenses on orders that are not **Completed** are not offered. Complete the order first. See [Order Workflow](order-workflow.md).

### Saving

Click **Save Changes**. You return to the Checks list with the message *Check was successfully created.* (or *Check was successfully updated.*). Click **Cancel** to leave without saving.

### Step-by-step: Pay a driver by check

1. :fontawesome-solid-arrow-right: Click **Expenses** in the left sidebar.
2. :fontawesome-solid-filter: In **Select a filter**, pick the driver. Set **Order status** to **Completed**, keep **Unpaid Only**, and click **Search**.
3. :fontawesome-solid-calculator: Note the **TOTAL** (or add up the lines you are paying).
4. :fontawesome-solid-money-check: Click **Checks** in the left sidebar, then **Add a new Check**.
5. :fontawesome-solid-calendar: Enter the **Issue date** and **Check Number**.
6. :fontawesome-solid-dollar-sign: Enter the amount in **Vendor invoice amount** (and the vendor invoice number and date, if any).
7. :fontawesome-solid-magnifying-glass: In **Search for a vendor**, type the driver's name and pick it, or fill in **Name** and the address by hand.
8. :fontawesome-solid-square-check: Under **Check Expenses**, tick the driver's lines.
9. :fontawesome-solid-circle-check: Click **Save Changes**.
10. :fontawesome-solid-print: Click **Print** on the check's row and print it from your browser.

---

## :fontawesome-solid-print: Printing a Check

Click **Print** on a check's row in the Checks list. The check opens in a new browser tab, laid out for printing on check stock. Use your browser's print command to print it.

The printed check shows:

| Part | Content |
| ---- | ---- |
| **Check face** | **DATE** followed by the issue date (MM DD YYYY), the amount in words (written as *... dollars & ... cents*), the amount in figures preceded by **$**, the payee's name, address, city, state and ZIP/postal code in capital letters, and the country |
| **Two stubs** | The issue date, the payee name, the vendor invoice date, the word **Invoice**, the vendor invoice number and the amount |

- The amount always comes from **Vendor invoice amount**.
- The amount in figures is printed as stored, without padding to two decimals (for example `$ 150.0` or `$ 150.5`).
- The check number is not printed. Your company name and logo are not printed either.
- Anyone who can see the check in the Checks list can print it.

!!! tip "Test your alignment"
    Print one check on plain paper first and hold it against your check stock to confirm the fields line up with your printer.

!!! warning "Proofread the amount in words"
    Always compare the amount in words with the amount in figures before you sign. For some cent values (for example .29, .57 and .58) the words can show one cent less than the figures. If they differ, correct the words by hand or contact UTX support.

---

## :fontawesome-solid-address-book: Vendors

UTX Freight keeps a vendor directory automatically. There is no page to add, edit or delete vendors.

- :fontawesome-solid-floppy-disk: **Saved on every check save.** Each time a check is created or updated with a **Name**, its name and address (Name, Address 1, City, State, ZIP/Postal Code, Country) are added to the vendor directory, linked to the check's office.
- :fontawesome-solid-magnifying-glass: **Search for a vendor** suggests saved vendors whose name contains what you typed (at least 2 letters, upper/lower case ignored). Suggestions come from the vendors of **all** offices. Entries with exactly the same name and address are shown only once. Picking one fills **Name**, **Address 1**, **City**, **State**, **ZIP/Postal Code** and **Country**.
- :fontawesome-solid-clone: **Address changes create a new entry.** If you change a vendor's address on a check, the new address is saved as well. The old one stays, so the same name can appear more than once in the suggestions, once per address.

!!! info "Drivers and brokers are not vendors automatically"
    Drivers and brokers you pick as payees in **Order Expenses** are not added to the vendor directory. A payee becomes a vendor the first time you save a check with their name.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-eye-slash: I don't see Expenses or Checks in the sidebar

!!! info "Solution"
    **Expenses** is shown to Admin users only. **Checks** is shown to Admins, and to Managers and Accountants only when your edition allows them to manage checks. Ask your administrator, or contact UTX support about your edition's options. See [User Roles](user-roles.md).

### :fontawesome-solid-list-check: An expense is missing from Check Expenses

!!! info "Solution"
    The check form only offers expense lines that are (1) on a **Completed** order, (2) in the office you are currently working in, and (3) not already linked to another check. Complete the order, switch to the right office, or check on the Expenses page whether the line is already **Paid** (its **Check Info** shows which check).

### :fontawesome-solid-eye-slash: There is no Check Expenses section on the check form

!!! info "Solution"
    Linking expenses to checks is an edition option. When it is off, checks record the vendor invoice and payee only, and the Expenses page keeps showing every line as unpaid. Contact UTX support if you need it enabled.

### :fontawesome-solid-calculator: The check amount doesn't match the expenses I ticked

!!! info "Solution"
    The amount on the check is whatever you typed in **Vendor invoice amount**. It is never calculated from the ticked expenses. Edit the check and correct the amount.

### :fontawesome-solid-rotate-left: I linked the wrong expense to a check

!!! info "Solution"
    Open the check (**Actions** > **Edit**, or **View Check** on the Expenses page), untick the line under **Check Expenses**, and click **Save Changes**. The line returns to unpaid.

### :fontawesome-solid-trash: I want to delete a check that pays expenses

!!! warning "Untick its expenses first"
    Deleting a check does not release the expense lines linked to it. Before deleting, edit the check, untick every line under **Check Expenses** and save. Then delete it. Otherwise those lines no longer appear under **Unpaid Only** and cannot be offered on a new check. They still appear under **Paid Only**, but with the red cross in **Paid** and an empty **Check Info**.

### :fontawesome-solid-building: The Expenses page shows lines from another office

!!! info "Solution"
    By design. The Expenses page is not limited to the current office; it lists expense lines from all offices. Use **Select a filter** and **Order status** to narrow it down. The Checks list, by contrast, shows only the current office's checks.

### :fontawesome-solid-address-book: A vendor shows up twice in the search

!!! info "Solution"
    The search shows one entry per distinct name and address, from all offices. If a vendor's address was typed differently on different checks, each version appears. There is no vendor page to merge or remove entries. Pick the suggestion with the right address, or correct the fields after picking.

---

!!! tip "Best Practices"
    - Record driver, broker and other costs in **Order Expenses** on every order, so the Expenses page is your complete payables list.
    - Complete orders promptly -- their expenses can only be linked to a check once the order is **Completed**.
    - Filter the Expenses page by payee with **Unpaid Only** before writing a check, and tick exactly those lines on the check.
    - Use **Search for a vendor** instead of retyping addresses, to keep the vendor directory clean.
    - Keep the **Check Number** filled in so you can find checks with **Search** and see them in **Check Info**.
    - Use **View History** to see who changed a check and when.
