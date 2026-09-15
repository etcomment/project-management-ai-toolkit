# Issue & Risk Review — Practical Scenario

## Use Case

Auditing an active issue backlog from a senior PM perspective to uncover governance gaps, reprioritize blockers, and identify latent project risks.

---

## Context Files Used

- `contexts/PM_CONTEXT.md`
- `contexts/ISSUE_RISK_CONTEXT.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
Project: Project Alpha (Fictitious)
Review Date: Week 9

[Active Issue Backlog]

Issue #1
  Title: Data synchronization interface specifications unconfirmed
  Status: In Progress
  Owner: Tech Lead
  Deadline: End of this week (awaiting client sign-off)
  Impact Scope: Entire External Integration Module
  Action Plan: Formal review request submitted to Client Lead A. Awaiting response.
  External Dependency: Requires client sign-off

Issue #2
  Title: Test Plan Specification document not drafted
  Status: Not Started
  Owner: Unassigned
  Deadline: None
  Impact Scope: Entire QA testing phase (Integration & UAT)
  Action Plan: Kickoff planned for next week
  External Dependency: None

Issue #3
  Title: Backend I/F architectural definition misalignment
  Status: Partially Resolved, 1 technical point outstanding
  Owner: Tech Lead, Backend Dev
  Deadline: Next weekly team sync
  Impact Scope: Frontend-to-Backend data exchange contract
  Action Plan: Final confirmation during upcoming technical sync
  External Dependency: None

Issue #4
  Title: Integration test schedule with external system partner not aligned
  Status: Not Started
  Owner: PM
  Deadline: None
  Impact Scope: Entire integration testing window
  Action Plan: Initiate alignment next week
  External Dependency: Partner technical counterpart schedule availability

Issue #5
  Title: Date for formal Go/No-Go release gate meeting unconfirmed
  Status: Not Started
  Owner: Unknown
  Deadline: Unknown
  Impact Scope: Overall release process and launch gate
  Action Plan: None
  External Dependency: Coordination with Client Lead A required
```

---

## Prompt

```text
After loading the context files below, review the active issue backlog from a senior PM perspective.

[Context Files]
- contexts/PM_CONTEXT.md
- contexts/ISSUE_RISK_CONTEXT.md

[Active Issue Backlog]
(Paste the Sanitized Input above)

Structure your audit across these dimensions:
1. Issue Categorization Matrix
2. Priority Realignment with Technical Rationale
3. Governance Gap Identification (Unassigned / Missing Deadlines)
4. Ambiguous Scope & Understated Blast Radius
5. Latent Delivery Risks
6. Escalation Candidate Shortlist
7. Immediate Action Plan
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Issue Categorization Matrix

| Category | Issue ID | Summary |
|---|---|---|
| External / Client Dependencies | Issue #1, #4, #5 | Data sync specs, partner test alignment, release gate scheduling |
| Internal Technical Architecture | Issue #3 | Backend I/F alignment |
| Governance, Planning & Staffing | Issue #2 | Test plan specification unstarted |

---

### 2. Priority Realignment with Technical Rationale

| Issue ID | Current Status | Recommended Priority | Justification & Critical Path Impact |
|---|---|---|---|
| Issue #2 | Not started, Unassigned, No deadline | **P1 - Critical** | Test planning delay paralyzes downstream QA. Threatens go-live milestone directly. |
| Issue #1 | Awaiting client response | **P2 - High** | Halting external integration. Must prepare dev team for immediate execution upon receipt. |
| Issue #5 | Unowned, No action plan | **P2 - High** | Risks reaching deployment deadline without agreed-upon release acceptance criteria. |
| Issue #4 | Unstarted, No deadline | **P2 - High** | Partner availability constraints could impose non-negotiable schedule slips. |
| Issue #3 | Partially resolved | **P3 - Medium** | Localized technical point. Finalize in upcoming scheduled sync. |

---

### 3. Governance Gap Identification (Missing Owners / Deadlines)

| Issue ID | Governance Vulnerability | Recommended Corrective Action |
|---|---|---|
| Issue #2 | Unassigned, No target date | Designate a lead QA author and set a firm completion deadline this week. |
| Issue #5 | No owner, no deadline, no action plan | PM must assume direct ownership and initiate formal scheduling with client leadership. |

---

### 4. Ambiguous Scope & Understated Blast Radius

- **Issue #5 (Release Gate Meeting)**: Understated as merely "scheduling a meeting". In reality, it involves agreeing on Definition of Done, critical defect thresholds, roll-back criteria, and executive sign-off authority.

---

### 5. Latent Delivery Risks

- **QA Window Compression**: Issues #2 (test design delay) and #4 (partner test misalignment) compound, threatening to crush the regression testing window.
- **Third-Party Partner Inertia**: Issue #4 relies on external partner bandwidth; unaligned schedules frequently cause multi-week delays.
- **Subjective Release Criteria**: If Issue #5 is unaddressed, the client may refuse acceptance at the final hour based on informal expectations.

---

### 6. Escalation Candidate Shortlist

- **Issue #5 (Release Gate Criterial & Schedule)**: PM must assume ownership and engage Client Lead A immediately; escalate to executive sponsors if alignment stalls.
- **Issue #2 (Test Plan Ownership)**: If internal staffing constraints prevent assigning a qualified test lead, escalate to engineering director for immediate staffing support.

---

### 7. Immediate Action Plan

| # | Action Item | Assigned Role | Target Deadline |
|---|---|---|---|
| 1 | Assign owner and lock in delivery date for Issue #2 (Test Plan) | PM | End of this week |
| 2 | Initiate formal alignment on Issue #5 (Release gate date & criteria) | PM | End of this week |
| 3 | Send formal scheduling inquiry for Issue #4 (Partner test window) | PM | Early next week |
| 4 | Prepare dev team for immediate mobilization upon receipt of Issue #1 | Tech Lead | Ongoing |
| 5 | Resolve final technical point for Issue #3 | Tech Lead | Next Weekly Sync |

---

## Human Review Points

Before acting on this audit:
- Confirm whether the reprioritization aligns with negotiated contractual milestone penalties.
- Verify whether escalation recommendations adhere to internal company governance thresholds.
