# ShiftSwap MVP Requirements

## User Stories (Deduplicated)

### 1) Post an open shift
**User Story:** As an hourly employee, I want to post a shift I cannot work, so that coworkers can pick it up in one shared place instead of ad-hoc texts.

**Acceptance Criteria:**
- Employee can create an open shift with date, start/end time, role/location, and optional note.
- Open shift is visible to eligible coworkers immediately after posting.
- Posting action is timestamped and linked to the posting employee.
- Shift status is set to **Open** when created.

### 2) Claim an open shift
**User Story:** As an hourly employee, I want to claim an open shift, so that I can cover coworkers and fill schedule gaps quickly.

**Acceptance Criteria:**
- Employee can claim an **Open** shift from the available list.
- Claimed shift moves to **Pending Approval** state.
- Original poster and manager receive notification that a claim was submitted.
- Claim action is timestamped and recorded in audit history.

### 3) Cancel a claim before approval
**User Story:** As an employee who claimed a shift, I want to cancel my claim before manager approval, so that I am not locked in if my availability changes.

**Acceptance Criteria:**
- Claimer can cancel only while request is in **Pending Approval**.
- Canceled claim returns shift to **Open** state.
- Manager and original poster are notified of cancellation.
- Cancellation event is timestamped in audit history.

### 4) Approve or reject swap requests
**User Story:** As a manager, I want to approve or reject swap requests, so that no shift swap becomes official without oversight.

**Acceptance Criteria:**
- Manager can view all **Pending Approval** requests in one queue.
- Manager can approve or reject each request.
- Approval marks swap final; rejection returns shift to **Open** (or closes per configured rule).
- Manager decision and timestamp are captured in audit history.

### 5) Notify users through reliable channels
**User Story:** As an employee/manager, I want timely notifications on key shift events, so that I can respond before coverage gaps occur.

**Acceptance Criteria:**
- System sends SMS for key events: new open shift, claim submitted, approval/rejection outcome.
- Notification events are triggered by status changes, not manual refresh.
- Notification failures are logged for operational follow-up.
- Push/email notifications are optional and not required for MVP completion.

### 6) Escalate unclaimed shifts
**User Story:** As a manager, I want alerts when an open shift remains unclaimed near start time, so that I can intervene manually before a gap occurs.

**Acceptance Criteria:**
- System checks for open shifts approaching start time.
- Manager receives an escalation alert when a shift remains unclaimed at the configured threshold (default: 4 hours before start).
- Escalation alert includes shift details and owner information.
- Escalation events are logged.

### 7) Maintain full audit trail
**User Story:** As an HR Director, I want a complete audit trail of swap actions, so that we can satisfy payroll and compliance audits.

**Acceptance Criteria:**
- Audit records include who posted, claimed, canceled (if applicable), approved/rejected, and timestamp for each action.
- Audit history is retained for at least trailing 90 days.
- Audit data is viewable to authorized manager/HR roles.
- No swap is marked final without an associated manager approval record.

### 8) Export 90-day swap history
**User Story:** As HR, I want to export shift swap history to CSV, so that audits and reporting can be handled outside the app.

**Acceptance Criteria:**
- Authorized user can export swap records to CSV.
- Export supports trailing 90-day date range.
- Export includes core audit fields (actors, actions, timestamps, status outcome).
- Export action is itself auditable.

### 9) Flag overtime risk for manager review
**User Story:** As a manager, I want a warning when a swap may push an employee over 40 hours/week, so that I can review labor risk before approving.

**Acceptance Criteria:**
- System computes and displays overtime risk indicator before manager decision.
- Overtime risk is a warning and does not auto-block approval in MVP.
- Overtime risk presence is included in request review context.
- Overtime-related decision remains manager-controlled.

### 10) Simple internal login
**User Story:** As a frontline employee, I want a simple internal login, so that I can access the tool quickly without enterprise identity setup overhead.

**Acceptance Criteria:**
- MVP supports employee-ID-based login flow for internal users.
- Role assignment distinguishes employee and manager capabilities.
- Login approach avoids dependency on enterprise SSO in MVP.
- Access attempts are recorded for basic operational traceability.

## Conflicts & Open Questions

- **Notification channel priority is inconsistent across inputs.** Early references suggest push/email/text (“whatever works”), while later discussion prioritizes SMS due to basic-phone users. Confirm whether SMS is required and whether push/email are MVP or backlog.
- **Who can claim a shift is partially ambiguous.** One source says “anyone on the team,” while safety/operations may require role/location qualification rules. Confirm exact eligibility logic for claimers.
- **Escalation timing was proposed but may need policy validation.** “4 hours before shift start” was set in a meeting; confirm if this is globally fixed, site-configurable, or manager-configurable.
- **MVP timeline differs between planning artifacts.** Kickoff transcript references roughly two sprints, while current project direction targets a single two-week Sprint 1 MVP. Confirm final delivery cadence as a governance decision.

## Deferred / Out of Scope (Phase Later)

- **Slack integration for shift posting/updates — deferred.**  
  Source: Sticky notes (“Slack integration would be cool” with “later??”); Slack thread 9:31 AM (“deprioritize Slack integration”), Requirements session (“explicitly later”).
- **Direct payroll system integration — deferred.**  
  Source: HR Email #2 item 4 (“Please do NOT connect this directly to payroll systems in the first release”); Kickoff transcript (standalone first release); Requirements session (explicitly later).
- **Enterprise SSO integration — deferred.**  
  Source: Sticky notes (“no fancy SSO”); Slack thread 9:33 AM (“employee ID, no need for SSO for v1”); Requirements session (employee ID login for v1).
- **Push-notification-first experience — deferred behind SMS-first baseline.**  
  Source: Slack thread 9:30 AM (SMS more important than push for v1); Requirements session (push as bonus if time, not MVP dependency).
