# Meeting Minutes & Action Item Structuring — Practical Scenario

## Use Case

Transforming raw, unstructured meeting notes taken during a client progress meeting into professional meeting minutes, confirmed decision logs, open issues, and an assigned action register (TODOs).

---

## Context Files Used

- `contexts/PM_CONTEXT.md`
- `contexts/MEETING_MINUTES_CONTEXT.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
Meeting Type: Weekly Client Progress Sync
Date / Cycle: Week 9, Wednesday
Attendee Roles: PM (Internal), Tech Lead (Internal), Client Lead A

[Raw Meeting Notes (Rapid Jottings)]
- Carried-over action item: Data specification confirmation -> Client Lead A presented formal orientation during meeting
- Data synchronization decisions agreed:
  - Item X: De-scoped from current release phase
  - Item Y: Simplified interface specification adopted (Client Lead A will provide details in a separate memo)
  - Item Z: Maintain baseline specification without changes
- External integration module development targeting completion by end of next week (schedule recovery underway)
- QA Test Plan design kickoff confirmed -> Tech Lead will initiate drafting next Monday
- Test window duration concern raised -> Tech Lead voiced: "5 business days for integration testing is insufficient"
  - PM replied that extending the testing window should be evaluated, but no formal decision reached yet
- Release Gate meeting schedule -> Inquired with Client Lead A, who indicated need to verify with executive sponsor. Awaiting response
- Next weekly sync: Next Wednesday
  - Client Lead A expected to bring leadership feedback
```

---

## Prompt

```text
After loading the context files below, structure the raw meeting notes into professional meeting minutes and an actionable TODO register.

[Context Files]
- contexts/PM_CONTEXT.md
- contexts/MEETING_MINUTES_CONTEXT.md

[Raw Meeting Notes]
(Paste the Sanitized Input above)

Please structure the output as follows:
1. Executive Meeting Summary
2. Confirmed Decisions
3. Open Issues & Pending Arbitrations
4. Action Item Register (TODOs with Owner & Deadline)
5. Unassigned Actions (Governance Blind Spots)
6. Agenda Items for Next Meeting
7. Emergent Risks & Concerns
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Executive Meeting Summary
During the Week 9 weekly sync, key orientations on data integration specifications were formally agreed upon with Client Lead A (Item X de-scoped, Item Y simplified, Item Z maintained). Implementation of external integration targets completion by end of next week. QA test plan design kicks off next Monday under the Tech Lead. However, technical concerns regarding the compressed 5-day testing window necessitate an urgent schedule review. Confirmation of the formal Release Gate date remains pending client executive approval.

---

### 2. Confirmed Decisions

| # | Confirmed Decision |
|---|---|
| 1 | Data Sync: Item X de-scoped from current release milestone. |
| 2 | Data Sync: Item Y simplified specification approved for development. |
| 3 | Data Sync: Item Z baseline specification confirmed without modification. |
| 4 | External integration module development target locked for end of Week 10. |
| 5 | QA Test Plan drafting kickoff confirmed for Monday of Week 10. |

---

### 3. Open Issues & Pending Arbitrations

| # | Open Topic | Action Required / Responsible Party |
|---|---|---|
| 1 | Integration test window extension | PM to evaluate schedule impact; tripartite decision required |
| 2 | Release Gate meeting date | Client Lead A confirming with executive sponsor |
| 3 | Item Y simplified technical details | Awaiting specification memo from Client Lead A |

---

### 4. Action Item Register (TODOs)

| # | Action Item | Assigned Role | Target Deadline |
|---|---|---|---|
| 1 | Complete external integration module implementation | Dev Team | End of Week 10 |
| 2 | Kick off QA Test Plan Specification drafting | Tech Lead | Monday, Week 10 |
| 3 | Receive and review Item Y specification memo | PM / Tech Lead | Upon client transmission |
| 4 | Evaluate schedule feasibility of extending test window | PM | Prior to next sync |
| 5 | Follow up on Release Gate date confirmation | PM | Next weekly sync |

---

### 5. Unassigned Actions & Governance Blind Spots

- **Reviewing Item Y Technical Memo**: Who reviews and approves the feasibility of Item Y once the client sends it? Action should be explicitly assigned to the Tech Lead to avoid integration stalls.

---

### 6. Agenda Items for Next Meeting

- Confirmation of the Release Gate meeting schedule (Client leadership feedback)
- PM proposal regarding integration test window adjustment
- External integration module implementation progress review
- QA Test Plan design kickoff status review

---

### 7. Emergent Risks & Concerns

| Risk Description | Operational Analysis & Impact |
|---|---|
| Test Window Compression | 5 days of integration testing is deemed unfeasible by engineering. Maintaining this timeline without adjustments risks catastrophic QA escapes into production. |
| Item Y Specification Latency | If the client memo is delayed, external integration completion will slip past the end of Week 10. |
| Unconfirmed Release Gate Date | Absence of firm acceptance criteria creates significant risk of subjective release disputes. |

---

## Human Review Points

Before sharing with the client or internal team:
- Verify that agreed-upon scope de-scopings (Item X) match verbal consensus exactly.
- Confirm whether the tone of the testing window extension is diplomatically calibrated.
- Replace generic role placeholders with exact team member names.
