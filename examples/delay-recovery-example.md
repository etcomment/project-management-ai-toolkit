# Schedule Delay Recovery — Practical Scenario

## Use Case

Structuring a schedule recovery plan when critical path delays impact both external integration modules and QA test planning.

---

## Context Files Used

- `contexts/PM_CONTEXT.md`
- `contexts/DELAY_RECOVERY_CONTEXT.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
Project: Project Alpha (Fictitious)
Review Date: Week 10

[Delayed Workstreams]
1. External Integration Module (Implementation & Unit Testing): Currently 1.5 weeks behind baseline
2. QA Test Plan Specification: Kickoff delayed by 1 week; currently drafting

[Root Causes]
1. External Integration: Development frozen awaiting client data specifications (now confirmed)
2. Test Plan: Delay in designating and onboarding a qualified QA author

[Variance Scale & Recovery Work Remaining]
- Recovering external integration slip requires a minimum of 1 focused engineer-week
- Test plan drafting is in progress, tracking 3 to 4 days behind schedule
- Outstanding tasks: Integration unit tests, partner test alignment, integration test execution, UAT, Release Gate meeting

[Critical Path]
External Integration Completion -> Integration Testing -> UAT Testing -> Release Gate Decision

[Available Resources & Levers]
- Lead Developer: Currently 100% focused on external integration
- QA Team: Ready to mobilize as soon as test plan is stabilized
- External contractor support: Feasible, but onboarding takes several business days

[Immovable Constraints]
- 3.5 weeks remaining until final go-live deadline (immovable corporate date announced by client)
- Release Gate meeting date remains unconfirmed
- Delay status has not yet been formally notified to Client Lead A
```

---

## Prompt

```text
After loading the context files below, formulate a structured schedule delay recovery strategy.

[Context Files]
- contexts/PM_CONTEXT.md
- contexts/DELAY_RECOVERY_CONTEXT.md

[Project Situation]
(Paste the Sanitized Input above)

Please structure the recovery plan across:
1. Root Cause Diagnosis
2. Critical Path Impact Assessment
3. Structured Recovery Scenarios (Options A, B, C)
4. Operational Priority Ranking
5. Task Pruning & De-scoping Candidates
6. Resource Support Requirements
7. Client Communication Strategy
8. Internal Escalation & Governance Alignment
9. Immediate Operational Plan (Next 24 to 72 Hours)
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Root Cause Diagnosis

| Delayed Task | Primary Root Cause | Current Recovery Status |
|---|---|---|
| External Integration | External blocker (waiting for client data specs) | Specifications approved; coding actively proceeding |
| Test Plan Specification | Internal governance lag (delayed staffing assignment) | Author assigned; drafting underway |

Delays result from compounding external dependency stalls and internal staffing latency.

---

### 2. Critical Path Impact Assessment

- **Integration Testing Kickoff**: Blocked until external integration finishes. QA engineers cannot begin testing upon test plan completion alone.
- **UAT Window**: The slip in integration testing directly compresses the client UAT window.
- **Release Gate**: Absence of a confirmed date prevents reverse-scheduling alignment.
- **Milestone Feasibility**: Without immediate compression of testing cycles, the 3.5-week deadline will be breached.

---

### 3. Structured Recovery Scenarios (Options A, B, C)

- **Option A: Focused Critical Path Acceleration (Recommended)**
  - Finish external integration unit tests by end of Week 10; launch integration testing early in Week 11.
  - Prioritize P1 test cases to compress testing duration without sacrificing core quality.
  - Risk: Reduced test coverage on secondary administrative flows.
- **Option B: Resource Crashing (Inject Additional Developer)**
  - Add contractor developer to assist with unit testing and test harness setup.
  - Risk: Onboarding overhead reduces immediate net velocity over a 3.5-week horizon.
- **Option C: Scope Descoping (Trade-off with Client)**
  - De-scope non-critical secondary connectors to v1.1 to safeguard core delivery.
  - Risk: Requires urgent executive negotiation and client agreement.

---

### 4. Operational Priority Ranking

| Priority | Workstream | Operational Justification |
|---|---|---|
| **P1 - Critical** | Complete External Integration Module & Unit Tests | Directly on the critical path; all downstream testing is blocked until complete. |
| **P2 - High** | Finalize QA Test Plan Specification | Prerequisite for structured, efficient integration test execution. |
| **P2 - High** | Lock in Release Gate Meeting Schedule | Essential for reverse-planning and managing stakeholder alignment. |
| **P3 - Medium** | Align Integration Test Windows with Partner | Prevent idle waiting times once code is ready. |

---

### 5. Task Pruning & De-scoping Candidates

- Simplify detailed test cases for secondary non-critical features.
- Focus UAT exclusively on core business transaction journeys to accelerate client sign-off.
- Defer non-critical cosmetic UI defect fixes to a post-launch maintenance patch.

---

### 6. Resource Support Requirements

- Reserve dedicated test alignment windows with the external integration partner counterpart.
- Ensure staging environments are pre-configured so testing starts the moment code is deployed.

---

### 7. Client Communication Strategy

- Transparently state that development resumed at full velocity immediately following spec approval.
- Present the accelerated critical path plan designed to safeguard the 3.5-week launch deadline.
- Emphasize collaborative prioritization of testing scenarios to ensure high stability on core journeys.

---

### 8. Internal Escalation & Governance Alignment

- Present status update to the Delivery Director; secure approval for Option A (test prioritization).
- Align with Account Executive regarding the client communication framing.

---

### 9. Immediate Operational Plan (Next 24 to 72 Hours)

- **Within 24h**: Review daily burndown with Lead Dev; confirm Friday unit test completion target.
- **Within 48h**: Complete test plan review; submit Release Gate scheduling request to Client Lead A.
- **Within 72h**: Confirm partner testing windows; hold internal executive checkpoint on velocity.

---

## Human Review Points

Before executing:
- Verify that QA leadership agrees with the prioritized test coverage strategy.
- Ensure the tone of client messaging remains constructive and forward-looking.
