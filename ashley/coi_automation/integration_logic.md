# COI Automation — Integration Logic

## A. Storis → SharePoint via API
**Trigger:** Delivery scheduled in Storis + XCOI identifier applied

System auto-creates SharePoint record with:
- Sale Number, Customer Name, Delivery Date
- Store Location, Guest Address, Building Management Info
- Initial status = "Pending Customer"

## B. SharePoint → Customer Notification
**Trigger:** SharePoint record creation

- Automated email to customer
- Secure upload link tied to specific SharePoint item
- Reminder automation if no response

## C. Customer Upload → Broker Routing
**Trigger:** Attachment added to SharePoint record

- Power Automate triggers email from coi@ashleyne.com
- Document forwarded to broker
- Status updated to "With Broker"
- Timestamp logged

## D. Broker Response → SharePoint Update
**Trigger:** Broker replies to coi@ashleyne.com

- Match email to Sale Number or XCOI reference
- Attach returned COI to SharePoint record
- Status → "Broker Returned"
- Auto-forward to building management email
- Status → "Completed"

## E. Escalation Logic
Manager alerts when:
- No customer response within defined window
- Broker SLA exceeded
- Delivery within 48 hours and COI incomplete

## Status Flow
```
Pending Customer → With Broker → Broker Returned → Completed
```
