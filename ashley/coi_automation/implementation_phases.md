# COI Automation — Implementation Phases

## Phase 1: Integration Mapping
- Confirm API capabilities from Storis
- Map data fields between Storis and SharePoint
- Document authentication and access requirements
- **Deliverable:** Integration spec document

## Phase 2: Build
- Develop API → SharePoint integration
- Build mailbox automation
- Implement status automation logic
- Configure Power Automate workflows
- Build escalation rules
- **Deliverable:** Working automation

## Phase 3: Pilot Testing
- Run parallel operations (manual + automated)
- Validate matching logic, status updates, escalations
- Collect feedback and resolve issues
- **Deliverable:** Validated system

## Phase 4: Go Live
- Transition to exception-only oversight
- Decommission manual processing
- Monitor and optimize
- **Deliverable:** Production system

## Success Criteria
- 75%+ reduction in manual processing hours
- Zero missed COI compliance deliveries
- Fully visible status dashboard in SharePoint
- Automated SLA tracking for broker response times
- Team operates in exception-only oversight mode
- Elimination of two full-time COI processor roles

## Dependencies
- Storis API access and integration capabilities
- Consistent XCOI identifier usage in Storis
- Reliable matching logic (Sale Number / unique ID)
- Mailbox monitoring permissions for coi@ashleyne.com
- Data governance and SharePoint access control

## Strategic Value
Same framework (Storis → API → SharePoint → automated routing) reusable for:
- Home damage claims processing
- Vendor compliance tracking
- Documentation tracking and management
