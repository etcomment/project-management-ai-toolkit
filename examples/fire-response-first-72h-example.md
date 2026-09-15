# Fire Response: First 72 Hours — Practical Scenario

## Use Case

Operational containment and crisis triage during the critical first 72 hours following the discovery of a critical production-blocking defect shortly before launch.

The objective is to leverage the AI to separate verified facts from speculation, evaluate blast radius, identify operational unknowns, and structure an immediate containment plan.

**Core Principle:** Prioritize objective facts, impact scoping, containment options, and immediate next steps over assigning blame or premature root-cause post-mortems.

---

## Context Files Used

- `contexts/PM_CONTEXT.md`
- `contexts/FIRE_RESPONSE_FIRST_72H.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
Project: Project Alpha (Fictitious)
Incident Discovery: 3 days prior to production go-live (Tuesday afternoon)

[What Happened]
During final pre-release regression checks, a critical defect was discovered in the payment processing workflow. Under specific conditions, transactions fail to complete, returning a fatal system exception.

[Timeline & Reproducibility]
- Discovered during final regression sweeps (Tuesday afternoon)
- Unconfirmed whether the defect existed in earlier staging builds
- Defect reproduced consistently on both Development and Staging environments

[Client & Business Impact]
- Go-live is scheduled for this Friday; client has already initiated company-wide internal launch announcements
- Schedule postponement will trigger severe operational disruption for the customer
- Client Lead A has not yet been notified; notification timing and framing remain unconfirmed

[Internal & Engineering Impact]
- Engineering team mobilized on technical diagnostics
- Collateral blast radius on downstream order modules unconfirmed
- Complete re-execution of the regression test suite may be required following any patch

[Established Facts (Verified)]
- Payment transactions fail under a specific data combination
- Defect is reproducible on staging and dev environments
- Discovery occurred at T-minus 3 days to release
- Client has commenced internal launch announcements
- Internal verbal escalation to executive delivery head completed

[Current Unknowns (Unconfirmed)]
- Exact technical root cause
- Blast radius on adjacent modules
- Engineering effort and time required for a clean fix
- Feasibility of completing fix and full re-testing before Friday launch

[Constraints & Immovable Deadlines]
- Target Release Date: Friday morning
- Client has published internal launch schedules
```

---

## Prompt

```text
After loading the context files below, structure an operational crisis containment plan for the first 72 hours of the incident.
Prioritize verified facts, blast radius, containment options, and immediate actions over premature root-cause speculation.

[Context Files]
- contexts/PM_CONTEXT.md
- contexts/FIRE_RESPONSE_FIRST_72H.md

[Incident Situation]
(Paste the Sanitized Input above)

Please structure the evaluation as follows:
1. Segregation of Facts vs. Speculation
2. Blast Radius & Impact Mapping
3. Critical Day-0 Verifications (Due Today)
4. Client Communication Framing (Holding Statement)
5. Internal Executive Arbitrations Required
6. Immediate Containment Checklist
7. 72-Hour Phased Operational Plan
8. Escalation Protocol & Authority Boundaries
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Segregation of Facts vs. Speculation

**Established Facts (Verified):**
- Payment processing defect reliably reproduced under specific conditions on dev and staging.
- Defect discovered at T-minus 3 days to scheduled release.
- Client has already initiated internal launch announcements.
- Internal leadership escalation completed verbally.

**Active Inferences / Unknowns (Unconfirmed):**
- Precise technical root cause.
- Extent of collateral blast radius across adjacent order workflows.
- Engineering hours required to develop, review, and test a fix.
- Feasibility of completing verification before Friday morning launch without compromising quality.

---

### 2. Blast Radius & Impact Mapping

| Dimension | Observed or Potential Impact | Current Verification Status |
|---|---|---|
| Payment Processing Module | Fatal exception under specific data parameters | Confirmed (Reproducible) |
| Downstream Order Modules | Risk of data corruption or orphaned records | Under Investigation |
| Deployment Schedule | Direct threat of go-live postponement | Dependent on fix effort estimate |
| Client Organizational Impact | Severe disruption due to pre-announced launch | Confirmed High Risk |

---

### 3. Critical Day-0 Verifications (Due Today)

- [ ] Isolate exact data parameters and trigger conditions causing the transaction failure.
- [ ] Conclude blast radius audit across adjacent order and reporting modules.
- [ ] Obtain engineering estimate for fix implementation (best case vs. worst case).
- [ ] Determine minimum required regression testing duration post-fix.

---

### 4. Client Communication Framing (Holding Statement)

> **Notice:** Client notification timing and wording must be approved by executive management. Do not transmit unvetted statements.

**Key Briefing Points:**
- Transparently state that a defect was identified during final pre-release sweeps and is under active technical investigation.
- Explain that engineering teams are actively determining root cause and remediation effort.
- Provide a commitment that a definitive status update and schedule impact assessment will be delivered by a specific time (e.g., Wednesday morning).
- Stick strictly to verified facts; avoid premature promises that Friday launch is guaranteed.

---

### 5. Internal Executive Arbitrations Required

- **Postponement Threshold**: Define the hard cutoff time (e.g., Wednesday 12:00 PM) beyond which the launch must be formally postponed if a stable fix is not verified.
- **Contingency Scope Options**: Evaluate whether launching with the payment feature temporarily disabled (phased rollout) is viable, or if a full release delay is required.
- **Resource Mobilization**: Reassign senior backend engineers to support diagnostics and peer reviews.

---

### 6. Immediate Containment Checklist

| # | Action Item | Assigned Role | Target Time |
|---|---|---|---|
| 1 | Isolate trigger conditions and blast radius | Senior Backend Dev | Tonight (18:00) |
| 2 | Deliver fix effort estimate and QA requirements | Tech Lead | Tonight (20:00) |
| 3 | Executive situation sync with Delivery Head | PM | Tonight (20:30) |
| 4 | Finalize client briefing posture and holding statement | PM / Executive Lead | Tonight (21:00) |
| 5 | Issue formal status update to Client Lead A | PM | Wednesday (09:00) |

---

### 7. 72-Hour Phased Operational Plan

- **Day 1 (Today / T-minus 3 Days)**: Triage root cause, quantify fix effort, align internal leadership, establish client holding briefing.
- **Day 2 (Wednesday / T-minus 2 Days)**: Develop patch, conduct initial verification, hold formal executive Go/No-Go decision gate regarding Friday launch.
- **Day 3 (Thursday / T-minus 1 Day)**: Deploy patch to staging, execute full regression sweeps, finalize go-live or execute postponement communications.

---

### 8. Escalation Protocol & Authority Boundaries

- Deciding to postpone the launch or alter contractual scope exceeds PM authority; formal sign-off from the Executive Delivery Head is mandatory.
- Client communications regarding release shifts must be approved by account leadership.

---

## Human Review Points

Before taking operational action:
- Confirm that the cutoff threshold for declaring a postponement is realistic given team stamina.
- Ensure legal and contractual notification requirements are verified prior to client briefings.
