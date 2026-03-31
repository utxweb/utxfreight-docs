---
type: page
title: Fuel Surcharge
listed: true
slug: fuel-surcharge
description:
index_title: Fuel Surcharge
hidden:
keywords: fuel surcharge, fuel rate, exempt, recalculate
tags:
---published

Manage monthly fuel surcharge rates that are applied automatically to qualifying orders -- all from one screen.

## $inline[icon,fas fa-gas-pump] Overview

The **Fuel Surcharge** is a percentage-based charge that UTX Freight applies automatically to your **Import**, **Export**, and **Transfer** orders when auto-compute is enabled. You set the rate once per month, and the system takes care of the rest.

Here is how it works at a glance:

- $inline[icon,fas fa-calendar-alt] **Rates are monthly** -- each rate covers the full calendar month.
- $inline[icon,fas fa-truck] **The order's delivery date** determines which month's rate applies.
- $inline[icon,fas fa-building] **Company overrides** let you set a different rate for specific customers.
- $inline[icon,fas fa-ban text-danger] **Exempt customers** skip fuel surcharges entirely.
- $inline[icon,fas fa-sync-alt] **Recalculate** updates all open orders in a month with one click.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:3n3sd68nph1v",
        "mode": "responsive",
        "width": 1424,
        "height": 970,
        "caption": "The Fuel Schedule page showing monthly rates, the Quick Set form, and the schedule table"
    }
}]$

$inline[icon,fas fa-bolt] Quick Start

Already familiar with fuel surcharges? Here is the fastest path to setting a rate:

1. Go to $inline[icon,fas fa-arrow-right] **Charges** $inline[icon,fas fa-arrow-right] **Fuel Schedule** from the main menu.
2. Enter a **Rate (%)**, pick the **Month**, and choose a **Service Type**.
3. Click **Save Rate**.

That's it -- the rate is now live for that month. Every qualifying open order delivered in that month will pick up this rate automatically when charges are computed.

$plugin[{
    "type": "callout",
    "data": {
        "text": "Changed a rate after orders were already created? No problem. Just click the **Recalculate** button on that month's row to update all open orders instantly.",
        "type": "success",
        "title": "Tip"
    }
}]$

---

## $inline[icon,fas fa-shield-alt] Access & Permissions

The Fuel Schedule page is available to users with one of these roles:

| Role | Access Level | 
| ---- | ---- | 
| $inline[icon,fas fa-user-tie] **Manager** | Full access | 
| $inline[icon,fas fa-headset] **Dispatch** (with `manage_rates` permission) | Full access | 
| $inline[icon,fas fa-file-invoice-dollar] **Accountant** | Full access | 


**How to get there:**

- $inline[icon,fas fa-arrow-right] From the left menu, click **Charges**
- $inline[icon,fas fa-arrow-right] Select **Fuel Schedule**

$plugin[{
    "type": "callout",
    "data": {
        "text": "If you don't see **Fuel Schedule** under the Charges menu, your user role may not have the required permissions. Ask your administrator to grant the **manage_rates** permission to your dispatch account.",
        "type": "warning",
        "title": "Can't find Fuel Schedule?"
    }
}]$

---

## $inline[icon,fas fa-pencil-alt] Setting a Fuel Rate

Use the **Quick Set** form at the top of the Fuel Schedule page to create or update a rate for any month.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:6a0p6lem2khd",
        "mode": "responsive",
        "width": 1402,
        "height": 184,
        "caption": "The Quick Set form with fields for Rate, Month, Service Type, Customer, and Copy months"
    }
}]$

### $inline[icon,fas fa-list-alt] Quick Set Form Fields

| Field | What It Does | 
| ---- | ---- | 
| $inline[icon,fas fa-percent] **Rate (%)** | The fuel surcharge percentage. Enter `15` for 15%. | 
| $inline[icon,fas fa-calendar-alt] **Month** | The month this rate applies to. |
| $inline[icon,fas fa-truck] **Service Type** | Which service type this rate covers (e.g., Intermodal). | 
| $inline[icon,fas fa-building] **Customer** | Leave this **blank** for a general rate that applies to everyone. Or select a specific customer to create a company override. | 
| $inline[icon,fas fa-copy] **Copy (mo)** | Number of extra months to copy the same rate forward (0 to 12). Great for setting rates several months in advance. |


### Step-by-step: Create a new monthly rate

