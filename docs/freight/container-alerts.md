# Container Alerts & Integration Health

One page that lists what changed at the terminals for your tracked containers, which Last Free Days are coming up, and whether each terminal feed is working.

## :fontawesome-solid-bell: Overview

The **Container Alerts** page (header: **Container Alerts** — *Container Tracking & Status Alerts*) is part of the Container Tracking add-on. Every 10 minutes the system pulls data from CN Rail, Termont and MGT (Racine/Cast). When a container's status changes, it creates an alert. You do not need to refresh anything or check each terminal yourself.

- :fontawesome-solid-heart-pulse: **Integration Health** — one card for each terminal source you have. The card shows whether the last data pull worked.
- :fontawesome-solid-table-cells: **Six summary cards** — **Unread**, **LFD Approaching**, **Ready for Pickup**, **Customs Released**, **Departed** and **All**. Click a card to filter the alert list.
- :fontawesome-solid-calendar-xmark: **Upcoming Last Free Days (Next 7 Days)** — every tracked container whose LFD is between today and 7 days from now.
- :fontawesome-solid-list: **Alerts list** — alerts from the last 90 days, newest first, with a **NEW** badge on unread ones.
- :fontawesome-solid-envelope: **Daily digest email** — the users you choose get an email listing the new alerts.

There are four alert types:

| Alert type | Badge in the list | What it means |
|------------|-------------------|---------------|
| :fontawesome-solid-truck: **Pickup Ready** | Green **Pickup Ready** | The container is off the train (CN) or available for pickup at the terminal (Termont / MGT). You can dispatch a driver. |
| :fontawesome-solid-circle-check: **Customs Released** | Blue **Customs Released** | Customs has released the container. |
| :fontawesome-solid-triangle-exclamation: **LFD Approaching** | Orange **LFD Approaching** | The Last Free Day is today, tomorrow or the day after. Schedule the pickup to avoid demurrage. |
| :fontawesome-solid-right-from-bracket: **Departed** | Gray **Departed** | The container has left the terminal. No further action needed. |

See [Container Tracking](container-tracking.md) for the tracking add-on itself and the tracking modal.

<!-- TODO: Screenshot — Container Alerts page showing the Integration Health cards, the six summary cards, the Upcoming Last Free Days table and the alerts list -->

---

## :fontawesome-solid-bolt: Quick Start

1. Go to :fontawesome-solid-road: **Dispatch** and click the :fontawesome-solid-bell: **Alerts** button in the header. The red badge on it is the number of unread alerts.
2. Check the **Integration Health** cards. Green means the data is fresh.
3. Look at **Upcoming Last Free Days (Next 7 Days)**. Red and yellow rows need a pickup soon.
4. Click a summary card (for example **Ready for Pickup**) to filter the alert list.
5. Click a container number to open its tracking details, or click the order number to find the order.
6. If you are an Admin, click **Mark All Read** when you have gone through the list.

---

## :fontawesome-solid-shield-halved: Access & Permissions

The page only exists when at least one Container Tracking add-on (CN, Port of Montreal / Termont, or MGT Racine/Cast) is enabled. Without one, opening the page sends you back to the home page with the message **Container tracking is not enabled.**

| Role | Access |
|------|--------|
| :fontawesome-solid-user-shield: **Admin** | Views the page. Can use **Mark All Read** and the per-alert read / unread toggle. Manages **Alert Email Subscriptions** in **Settings**. |
| :fontawesome-solid-user-tie: **Manager**, :fontawesome-solid-headset: **Dispatch**, :fontawesome-solid-headset: **Customer Service** | Views the page (reached from the **Dispatch** header). Cannot mark alerts read or unread. |
| Other signed-in users | Can open the page from a link (for example the digest email). Cannot mark alerts read or unread. |

**How to get there:**

