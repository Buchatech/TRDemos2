# ShiftSwap Requirements Traceability Matrix

## Validation Review Summary

### Missing traceability (resolved in this update)
- Added standardized PB issues `PB-001` through `PB-014` with `requirement` labels.
- Added linked test case issues `TC-001` through `TC-014` with `test-case` labels.
- Added linked evidence issues `EV-001` through `EV-014` with `evidence` labels.
- Added `deferred` labels for future-release requirements (`PB-011` to `PB-014`).

### Potential compliance or governance gaps
- Evidence artifacts are still in `Pending` state, so no requirement has execution proof yet.
- Requirement `PB-007` (audit trail) does not yet include objective validation output demonstrating retention and access control behavior.
- Requirement `PB-009` (overtime warning) lacks policy-level evidence confirming labor-rule coverage beyond the baseline 40-hour threshold.
- Existing backlog items `#6`, `#9`, and `#11` are not currently mapped to explicit `RQ-*` requirements and should be reconciled or reclassified.

### Requirements that are ambiguous or not fully testable yet
- Eligibility logic for who can claim a shift is still broad ("eligible coworkers") and needs explicit role/site rule criteria.
- Escalation threshold governance needs confirmation on whether the 4-hour default is globally fixed or configurable.
- Notification fallback behavior between SMS and optional channels is not fully specified for outage scenarios.
- Employee-ID login requirements do not yet define minimum security controls (e.g., lockout, retry policy).

### Missing acceptance criteria (resolved)
- All `PB-*` requirement issues now include explicit acceptance criteria sections.

### Missing validation evidence
- All linked evidence issues are currently placeholders pending test execution and artifact upload.

### Deferred requirements (future release)
- `RQ-011` Slack integration (`PB-011`)
- `RQ-012` Direct payroll integration (`PB-012`)
- `RQ-013` Enterprise SSO integration (`PB-013`)
- `RQ-014` Push-notification-first experience (`PB-014`)

## Traceability Matrix

