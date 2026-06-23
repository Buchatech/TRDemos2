# Scope: ShiftSwap MVP (Sprint 1)

## Sprint Goal (Sprint 1)
Deliver a usable MVP that allows hourly employees to post shifts for coverage and request open shifts, with manager approval required before any swap is finalized.

## In Scope (MVP)
- Employee can create an open shift request with core details (date, time, location/role, optional note).
- Employees can view available open shifts and submit a pickup request.
- Manager can review requests and approve or reject swaps.
- System tracks and displays request status (Open, Pending Approval, Approved, Rejected).
- Basic role-based access for employees and managers.
- Minimal audit visibility (who requested, who approved/rejected, and when).

## Out of Scope (v1)
- **Single Sign-On (SSO) / enterprise identity integration:** Deferred to reduce security/infrastructure complexity and avoid identity-provider dependencies during MVP delivery.
- **Payroll/timekeeping integration:** Deferred because mapping approvals directly into payroll systems adds integration risk and requires additional compliance validation.
- **Third-party scheduling platform integrations (e.g., UKG, Workday, ADP connectors):** Deferred to keep Sprint 1 focused on validating core workflow before investing in connector development and vendor API dependencies.
- Advanced mobile-native app experience (iOS/Android) beyond responsive web.
- Automated rule engines for complex labor-contract edge cases.
- Analytics dashboards beyond basic status visibility.