1. $inline[icon,fas fa-arrow-right] Navigate to **Charges** $inline[icon,fas fa-arrow-right] **Fuel Schedule**.
2. $inline[icon,fas fa-percent] Enter the **Rate (%)** -- for example, `15` for a 15% surcharge.
3. $inline[icon,fas fa-calendar-alt] Pick the **Month** from the dropdown.
4. $inline[icon,fas fa-truck] Choose the **Service Type** from the dropdown.
5. $inline[icon,fas fa-building] Leave **Customer** blank if this is a general rate for all customers.
6. $inline[icon,fas fa-copy] Optionally enter a number in **Copy (mo)** to repeat this rate for multiple future months.
7. $inline[icon,fas fa-check-circle text-success] Click **Save Rate**.

If a rate already exists for that month and customer combination, it is updated with the new value.

$plugin[{
    "type": "callout",
    "data": {
        "text": "Use the **Copy (mo)** field to save time! If your fuel rate stays the same for the next 4 months, enter `4` and all four months are set in one shot.",
        "type": "success",
        "title": "Time Saver"
    }
}]$

### $inline[icon,fas fa-calculator] How the Fuel Amount Is Calculated

The formula is straightforward:

$plugin[{
    "type": "callout",
    "data": {
        "text": "Base Rate x Fuel Rate % = Fuel Surcharge Amount",
        "type": "info",
        "title": "Info"
    }
}]$

**Example:** An order has a base rate of **$1,000** and the fuel rate for that month is **15%**.

- $1,000 x 15% = **$150.00** fuel surcharge

The amount is always rounded to the nearest cent.

$plugin[{
    "type": "callout",
    "data": {
        "text": "The fuel surcharge is calculated based on the **order's delivery date**, not the date the order was created. If you move an order's delivery date to a different month, the fuel rate for the new month applies.",
        "type": "info",
        "title": "Important"
    }
}]$

---

## $inline[icon,fas fa-table] Understanding the Schedule Table

The schedule table is the heart of the Fuel Schedule page. It shows every month's fuel rate at a glance, organized chronologically with clear visual cues so you can scan it quickly.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:5n1mh42uuq13",
        "mode": "responsive",
        "width": 1372,
        "height": 504,
        "caption": "The schedule table showing General Rates in green, custom company rates in blue, and the current month highlighted"
    }
}]$

### $inline[icon,fas fa-palette] Color Guide -- What the Colors Mean

The schedule table uses a **color system** to help you instantly understand what you are looking at. This is one of the most important things to learn:

#### $inline[icon,fas fa-circle text-success] Green -- General Rate

The **green row** labeled **"General Rate"** is the default fuel rate for **all customers** that month. If a customer does not have a custom override, this is the rate that applies to their orders.

#### $inline[icon,fas fa-circle text-primary] Blue -- Custom Company Rate

A **blue row** with a company name means that specific customer has a **custom rate override** for that month. This custom rate takes priority over the green general rate.

#### $inline[icon,fas fa-circle text-danger] Red -- Attention Needed

Red text anywhere in the table means something needs your attention:

- **"charges pending removal"** -- An exempt customer still has fuel charges on open orders. You need to recalculate.
- **"No rate"** -- No rate is defined for that month. Orders delivered that month will **not** have fuel surcharge applied.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:wibp3j6wg80z",
        "mode": "responsive",
        "width": 962,
        "height": 56,
        "caption": "A month row showing 'No rate' in red, indicating no fuel surcharge will be applied for orders delivered that month"
    }
}]$

### $inline[icon,fas fa-info-circle] Other Visual Indicators

- $inline[icon,fas fa-tag text-primary] **"Current" label** -- A blue badge marks the current month so you always know where you are.
- $inline[icon,fas fa-eye-slash] **Faded rows** -- Past months appear faded. Their rates are locked and cannot be edited.
- $inline[icon,fas fa-grip-lines] **Double borders** -- A thick border separates each month so you can scan rows quickly without losing your place.

### $inline[icon,fas fa-hashtag] Orders Affected Column

Each row shows the count of **open orders** that use that month's rate. This tells you how many orders will be impacted if you change the rate or click Recalculate.

If any of those orders belong to **exempt customers** who still have fuel charges, the count appears in **red** as a reminder to recalculate.

---

## $inline[icon,fas fa-building] Custom Company Rates

Need to charge a different fuel rate for a specific customer? You can create a **custom company rate** that overrides the general rate for that month.

### Step-by-step: Set a custom rate for a customer

