# Website Content (Manage Content)

Edit the text of your company's public website (the Home, Equipment, Tracking and Contact pages) from inside UTX Freight.

## :fontawesome-solid-globe-americas: Overview

Every UTX Freight system comes with a small public website at the root address of your system. It is what visitors see before they sign in. The page layout, logo and main image are fixed. The **text** comes from content pages that an Admin edits on **Manage Content**.

- :fontawesome-solid-file-lines: The public site reads six content pages, each identified by its **Name**: `about`, `company`, `contact`, `equipment`, `tracking` and `login`. A new system also has a seventh page, `home_equipment`, which is not shown anywhere on the public site. See [The Pages List](#the-pages-list).
- :fontawesome-solid-pen: You can **edit** and **view** these pages. There is no button to create or delete a page.
- :fontawesome-solid-font: Content is written in **Textile**, a simple text markup. It is converted to formatted text (headings, bold, lists, links) on the public site and in the preview.
- :fontawesome-solid-columns: Each public page shows two content pages: one in the large main column and one in the narrow side column. See [Which page appears where](#which-page-appears-where).
- :fontawesome-solid-bolt: Changes appear on the public site as soon as you save.
- :fontawesome-solid-user-shield: **Manage Content** is for Admins only.

!!! info "Placeholder text"
    The public pages ship with placeholder text. Your logo, tax rates and company record are set when your system is built, but the website text is the part only you can write. The [Setup Checklist](setup-checklist.md) reminds you of this in the **Check what your website says** step.

---

## :fontawesome-solid-bolt: Quick Start

1. Click your **name** at the top of the screen to open the user menu, then click **Manage Content**.
2. Find the page you want to change in the **Name** column (for example `contact`).
3. Open its **Actions** menu and click **Edit**.
4. Change the text in the **Content** box, using Textile formatting.
5. Click **Save Changes**.

The message **Page was successfully updated.** appears and the new text is live on the public site.

---

## :fontawesome-solid-shield-halved: Access & Permissions

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Can view and edit every content page. Cannot create pages, and there is no button to delete one. |
| :fontawesome-solid-user-tie: **Manager** | No access |
| :fontawesome-solid-headset: **Dispatch** | No access |
| :fontawesome-solid-file-invoice-dollar: **Accountant** | No access |
| :fontawesome-solid-user: **Customer, Driver, Warehouse, Garage and other users** | No access |

**How to get there:**

- :fontawesome-solid-arrow-right: Click your **name** at the top of the screen to open the user menu, then click **Manage Content**. It sits near the bottom of the menu, just above **Manage Offices**.
- :fontawesome-solid-arrow-right: From the [Setup Checklist](setup-checklist.md), the **Check what your website says** step has an **Open Manage Content** button.

The **Manage Content** item only appears in the menu for Admin users. Any other signed-in user who opens the page address directly is sent back to the dashboard with a not-authorized message.

!!! info "Not per office"
    The content pages are shared by your whole system. They are not tied to an office, so switching offices does not change what you see on **Manage Content** or on the public site.

---

## :fontawesome-solid-list: The Pages List

**Manage Content** opens the **Pages** list (subtitle *Management of Pages*). All content pages are shown on one screen.

<!-- TODO: Screenshot — Pages list showing the Name and Content Preview columns and the Actions menu open on one row -->

| Column | Description |
|--------|-------------|
| **Name** | The page's fixed name, such as `about` or `contact`. This name is what links the page to the public site. It cannot be changed. |
| **Content Preview** | The full page content, already formatted from Textile, so you can see how it will read. |
| *(Actions)* | The **Actions** menu with **Edit** and **Show**. |

There is no **Add** button on this list. Admins cannot create new content pages, and the public site only reads the six names listed in [Which page appears where](#which-page-appears-where).

!!! info "The `home_equipment` page"
    A new system is set up with a seventh content page, `home_equipment`, holding a copy of the starting equipment list. No public page reads it, so editing it changes nothing on your website. To change the equipment text visitors see, edit the `equipment` page.

---

## :fontawesome-solid-pen-to-square: Editing a Page

1. On the **Pages** list, open the **Actions** menu of the page and click **Edit**.
2. The **Edit Page** screen opens. Inside the **Content** box it shows **Page Name: *name***. The name cannot be changed.
3. Change the text in the **Content** box. Use [Textile formatting](#textile-formatting) for headings, bold text, lists and links.
4. Click **Save Changes**.

<!-- TODO: Screenshot — Edit Page screen showing "Page Name: contact", the Content box and the Save Changes / Cancel buttons -->

You return to the **Pages** list with the message **Page was successfully updated.** The **Content Preview** column shows the new text.

To leave without saving, click **Cancel**.

!!! warning "Content cannot be empty"
    The **Content** field is required. If you clear it and click **Save Changes**, the page is not saved and the field shows an error. To hide a section, replace the text with something short instead of leaving it blank.

!!! tip "Do not repeat the section heading"
    Each block on the public site already has a heading (for example **CONTACT US** or **COMPANY**). Start your content with the text itself rather than repeating that heading.

---

## :fontawesome-solid-eye: Viewing a Page

On the **Pages** list, open the **Actions** menu and click **Show**. The page shows **Page Name: *name*** with the subtitle *Website page content*, and the content formatted as it will appear on the website.

From here, click **Edit** to change the page, or **Back** to return to the list.

---

## :fontawesome-solid-columns: Which Page Appears Where

The public website has four pages, reached from the top menu: **HOME**, **EQUIPMENT**, **TRACKING** and **CONTACT**. Each one shows a fixed main image, a large main column and a narrow side column. The heading of each column is fixed; the text below it comes from a content page.

| Public page | Main column heading | Content page used | Side column heading | Content page used |
|-------------|--------------------|-------------------|---------------------|-------------------|
| **HOME** (the root address of your system) | **ABOUT** | `about` | **OFFICES** | `company` |
| **EQUIPMENT** | **EQUIPMENT** | `equipment` | **LOGIN** | `login` |
| **TRACKING** | **TRACKING SYSTEM** | `tracking` | **LOGIN** | `login` |
| **CONTACT** | **CONTACT US** | `contact` | **COMPANY** | `company` |

Key points:

- :fontawesome-solid-building: The `company` page is shown on **two** public pages: as **OFFICES** on HOME and as **COMPANY** on CONTACT. Put your address, phone and fax there.
- :fontawesome-solid-right-to-bracket: The `login` page is shown on **two** public pages: EQUIPMENT and TRACKING. It has no sign-in form; a new system starts it with a short sentence and a **My Account** link. The actual sign-in is the **LOGIN** link at the top of the public site (it reads **MY ACCOUNT** when you are already signed in).
- :fontawesome-solid-pen: Editing one content page changes every public page that uses it.

<!-- TODO: Screenshot — Public website Contact page with the CONTACT US and COMPANY columns labelled with their content page names -->

### Mobile version

Visitors on a phone see a simpler mobile site with **Home**, **Equipment** and **Contact** in the menu (there is no Tracking item). The sign-in link at the top reads **Login**, or **Account** when you are already signed in.

| Mobile page | Content pages shown |
|-------------|--------------------|
| **Home** | `about` only |
| **Equipment** | `equipment` only |
| **Contact** | `contact` and `company` |

On the mobile **Home** and **Equipment** pages there is no side column, so `company` (as **OFFICES**) and `login` are not shown there. Because the Tracking page is not in the mobile menu, the `tracking` and `login` text is normally not seen on a phone.

### When changes appear

The public site keeps a cached copy of the content pages so it loads quickly. The copy is tied to the pages' last-saved time, so as soon as any content page is saved the old copy is no longer used and your change shows on the next page load. You do not need to clear anything or wait.

---

## :fontawesome-solid-font: Textile Formatting

Content is written in Textile. Plain text works as-is; the markup below adds formatting. The **Content Preview** column and the **Show** screen display the formatted result, so you can check your work after saving.

| You type | Result |
|----------|--------|
| A blank line between two blocks of text | Two separate paragraphs |
| `*Open Monday to Friday*` | **Open Monday to Friday** (bold) |
| `_by appointment_` | *by appointment* (italic) |
| `h3. Our yard` at the start of a line, followed by a blank line | A heading reading "Our yard" |
| `* Dry van` on separate lines | A bulleted list |
| `# Call dispatch` on separate lines | A numbered list |
| `"Email us":mailto:info@example.com` | A link reading "Email us" that opens an email |
| `"Our services":https://www.example.com` | A link reading "Our services" |

Example for the `company` page:

```text
*Your Company Inc.*
123 Example Street
City, Province A1A 1A1

Phone: 555-555-0100
Fax: 555-555-0101
```

!!! info "HTML in your content"
    Textile also lets plain HTML through. The `contact` page of a new system starts wrapped in `<div class="contact">` and `</div>`. You can keep those lines or remove them; write your text between them if you keep them.

!!! tip "Keep it short"
    The side column (`company` and `login`) is narrow. A few lines of address and phone details read better there than long paragraphs.

---

## :fontawesome-solid-clipboard-check: The "Check what your website says" Setup Step

The [Setup Checklist](setup-checklist.md) has a step called **Check what your website says**, in the stage about what appears on your invoice. It points you to **Manage Content** with the **Open Manage Content** button and suggests:

1. Open **Manage Content**.
2. Read the **Company** page (`company`). That is your address, phone and fax.
3. Read the **Contact** and **About** pages (`contact`, `about`) and put your own words in.
4. Tell UTX if you want the logo or anything else on the invoice changed.

**What we found** counts every page on the **Pages** list (including `home_equipment`), for example **7 public pages, none confirmed yet**.

This step is not completed by editing the pages. When the text is right, go back to the checklist and click **Looks right to me** on this step. It then reads, for example, **7 pages, confirmed as they are**. See [Looks right to me](setup-checklist.md#looks-right-to-me).

!!! info "Managers and this step"
    A Manager can see this step and click **Looks right to me**, but cannot open **Manage Content**. Ask an Admin to make any changes.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-plus: How do I add a new page to my website?

!!! info "Solution"
    You cannot. The public website has a fixed set of four pages (HOME, EQUIPMENT, TRACKING, CONTACT) fed by six fixed content pages, and Admins cannot create new content pages. To add information, put it in an existing page, for example a new heading and paragraph on the `about` page.

### :fontawesome-solid-trash: How do I remove a page?

!!! info "Solution"
    There is no button to delete a content page, and the public site needs all six it reads. To make a section say less, edit it down to a short line of text.

### :fontawesome-solid-eye-slash: I do not see Manage Content in my menu

!!! info "Solution"
    **Manage Content** is shown only to Admin users. Ask an Admin to make the change, or to give you the Admin role. See [User Roles](user-roles.md).

### :fontawesome-solid-repeat: I changed my address but it only changed in one place

!!! info "Solution"
    Check which content page you edited. Your address normally belongs on the `company` page, which appears on both HOME (as **OFFICES**) and CONTACT (as **COMPANY**). If you also typed it into `about` or `contact`, update those too.

### :fontawesome-solid-asterisk: My text shows stray asterisks, underscores or quotes

!!! info "Solution"
    Textile treats `*`, `_`, `#` and `"text":link` as formatting. Check that each `*` or `_` has a matching closing one, that list lines start with `* ` or `# ` (with a space), and that links use the `"text":address` form with no space before the colon. Open **Show** to check the result.

### :fontawesome-solid-image: Can I change the logo or the main image?

!!! info "Solution"
    No, not from **Manage Content**. The logo and the main image on the public site are part of your system's setup. Contact UTX support if you want them changed.

### :fontawesome-solid-list-check: I edited my pages but the setup step is still open

!!! info "Solution"
    Editing does not complete **Check what your website says**. Go to the [Setup Checklist](setup-checklist.md) and click **Looks right to me** on that step.

---

!!! tip "Best Practices"
    - Replace the placeholder text in `about`, `company` and `contact` before you send customers to your website.
    - Keep your address, phone and fax in **one** place, the `company` page, so they stay consistent on HOME and CONTACT.
    - Use the `login` page to tell customers how to get an account or who to call for tracking access.
    - After saving, open the public site (and check it on a phone) to see the result in context.
