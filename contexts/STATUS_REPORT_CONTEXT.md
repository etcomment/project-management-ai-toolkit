# Status Report Context

---

## Purpose

This context facilitates the drafting and structuring of professional project status reports with AI assistance.

It is designed to generate tailored draft reports calibrated to specific audience tiers: internal engineering leadership, executive management, and external clients.

**AI drafts are working materials.** Never send or publish an AI-generated report directly. A qualified human manager must review, verify, and adapt the text prior to dissemination.

---

## Use Cases

- Drafting weekly or monthly project status reports
- Generating dual versions of a report: internal operational view vs. external client view
- Structuring factual reporting when schedule slippage, issues, or risks arise
- Preparing executive briefing summaries for leadership consultations

---

## Input (Information to Provide to the AI)

After loading this context, provide the following details with confidential identifiers masked:

```
### Reporting Scope & Metadata
- Project Name (Sanitized):
- Reporting Period: (e.g., Week 12 / May 2026)
- Audience / Target: (e.g., Internal Leadership, Executive Board, Client Stakeholder)

### Completed Deliverables (This Cycle)
- Key achievements and finished tasks:
- Milestones reached:

### Incomplete / Carried-Over Work
- Planned work not finished during this cycle:
- Root cause for carry-over:

### Variances & Delayed Workstreams
- Workstreams experiencing schedule slip:
- Variance in days/weeks:
- Root cause (client dependencies, technical bottlenecks, scope changes):

### Active Issues & Blockers
- Top unresolved blockers:
- Impact scope and current mitigation:

### Active & Emerging Risks
- Key risks to timeline, cost, or quality:
- Trigger events and mitigation actions:

### Items Awaiting Client Action
- Approvals, reviews, or specifications pending from the client:
- Agreed-upon due dates:

### Upcoming Plan (Next Cycle)
- Committed milestones and deliverables for next week/month:
- Critical path focus areas:
```

---

## Expected Output

The AI synthesizes the provided status into the following structured deliverables:

### 1. Internal Status Report (Engineering Leadership & PMO)
A detailed operational report highlighting variances, internal bottlenecks, team velocity, and technical dependencies.

### 2. Client-Facing Status Report
A professional, diplomatic update emphasizing accomplished milestones, planned deliverables, and clearly identified client action items without exposing internal friction.

### 3. Executive Summary (3 Lines Max)
A high-level synthesis capturing overall status, key blockers, and core next actions designed for C-level or sponsor briefings.

### 4. Risk-Weighted Status Table
A table correlating active risks, blast radius, and proactive containment plans.

### 5. Prioritized Action Checklist
Assigned tasks and milestones for the upcoming cycle with clear deadlines.

---

## Caution & Operational Safeguards

> [!CAUTION]
> AI-generated status drafts do not replace professional managerial judgment.
>
> Never transmit AI-generated text directly to clients without human review.
>
> Ensure all client names, corporate identities, contract figures, and credentials are fully sanitized before submitting to AI tools.

---

## Standard Prompt Template

```text
# Status Report Drafting Request

Using the contexts below, draft a comprehensive status report based on the provided project updates.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of STATUS_REPORT_CONTEXT.md here]

---

## Project Status Data (Sanitized)

[Paste sanitized status metrics here]

---

## Requested Deliverables

1. Internal Status Report (for Management/PMO)
2. Client-Facing Status Report
3. Executive Summary (3 lines maximum)
4. Risk-Weighted Status Table
5. Immediate Action Checklist for Next Period

*Note: AI output serves as analytical support. Final operational decisions remain human responsibility.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Draft an internal status report, a client-facing status report, an executive 3-line summary, and a risk table based on the input data.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of STATUS_REPORT_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized status metrics here]
</input>
<constraints>
- Maintain strict confidentiality; assume all names and projects are sanitized.
- Calibrate the tone: objective and transparent for internal leadership; constructive, respectful, and diplomatic for clients.
- Append a mandatory human review notice to all client-facing sections.
</constraints>
<output_format>
1. Internal Status Report (Management & PMO)
2. Client-Facing Status Report
3. Executive Summary (3 lines maximum)
4. Risk-Weighted Status Table
5. Immediate Action Checklist for Next Period
</output_format>
```
