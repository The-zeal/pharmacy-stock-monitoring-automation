# Workflow Export

This folder contains the exported n8n workflow for the Pharmacy Stock Monitoring Automation project.

## File

**`pharmacy-stock-monitoring-automation-sanitized.json`**

The workflow automates pharmacy inventory monitoring by:

- Retrieving inventory records from Google Sheets.
- Checking stock levels against minimum stock requirements.
- Identifying low-stock products.
- Sending email notifications for newly detected low-stock items.
- Preventing duplicate alerts while an item remains low in stock.
- Resetting alert status when stock is replenished.
- Logging inventory execution results.
- Supporting error notifications.

## Import Instructions

1. Download the JSON workflow file.
2. Open your n8n instance.
3. Import the workflow from the downloaded JSON file.
4. Configure your own Google Sheets credentials and inventory spreadsheet.
5. Configure your Data Table and email credentials.
6. Review the workflow settings and test all nodes before activating it.

**Note:** This is a sanitized portfolio export. Personal email addresses, credentials, and private spreadsheet identifiers have been removed or replaced with placeholders. The workflow requires configuration before use.
