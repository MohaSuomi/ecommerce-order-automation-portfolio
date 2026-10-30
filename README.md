# E-commerce Order Automation
![E-commerce Order Automation](E-commerce%20Order%20Automation.png)

### Automated Order Processing Built with n8n

## Project Overview
An e-commerce order automation workflow built with n8n that receives incoming orders through a webhook, structures the order data, checks for duplicates, stores validated orders in Google Sheets, and sends Gmail notifications for new orders.

The system demonstrates practical business automation for small e-commerce operations using familiar tools that non-technical business owners can easily understand and manage.

## Key Features
- **Webhook Order Intake:** Receives new order data through an HTTP webhook.
- **Data Structuring:** Extracts and formats essential order information.
- **Duplicate Detection:** Checks Google Sheets for an existing order before processing.
- **Conditional Logic:** Processes only new orders and stops duplicate ones.
- **Google Sheets Integration:** Saves and updates order records in a spreadsheet.
- **Automatic Order Status:** Assigns new orders the default status `New`.
- **Gmail Notifications:** Sends an automatic email alert when a new order is received.
- **Client-Friendly Design:** Uses Google Sheets as the client-facing system instead of requiring access to n8n.

## Technologies & Skills
- n8n — Workflow Automation
- Webhooks — Order Intake
- Google Sheets API — Order Storage and Management
- Gmail API — Email Notifications
- Conditional Logic — Duplicate Prevention
- Data Mapping — Structured Order Processing
- Business Process Automation

## How It Works
1. A new order is sent to the workflow through a webhook.
2. The system extracts the important fields from the incoming payload.
3. It checks Google Sheets to see whether the order ID already exists.
4. If the order already exists, the workflow stops and no duplicate notification is sent.
5. If the order is new, the workflow restores the clean order data.
6. The order is written to Google Sheets with the default status `New`.
7. A Gmail notification is sent to the store owner.

## Testing & Results
Successfully demonstrated:
- Receiving test orders through webhook requests
- Structuring incoming order data
- Saving new orders to Google Sheets
- Automatically assigning `New` as the initial order status
- Sending Gmail notifications for new orders
- Preventing duplicate order processing in tested scenarios

## Business Value
This workflow helps online sellers reduce manual admin work by automatically recording incoming orders, preventing duplicate handling, and notifying the store owner immediately.

Using Google Sheets as the visible order management layer also makes the solution easy for small business owners to inspect and use without needing to learn n8n.

## Project Status
**Functional portfolio prototype — not a production deployment.**

The system has been tested successfully for manual workflow executions and duplicate prevention scenarios. Additional security, concurrency protection, platform-specific integrations, and production hardening would be required for real-world deployment.

## Implementation & Demonstration
The complete n8n workflow is maintained privately.

This public repository documents the workflow architecture, capabilities, and testing results without distributing the full implementation.

Live demonstration available upon request.