1. $inline[icon,fas fa-arrow-right] Go to **Charges** $inline[icon,fas fa-arrow-right] **Fuel Schedule**.
2. $inline[icon,fas fa-building] In the **Quick Set** form, select the customer from the **Customer** dropdown.
3. $inline[icon,fas fa-percent] Enter the custom **Rate (%)**.
4. $inline[icon,fas fa-calendar-alt] Pick the **Month**.
5. $inline[icon,fas fa-truck] Choose the **Service Type**.
6. $inline[icon,fas fa-check-circle text-success] Click **Save Rate**.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:7j5948gccowg",
        "mode": "responsive",
        "width": 1180,
        "height": 47,
        "caption": "A custom company override row in blue, indented under the green General Rate row for the same month"
    }
}]$

The override appears **indented** below the general rate row for that month, with the company name displayed in **blue**. Whenever this customer's orders are created or updated, the system uses their custom rate instead of the general rate.

### $inline[icon,fas fa-trash text-danger] Removing a Custom Rate

To remove a custom company rate, click the red **Remove** button on the override row. The customer will then fall back to the green general rate for that month.

$plugin[{
    "type": "callout",
    "data": {
        "text": "After removing a custom rate, remember to click **Recalculate** on that month so open orders for that customer are updated to use the general rate.",
        "type": "warning",
        "title": "Don't forget to recalculate"
    }
}]$

---

## $inline[icon,fas fa-ban text-danger] Exempting a Customer from Fuel Surcharges

Some customers may have contractual agreements that exclude fuel surcharges entirely. You can mark these customers as **exempt**.

### Step-by-step: Exempt a customer

1. $inline[icon,fas fa-arrow-right] From the left menu, select $inline[icon,fas fa-building] **Customers**.
2. $inline[icon,fas fa-search] Find the customer by name.
3. $inline[icon,fas fa-pencil-alt] Click the **Edit** button on that customer.
4. $inline[icon,fas fa-gas-pump] Scroll down to the **Fuel Surcharge** section.
5. $inline[icon,fas fa-check-square] Check the box labeled **Exempt from Fuel Surcharge**.
6. $inline[icon,fas fa-check-circle text-success] Click **Save**.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:lmm0s8411s6u",
        "mode": "responsive",
        "width": 810,
        "height": 131,
        "caption": "The Customer edit page showing the 'Exempt from Fuel Surcharge' checkbox in the Fuel Surcharge section"
    }
}]$

After saving, if the customer has **open orders** that already carry fuel charges, you will see a **yellow warning banner** on the Customers page.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:m1kv6a69dz2q",
        "mode": "responsive",
        "width": 799,
        "height": 47,
        "caption": "Yellow flash warning banner indicating the exempt customer has open orders with fuel charges that need recalculation"
    }
}]$

$plugin[{
    "type": "callout",
    "data": {
        "text": "Exempting a customer does **not** automatically remove fuel charges from their existing open orders. You **must** go to the Fuel Schedule and click **Recalculate** on the affected month(s) to remove those charges. Until you do, those stale charges remain on the orders.",
        "type": "error",
        "title": "Critical: Recalculate After Exempting"
    }
}]$

### $inline[icon,fas fa-eye] Viewing All Exempt Customers

Want to see every customer who is currently exempt? Click the **Exempt Customers** button in the top-right corner of the Fuel Schedule page.

The badge on the button shows the total count of exempt customers at a glance.

---

## $inline[icon,fas fa-exclamation-triangle text-warning] Stale Charges on Exempt Customers

When a customer is exempted but their open orders still carry fuel charges, those charges are considered **stale**. This is the most common issue dispatchers run into, so here is exactly what to look for.

The schedule table flags stale charges with a **red indicator** on the affected month's row:

$plugin[{
    "type": "callout",
    "data": {
        "text": "(3 exempt -- charges pending removal)",
        "type": "info",
        "title": "Info"
    }
}]$

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:xtfxpelzn4yn",
        "mode": "responsive",
        "width": 1236,
        "height": 86,
        "caption": "A month row showing '3 exempt -- charges pending removal' in red text, indicating stale fuel charges that need to be recalculated"
    }
}]$

This tells you that **3 orders** for exempt customers in that month still have fuel charges that need to be removed.

**How to fix it:** Click the $inline[icon,fas fa-sync-alt] **Recalculate** button on that month's row. The stale charges will be cleared to $0 for all exempt customers.

