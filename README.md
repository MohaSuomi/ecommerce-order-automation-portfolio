# E-commerce Order Automation

**Automated order intake, duplicate detection, order tracking, and email alerts — built with n8n.**

![E-commerce Order Automation workflow](E-commerce%20Order%20Automation.png)

The diagram above illustrates the seven-node architecture implemented and tested in n8n.

## Project Overview

A working n8n portfolio prototype that receives e-commerce orders via an HTTP webhook, checks whether each order already exists, records new orders in Google Sheets, and emails the store owner. Google Sheets provides a familiar, client-facing place to review orders and update their status without opening n8n.

## How It Works

1. **Webhook** — receives a new order via an HTTP POST request.
2. **Edit Fields** — extracts and standardizes the order ID, customer name, email, total, and currency.
3. **Check Existing Order (Google Sheets)** — looks up the order ID.
4. **If** — sends existing orders to the stop branch and new orders onward.
5. **Restore Order Data** — prepares the clean record and sets `order_status` to `New`.
6. **Append or Update Row (Google Sheets)** — stores the new order in a spreadsheet.
7. **Send a Message (Gmail)** — emails the store owner about the new order.

## Key Features

- Automated order intake through a webhook
- Duplicate checking before saving or notifying
- Google Sheets order log and editable status dropdown
- Automatic `New` status for new orders
- Gmail notifications for newly processed orders
- No n8n knowledge required for the store owner

## Tech Stack

**n8n · Webhooks · Google Sheets API · Gmail API · Conditional Logic · Data Mapping**

## Verified Testing

The prototype was tested with sample order data:
- **New order:** successfully saved to Google Sheets with status `New`, followed by a Gmail notification.
- **Repeated order ID:** correctly found in Google Sheets, routed to the **False** branch of the If node, and stopped without a duplicate row or another email.

## Business Value

Reduces manual order-entry work, makes new orders easier to monitor, and avoids repeat notifications in the tested sequential workflow. The order log lives in Google Sheets, which business staff can use directly.

## Project Status & Availability

**Functional portfolio prototype — not a production deployment.**

Production use would require webhook authentication, concurrency-safe duplicate prevention, validation/error handling, and integration with the specific e-commerce platform. The full n8n implementation is maintained privately; this public repository documents the architecture and demonstrated results without exposing credentials or distributing the workflow JSON.
