# User Roles

Each user in the system has one of the predefined roles. Here is a breakdown of the available roles and their abilities.

## Roles overview

| **Role Name** | **Description** |
| ---- | ---- |
| Administrator | An administrator is the super user with all the available authorizations. |
| Manager | A manager has all the administrator rights for a specific office, when the company has only 1 office, the manager has the same privileges as an Administrator |
| Dispatcher | A dispatcher is the person managing the day-to-day operations related to orders and dispatching. He/she is authorized to manage orders and to dispatch them to drivers. |
| Driver | A driver is the mobile application user who has access to assigned orders, to sign PODs on a mobile device and information about the location of the orders. |
| Accountant | An accountant is authorized to read all the orders, manage rates, manage invoices and print checks. |
| Customer | Customers can place new orders and view the history of their orders. They can also receive notifications when their orders are dispatched for delivery. |

!!! info "Administrator vs Manager"
    A Manager has all the administrator rights for a specific **office**, when the company has only 1 office, the Manager has the same privileges as an Administrator

## Detailed authorization rules for each role

| **Ability** | **Admin/Manager** | **Dispatcher** | **Driver** | **Accountant** | **Customer** |
| ---- | ---- | ---- | ---- | ---- | ---- |
| Login | **YES** | **YES** | **YES** | **YES** | **YES** |
| Manage Users | **YES** | | | | |
| **ORDERS** | | | | | |
| View all the orders | **YES** | **YES** | | **YES** | |
| View dispatched orders | **YES** | **YES** | **YES** | **YES** | |
| View their order | **YES** | **YES** | | | **YES** |
| Create order | **YES** | **YES** | | | **YES** |
| Update order | **YES** | **YES** | | | |
| Complete a dispatched order | **YES** | **YES** | | **YES** | |
| Sign POD | **YES** | **YES** | **YES** | | |
| Duplicate orders | **YES** | **YES** | | | |
| Audit orders history | **YES** | | | - | |
| Email POD to client | **YES** | **YES** | | | |
| **INVOICES** | | | | | |
| Manage Invoices | **YES** | | | **YES** | |
| **CHECKS** | | | | | |
| Manage Checks | **YES** | | | **YES** | |
| **REPORTS** | | | | | |
| View reports | **YES** | | | | |
| **OTHER** | | | | | |
| Manage Cities | **YES** | **YES*** | | | |
| Manage Customers | **YES** | **YES*** | | | |
| Manage Drivers | **YES** | **YES** | | | |
| Manage Equipment | **YES** | **YES** | | | |
| Manage Equipment Type | **YES** | **YES** | | | |
| Manage Expenses | **YES** | **YES*** | | **YES** | |
| Manage Legs | **YES** | **YES** | | | |
| Manage Rates | **YES** | **YES*** | | **YES** | |
| Manage Settings | **YES** | | | | |
| Manage Shippers/Receivers | **YES** | **YES** | | | |
| Manage Taxes | **YES** | | | **YES** | |
| Manage Terminals | **YES** | **YES*** | | | |
| Manage Website Content | **YES** | | | | |
| Manage Zones | **YES** | | | | |

!!! info "Dispatcher abilities marked with YES* are conditional:"
    - **Can Manage Rates** permissions (Cities, Expenses, Rates, Audit orders): Enable per dispatcher user in their profile settings.
    - **Manage Customers** and **Manage Terminals**: Require system configuration (contact your administrator).
