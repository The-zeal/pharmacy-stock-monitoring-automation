# Pharmacy Stock Monitoring Automation

An automated pharmacy inventory monitoring system built with **n8n, Google Sheets, JavaScript, and email notifications**.

## Project Overview

This project automates routine pharmacy stock monitoring by checking inventory levels, identifying low-stock products, sending email alerts, preventing duplicate notifications, and recording workflow execution results.

It demonstrates how workflow automation can improve inventory visibility and reduce the need for repetitive manual stock checks in pharmacy operations.

## Key Features

- **Automated stock monitoring:** Retrieves inventory records from Google Sheets.
- **Stock classification:** Categorizes products as LOW STOCK, SUFFICIENT, or INVALID DATA.
- **Low-stock email alerts:** Notifies the responsible person when stock falls below the defined minimum.
- **Duplicate alert prevention:** Tracks alert states to prevent repeated notifications for the same low-stock condition.
- **Alert reset:** Updates alert status when stock levels recover.
- **Data validation:** Detects missing, negative, and invalid inventory values.
- **Execution logging:** Records product status and alert decisions in Google Sheets.
- **Error monitoring:** Sends email notifications when automatic workflow executions fail.
- **Scheduled execution:** Configured for daily monitoring at 18:00 (Africa/Lagos).

## Workflow Architecture

1. The workflow retrieves pharmacy inventory records from Google Sheets.
2. A JavaScript code node validates and classifies each product.
3. Existing alert states are retrieved and compared with current stock conditions.
4. The workflow decides whether to send a new alert, reset an existing alert, or take no action.
5. Low-stock notifications are sent by email when required.
6. Alert states are updated in an n8n Data Table.
7. Inventory execution results are recorded in Google Sheets.
8. A separate error workflow handles automatic execution failures.

## Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation |
| Google Sheets | Inventory database and execution log |
| JavaScript | Data validation and decision logic |
| Email | Low-stock and error notifications |
| Docker | Local n8n deployment |

## Testing and Validation

The workflow was tested against the following scenarios:

| Test scenario | Expected result |
|---|---|
| First low-stock detection | Send email alert |
| Repeated low-stock condition | Suppress duplicate alert |
| Stock level recovery | Reset alert state |
| New low-stock condition after recovery | Send a fresh alert |
| Missing inventory values | Classify as INVALID DATA |
| Negative inventory values | Classify as INVALID DATA |
| Automatic workflow failure | Trigger error notification |

## Business Value

This automation demonstrates how pharmacy inventory processes can be improved through:

- Faster identification of products requiring replenishment.
- Reduced repetitive manual stock checking.
- Better visibility into inventory conditions.
- Prevention of unnecessary duplicate notifications.
- Improved record keeping and operational monitoring.

## Future Improvements

- Integration with pharmacy management systems.
- Automatic stock replenishment recommendations.
- Inventory trend analysis and dashboards.
- Multi-branch pharmacy inventory monitoring.

## Author

**The-zeal**

GitHub: [https://github.com/The-zeal](https://github.com/The-zeal)




## Final Workflow Validation

The Pharmacy Stock Monitoring Automation workflow was successfully executed after the final connection corrections.

### End-to-End Test Results

| Test | Expected Result | Status |
|---|---|---|
| Low-stock detection | Identify products below minimum stock | Passed |
| Alert generation | Build a low-stock notification | Passed |
| Email notification | Deliver alert to the configured email address | Passed |
| Alert-state update | Save the alert state after notification | Passed |
| Workflow execution | Execute the connected workflow nodes successfully | Passed |

### Final Verification

- All relevant workflow nodes displayed successful execution indicators (green checkmarks).
- The low-stock alert email was successfully received.
- The workflow was published and active after the corrections.

These tests demonstrate the workflow's ability to detect low inventory, notify stakeholders, and maintain alert states while reducing unnecessary duplicate notifications.
