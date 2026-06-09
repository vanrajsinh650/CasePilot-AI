# UiPath RPA Integration Build Notes

This document provides details on configuring and running the UiPath automation scripts that integrate with CasePilot AI.

## Workflow Overview

1. **Dispatcher Robot**:
   - Polls external email inboxes or ticketing systems.
   - Extracts attachments or message bodies and formats them into a CSV row.
   - Appends the row to `sample-data/signals_raw.csv`.

2. **Performer Robot**:
   - Monitores the CasePilot AI output folder for new reports.
   - Reads the generated report (markdown/text).
   - If the report requires escalation, creates a ticket in ServiceNow and assigns it to the Compliance Queue.
   - Sends email notifications to compliance managers.

## Requirements & Setup
- **UiPath Studio Version**: 2026.4 or later
- **Dependencies**:
  - `UiPath.Mail.Activities`
  - `UiPath.Excel.Activities`
  - `UiPath.WebAPI.Activities` (for calling CasePilot local API endpoints)

## Execution Instructions
1. Open the project folder in UiPath Studio.
2. Verify the configuration settings in `Assets` (Orchestrator assets for API paths).
3. Run the `Main.xaml` workflow in debug or normal mode.
