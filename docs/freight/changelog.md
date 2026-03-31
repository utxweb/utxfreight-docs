# Changelog

## Release 2.25

### Orders

- Add **last free day** to the listing for Imports for customers view

### Tagging

- Add the ability to make the tagging mandatory for all orders

## Release 2.11

### Dispatch

- Add Port of Montreal bulk update modal

## Release 2.10

### Invoices

- Automatically include the PO# in the invoice email subject

## Release 2.9

### Dispatch

- Include all the Orders in progress with a Last Free Date
- Add the **Last Free Date (LFD)** filter for the date range
- Add the **No Date** and **Any Date** filters

### Track and Trace

- Hide **new** Orders when there is no information available from CN
- Limit the history changes to the last few relevant items

## Release 2.8

### Audit

- Fix: The history window not displaying occasionally

### Customers

- Standardize Customer address book with all Canada / US provinces and states

### Dispatch

- Make the container filter exclusive
- Add the pickup number to searchable fields

### Invoices

- Highlight active companies when creating **Invoices**

### Reports

- Highlight active companies in the selection menu

### Statement

- Remove disabled companies from reporting

### Track and Trace

- Add **Port of Montreal** container tracking
- Add **Container** information for Termont 68 and Viau 52
- Add **Last Free Date** for CN tracking

## Release 2.7

### Reports

- Add **Income by Shipper**
- Add totals to **Income by Customer**

### Orders

- Add **pickup number** to the listing for Imports

## Release 2.6

### Orders

- Inline edit for **Purchase Order, Container Size, Steamship Line** and **Terminal**
- Normalize the **container number**

### Tagging

- Add the ability to set a **default tag** for each customer

### Track and Trace

- Add **Container** movement history
- Track container **Destination ETA** updates

## Release 2.5

### Dispatch

- Enable **Dispatch** filter toggling to improve user experience
- Add the Order **Pickup Number** to the Dispatch page

### Warehouse Addon ( Pro Module )

- Documentation coming soon

## Release 2.4

### Dispatch

- Improve the **Dispatch** filtering to support combined filters, **ETA** and **Delivery** date filtering, **Terminal** filtering and container status combined with text search.

### Orders

- Add the ability to export **open** orders to **CSV**

## Release 2.3

### Track and Trace

- Add **CN** Track'n Trace scheduler
- Add **CN** Track'n Trace  modal on the **Dispatch** page
- Add **CN Terminal** filter on the **Order** and **Dispatch page**

## Release 2.2

### Dispatch

- Enhance the **driver link** to display the driver name when copying the link

### Invoices

- New **clean** invoice template optimized to fit more information on a single page

### Orders

- Add **confirmation** messages before performing assertive actions such as delete or reset orders

## Release 2.1

### Equipments

- Add a sub type to the Equipments Type in order to categorize the Equipment into **Chassis, Trailers and Trucks**
- Add a **search box, pagination** and multiple **filters** on the Equipment list page. The new filters include **Inspection Due, Inspection Past Due, Chassis, Trailers and Trucks**
- Add an **Export to CSV** button to the Equipment list page
- Add the ability to **Enable / Disable** the equipment directly from the Equipment list page
- Add clear codes ( green, orange and red ) for the different Equipment attributes such as **Inspection Status, Mechanical Status, Order Assignment and Active Status.** Those attributes determine the Equipment  **Current Availability**
- Add a quick view of the Equipment list on the **Orders** page
- Improve the **Equipment Selection** on the Orders and Dispatch page to display **only active** equipment. Also inform the user of any problems with the equipment when assigning it to the Order.

### Orders

- Add a **Magic Link** that can be sent to drivers which allows them to auto-login to the application and see their assigned **Work Orders**
- Make the Order history modal scrollable

### SMS Addon ( Pro Module )

- Add an **SMS module** which allows to send SMS messages to Drivers with the **Magic Link** to auto login to the mobile application
