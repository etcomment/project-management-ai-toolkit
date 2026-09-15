# Scope Change Evaluation — Practical Scenario

## Use Case

Evaluating customer scope change requests mid-development to quantify impacts on engineering effort, critical path milestones, budgets, and commercial contract boundaries.

---

## Context Files Used

- `contexts/PM_CONTEXT.md`
- `contexts/SCOPE_CHANGE_CONTEXT.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
Project: Project Alpha (Fictitious)
Phase: Mid-Development (70% overall completion)

[Scope Change Requests]
Client Lead A has submitted the following three requests:
- Request 1: Add a "Batch Export Functionality" to the Admin Management Console.
- Request 2: Add a "Month-over-Month Comparative Analytics Graph" to the Dashboard.
- Request 3: Expand input validation rules on the Registration Form (specific rules unconfirmed).

[Business Context & Origin]
- Senior client executives requested improved operational ergonomics for operational field staff.
- Operational workflows were overlooked by the client during initial requirements gathering.

[Approved Contractual Baseline Scope]
- Admin Console: Search, view, and single-record export only.
- Dashboard: Current fiscal period summary aggregations only.
- Form Validation: Limited strictly to fields defined in Requirements Specification v1.0.

[Preliminary Effort Estimates]
- Batch Export: 3 to 5 engineer-days (preliminary rough order of magnitude).
- MoM Analytics Graph: 2 to 3 engineer-days (preliminary rough order of magnitude).
- Form Validation Additions: Cannot estimate until detailed rules are provided.

[Potential Technical Impacts]
- Data export consistency: Batch export format must align with single-record exports.
- Database impact: MoM queries may require schema indexing or caching optimizations.

[Delivery Constraints]
- 4 weeks (20 business days) remaining until final release gate.
- Target launch date has been announced internally by client executives (hard constraint).
- No commercial agreement reached yet regarding additional fees or change orders.
```

---

## Prompt

```text
After loading the context files below, evaluate the scope change requests against baseline delivery commitments.

[Context Files]
- contexts/PM_CONTEXT.md
- contexts/SCOPE_CHANGE_CONTEXT.md

[Scope Change Details]
(Paste the Sanitized Input above)

Please structure the evaluation as follows:
1. Scope Change Categorization Matrix
2. Baseline Scope Variance Analysis
3. Cross-Functional Blast Radius
4. Technical Effort Assessment
5. Timeline & Milestone Impact
6. Contractual & Commercial Considerations
7. Clarifications Needed from Client
8. Structured Decision Options (Options A, B, C)
9. Internal Escalation Requirements
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Scope Change Categorization Matrix

| # | Requested Feature | Baseline Status | Change Type |
|---|---|---|---|
| 1 | Admin Console Batch Export | Out of Scope | Major Functional Addition |
| 2 | Dashboard MoM Comparative Graph | Out of Scope | Minor Enhancement |
| 3 | Expanded Registration Validations | Out of Scope | Scope Expansion (Undefined) |

---

### 2. Baseline Scope Variance Analysis

- **Admin Console**: Contractual baseline covers single-record exports. Batch export requires asynchronous background job processing to avoid thread exhaustion.
- **Dashboard**: Baseline covers current-period metrics. MoM requires historical data aggregation and caching.
- **Validation**: Exceeds the approved field validation rules cataloged in Requirements v1.0.

None of the three requests are included in the approved contractual scope.

---

### 3. Cross-Functional Blast Radius

- **Documentation**: Functional specifications and UI designs must be formally revised and re-approved.
- **Engineering Effort**: Implementation across 3 distinct architectural layers.
- **Testing Window**: New test cases, edge cases, and performance testing for batch exports required.
- **Data Model**: Historical MoM queries may require database index restructuring.

---

### 4. Technical Effort Assessment

| Request | Estimated Effort (Days) | Remarks |
|---|---|---|
| Batch Export | 3 to 5 days | Requires async worker design |
| MoM Graph | 2 to 3 days | Contingent on query optimization |
| Expanded Validations | Indeterminate | Cannot estimate without rule definitions |
| **Total Estimated Effort** | **5 to 8+ engineer-days** | Subject to validation spec complexity |

---

### 5. Timeline & Milestone Impact

With only 4 weeks (20 business days) remaining and ongoing schedule recovery on external integrations, adding 5 to 8 days of development will compress regression testing to a dangerous breaking point.

- **Absorbing All 3 Requests**: Schedule breach is virtually guaranteed without an extension.
- **Selective Scope Inclusion**: Feasible only if strictly limited to 2 days of work.
- **Conclusion**: Delivering all requested additions within the current deadline is technically unfeasible.

---

### 6. Contractual & Commercial Considerations

- Accepting additions informally without a signed change order sets a harmful commercial precedent and erodes project profitability.
- Under fixed-price terms, scope expansions without corresponding budget/schedule extensions create unhedged delivery liabilities.

---

### 7. Clarifications Needed from Client

- Establish priority ranking among the 3 requests (which are mandatory vs. nice-to-have).
- Provide detailed business rules for Request 3 within 48 hours.
- Confirm whether the client leadership will approve a change order with schedule/budget adjustments.

---

### 8. Structured Decision Options (Options A, B, C)

| Option | Scope Delivered | Timeline Impact | Commercial Impact |
|---|---|---|---|
| **Option A: Full Scope with Deadline Extension** | Deliver all 3 requests once specifications are finalized | Postpone launch by 2-3 weeks | Formal Change Order with additional fees |
| **Option B: Core Baseline Launch + Phased v1.1** | Launch baseline scope in 4 weeks; deliver new features in v1.1 sprint 3 weeks later | Target deadline guaranteed | Change Order for Phase 1.1 sprint |
| **Option C: Scope Swap (Trade-off)** | Implement Batch Export in exchange for de-scoping a non-critical baseline feature | Target deadline guaranteed | Cost-neutral amendment |

---

### 9. Internal Escalation Requirements

- Inform Account Executive and Delivery Director immediately.
- Enforce strict instructions to the engineering team prohibiting any coding on these requests until commercial sign-off is achieved.

---

## Human Review Points

Before meeting with the client:
- Verify that the 5-8 day estimate is corroborated by the lead developers.
- Validate the preferred option (Option B is typically optimal for enterprise stability) with account leadership.
