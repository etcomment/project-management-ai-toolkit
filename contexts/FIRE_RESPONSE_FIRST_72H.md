# Fire Response - First 72 Hours Context

---

## Purpose

This context provides an operational triage framework for the critical **first 72 hours** following a major project crisis, severe production incident, or critical delivery breakdown.

In high-stress emergency situations, it assists Project Managers in separating facts from speculation, evaluating blast radius, identifying unknowns, and orchestrating immediate containment.

**Prioritize verified facts, actual impact, containment options, and immediate actions over assigning blame or premature root-cause post-mortems.**

**AI does not make crisis leadership decisions.** All outputs are structured decision inputs. Final crisis management choices remain strictly with human leadership.

---

## Use Cases

- Critical production outages or fatal defects discovered shortly before release
- Severe customer escalations, breach-of-contract warnings, or executive crises
- Irreversible schedule slips impacting immovable go-live deadlines
- Catastrophic team disruptions or sudden departures of key personnel
- Major security breaches, data corruption, or third-party infrastructure collapse

---

## Input (Information to Provide to the AI)

After loading this context, submit all available incident details with personal and client names strictly masked:

```
### Incident Metadata
- Project Name (Sanitized):
- Time of Incident / Discovery:
- Current Release / Go-Live Target:

### What Happened (Observed Incident)
- Description of the anomaly / failure:
- Environments impacted (Production, Staging, Development):
- Reproducibility status:

### Impact Scope
- Impact on client business operations & end users:
- Client counterpart notification status:
- Internal team & downstream dependencies affected:

### Established Facts (Verified)
- Objectively verified events, logs, and statuses:

### Current Unknowns (Unconfirmed)
- Questions under active investigation (root cause, fix duration, blast radius):

### Actions Taken So Far
- Initial technical investigations & executive verbal alerts:

### Constraints & Immovable Deadlines
- Contractual deadlines, public launch dates, or compliance requirements:
```

---

## Expected Output

### 1. Strict Segregation of Facts vs. Speculation
Delineating confirmed objective truths from active hypotheses and unverified rumors.

### 2. Blast Radius & Impact Mapping
Clear assessment of affected modules, business workflows, deployment schedules, and stakeholder commitments.

### 3. Immediate Day-0 Verifications (Must Answer Today)
Critical questions that the engineering team must resolve within the next few hours.

### 4. Client Communication Framing (Holding Statement / Briefing)
Carefully calibrated messaging that acknowledges active investigations without making unverified promises.

### 5. Internal Executive Arbitrations
Key management decisions required from leadership (Go/No-Go criteria, resource mobilization, contingency activation).

### 6. Immediate Containment Action Checklist
Assigned tasks for the technical and management teams covering the immediate hours.

### 7. 72-Hour Operational Roadmap
Phased triage roadmap across Day 1 (Triage & Containment), Day 2 (Fix & Validate), and Day 3 (Final Go/No-Go & Resolution).

### 8. Escalation Protocol & Authority Boundaries
Determining required escalation to C-level leadership, legal counsel, or PR teams.

---

## Caution & Operational Safeguards

> [!CAUTION]
> AI outputs do not make emergency leadership calls, crisis arbitrations, or legal liability admissions.
>
> All client statements and recovery commitments must be authorized by executive management.
>
> Never enter unmasked security credentials, vulnerability details, or confidential customer identifiers into the AI.

---

## Standard Prompt Template

```text
# Crisis Response Triage Request (First 72 Hours)

Using the contexts below, structure a 72-hour operational response plan for the emergency situation described below.
Prioritize verified facts, blast radius, containment options, and immediate actions over premature root-cause analysis.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of FIRE_RESPONSE_FIRST_72H.md here]

---

## Incident Situation (Sanitized)

[Paste sanitized incident data here]

---

## Requested Deliverables

1. Segregation of Facts vs. Speculation
2. Blast Radius & Impact Mapping
3. Critical Day-0 Verifications (Due Today)
4. Client Communication Framing
5. Internal Executive Arbitrations Required
6. Immediate Containment Checklist
7. 72-Hour Phased Operational Plan
8. Escalation Protocols & Executive Briefing Needs

*Note: AI output serves as analytical support. Final crisis leadership decisions remain human responsibility.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Structure an operational crisis containment plan for the first 72 hours of the incident described below.
Prioritize facts, impact, containment, and immediate actions over root-cause speculation.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of FIRE_RESPONSE_FIRST_72H.md here]
</specific_context>
</context>
<input>
[Paste sanitized incident data here]
</input>
<constraints>
- Strictly delineate verified facts from unconfirmed conjectures.
- Never draft definitive promises on resolution timelines without human review.
- Provide objective decision options for management arbitration.
</constraints>
<output_format>
1. Segregation of Facts vs. Speculation
2. Blast Radius & Impact Mapping
3. Critical Day-0 Verifications (Due Today)
4. Client Communication Framing
5. Internal Executive Arbitrations Required
6. Immediate Containment Checklist
7. 72-Hour Phased Operational Plan
8. Escalation Protocols & Executive Briefing Needs
</output_format>
```
