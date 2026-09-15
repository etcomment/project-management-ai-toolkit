# Stakeholder Report Context

---

## Purpose

This context assists Project Managers in synthesizing project status, critical delivery risks, and strategic decisions for executive sponsors, steering committees, senior client leadership, and PMO directors.

**AI does not replace professional PM judgment.** AI assists in framing information and drafting executive summaries. Final strategic reports and governance presentations must be approved by human leadership.

> [!CAUTION]
> Never submit real client names, corporate identities, personal information, contract figures, or credentials into the AI.
> Content intended for C-level or client executives must be thoroughly validated by human management prior to presentation.

---

## Use Cases

- Drafting executive summaries for Steering Committee (SteerCo) decks
- Preparing high-level briefing notes for executive sponsors and PMO directors
- Structuring complex, technical delivery issues into clear business trade-offs
- Requesting executive decisions, budget arbitrations, or cross-departmental escalations
- Calibrating communication to focus on strategic outcomes, ROI, and delivery certainty

---

## Input (Information to Provide to the AI)

```
### Stakeholder Context
- Target Audience: (e.g., Executive Steering Committee, C-Suite, PMO Director)
- Core Business Objective:
- Current Overall Health: (Green / Amber / Red)

### Strategic Progress & Milestones
- Key business milestones achieved:
- Upcoming critical delivery gates:

### Critical Issues & Strategic Risks
- Major blockers threatening timeline, budget, or business value:
- Potential business impact:

### Specific Decisions / Approvals Requested
- Formal decisions required from executive leadership:
- Trade-off options presented:
```

---

## Expected Output

### 1. Executive Summary (1-Page Briefing Format)
Concise, high-impact synthesis of current health, business value delivered, and strategic horizon.

### 2. Milestone Achievement & Trajectory Tracker
Status of core milestones relative to the approved business baseline.

### 3. Strategic Risk Matrix
Top delivery risks mapped against business impact and mitigation roadmaps.

### 4. Decision & Arbitration Memoranda
Structured presentation of options requiring executive approval (Options A, B, C with trade-offs).

### 5. Recommended Leadership Actions
Specific interventions requested from sponsors to unblock delivery teams.

---

## Standard Prompt Template

```text
# Executive Stakeholder Briefing Request

Using the contexts below, structure a high-level executive report and decision memorandum based on the provided project data.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of STAKEHOLDER_REPORT_CONTEXT.md here]

---

## Project & Stakeholder Data (Sanitized)

[Paste sanitized stakeholder briefing data here]

---

## Requested Deliverables

1. Executive Summary (High-Impact Briefing Format)
2. Milestone Trajectory Tracker
3. Strategic Risk Matrix
4. Decision & Arbitration Memoranda (Structured Trade-Offs)
5. Recommended Sponsor Actions

*Note: AI output serves as analytical support. Final executive presentations require human leadership sign-off.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Draft an executive stakeholder briefing and decision memorandum based on the provided project data.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of STAKEHOLDER_REPORT_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized stakeholder briefing data here]
</input>
<constraints>
- Adopt an executive, strategic, and concise communication style.
- Focus on business impact, delivery certainty, and clear trade-off choices.
- Avoid technical minutiae; focus on governance, milestones, and risk mitigation.
</constraints>
<output_format>
1. Executive Summary (High-Impact Briefing Format)
2. Milestone Trajectory Tracker
3. Strategic Risk Matrix
4. Decision & Arbitration Memoranda (Structured Trade-Offs)
5. Recommended Sponsor Actions
</output_format>
```