$plugin[{
    "type": "callout",
    "data": {
        "text": "Check the Fuel Schedule page regularly -- especially after exempting customers. Stale charges are easy to miss if you do not look for the red indicators.",
        "type": "warning",
        "title": "Best Practice"
    }
}]$

---

## $inline[icon,fas fa-sync-alt] Recalculating Fuel Charges

The **Recalculate** button is your tool for updating all open orders in a given month with the current fuel rate. It appears on **current and future months** whenever there are open orders or exempt charges to process.

### $inline[icon,fas fa-list-ol] Step-by-step: Recalculate a month

1. $inline[icon,fas fa-arrow-right] On the Fuel Schedule page, find the month you want to update.
2. $inline[icon,fas fa-sync-alt] Click the **Recalculate** button on that month's row.
3. $inline[icon,fas fa-eye] A **preview modal** opens showing every affected order, its **current fuel amount**, and the **new amount** after recalculation.
4. $inline[icon,fas fa-ban text-danger] If any exempt customers have stale charges, they appear in a separate **Exempt Orders** section at the bottom of the modal. These orders will have their fuel charges set to **$0**.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:fi8yr6979o7s",
        "mode": "responsive",
        "width": 876,
        "height": 385,
        "caption": "The Exempt Orders section inside the Recalculate modal, showing orders that will have fuel charges removed"
    }
}]$

5. $inline[icon,fas fa-check-circle text-success] Review everything carefully, then click **Confirm** to apply all changes.

All open orders for that month are updated in one step. **Completed and invoiced orders are never modified** -- they are safe.

$plugin[{
    "type": "callout",
    "data": {
        "text": "You can click on any **order number** in the Recalculate modal to open that order in a new tab. This is helpful if you want to review an order before confirming the recalculation.",
        "type": "info",
        "title": "Quick Access"
    }
}]$

$plugin[{
    "type": "callout",
    "data": {
        "text": "Past months do **not** show a Recalculate button. If you need to fix charges on a past month, you must adjust those orders individually from the Orders page.",
        "type": "warning",
        "title": "Past Months Are Locked"
    }
}]$

---

## $inline[icon,fas fa-exclamation-circle text-danger] Missing Rates Warning

If any upcoming months do not have a fuel rate defined, a **red warning banner** appears at the top of the Fuel Schedule page listing the affected months.

$plugin[{
    "type": "image",
    "data": {
        "url": "asset:oascpg2afrw6",
        "mode": "responsive",
        "width": 983,
        "height": 68,
        "caption": "Red warning banner at the top of the Fuel Schedule page listing months that have no fuel rate defined"
    }
}]$

Orders delivered in months without a rate will **not** have any fuel surcharge applied. Use the Quick Set form to define rates for those months as soon as possible.

$plugin[{
    "type": "callout",
    "data": {
        "text": "Set your fuel rates at least **2-3 months in advance** to avoid missing rates on new orders. Use the **Copy (mo)** field in the Quick Set form to set multiple months at once.",
        "type": "success",
        "title": "Stay Ahead"
    }
}]$

---

## $inline[icon,fas fa-history] Legacy Weekly Rates

Before the monthly fuel schedule was introduced, fuel rates were set on a **weekly** basis (Monday through Sunday). If your account has been around for a while, you may still see these older weekly rates.

Here is what you need to know:

- $inline[icon,fas fa-calendar-alt] Orders delivered **before the monthly cutoff date** still use the legacy weekly rates.
- $inline[icon,fas fa-info-circle] The cutoff date is displayed in a **blue info banner** at the top of the Fuel Schedule page.
- $inline[icon,fas fa-table] Legacy weekly rates appear in a **separate table** at the bottom of the page.
- $inline[icon,fas fa-pencil-alt] You can still **edit** legacy weekly rates if you need to make adjustments.

$plugin[{
    "type": "callout",
    "data": {
        "text": "All new rates should be set using the monthly system. The legacy weekly table is only for historical orders that predate the monthly cutoff.",
        "type": "info",
        "title": "Going Forward"
    }
}]$

---

## $inline[icon,fas fa-question-circle] FAQ / Troubleshooting

### $inline[icon,fas fa-ban text-danger] Customer was exempted but still has fuel charges

$plugin[{
    "type": "callout",
    "data": {
        "text": "Exempting a customer does not automatically remove existing fuel charges from their open orders. Go to **Charges &gt; Fuel Schedule**, find the affected month, and click **Recalculate** to remove the stale charges. The preview modal will show those orders in the **Exempt Orders** section with their fuel set to $0.",
        "type": "info",
        "title": "Solution"
    }
}]$

