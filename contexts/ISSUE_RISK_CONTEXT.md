# Issue & Risk Management Context

---

## Purpose

This context assists Project Managers in auditing active issue registers and risk matrices, uncovering governance gaps, re-evaluating priorities, and identifying escalation candidates.

**AI does not perform legal liability assessments or contractual priority determinations.** All outputs are structured decision-support materials. Final managerial decisions rest solely with human leadership.

---

## Use Cases

- Auditing issue backlogs for missing owners, ambiguous scopes, or open-ended deadlines
- Re-evaluating relative priority levels based on critical path dependencies
- Uncovering latent systemic delivery risks hidden beneath surfaced operational issues
- Preparing structured escalation rationale for executive sponsors or steering committees
- Consolidating items requiring formal customer clarification or arbitration

---

## Input (Information to Provide to the AI)

After loading this context, submit active issue and risk logs with confidential details masked:

```
### Project Context
- Project Name (Sanitized):
- Current Delivery Phase:
- Milestone Deadlines:

### Active Issue Backlog
For each active issue:
- Issue ID:
- Title / Summary:
- Current Status: (Open, In Progress, Blocked)
- Assigned Owner (Role):
- Target Resolution Date:
- Impact Scope:
- Current Action Plan:
- External Dependencies:

### Risk Register (Known & Potential)
- Risk Description:
- Estimated Probability:
- Impact Severity:
- Mitigation / Contingency Strategy:
- Current Trigger Status:
```

---

## Expected Output

### 1. Issue Categorization Matrix
Grouping issues by structural origin: Client/External Dependencies, Internal Technical Architecture, or Governance/Resource Bottlenecks.

### 2. Priority Re-alignment
Re-evaluating urgency and impact against the critical path (Critical, High, Medium, Low) with explicit technical justifications.

### 3. Governance Gap Identification
Explicitly highlighting issues lacking designated owners, definite target dates, or clear action plans.

### 4. Ambiguous Scope Alerts
Flagging issues where the blast radius is poorly defined or understated.

### 5. Latent Risk Detection
Uncovering second-order delivery risks (e.g., test cycle compression, third-party vendor alignment failure).

### 6. Escalation Candidate Shortlist
Identifying critical issues exceeding the PM's delegated authority that require immediate executive or steering committee intervention.

### 7. Action Plan & Next Steps
Concrete operational next steps with assigned owners and deadlines.

---

## Caution & Operational Safeguards

> [!CAUTION]
> AI-generated risk evaluations do not substitute for formal PMO audits, legal compliance, or contractual determinations.
>
> All escalation decisions and priority shifts must be validated by human management.
>
> Do not input real client names, corporate identities, contract figures, or credentials into AI tools.

---

## Standard Prompt Template

```text
# Issue and Risk Audit Request

Using the contexts below, perform a rigorous review of the active issue backlog and risk register from a senior PM perspective.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of ISSUE_RISK_CONTEXT.md here]

---

## Active Issues and Risk Data (Sanitized)

[Paste sanitized issue and risk data here]

---

## Requested Deliverables

1. Issue Categorization Matrix
2. Priority Re-alignment with Rationale
3. Governance Gap Identification (Missing Owners/Deadlines)
4. Ambiguous Impact Alerts
5. Latent Delivery Risks
6. Escalation Candidate Shortlist
7. Immediate Action Plan

*Note: AI output serves as analytical support. Final operational decisions remain human responsibility.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Audit the provided issue backlog and risk matrix from a senior PM perspective.
Output categorization, reprioritization, governance gaps, latent risks, escalation candidates, and next actions.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of ISSUE_RISK_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized issue and risk data here]
</input>
<constraints>
- Base findings strictly on supplied data; tag inferences explicitly as "(Inferred)".
- Highlight any issue missing an owner or deadline as an urgent governance vulnerability.
- Maintain a decision-support framing; do not make binding contractual conclusions.
</constraints>
<output_format>
1. Issue Categorization Matrix
2. Priority Re-alignment with Technical Rationale
3. Governance Gap Identification (Unassigned/No Deadline)
4. Ambiguous Impact Alerts
5. Latent Delivery Risks
6. Escalation Candidate Shortlist
7. Immediate Action Plan
</output_format>
```