| Req ID | Requirement | PB ID / GitHub Issue | Acceptance Criteria | Test Case Issue(s) | Validation Type | Evidence Link(s) | Status | Owner | Notes / Proof |
|---|---|---|---|---|---|---|---|---|---|
| RQ-001 | Post an open shift | [PB-001 / #5](https://github.com/Buchatech/TRDemos2/issues/5) | Create open shift with required fields; visibility to eligible coworkers; timestamped posting; initial status Open | [TC-001 / #23](https://github.com/Buchatech/TRDemos2/issues/23) | Functional + UAT | [EV-001 / #24](https://github.com/Buchatech/TRDemos2/issues/24) | Open | Operations Manager | Reopened pending evidence completion. |
| RQ-002 | Claim an open shift | [PB-002 / #7](https://github.com/Buchatech/TRDemos2/issues/7) | Claim Open shift; move to Pending Approval; notify poster/manager; audit timestamp | [TC-002 / #25](https://github.com/Buchatech/TRDemos2/issues/25) | Functional + UAT | [EV-002 / #26](https://github.com/Buchatech/TRDemos2/issues/26) | Open | Frontline Employee | Awaiting test execution evidence. |
| RQ-003 | Cancel a claim before approval | [PB-003 / #13](https://github.com/Buchatech/TRDemos2/issues/13) | Cancel allowed only in Pending Approval; return to Open; notify stakeholders; audit event logged | [TC-003 / #27](https://github.com/Buchatech/TRDemos2/issues/27) | Functional + UAT | [EV-003 / #28](https://github.com/Buchatech/TRDemos2/issues/28) | Open | Frontline Employee | Awaiting test execution evidence. |
| RQ-004 | Approve or reject swap requests | [PB-004 / #8](https://github.com/Buchatech/TRDemos2/issues/8) | Manager queue for Pending Approval; approve/reject action; approved finalizes; decision timestamp recorded | [TC-004 / #29](https://github.com/Buchatech/TRDemos2/issues/29) | Functional + UAT | [EV-004 / #30](https://github.com/Buchatech/TRDemos2/issues/30) | Open | Operations Manager | Awaiting test execution evidence. |
| RQ-005 | Notify users through reliable channels (SMS-first) | [PB-005 / #14](https://github.com/Buchatech/TRDemos2/issues/14) | SMS for key events; status-driven triggers; failure logging; push/email optional in MVP | [TC-005 / #31](https://github.com/Buchatech/TRDemos2/issues/31) | Functional + Operational | [EV-005 / #32](https://github.com/Buchatech/TRDemos2/issues/32) | Open | Dev Lead | Channel fallback policy still needs formal definition. |
| RQ-006 | Escalate unclaimed shifts | [PB-006 / #15](https://github.com/Buchatech/TRDemos2/issues/15) | Detect approaching unclaimed shifts; notify manager at threshold; include shift details; log escalation event | [TC-006 / #33](https://github.com/Buchatech/TRDemos2/issues/33) | Functional + UAT | [EV-006 / #34](https://github.com/Buchatech/TRDemos2/issues/34) | Open | Operations Manager | Need governance confirmation on threshold configurability. |
| RQ-007 | Maintain full audit trail | [PB-007 / #10](https://github.com/Buchatech/TRDemos2/issues/10) | Full actor/action timestamps; 90-day retention; authorized role visibility; no final swap without manager approval record | [TC-007 / #35](https://github.com/Buchatech/TRDemos2/issues/35) | Compliance + Audit Review | [EV-007 / #36](https://github.com/Buchatech/TRDemos2/issues/36) | Open | HR Director | High compliance priority; objective retention proof still pending. |
| RQ-008 | Export 90-day swap history | [PB-008 / #17](https://github.com/Buchatech/TRDemos2/issues/17) | Authorized CSV export; trailing 90-day support; include audit fields; export action auditable | [TC-008 / #37](https://github.com/Buchatech/TRDemos2/issues/37) | Functional + Compliance | [EV-008 / #38](https://github.com/Buchatech/TRDemos2/issues/38) | Open | HR Director | Awaiting export evidence artifact upload. |
| RQ-009 | Flag overtime risk for manager review | [PB-009 / #18](https://github.com/Buchatech/TRDemos2/issues/18) | Compute warning pre-decision; warning-only behavior; risk shown in review context; manager-controlled decision | [TC-009 / #39](https://github.com/Buchatech/TRDemos2/issues/39) | Functional + Policy Review | [EV-009 / #40](https://github.com/Buchatech/TRDemos2/issues/40) | Open | Operations Manager | Requires policy confirmation for jurisdictional edge cases. |
| RQ-010 | Simple internal login | [PB-010 / #4](https://github.com/Buchatech/TRDemos2/issues/4) | Employee-ID login; role separation; no SSO dependency in MVP; access attempts logged | [TC-010 / #41](https://github.com/Buchatech/TRDemos2/issues/41) | Functional + Security Review | [EV-010 / #42](https://github.com/Buchatech/TRDemos2/issues/42) | Open | Dev Lead | Security control detail should be expanded before release sign-off. |
| RQ-011 | Slack integration for shift updates | [PB-011 / #19](https://github.com/Buchatech/TRDemos2/issues/19) | Deferred from MVP; future posting/status updates; configurable channel mapping; security gating | [TC-011 / #43](https://github.com/Buchatech/TRDemos2/issues/43) | Integration Test (Future Release) | [EV-011 / #44](https://github.com/Buchatech/TRDemos2/issues/44) | Deferred | Product Owner | Explicitly deferred to later release. |
| RQ-012 | Direct payroll integration | [PB-012 / #20](https://github.com/Buchatech/TRDemos2/issues/20) | Deferred from MVP; future payroll sync with reconciliation; rollback/audit controls; compliance gate | [TC-012 / #45](https://github.com/Buchatech/TRDemos2/issues/45) | Integration + Compliance Test (Future Release) | [EV-012 / #46](https://github.com/Buchatech/TRDemos2/issues/46) | Deferred | HR Director | High-risk integration deferred intentionally. |
| RQ-013 | Enterprise SSO integration | [PB-013 / #21](https://github.com/Buchatech/TRDemos2/issues/21) | Deferred from MVP; IdP + role mapping in future; authentication auditability retained; security approval gate | [TC-013 / #47](https://github.com/Buchatech/TRDemos2/issues/47) | Security + Integration Test (Future Release) | [EV-013 / #48](https://github.com/Buchatech/TRDemos2/issues/48) | Deferred | IT Security | Deferred to avoid MVP identity complexity. |
| RQ-014 | Push-notification-first experience | [PB-014 / #22](https://github.com/Buchatech/TRDemos2/issues/22) | Deferred from MVP; future push preference model; fallback delivery retained; mobile plan gate | [TC-014 / #49](https://github.com/Buchatech/TRDemos2/issues/49) | Functional Test (Future Release) | [EV-014 / #50](https://github.com/Buchatech/TRDemos2/issues/50) | Deferred | Product Owner | SMS-first remains baseline for MVP. |

