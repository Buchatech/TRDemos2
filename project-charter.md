# Project Charter: ShiftSwap MVP

## Project Purpose
Deliver a simple web app that helps hourly employees request shift coverage and pick up open shifts, while requiring manager approval before any swap is finalized. The MVP will reduce manual coordination through texts/calls and improve schedule visibility and control.

## Objectives
1. Enable employees to post shifts they need covered with essential details (date, time, location/role).
2. Enable coworkers to view and request available open shifts.
3. Route each proposed swap to a manager for approve/reject decision before it becomes final.
4. Provide basic status tracking for all parties (Open, Pending Approval, Approved, Rejected).
5. Deliver a working MVP within one 2-week Sprint 1, ready for limited pilot use.

## Stakeholders & Roles
- **Operations Manager (Sponsor/Product Owner proxy):** Defines operational priorities, approves process fit, accepts MVP for pilot.
- **HR Director (Policy Owner):** Confirms compliance with labor and HR policy, reviews approval workflow requirements.
- **Dev Lead (Delivery Owner):** Owns technical scope, architecture, sprint execution, and release readiness.
- **Frontline Employees (Primary Users):** Post and claim shifts, provide usability feedback during pilot/UAT.

## Success Criteria
- 100% of shift swaps in the MVP require explicit manager approval before finalization.
- Employees can complete core actions (post shift, request pickup, check status) end-to-end in under 3 minutes.
- At least one pilot team can execute the full swap workflow in Sprint 1 UAT with no blocker defects.
- Stakeholders (Ops + HR + Dev Lead) sign off that MVP is fit for controlled pilot.

## High-Level Timeline
- **Days 1-2:** Finalize MVP scope, workflow, acceptance criteria, and UX wireframes.
- **Days 3-8:** Build core features (post shift, open shifts list, request flow, manager approval).
- **Days 9-10:** System/integration testing, defect fixes, UAT with pilot users, release decision.

## Assumptions & Constraints
- Single 2-week sprint only; non-MVP features are deferred.
- Web app only (no native mobile app in Sprint 1).
- Authentication/authorization will be basic but sufficient for role-based access (employee vs manager).
- Integrations with payroll/timekeeping systems are out of scope for Sprint 1.
- Team availability and stakeholder review windows are sufficient to complete sign-off within sprint.
