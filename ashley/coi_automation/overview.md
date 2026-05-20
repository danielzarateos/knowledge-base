# COI Automation — Home Delivery

Project: XCOI Workflow Automation & Systems Integration
Executive Sponsor: James Bader
Department: Home Delivery
Desired Start Date: March 9, 2026

## Summary
Automate the Certificate of Insurance (COI) workflow for Home Delivery. Replace manual XCOI processing (2 FTEs, ~$88K/year) with an event-driven, exception-based oversight model using Storis API, SharePoint, and Power Automate.

## Current State
- 2 full-time employees manage COI process entirely by hand
- 4,000 hours annually / 16 hours per day
- $88,000 annual labor cost
- Systems not integrated: Storis, SharePoint, coi@ashleyne.com mailbox

## Target State
- ~1,000 hours oversight annually / ~4 hours per day
- $22,000 annual cost
- **$66,000 projected annual savings**
- 75-85% hour reduction
- Payback period: less than 1 year

## Systems
| System | Role |
|--------|------|
| Storis | Source system — delivery scheduling, XCOI identifier, Sale Number |
| API Layer | Trigger automation, pass data, monitor status, match replies |
| SharePoint | Workflow engine — COI list, document storage, status, escalations |
| Outlook (coi@ashleyne.com) | Broker communication channel |
