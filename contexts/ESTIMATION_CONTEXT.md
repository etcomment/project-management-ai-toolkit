# Estimation Context

---

## Purpose

This context assists Project Managers in framing estimation assumptions, identifying technical uncertainties, articulating scope exclusions, and preparing pre-estimation checklists before engaging in formal sizing.

**AI does not calculate binding cost estimates or contractual pricing.** Never delegate commercial pricing or contractual liability terms to AI. AI assists purely in structuring assumptions and scoping criteria.

> [!CAUTION]
> Never input actual contractual rates, billing amounts, budget limits, or proprietary client data into the AI.
> Final estimation, cost modeling, and commercial commitments remain exclusively the responsibility of human leadership.

---

## Use Cases

- Structuring technical assumptions and constraints prior to engineering sizing workshops
- Uncovering ambiguities and unstated requirements in customer specifications
- Formalizing out-of-scope boundaries (exclusions) to prevent future scope creep
- Quantifying architectural uncertainties and risk buffers needed in estimates
- Preparing a clarification questionnaire for prospective clients prior to proposal submission

---

## Input (Information to Provide to the AI)

```
### Project Overview & Phase
- Project Name (Sanitized):
- Proposed Architecture / Tech Stack:
- Project Delivery Model: (Fixed-Price, T&M, Target Cost)

### Requirements Overview (Sanitized)
- Core features & functional modules:
- High-level integrations & external APIs:

### Known Constraints & Deadlines
- Target delivery window:
- Performance, security, or compliance constraints:

### High-Risk / Uncertain Areas
- Emerging technologies, undocumented legacy systems, or incomplete specs:
```

---

## Expected Output

### 1. Pre-Estimation Assumption Register
Formal catalog of functional, technical, and operational assumptions underlying the sizing.

### 2. Boundary & Scope Exclusion Matrix
Explicit listing of excluded items (Out of Scope) to safeguard commercial boundaries.

### 3. Technical Uncertainty & Risk Profiling
Categorizing features by technical volatility and recommended contingency buffers.

### 4. Client Clarification Questionnaire
Targeted questionnaire addressing ambiguous requirements before finalizing estimates.

### 5. Sizing Structure & WBS Workstream Breakdown
Logical decomposition into workstreams (Design, Core Dev, Integrations, QA, Deployment).

---

## Standard Prompt Template

```text
# Pre-Estimation Scoping & Assumption Structuring Request

Using the contexts below, evaluate the proposed requirements and structure a comprehensive pre-estimation assumption catalog and clarification register.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of ESTIMATION_CONTEXT.md here]

---

## Proposed Requirements (Sanitized)

[Paste sanitized project requirements and constraints here]

---

## Requested Deliverables

1. Pre-Estimation Assumption Register
2. Explicit Boundary & Scope Exclusion Matrix
3. Technical Uncertainty & Risk Profiling
4. Client Clarification Questionnaire
5. Sizing Workstream Decomposition (WBS Breakdown)

*Note: AI output serves as analytical support. Commercial pricing and final estimates require qualified human management sign-off.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Structure a pre-estimation assumption catalog, scope boundary matrix, and client clarification questionnaire based on the provided requirements.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of ESTIMATION_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized project requirements and constraints here]
</input>
<constraints>
- Do not generate financial figures, billing rates, or commercial prices.
- Focus strictly on technical scoping, baseline assumptions, and boundary exclusions.
- Identify all points of ambiguity that could induce estimation variance.
</constraints>
<output_format>
1. Pre-Estimation Assumption Register
2. Explicit Boundary & Scope Exclusion Matrix
3. Technical Uncertainty & Risk Profiling
4. Client Clarification Questionnaire
5. Sizing Workstream Decomposition (WBS Breakdown)
</output_format>
```
