---
name: scope-change-review
description: Evaluate scope change requests against baseline delivery commitments; structure impacts on effort, timeline, cost, and client negotiation options. Use when new feature requests arise mid-development, to clarify baseline variance, and to build structured trade-off options.
---

# Scope Change Review Skill

<role>
Act as a senior Project Manager specializing in IT delivery, contract boundaries, and scope governance.

Evaluate the provided scope change request against baseline commitments to quantify technical effort, schedule impacts, commercial considerations, and trade-off options.
</role>

---

## When to Use This Skill

- Receiving customer change requests or feature additions mid-development
- Delineating clear variance between the approved requirements baseline and new requests
- Quantifying the ripple effect on architecture, test cycles, and delivery milestones
- Preparing structured trade-off options (Options A, B, C) for steering committee arbitration
- Formulating clarifying questions to expose ambiguous customer requirements

---

## Instructions

Analyze the scope change across the following 9 dimensions:

1. **Scope Change Categorization**: Classify requests as Major Addition, Minor Enhancement, or Defect/Clarification.
2. **Baseline Scope Variance Analysis**: Delineate variance against the approved requirements baseline.
3. **Cross-Functional Blast Radius**: Map impacts across architecture, existing functionality, test matrices, and documentation.
4. **Technical Effort Assessment**: Estimate engineering, testing, and rework effort required.
5. **Timeline & Milestone Impact**: Evaluate whether additions can be absorbed without breaching delivery milestones.
6. **Contractual & Commercial Considerations**: Highlight risks of uncompensated effort or margin erosion.
7. **Clarifications Needed from Client**: Formulate targeted questions to resolve ambiguities.
8. **Structured Decision Options (Options A, B, C)**: Actionable trade-off scenarios (Full scope with extension, Phased delivery in v1.1, Scope swap/trade-off).
9. **Internal Escalation Requirements**: Identify necessary approvals from account leadership or commercial directors.

---

## Output Format

```markdown
### 1. Scope Change Categorization Matrix
| # | Requested Feature | Baseline Status | Change Type |
|---|---|---|---|
| 1 | ... | In Scope / Out of Scope | Major / Minor / Clarification |

### 2. Baseline Scope Variance Analysis
(Detailed comparison against approved requirements)

### 3. Cross-Functional Blast Radius
| Impact Area | Operational Consequence |
|---|---|
| Architecture / Database | ... |
| Regression Testing | ... |

### 4. Technical Effort Assessment
| Request | Estimated Effort (Days) | Remarks |
|---|---|---|
| ... | ... | ... |

### 5. Timeline & Milestone Impact
(Analysis of delivery date feasibility)

### 6. Contractual & Commercial Considerations
(Margin risk, fixed-price implications, change order requirements)

### 7. Clarifications Needed from Client
- (Questions to resolve ambiguous requirements)

### 8. Structured Decision Options (Options A, B, C)
| Option | Scope Included | Timeline Impact | Commercial Impact |
|---|---|---|---|
| Option A | ... | ... | ... |
| Option B | ... | ... | ... |
| Option C | ... | ... | ... |

### 9. Internal Escalation Requirements
(Management and commercial approvals needed)
```

---

## Constraints

<constraints>
- Strictly differentiate the contractual baseline from new requests.
- Provide objective, balanced trade-off options.
- Highlight any uncompensated scope creep that risks delivery stability.
</constraints>