- :fontawesome-solid-arrow-right: **From Dispatch:** click :fontawesome-solid-road: **Dispatch** in the left menu, then the :fontawesome-solid-bell: **Alerts** button in the header (shown when any tracking add-on is enabled). See [Dispatch](dispatch.md#header-buttons).
- :fontawesome-solid-arrow-right: **From the digest email:** click **View Alerts Dashboard** at the bottom of the email.

!!! info "No Container Tracking menu"
    There is no **Container Tracking** or **Alerts** item in the left menu. Use the **Alerts** button on the Dispatch page or the link in the digest email.

To go back, click **Back to Dispatch** in the top right of the page.

---

## :fontawesome-solid-heart-pulse: Integration Health

At the top of the page, under **Integration Health**, there is one card for each tracking source enabled on your account: **CN Rail**, **Termont** and/or **MGT (Racine/Cast)**. Each card has a colored left border.

### Card color

| Color | Meaning |
|-------|---------|
| :fontawesome-solid-circle:{ style="color:#4caf50" } **Green** | Healthy. The last pull ran less than 30 minutes ago and the terminal returned at least one container. |
| :fontawesome-solid-circle:{ style="color:#ff9800" } **Orange** | The last pull ran less than 30 minutes ago and asked about containers, but the terminal returned none. Usually a problem on the terminal side. |
| :fontawesome-solid-circle:{ style="color:#f44336" } **Red** | The last pull failed (**ERROR** label), has not run for more than 1 hour, or has never run. |
| :fontawesome-solid-circle:{ style="color:#9e9e9e" } **Gray** | None of the above. For example, the last pull was between 30 and 60 minutes ago, or it had no containers to ask about. |

### Card details

When the source has run at least once, the card shows two bars and the time of the last pull:

| Line | What it shows |
|------|---------------|
| **Discovery** | `found / submitted (percent)` — of the containers the system asked the terminal about, how many the terminal returned. |
| **Synced** | `updated / found (percent)` — of the containers the terminal returned, how many were saved in UTX Freight. |
| **Last pull: … ago** | How long ago the last pull ran. |

Labels that can appear on a card:

- **Never run** (red text) — the source has never been pulled.
- **ERROR** (red label) — the last pull failed.
- **No API results** (orange label) — the last pull asked about containers and got nothing back.

!!! warning "Red or orange card = data may be out of date"
    While a card is red or orange, statuses, LFDs and alerts for that source may be old. Alerts for that source will not appear until pulls work again. Contact UTX support if a card stays red.

The Integration Health cards do not update on their own. Reload the page to see the latest values.

---

## :fontawesome-solid-table-cells: Summary Cards

Below Integration Health there are six cards. Click a card to filter the alert list below it.

| Card | Color | What the number counts | Filter when clicked |
|------|-------|------------------------|---------------------|
| **Unread** | Red | All unread alerts, from any date, including alerts whose order is no longer in progress | Unread alerts |
| :fontawesome-solid-triangle-exclamation: **LFD Approaching** | Orange | **Containers** in the Upcoming Last Free Days table (LFD between today and 7 days from now). This is a count of containers, not alerts. | **LFD Approaching** alerts |
| :fontawesome-solid-truck: **Ready for Pickup** | Green | **Pickup Ready** alerts created in the last 7 days | **Pickup Ready** alerts |
| :fontawesome-solid-circle-check: **Customs Released** | Blue | **Customs Released** alerts created in the last 7 days | **Customs Released** alerts |
| :fontawesome-solid-right-from-bracket: **Departed** | Gray | **Departed** alerts created in the last 7 days | **Departed** alerts |
| :fontawesome-solid-list: **All** | Default (no color) | The total of the five cards above | All alerts (no filter) |

!!! info "The card number and the list can differ"
    The cards use different rules from the list. For example, **Ready for Pickup** counts the last 7 days, but its filtered list shows the last 90 days. **LFD Approaching** counts containers, but its list shows LFD alerts. The cards also count alerts whose order is no longer in progress (for example **Completed**), which the list hides.

With [multiple offices](multi-office.md), the alert cards count alerts for orders in your current office plus alerts with no order. The **LFD Approaching** card and the Upcoming LFD table are not limited to an office.

---

## :fontawesome-solid-calendar-xmark: Upcoming Last Free Days

The table **Upcoming Last Free Days (Next 7 Days)** lists every tracked container (CN Rail, Termont, MGT) whose Last Free Day is **from today up to 7 days from now**, sorted by LFD. The table is hidden when there are none.

!!! warning "Past LFDs are never listed"
    A container drops out of this table the day after its LFD. The table does not show containers whose LFD has already passed.

| Column | What it shows |
|--------|---------------|
| **Source** | **CN Rail**, **Termont** or **MGT (Racine/Cast)** |
| **Container** | The container number. If an in-progress order (**New**, **App. Taken** or **Dispatched**) has this container, the number is a link (:fontawesome-solid-arrow-up-right-from-square:) that opens the container's tracking details. |
| **Shipping Line** | The shipping line from the terminal. Empty for CN Rail containers, because CN does not send it. |
| **Terminal** | The terminal section |
| **Last Free Day** | The date, for example *Oct 14, 2026* |
| **Days Left** | A badge (see below) |
| **Status** | Green **Ready** when the terminal says the container is available for pickup. Otherwise the terminal's visit state, or **Unknown**. |

**Days Left badges and row colors:**

| Days left | Badge | Row color |
|-----------|-------|-----------|
| LFD is today | Red **EXPIRED** | Red |
| LFD is tomorrow | Yellow **TOMORROW** | Yellow |
| LFD is in 2 days | Gray **2 days** | Yellow |
| LFD is in 3 to 7 days | Gray **N days** (for example **5 days**) | No color |

!!! tip "EXPIRED means today"
    Because past LFDs are not listed, an **EXPIRED** badge always means the LFD is **today**. Pick the container up today to avoid demurrage.

!!! info "Check the Status column"
    The table lists containers by Last Free Day, including containers that have already left the terminal. Check the **Status** column before dispatching a driver.

---

## :fontawesome-solid-list: The Alerts List

The list title is **All Alerts**. When you click a summary card, the title changes to show which filter is on (for example **Unread Alerts**). Click **All** to clear the filter.

### Which alerts are listed

- :fontawesome-solid-calendar: **Last 90 days** by default. Click **Show all time** (top right of the list) to see older alerts. Click **Last 90 days** to go back.
- :fontawesome-solid-truck-fast: **In-progress orders only.** An alert linked to an order is listed only while that order is **New**, **App. Taken** or **Dispatched**. When the order moves to any other status (for example **Completed**), its alerts disappear from the list. Alerts not linked to any order are always listed.
- :fontawesome-solid-building: **Current office.** With [multiple offices](multi-office.md), you see alerts for orders in the office you are working in, plus alerts with no order.
- :fontawesome-solid-arrow-down-wide-short: **Newest first**, **25 per page**. Use the page links under the list to see more.

If nothing matches, the list shows **No alerts found.**

### Columns

| Column | What it shows |
|--------|---------------|
| (icon) | An icon for the alert type |
| **Source** | **CN Rail**, **Termont** or **MGT (Racine/Cast)** |
| **Container** | The container number. A red **NEW** badge means the alert is unread. When the alert has an order, the number is a link (:fontawesome-solid-arrow-up-right-from-square:) that opens the container's tracking details on this page. |
| **Type** | **Pickup Ready**, **Customs Released**, **LFD Approaching** or **Departed** |
| **Message** | The alert message (see [Alert Rules and Messages](#alert-rules-and-messages)) |
| **Order** | The order's reference number, or **N/A** when no order is linked. The link opens the **Orders** page **in a new tab**, searched on that reference number. |
| **When** | The date and time the alert was created |
| (eye) | The read / unread toggle (Admin only, see below) |

### How an alert is linked to an order

When the alert is created, the system looks for an in-progress order (**New**, **App. Taken** or **Dispatched**) with the same container number. If it finds one, the alert is linked to that order. If not, the alert has no order (**N/A**). For **Pickup Ready**, **Customs Released** and **Departed** alerts, the order must also have been created on or after the **Order Archive Cutoff Date** in [Application Settings](application-settings.md) (when that date is set). The link is set once, when the alert is created. Adding the container to an order later does not link existing alerts.

### Auto-refresh

While the page is open, the summary cards and the alerts list refresh every **60 seconds** without reloading the page. The refresh pauses while the browser tab is hidden. The Integration Health cards and the Upcoming LFD table only update when you reload the page.

---

## :fontawesome-solid-eye: Read and Unread

Unread alerts are shown in **bold** with a red **NEW** badge.

| Action | Who | What it does |
|--------|-----|--------------|
| :fontawesome-solid-check: **Mark All Read** (top right) | Admin only | Marks **every** unread alert as read, for all sources, all offices and all dates, not only what is on screen. Shows **All alerts marked as read.** |
| :fontawesome-solid-eye: / :fontawesome-solid-eye-slash: eye icon (last column) | Admin only | Switches one alert between read and unread. The green eye means **Mark as read**. The gray crossed eye means **Mark as unread**. The **Unread** card updates right away. |
| Opening **Port Tracking** on Dispatch | Anyone who opens it | The Port Tracking window shows up to the 10 newest unread Termont and MGT alerts in an alerts panel, and marks those alerts as read. CN alerts are not affected. |

!!! warning "Read status is shared by everyone"
    An alert is read or unread for the whole company, not per user and not per office. When one person marks alerts read (or opens Port Tracking), they are read for every user in every office. The **Alerts** badge on Dispatch also counts unread alerts for all offices.

!!! info "Marking read does not delete"
    Read alerts stay in the list. Only the bold text and the **NEW** badge go away.

Only Admins can change read status. Other users see the alerts but cannot mark them read or unread.

---

## :fontawesome-solid-gears: Alert Rules and Messages

Alerts are created by the tracking pull that runs every 10 minutes. An alert is created only when a value **changes** to the new state since the last pull (or the first time the system sees the container already in that state). The same alert is not created again on later pulls while the value stays the same.

### CN Rail

| Alert | Created when | Message |
|-------|--------------|---------|
| **Pickup Ready** | The CN status shows the container as **De-ramped** | `Container <number> has been de-ramped and is available for pickup at CN` |
| **Customs Released** | The terminal reports the container as released by customs | `Customs released for container <number>` |
| **Departed** | The visit state becomes **Completed** | `Container <number> has departed CN terminal` |

After a CN container's visit state is **Departed** or **Completed**, no more status alerts are created for it.

### Termont and MGT (Racine/Cast)

| Alert | Created when | Message |
|-------|--------------|---------|
| **Pickup Ready** | The terminal shows the container as available for pickup | `Container <number> is now available for pickup` |
| **Customs Released** | The terminal reports the container as released by customs | `Customs released for container <number>` |
| **Departed** | The visit state becomes **Departed** | `Container <number> has departed the terminal` |

After the terminal reports the container as out of the terminal, no more status alerts are created for it.

### LFD Approaching (all sources)

After each pull, the system checks every tracked container (CN Rail, Termont and MGT) whose Last Free Day is **today, tomorrow or the day after**.

- It creates an **LFD Approaching** alert if that container has not had one in the **last 24 hours**.
- So the alert **repeats about once a day**: up to **3 times** (2 days before, 1 day before, and on the LFD itself).
- It **never fires after the LFD**. Once the date has passed, no more LFD alerts are created for that container.
- The 24-hour check is by container number, across all sources.

Message: `Last Free Day for <number> is in <N> days (<Mon DD, YYYY>)`. It says *1 day* when the LFD is tomorrow and *0 days* when it is today. Example: *Last Free Day for ABCU1234567 is in 2 days (Oct 14, 2026)*.

!!! tip "Alerts are created for every tracked container"
    Alerts are created even when no in-progress order has the container. Those alerts show **N/A** in the **Order** column.

---

## :fontawesome-solid-envelope: Alert Email Subscriptions and the Daily Digest

### Choosing who gets the email

Only Admins can do this, and only when a Container Tracking add-on is enabled.

1. Open :fontawesome-solid-arrow-right: **Your Name** :fontawesome-solid-arrow-right: :fontawesome-solid-gear: **Settings**.
2. Find the :fontawesome-solid-bell: **Alert Email Subscriptions** box, section **Container Tracking Alerts**.
3. Pick a person in **— Select a user —**. The list shows active users of your own company (the company that owns the UTX Freight account) who are not subscribed yet. Customers' users are not listed.
4. Click **Add Subscriber**.

The subscriber table shows **Name**, **Email** and **Role**. With no subscribers, the box says *No subscribers yet. Add users from the dropdown above.* To stop the email for someone, click **Remove** on their row and confirm *Remove <name> from alerts?*.

When the add-on is enabled, the people list of a company also has an **Alerts** column that shows who is subscribed.

<!-- TODO: Screenshot — Settings page, Alert Email Subscriptions box with the user dropdown, Add Subscriber button and subscriber table -->

### The digest email

Once a day, the system sends one email to each subscriber.

- **Subject:** *Container Tracking — N alerts* (*1 alert* when there is one).
- **From:** your company name and the **Admin Email** address from [Application Settings](application-settings.md).
- **Title:** **Container Tracking Alerts**, then *Summary for <day, date> — N alerts*.
- **⚠ Action Required (N)** — the **Pickup Ready** alerts (shown as *Ready for Pickup*) and **LFD Approaching** alerts, with container, source and order number. This box only appears when there is at least one.
- **One section per alert type**, titled *Pickup Available*, *Customs Released*, *Departed* or *LFD Approaching* with the count in brackets. Each has a table: **Container**, **Source**, **Message**, **Order**, **Time**. The **Order** column shows the order's reference number, or **—** when no order is linked.
- With [multiple offices](multi-office.md), the email is split by office, each with its own **Action Required** box and type sections. Alerts with no order are under **Unassigned**.
- **View Alerts Dashboard** button — opens the Container Alerts page.
- Footer: *This notification is sent automatically by* your company name.

**What goes in the email:**

- Every alert that has not been emailed yet, from all sources and all offices. Each subscriber gets the same full list.
- **Each alert is emailed only once.** After a digest is sent, its alerts are not included again.
- If there are no new alerts, no email is sent.
- If the email fails for **every** subscriber, the alerts are kept and sent with the next digest. If it reaches at least one subscriber, the alerts count as sent.
- Read status does not matter. An alert already marked read in the app is still included if it was not emailed yet.

!!! warning "First digest after adding subscribers can be long"
    Alerts are only marked as emailed when a digest is actually sent. If nobody was subscribed for a while, the first digest includes all the alerts created since then.

---

## :fontawesome-solid-circle-info: Other Things on the Page

- **Help box** — click **How do container alerts work?** at the top to expand a short guide to alert types, terminal sources, the dashboard and the colors.
- **All clear** — when every card is 0, there are no upcoming LFDs and every Integration Health card is green, the page shows **All clear! No container alerts right now.** A source that has never run (**Never run**) is ignored in this check.
- **Office name** — with [multiple offices](multi-office.md), the current office name is shown next to the page subtitle.

---

## :fontawesome-solid-circle-question: FAQ / Troubleshooting

### :fontawesome-solid-bars: I can't find Container Alerts in the menu

!!! info "Solution"
    There is no menu item. Go to **Dispatch** and click the **Alerts** button in the header. If the button is missing, no Container Tracking add-on is enabled on your account. Contact UTX support.

### :fontawesome-solid-ban: I can't mark alerts as read

!!! info "Solution"
    Only Admins can use **Mark All Read** and the eye icon. Ask an Admin to mark the alerts as read.

### :fontawesome-solid-eye-slash: Alerts disappeared from the list

!!! info "Solution"
    The list hides alerts older than 90 days (click **Show all time**) and alerts whose order is no longer **New**, **App. Taken** or **Dispatched**. With multiple offices, check that you are in the right office.

### :fontawesome-solid-calendar-xmark: A container with an expired LFD is not in the Upcoming LFD table

!!! info "Solution"
    The table only shows LFDs from today to 7 days ahead. Once the LFD has passed, the container leaves the table. Check the order or its tracking details instead.

### :fontawesome-solid-repeat: I get the same LFD alert several days in a row

!!! info "Solution"
    That is expected. The **LFD Approaching** alert repeats about once a day while the LFD is 2 days away, 1 day away and today. It stops after the LFD.

### :fontawesome-solid-bell-slash: No alerts are coming in

!!! info "Solution"
    Check the **Integration Health** cards. Red means the pull failed, is more than 1 hour late, or never ran. Orange means the terminal returned no data. Gray can mean the last pull is 30–60 minutes old. Contact UTX support if a card stays red or orange.

### :fontawesome-solid-envelope: Someone is not receiving the digest

!!! info "Solution"
    An Admin should check **Settings** :fontawesome-solid-arrow-right: **Alert Email Subscriptions**. Only users of your own company can be added. No email is sent on days with no new alerts.

### :fontawesome-solid-circle-exclamation: "User is already subscribed to this alert type" when adding a subscriber

!!! info "Solution"
    A **Subscription Error** popup with this message means the user is already on the list. Check the subscriber table in **Alert Email Subscriptions**.

---

!!! tip "Best Practices"
    - Open the Alerts page from Dispatch at the start of each shift and work through **Upcoming Last Free Days** first.
    - Have an Admin click **Mark All Read** once the team has reviewed the list, so the **Alerts** badge on Dispatch only counts new items. Remember this is shared by everyone.
    - Subscribe at least one dispatcher to the digest so pickups and LFDs are not missed when nobody is logged in.
    - If an Integration Health card is not green, do not rely on that source's alerts until it is fixed.
