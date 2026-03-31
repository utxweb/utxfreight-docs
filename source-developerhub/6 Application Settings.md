---
type: page
title: Application Settings
listed: true
slug: application-settings
---published

The application settings can only be accessed and configured by an administrator of the application. The settings are available from the **Your Name -> $inline[icon,fas fa-cog] Settings** dropdown menu. The settings are separated by category to which they correspond.

## Test Email Configuration

At the top of the Settings page, there is a **Test Email Configuration** section that allows you to send test emails to verify your email settings are working correctly.

| Field | Description | 
| ---- | ---- | 
| **Send Test Emails To** | Enter an email address to receive test emails. Clicking "Send Test" will send two test emails: one using the Notification Mailer settings and one using the Invoice Mailer settings. This helps verify that both email configurations are working properly. | 

## Order Settings

| Field | Description | 
| ---- | ---- | 
| **Order Archive Cutoff Date** | Only orders created after this date will show up in the Orders / Search and Dispatch pages. This is useful to improve the performance of UTX Freight by reducing the time range of accessible orders. | 

## Invoice Settings

| Field | Description | 
| ---- | ---- | 
| **GST Number** | The **GST Number** shows up on the invoice and should be set if your company has a GST Number. The format should be "#00000000RT0001" | 
| **QST Number** | The **QST Number** also shows up on the invoice and should be set if your company has a QST Number. The format should be "#0000000000TQ0001" | 
| **Default Terms** | Set the default **Invoice Terms** for all companies when creating new invoices. Available options include: Due on Receipt, 10 Days, 15 Days, 21 Days, 30 Days, 45 Days, 60 Days, 90 Days. | 
| **Order Start Date** | When creating an invoice, only orders completed after this date will show up. This is useful if you were not using UTX Freight for invoicing in the past. | 
| **Message** | The invoice message will be added to the header of each invoice and can include any accounting related information that should be communicated to the client. | 

## POD Settings

| Field | Description | 
| ---- | ---- | 
| **NIR Number** | The **NIR Number** appears on PODs (Proof of Delivery). The format should be "R-000000-0" | 
| **POD Footer** | This message will show up in the footer of each POD document. | 

## General SMTP Settings

These settings configure the base SMTP server connection that may be shared by both Invoice and Notification mailers.

| Field | Description | 
| ---- | ---- | 
| **SMTP Address** | The SMTP server address (e.g., smtp.example.com) | 
| **SMTP Port** | The SMTP server port (e.g., 587) | 
| **SMTP Authentication** | The authentication method used by the SMTP server (e.g., plain, login, cram_md5) | 

## Invoice Mailer Settings

These settings configure the email account used specifically for sending invoices to customers.

| Field | Description | 
| ---- | ---- | 
| **Domain** | Domain used for sending invoices (e.g., yourcompany.com) | 
| **Username** | Email address used to send invoices (e.g., user@example.com) | 
| **Password** | Password for the invoice email account. Leave blank when editing to keep the current password unchanged. | 

## Notification Mailer Settings

These settings configure the email account used for sending system notifications (order updates, dispatch notifications, etc.).

| Field | Description | 
| ---- | ---- | 
| **Domain** | Domain used for sending notifications (e.g., yourcompany.com) | 
| **Username** | Email address used to send notifications (e.g., notify@example.com) | 
| **Password** | Password for the notification email account. Leave blank when editing to keep the current password unchanged. | 

## Administrative Email Addresses

| Field | Description | 
| ---- | ---- | 
| **Admin Email** | Used for system notifications and as the Devise sender address for password resets and other authentication emails. | 
| **Accountant Email** | Default "From" address for invoices. This is used if the Invoice 'From' Override is not set. | 
| **Invoice 'From' Override** | Overrides the default accountant email if set. Can include a display name (e.g., "Accounting Dept <accounting@example.com>"). | 
| **Invoice Default CC** | Default CC address that will be automatically added to all invoices sent via email. | 


