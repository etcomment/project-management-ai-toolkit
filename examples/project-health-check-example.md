# Project Health Check — Practical Scenario

## Use Case

Conducting an end-to-end diagnostic audit of project delivery health from a senior PM perspective.

In this scenario, a Project Manager compiles progress metrics, open blockers, staffing bottlenecks, and quality risks mid-development, prompting the AI to evaluate health, surface blind spots, and prioritize actions.

---

## Context Files Used

- `contexts/PM_CONTEXT.md`
- `contexts/PROJECT_HEALTH_CHECK.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
Project: Project Alpha (Fictitious)
Current Phase: Mid-Development (Sprint 6 of 10)

[Progress Status]
- Overall Completion: ~60%
- Delayed Workstreams: External Integration Module, QA Test Plan Design
- External Integration is currently 1.5 weeks behind baseline
- Test plan design has not yet been initiated

[Active Blockers]
- Specification clarification request sent to Client Lead A has been pending response for over 2 weeks
- Data synchronization specs unconfirmed, partially halting backend development
- High risk of interface (I/F) definition misalignment between frontend and backend teams

[Team & Staffing Concerns]
- Single code reviewer bottle-necking PR throughput due to competing operational commitments
- Tech Lead scheduled for 3 days of planned absence next week

[Quality & Non-Functional Concerns]
- Integration test window currently compressed to only 5 business days
- Unit test code coverage unverified
- Defect tracking register not yet standardized

[Delivery Constraints]
- 6 weeks remaining until final go-live milestone
- Date for formal Go/No-Go release gate meeting unconfirmed
```

---

## Prompt

```text
After loading the context files below, perform a comprehensive project health check from a senior PM perspective.

[Context Files]
- contexts/PM_CONTEXT.md
- contexts/PROJECT_HEALTH_CHECK.md

[Project Status]
(Paste the Sanitized Input above)

Structure your evaluation across these dimensions:
1. Executive Situation Summary
2. Risk Level Rating (🔴 High / 🟡 Medium / 🟢 Low) and Rationale
3. Primary Critical Concerns
4. Overlooked Risks & Blind Spots
5. Confirmations Needed from Client
6. Internal Managerial Decisions Required
7. Immediate Action Plan for Next 24 to 72 Hours
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Executive Situation Summary
Project Alpha is at 60% completion mid-development but faces significant compounding risks. Slippage in external integration and unstarted test planning are exacerbated by a two-week client response bottleneck. With a single-reviewer bottleneck and the integration test window compressed to just 5 days, quality risks to the 6-week go-live deadline are acute.

---

### 2. Risk Level Rating

**🔴 High (Immediate Action Required)**

- Recovery feasibility within the remaining 6 weeks is doubtful under current velocity.
- Test planning has not started while the integration test window is critically compressed.
- Critical architectural dependencies remain stalled awaiting client clarification.

---

### 3. Primary Critical Concerns

| # | Concern | Operational Impact & Rationale |
|---|---|---|
| 1 | Test Plan Design Unstarted | Completing test design, execution, bug fixing, and retesting within 6 weeks is at high risk of failure. |
| 2 | Client Clarification Pending 2+ Weeks | Proceeding on unconfirmed assumptions guarantees major architectural rework later. |
| 3 | Single-Reviewer Bottleneck | PR review latency will choke delivery velocity as code volume peaks. |
| 4 | Data Sync Specs Unfinalized | Root cause of external integration slip; risks data integrity across interfaces. |

---

### 4. Overlooked Risks & Blind Spots

- **Unconfirmed Go/No-Go Gate Date**: Without an agreed-upon gate date, release acceptance criteria and sign-off prerequisites remain undefined.
- **Absence of Standard Defect Register**: Defect triage will descend into chaos once integration testing starts without a centralized tracking tool.
- **Tech Lead Absence Decision Latency**: No delegation framework established for the 3-day absence next week.
- **Partner System Test Alignment**: Unknown whether external integration partner has scheduled UAT testing windows.

---

### 5. Confirmations Needed from Client

- Issue an urgent escalation email with a firm response deadline for the pending data specs.
- Formalize the sign-off procedure for external interface definitions.
- Agree upon the date and acceptance criteria for the formal Go/No-Go release gate.
- Confirm post-launch operational support and tier-2 incident escalation contacts.

---

### 6. Internal Managerial Decisions Required

- Authorize an immediate kickoff for test design (must start without delay).
- Decide whether to extend the integration test window or adjust scope to safeguard quality.
- Rebalance reviewer workload or assign a second peer reviewer to unblock PR queues.
- Formalize technical delegation authority during the Tech Lead's 3-day absence.
- Deploy a standardized bug tracking board immediately.

---

### 7. Immediate Action Plan (Next 24 to 72 Hours)

- [ ] Send formal reminder to Client Lead A regarding data specs with a firm 48-hour response deadline.
- [ ] Assign owner and lock in kickoff date for QA test design.
- [ ] Establish and communicate decision authority delegation during Tech Lead absence.
- [ ] Initiate scheduling alignment for the formal Go/No-Go release meeting.
- [ ] Deploy standard defect tracking register and triage workflow.

---

## Human Review Points

Before utilizing this output operationally:
- Verify whether the risk rating aligns with actual contractual obligations and client dynamics.
- Check that client requests adhere to agreed-upon governance protocols.
- Confirm internal resource availability before promising reviewer rebalancing.
- Verify whether unstated constraints known only to you alter the priority ranking.
