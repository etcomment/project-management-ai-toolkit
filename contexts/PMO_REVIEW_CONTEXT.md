# PMO Review Context

---

## Purpose

This context assists PMO Directors, Delivery Heads, and Program Managers in conducting cross-project portfolio reviews, identifying high-risk engagements, surfacing systemic risks, and triaging management interventions across multiple delivery streams.

**AI does not replace executive PMO judgment.** AI assists in synthesizing multi-project updates and detecting portfolio-wide correlations. Final staffing, commercial, and organizational decisions remain human responsibilities.

> [!CAUTION]
> Never use AI outputs for individual employee evaluations or HR performance management.
> Do not input real client names, company identities, employee names, or contractual commercials.
> Treat all portfolio data with strict sanitization and operational abstraction.

---

## Use Cases

- Conducting monthly or quarterly cross-portfolio delivery health reviews
- Detecting systemic patterns (e.g., recurring QA bottlenecks across 3 separate projects)
- Triage and prioritization of PMO coaching or senior engineering interventions
- Preparing consolidated executive dashboards for executive leadership
- Flagging projects requiring immediate governance audit or recovery intervention

---

## Input (Information to Provide to the AI)

```
### Portfolio Scope
- Portfolio / Division Name (Sanitized):
- Number of Active Engagements:
- General Delivery Framework: (Agile, Waterfall, Hybrid)

### Multi-Project Summaries (Sanitized)
For each project (Project Alpha, Project Beta, Project Gamma):
- Current Phase & Completion Rate:
- Delivery Health Status: (Green / Amber / Red)
- Active Blockers & Schedule Variance:
- Critical Staffing or Technical Constraints:
- Client Counterpart Dynamics:
```

---

## Expected Output

### 1. Portfolio Delivery Health Matrix
Consolidated scorecard ranking all projects by risk profile and milestone stability.

### 2. High-Risk Engagement Triage (Red / Amber Deep-Dives)
Deep-dive into struggling projects with explicit failure modes and critical path vulnerabilities.

### 3. Cross-Cutting Systemic Risks
Identifying portfolio-wide patterns (e.g., dependency on a shared infrastructure team, common third-party API delays).

### 4. PMO Intervention & Resource Allocation Plan
Targeted recommendations for where senior PMO coaching, technical triage, or resource rebalancing will yield the highest return.

### 5. Executive Portfolio Briefing (3 Lines per Project)
High-level summary for the COO, CTO, or Head of Delivery.

---

## Standard Prompt Template

```text
# Cross-Portfolio PMO Review Request

Using the contexts below, conduct a comprehensive cross-project delivery audit across the portfolio updates provided.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of PMO_REVIEW_CONTEXT.md here]

---

## Multi-Project Status Data (Sanitized)

[Paste sanitized multi-project updates here]

---

## Requested Deliverables

1. Portfolio Delivery Health Matrix
2. High-Risk Engagement Triage
3. Cross-Cutting Systemic Risk Analysis
4. PMO Intervention & Resource Rebalancing Plan
5. Executive Portfolio Briefing

*Note: AI output serves as analytical support. Operational interventions require human PMO executive approval.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Conduct a cross-project delivery audit and portfolio risk synthesis based on the provided multi-project status data.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of PMO_REVIEW_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized multi-project updates here]
</input>
<constraints>
- Focus on portfolio-wide governance, systemic bottlenecks, and critical delivery risks.
- Maintain an objective, constructive, and analytical tone.
- Do not evaluate individual personal performance; focus on project operational dynamics.
</constraints>
<output_format>
1. Portfolio Delivery Health Matrix
2. High-Risk Engagement Triage
3. Cross-Cutting Systemic Risk Analysis
4. PMO Intervention & Resource Rebalancing Plan
5. Executive Portfolio Briefing
</output_format>
```
