# Status Report Drafting — Practical Scenario

## Use Case

Drafting tailored weekly progress reports for both internal engineering leadership and external client stakeholders from raw weekly work logs.

---

## Context Files Used

- `contexts/PM_CONTEXT.md`
- `contexts/STATUS_REPORT_CONTEXT.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
Project: Project Alpha (Fictitious)
Reporting Cycle: Week 8
Audiences: Internal Delivery Head, Client Lead A

[Completed This Week]
- UI screen design review (List and Detail views) completed and approved
- Database Architecture Specification v1.1 revisions finalized
- Core implementation of External Integration Module completed (unit tests pending)

[Incomplete / Carried-Over Work]
- Unit testing for External Integration Module (deferred to early next week)
- Test Plan Specification v1.0 initial draft (scheduled to kick off next week)

[Variances & Delays]
- External Integration Module: Currently 1 week behind baseline
  Root Cause: Development paused awaiting client data specification confirmation

[Active Blockers]
- Data specification clarification from Client Lead A pending response (carried over from Week 7)
- Backend I/F alignment partially resolved in weekly sync; 1 technical point remains unconfirmed

[Active Delivery Risks]
- Test plan design delay risks compressing downstream integration testing
- Schedule alignment with external partner system for integration testing unconfirmed

[Items Awaiting Client Action]
- Data specification confirmation (escalated with response deadline set for end of this week)

[Upcoming Plan (Next Week)]
- Execute unit testing for External Integration Module
- Draft Test Plan Specification v1.0
- Weekly client progress sync (alignment with Client Lead A)
- Finalize remaining backend I/F definition point
```

---

## Prompt

```text
After loading the context files below, draft a comprehensive status report based on the provided weekly update.

[Context Files]
- contexts/PM_CONTEXT.md
- contexts/STATUS_REPORT_CONTEXT.md

[Weekly Project Data]
(Paste the Sanitized Input above)

Please generate:
1. Internal Management Status Report (for Delivery Head / PMO)
2. Client-Facing Status Report
3. Executive Summary (3 lines maximum)
4. Risk-Weighted Status Table
5. Immediate Action Item Checklist
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Internal Management Status Report (Delivery Head & PMO)

**Subject:** Project Alpha - Weekly Status Report - Week 8

**Overall Status:**
This week, screen design reviews and DB specification updates were successfully concluded. The core implementation of the external integration module was completed; however, it remains 1 week behind baseline due to delayed client data specifications. A recovery plan is underway to absorb the variance once specifications are approved.

**Completed Deliverables:**
- Screen design review completed for List and Detail views
- DB Architecture Specification v1.1 revisions signed off
- External Integration Module core logic implemented

**Carried-Over Work:**
- External Integration unit testing (rescheduled for early Week 9)
- Test Plan v1.0 initial draft (rescheduled for Week 9)

**Variances & Concerns:**
- External integration is 1 week behind. Recovery trajectory depends on receiving client data specs by end of this week.
- Test design has not started. Early Week 9 kickoff is critical to safeguard the downstream qualification window.

**Pending Client Actions:**
- Data specification approval (Due: End of this week).

**Next Week Plan:**
Execute external integration unit tests, draft test plan specification, conduct weekly steering sync.

---

### 2. Client-Facing Status Report

**Subject:** [Project Alpha] Weekly Progress Update - Week 8

Dear Client Lead A,

Please find below our progress summary for Week 8.

**Key Achievements This Week:**
- Successfully finalized and signed off the UI design reviews for both List and Detail views.
- Updated and incorporated feedback into the Database Architecture Specification.
- Completed the foundational implementation for the External Integration Module.

**Upcoming Milestones (Next Week):**
- Execute unit and functional validation on integration modules.
- Formulate the initial draft of the Test Plan Specification.
- Align on remaining technical checkpoints during our weekly sync.

**Action Items & Approvals Requested:**
Regarding the data specifications submitted for review last week, we would greatly appreciate receiving your formal confirmation by the end of this week. This sign-off is essential to maintain our target delivery trajectory for subsequent integration gates.

Thank you for your ongoing partnership.

Sincerely,  
Project Management Team

---

### 3. Executive Summary (3 Lines Max)

External integration module is 1 week behind baseline awaiting client data specifications, with confirmation expected by week-end to enable schedule recovery. Test plan design kicks off early next week to prevent downstream compression of the QA window.

---

### 4. Risk-Weighted Status Table

| Risk Description | Severity & Blast Radius | Mitigation / Contingency Plan |
|---|---|---|
| Continued external integration slip | High: Will propagate across critical path | Response deadline set with client; recovery dev plan ready upon receipt |
| Unstarted test plan design | High: Threatens to compress QA window | Early Week 9 kickoff locked; resources assigned |
| Partner system test alignment unconfirmed | Medium: Risks integration test delay | Initiate formal scheduling alignment next week |

---

### 5. Immediate Action Item Checklist

| # | Action Item | Assigned Role | Target Deadline |
|---|---|---|---|
| 1 | Follow up on client data spec approval with Client Lead A | PM | End of Week 8 |
| 2 | Execute External Integration unit tests | Dev Team | Early Week 9 |
| 3 | Kick off Test Plan Specification draft | PM / Tech Lead | Mid Week 9 |
| 4 | Finalize remaining backend I/F definition point | Tech Lead | Weekly Sync |
| 5 | Initiate integration testing schedule alignment with partner | PM | Week 9 |

---

## Human Review Points

Before sending:
- Verify that client communication tone aligns with established relationship diplomacy.
- Ensure factual justifications for delays match previously approved steering committee minutes.
- Confirm assigned roles reflect actual team staffing.
