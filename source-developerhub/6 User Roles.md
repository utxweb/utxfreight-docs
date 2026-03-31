---
type: page
title: User Roles
listed: true
slug: user-roles
description: 
index_title: User Roles
hidden: 
keywords: 
tags: 
---published

Each user in the system has one of the predefined roles. Here is a breakdown of the available roles and their abilities.

## Roles overview

| **Role Name** | **Description** | 
| ---- | ---- | 
| Administrator | An administrator is the super user with all the available authorizations. | 
| Manager | A manager has all the administrator rights for a specific office, when the company has only 1 office, the manager has the same privileges as an Administrator | 
| Dispatcher | A dispatcher is the person managing the day- to-day operations related to orders and dispatching. He/she is authorized to manage orders and to dispatch them to drivers. | 
| Driver | A driver is the mobile application user who has access to assigned orders, to sign PODs on a mobile device and information about the location of the orders. | 
| Accountant | An accountant is authorized to read all the orders, manage rates, manage invoices and print checks. | 
| Customer | Customers can place new orders and view the history of their orders. They can also receive notifications when their orders are dispatched for delivery. | 


$plugin[{
    "type": "callout",
    "data": {
        "text": "A Manager has all the administrator rights for a specific **office**, when the company has only 1 office, the Manager has the same privileges as an Administrator",
        "type": "info",
        "title": "Administrator vs Manager"
    }
}]$

## Detailed authorization rules for each role

$plugin[{
    "type": "table",
    "data": {
        "cols": 6,
        "rows": 34,
        "widths": [
            0,
            153,
            0,
            0,
            0
        ],
        "contents": [
            [
                "**Ability**",
                "**Admin\/Manager**",
                "**Dispatcher**",
                "**Driver**",
                "**Accountant**",
                "**Customer**"
            ],
            [
                "Login",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]"
            ],
            [
                "Manage Users",
                "$inline[badge,YES,success]",
                "",
                "",
                "",
                ""
            ],
            [
                "**ORDERS**",
                "",
                "",
                "",
                "",
                ""
            ],
            [
                "View all the orders",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "$inline[badge,YES,success]",
                ""
            ],
            [
                "View dispatched orders",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                ""
            ],
            [
                "View their order",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                "$inline[badge,YES,success]"
            ],
            [
                "Create order",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                "$inline[badge,YES,success]"
            ],
            [
                "Update order",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                ""
            ],
            [
                "Complete a dispatched order",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "$inline[badge,YES,success]",
                ""
            ],
            [
                "Sign POD",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                ""
            ],
            [
                "Duplicate orders",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                ""
            ],
            [
                "Audit orders history",
                "$inline[badge,YES,success]",
                "",
                "",
                "-",
                ""
            ],
            [
                "Email POD to client",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                ""
            ],
            [
                "**INVOICES**",
                "",
                "",
                "",
                "",
                ""
            ],
            [
                "Manage Invoices",
                "$inline[badge,YES,success]",
                "",
                "",
                "$inline[badge,YES,success]",
                ""
            ],
            [
                "**CHECKS**",
                "",
                "",
                "",
                "",
                ""
            ],
            [
                "Manage Checks",
                "$inline[badge,YES,success]",
                "",
                "",
                "$inline[badge,YES,success]",
                ""
            ],
            [
                "**REPORTS**",
                "",
                "",
                "",
                "",
                ""
            ],
            [
                "View reports",
                "$inline[badge,YES,success]",
                "",
                "",
                "",
                ""
            ],
            [
                "**OTHER**",
                "",
                "",
                "",
                "",
                ""
            ],
            [
                "Manage Cities",
                "$inline[badge,YES,success]",
                "$inline[badge,YES*,info]",
                "",
                "",
                ""
            ],
            [
                "Manage Customers",
                "$inline[badge,YES,success]",
                "$inline[badge,YES*,info]",
                "",
                "",
                ""
            ],
            [
                "Manage Drivers",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                ""
            ],
            [
                "Manage Equipment",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                ""
            ],
            [
                "Manage Equipment Type",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                ""
            ],
            [
                "Manage Expenses",
                "$inline[badge,YES,success]",
                "$inline[badge,YES*,info]",
                "",
                "$inline[badge,YES,success]",
                ""
            ],
            [
                "Manage Legs",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                ""
            ],
            [
                "Manage Rates",
                "$inline[badge,YES,success]",
                "$inline[badge,YES*,info]",
                "",
                "$inline[badge,YES,success]",
                ""
            ],
            [
                "Manage Settings",
                "$inline[badge,YES,success]",
                "",
                "",
                "",
                ""
            ],
            [
                "Manage Shippers\/Receivers",
                "$inline[badge,YES,success]",
                "$inline[badge,YES,success]",
                "",
                "",
                ""
            ],
            [
                "Manage Taxes",
                "$inline[badge,YES,success]",
                "",
                "",
                "$inline[badge,YES,success]",
                ""
            ],
            [
                "Manage Terminals",
                "$inline[badge,YES,success]",
                "$inline[badge,YES*,info]",
                "",
                "",
                ""
            ],
            [
                "Manage Website Content",
                "$inline[badge,YES,success]",
                "",
                "",
                "",
                ""
            ],
            [
                "Manage Zones",
                "$inline[badge,YES,success]",
                "",
                "",
                "",
                ""
            ]
        ]
    }
}]$

$plugin[{
    "type": "callout",
    "data": {
        "text": "- **Can Manage Rates** permissions (Cities, Expenses, Rates, Audit orders): Enable per dispatcher user in their profile settings.\n- **Manage Customers** and **Manage Terminals**: Require system configuration (contact your administrator).",
        "type": "info",
        "title": "Dispatcher abilities marked with YES* are conditional:"
    }
}]$