### $inline[icon,fas fa-lock] No Recalculate button for a past month

$plugin[{
    "type": "callout",
    "data": {
        "text": "Past months are locked and cannot be recalculated. The **Recalculate** button only appears on the **current month** and **future months**. To fix fuel charges on past-month orders, you need to edit those orders individually from the Orders page.",
        "type": "info",
        "title": "Solution"
    }
}]$

### $inline[icon,fas fa-sync-alt] Rate was changed but orders still show the old amount

$plugin[{
    "type": "callout",
    "data": {
        "text": "Changing a fuel rate does **not** automatically update existing orders. Click **Recalculate** for that month to apply the new rate to all open orders. The preview modal will show you the old and new amounts before you confirm.",
        "type": "info",
        "title": "Solution"
    }
}]$

### $inline[icon,fas fa-building] Customer has a custom rate but orders use the general rate

$plugin[{
    "type": "callout",
    "data": {
        "text": "Double-check that the custom rate is set for the correct **month** and **service type**. The order's **delivery date** determines which month's rate applies, and the **service type** must match exactly. If the rate was added after the orders were created, click **Recalculate** to apply it.",
        "type": "info",
        "title": "Solution"
    }
}]$

### $inline[icon,fas fa-lightbulb text-warning] Tips for managing fuel surcharges effectively

$plugin[{
    "type": "callout",
    "data": {
        "text": "**Set rates early.** Use the Copy (mo) field to set rates 4-8 months in advance.\n\n**Check for red indicators.** Red text on the schedule table always means something needs your attention.\n\n**Recalculate after changes.** Any time you change a rate, exempt a customer, or remove a custom override, click Recalculate on the affected months.\n\n**Review the preview.** Always check the Recalculate preview modal before confirming -- it shows you exactly what will change.",
        "type": "success",
        "title": "Best Practices"
    }
}]$

<!-- asset:3n3sd68nph1v=https://uploads.developerhub.io/prod/k8VN/h6st41dasp57lj7jt6xg9dxl996f3qps3tza01mbm5zmhko9z2qf3r7lql34bhxf.png -->
<!-- asset:6a0p6lem2khd=https://uploads.developerhub.io/prod/k8VN/jjfk7zjh9tqcofgmw1tu0afc3gulwmldj2bjzy9ulq3zjlhjv702ddztul36rfwa.png -->
<!-- asset:5n1mh42uuq13=https://uploads.developerhub.io/prod/k8VN/ea0harodf9pg46r0hxbvixa3q24fr5h0fh69qis132bne6g8w0pew1m494nr7jx1.png -->
<!-- asset:wibp3j6wg80z=https://uploads.developerhub.io/prod/k8VN/57nqjo1fhany90fz474oemlutvcr5jncmeoc6tttlbu7d8b7bhmpor5axp1nwjs4.png -->
<!-- asset:7j5948gccowg=https://uploads.developerhub.io/prod/k8VN/omwx23c762zvjxagzlqto07w9un5rg8dc9lqo8jgbfd2uzw14d3bvuzhuon5tk1z.png -->
<!-- asset:lmm0s8411s6u=https://uploads.developerhub.io/prod/k8VN/hdz1eyqmddzjhs4xn73z4il0upa1snon35icoww21tsfvovfl537ra15uvgxqni6.png -->
<!-- asset:m1kv6a69dz2q=https://uploads.developerhub.io/prod/k8VN/h3r6ad0hyii3hhihp65ohw0g29hjrjjv48yuur4oimroa5gr14ie4lj8avx8dfc3.png -->
<!-- asset:xtfxpelzn4yn=https://uploads.developerhub.io/prod/k8VN/9jncy39ddl7w6svc0xjyvhx614yf1wrsz2qxjtbxeuytlquhh9yw2a614ni3ye4f.png -->
<!-- asset:fi8yr6979o7s=https://uploads.developerhub.io/prod/k8VN/wvqjx30swjgkrbg1tgutcd89mdp13qx2qxdw6gxmpr57un7scteeeris4tccjndy.png -->
<!-- asset:oascpg2afrw6=https://uploads.developerhub.io/prod/k8VN/9o84hg37ucmbvfs8dxy1t2mdqbq7eqxd6ocurxourv4v8dyl7onqh39wqhch4ixr.png -->

