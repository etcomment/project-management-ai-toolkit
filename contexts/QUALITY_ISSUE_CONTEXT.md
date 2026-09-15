# Quality Issue Context

---

## Purpose

This context assists Project Managers in framing quality failures, defect spikes, insufficient test coverage, and code review gaps. It supports root-cause analysis (RCA), preventive action formulation, and structured incident reporting.

**AI does not replace professional PM judgment.** AI assists in categorizing facts and structuring analysis. Final technical assessments, warranty responses, and incident disclosures must be approved by human leadership.

> [!CAUTION]
> Never enter proprietary source code, credentials, or confidential system architectures into the AI.
> Do not input real client names, corporate identities, or contract liability terms.
> Incident reports, root-cause summaries, and corrective commitments must always be reviewed by management and legal counsel before external release.

---

## Use Cases

- Conducting 5-Whys or Ishikawa root-cause analysis on critical production defects or QA escapes
- Evaluating systemic quality risks (e.g., compressed UAT windows, inadequate regression testing)
- Structuring permanent corrective and preventive action (CAPA) plans
- Drafting objective, blameless quality incident reports for stakeholders
- Establishing measurable quality gates and Definition of Done (DoD) criteria

---

## Input (Information to Provide to the AI)

```
### Defect Metadata
- Incident / Defect Description:
- Severity / Priority Level:
- Discovery Phase: (e.g., Unit Testing, Integration Testing, UAT, Production)
- Environments Impacted:

### Quality Timeline & Chain of Events
- When the defect was introduced (estimated):
- Why it escaped earlier testing gates:
- Root cause identified by engineering:

### Operational Impact
- Impact on end-users / client operations:
- Downstream modules affected:

### Preventive Measures Under Consideration
- Proposed engineering, QA, or process improvements:
```

---

## Expected Output

### 1. Incident Executive Summary
Factual, objective synthesis of the defect, impact, and immediate containment status.

### 2. Root Cause Analysis (Direct vs. Systemic Causes)
Distinguishing immediate technical triggers from underlying process or governance gaps.

### 3. Corrective & Preventive Action Plan (CAPA)
Concrete, actionable measures categorized by Immediate Containment, Process Enhancement, and Long-Term Prevention.

### 4. Quality Gate & Testing Hardening Measures
Specific enhancements to test matrices, automated regression suites, or review checklists.

### 5. Stakeholder Communication Draft (Blameless & Objective)
Professional incident summary suitable for client or executive review.

---

## Standard Prompt Template

```text
# Quality Incident & Root Cause Analysis Request

Using the contexts below, structure an objective root-cause analysis and preventive action plan for the quality issue described.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of QUALITY_ISSUE_CONTEXT.md here]

---

## Incident Details (Sanitized)

[Paste sanitized defect and quality data here]

---

## Requested Deliverables

1. Incident Executive Summary
2. Direct vs. Systemic Root Cause Analysis
3. Corrective & Preventive Action Plan (CAPA)
4. Quality Gate & Testing Hardening Recommendations
5. Client-Facing Incident Briefing Draft

*Note: AI output serves as analytical support. Final reports require human executive validation.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Structure an objective root-cause analysis, preventive action plan, and client briefing draft based on the provided quality incident.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of QUALITY_ISSUE_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized defect and quality data here]
</input>
<constraints>
- Maintain a blameless, fact-focused, and constructive analytical posture.
- Differentiate superficial technical bugs from systemic process vulnerabilities.
- Ensure all customer-facing drafts are flagged for mandatory human review.
</constraints>
<output_format>
1. Incident Executive Summary
2. Direct vs. Systemic Root Cause Analysis
3. Corrective & Preventive Action Plan (CAPA)
4. Quality Gate & Testing Hardening Recommendations
5. Client-Facing Incident Briefing Draft
</output_format>
```
