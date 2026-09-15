# Weekly Meeting Context

---

## Purpose

This context assists Project Managers in structuring weekly progress agendas, establishing a logical review sequence, preparing meeting prerequisites, and tracking post-meeting action items for both client-facing and internal team syncs.

**AI does not replace professional PM judgment.** AI serves as a preparation and structuring tool. Final agendas and steering decisions remain human responsibilities.

> [!CAUTION]
> Never enter real client names, corporate identities, personal information, or credentials into the AI.
> Abstract sensitive business data into roles, milestones, and high-level deliverables before submission.

---

## Use Cases

- Structuring efficient, focused agendas for weekly client progress meetings
- Preparing internal weekly team synchronization sessions
- Ensuring all critical decision points and blockers are queued in the right order of priority
- Generating pre-meeting preparation checklists for engineering and management leads
- Tracking post-meeting action items and agreements

---

## Input (Information to Provide to the AI)

```
### Meeting Setup
- Meeting Type: (Client Progress Meeting / Internal Team Sync)
- Duration & Cadence: (e.g., 60 minutes, Weekly)
- Key Stakeholder Roles: (e.g., Client PM, Sponsor, Internal Lead Dev)

### Current Project Status (Sanitized)
- Milestone Progress:
- Active Blockers / Decisions Required:
- Pending Client Reviews:
- Upcoming Delivery Gates:
```

---

## Expected Output

### 1. Structured Time-Boxed Agenda
Logical breakdown of meeting topics (Progress Review, Blocker Arbitration, Next Milestone Planning).

### 2. High-Priority Decision Items
Specific topics requiring formal managerial sign-off during the session.

### 3. Pre-Meeting Preparation Checklist
Specific data points, documents, or metric summaries that attendees must prepare beforehand.

### 4. Post-Meeting Action Item Template
Standardized structure for recording assigned next steps, owners, and deadlines.

---

## Standard Prompt Template

```text
# Weekly Meeting Agenda & Preparation Request

Using the contexts below, build a structured, time-boxed weekly meeting agenda and preparation checklist based on the project status.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of WEEKLY_MEETING_CONTEXT.md here]

---

## Project Status (Sanitized)

[Paste sanitized status and discussion points here]

---

## Requested Deliverables

1. Time-Boxed Meeting Agenda
2. Core Decision Points Requiring Arbitration
3. Pre-Meeting Preparation Checklist by Attendee Role
4. Post-Meeting Action Tracking Framework

*Note: AI output serves as analytical support. Final agendas require human approval.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Build a structured, time-boxed weekly meeting agenda and preparation checklist based on the provided project status.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of WEEKLY_MEETING_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized status and discussion points here]
</input>
<constraints>
- Prioritize topics by operational urgency and critical path dependency.
- Structure agenda items with realistic time allocations.
- Maintain professional, neutral framing suitable for stakeholder alignment.
</constraints>
<output_format>
1. Time-Boxed Meeting Agenda
2. Core Decision Points Requiring Arbitration
3. Pre-Meeting Preparation Checklist by Attendee Role
4. Post-Meeting Action Tracking Framework
</output_format>
```
