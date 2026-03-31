---
type: page
title: Automatic Statements
listed: true
slug: automatic-statements
description: 
index_title: Automatic Statements
hidden: 
keywords: 
tags: 
---published

Schedule your customer statements to automatically notify them of unpaid invoices.

## Scheduling

Scheduling of the Statements works by setting the day on which the statement should be delivered to the client. 

The mailer will check if there is something to deliver every hour, so if you change the day to **Today** for any customer**,** the email is automatically sent within the next hour.

**Eg.:** For a customer scheduled for **Friday**, the email will be sent **early in the morning on Friday**. Any updates to this customer should be done the day before it is scheduled to make sure they receive an accurate report.

Once the statement is delivered it will set the **Sent Date** on the **Customer Reports** page to the actual date so you can track the delivery if there was any errors sending the statement.

$plugin[{
    "type": "callout",
    "data": {
        "text": "The statement email is only sent if the customer balance is  **greater than** **0$!**",
        "type": "info",
        "title": "Info"
    }
}]$

### Adding a statement schedule to Customers

Adding a statement schedule to a customer will automatically deliver his statement of account. There are **2 ways** this can be accomplished 

### Edit the scheduler on the Customer Reports screen

- From the left menu, select $inline[icon,fas fa-chart-bar] **Report -&gt; Customer Reports**
- Find your **Customer** by name
- Edit the **Delivery Day** column dropdown for this **Customer**
- Click on blue $inline[icon,fas fa-check-square primary-text] to **Save Changes**
- As soon as the changes are saved, the **Next Date** will display when the report will be delivered automatically

$plugin[{
    "type": "image",
    "data": {
        "url": "https:\/\/uploads.developerhub.io\/prod\/k8VN\/lx2d4jlb1irrx627onobjjrrpxwqeb6anfjqjdlj0vqenqhyzcqk6sctyt7w87fl.png",
        "mode": "responsive",
        "width": 1263,
        "height": 275,
        "caption": null
    }
}]$

$plugin[{
    "type": "callout",
    "data": {
        "text": "Spread the scheduling across multiple days to avoid sending 300-400 emails in a day, ideally you want to keep the number under 100 per day.",
        "type": "warning",
        "title": "Warning"
    }
}]$

### Edit the Customer to set the scheduler

- From the left menu, select $inline[icon,fas fa-building] **Customers**
- Find your **Customer** by name
- Click on the **Edit customer** button
- On the **Customer Edit** form, select a **Configuration** from the **Send statement on** dropdown
- Click on **Save Changes**

$plugin[{
    "type": "image",
    "data": {
        "url": "https:\/\/uploads.developerhub.io\/prod\/k8VN\/26mbsjtvzfqg3lzixeg1aucr5363ye85ke1i6ba25s168y1epjuabxlrv1ig32l7.png",
        "mode": "responsive",
        "width": 1294,
        "height": 414,
        "caption": null
    }
}]$

Scheduler information

The information is available from the **Customer Reports** page and displays on statistics about each day and the number of deliveries

$plugin[{
    "type": "image",
    "data": {
        "url": "https:\/\/uploads.developerhub.io\/prod\/k8VN\/jp3luzp5da0pis1trkiw1clpdrq4f8phrb7n9x2ozutt4196bypbejfdsf3cs7ac.png",
        "mode": "responsive",
        "width": 1303,
        "height": 73,
        "caption": null
    }
}]$

