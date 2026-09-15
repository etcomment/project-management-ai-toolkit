# Scope Change Context

---

## Purpose

This context assists Project Managers in evaluating specification changes, scope modifications, and feature requests. It structures impact assessments across technical effort, delivery milestones, budgets, and contractual boundaries.

**AI does not replace professional PM judgment.** AI assists in organizing information and mapping dependencies. Final contractual and commercial decisions must be validated by human management.

> [!CAUTION]
> Never input specific contract values, commercial rates, or confidential client identities into the AI.
> Ensure all project data is sanitized prior to analysis.

---

## Use Cases

- Structuring impact assessments when a customer requests changes or additions mid-flight
- Delineating clear variance between the baseline contractual scope and requested additions
- Quantifying the ripple effect on architecture, test cycles, and delivery milestones
- Preparing structured trade-off options (Options A, B, C) for steering committee arbitration
- Formulating clarifying questions to expose ambiguous customer requirements

---

## Input (Information to Provide to the AI)

After loading this context, submit the scope change details with confidential data masked:

```
### Project Baseline & Phase
- Project Name (Sanitized):
- Current Phase: (e.g., Mid-development, 70% completed)
- Immovable Milestone Constraints:

### Scope Change Requests
- Detailed description of requested additions / modifications:
- Origin & Business Rationale behind the request:

### Baseline Scope (Contractual / Approved)
- Functionality originally agreed upon in requirements specifications:

### Preliminary Technical Estimates
- Estimated additional effort (engineering days/weeks):
- System components & interfaces impacted:
- Database schema or architecture impacts:

### Schedule & Commercial Constraints
- Remaining timeline to release:
- Flexibility of target delivery date:
- Budgetary constraints / commercial contract model (Fixed-Price, Time & Materials):
```

---

## Expected Output

### 1. Scope Change Categorization Matrix
Classifying each request as Major Addition, Minor Enhancement, or Defect/Clarification.

### 2. Baseline Scope Variance Analysis
Detailed contrast between the approved requirements baseline and the proposed changes.

### 3. Cross-Functional Blast Radius
Mapping the ripple effect across architecture, existing functionality, test matrices, and documentation.

### 4. Technical Effort & Capacity Assessment
Estimated engineering, testing, and rework effort required.

### 5. Critical Path & Timeline Impact
Analysis of whether additions can be absorbed without breaching delivery milestones.

### 6. Contractual & Commercial Implications
Highlighting risks of uncompensated effort, margin erosion, or contractual exposure under fixed-price models.

### 7. Clarifications Required from Client
Targeted questions to resolve ambiguous requirements before committing.

### 8. Structured Decision Options (Options A, B, C)
Actionable trade-off scenarios (e.g., Option A: Full scope with deadline extension; Option B: Phased delivery in v1.1; Option C: Scope swap/trade-off).

### 9. Internal Escalation & Approval Protocol
Identifying required approvals from account leadership, legal, or commercial directors.

---

## Standard Prompt Template

```text
# Scope Change Impact Assessment Request

Using the contexts below, evaluate the requested scope changes against the baseline project delivery.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of SCOPE_CHANGE_CONTEXT.md here]

---

## Scope Change Data (Sanitized)

[Paste sanitized scope change details here]

---

## Requested Deliverables

1. Scope Change Categorization Matrix
2. Baseline Scope Variance Analysis
3. Cross-Functional Blast Radius
4. Technical Effort Assessment
5. Timeline & Milestone Impact
6. Contractual & Commercial Considerations
7. Clarifications Needed from Client
8. Structured Decision Options (Options A, B, C)
9. Internal Escalation & Approval Requirements

*Note: AI output serves as analytical support. Final contractual decisions remain human responsibility.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Evaluate the provided scope change request against baseline delivery commitments from a senior PM perspective.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of SCOPE_CHANGE_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized scope change details here]
</input>
<constraints>
- Strictly differentiate the contractual baseline from new requests.
- Provide objective, balanced trade-off options.
- Highlight any uncompensated scope creep that risks delivery stability.
</constraints>
<output_format>
1. Scope Change Categorization Matrix
2. Baseline Scope Variance Analysis
3. Cross-Functional Blast Radius
4. Technical Effort Assessment
5. Timeline & Milestone Impact
6. Contractual & Commercial Considerations
7. Clarifications Needed from Client
8. Structured Decision Options (Options A, B, C)
9. Internal Escalation & Approval Requirements
</output_format>
```
