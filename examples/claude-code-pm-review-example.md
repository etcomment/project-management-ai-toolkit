# Claude Code PM Review — Practical Scenario

## Use Case

Auditing a project development repository (README, issue tracker, progress notes, specification summaries) from a senior PM perspective using Claude Code.

The goal is to invoke `.claude/skills/pm-review/SKILL.md` to evaluate delivery health, unassigned tasks, and next steps directly from within the CLI.

> **Notice:** This scenario illustrates prompts for Claude Code. It contains no executable hooks, background daemons, MCP servers, or automated commits.

---

## Context Files Used

- `.claude/skills/pm-review/SKILL.md`
- `contexts/PM_CONTEXT.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

**Fictitious Repository README (Excerpt):**
```markdown
# Project Alpha - Core Services Repository

## Overview
New development of internal enterprise operations management platform.
Phase 1 includes Administration, Reporting, and External Integration modules.

## Current Status
Mid-Development (~70% overall completion)

## Target Release
End of Week 14 (3.5 weeks remaining)
```

**Fictitious Issue Backlog (Excerpt):**
```
Issue #12: External Integration Module - Core Implementation
  - Status: Closed
  - Owner: Dev Lead

Issue #18: External Integration Module - Unit Testing
  - Status: Open
  - Owner: Dev Lead
  - Deadline: None

Issue #21: QA Test Plan Specification Drafting
  - Status: Open
  - Owner: Unassigned
  - Deadline: End of this week

Issue #24: Partner Integration Testing
  - Status: Not Started
  - Owner: Unassigned
  - Deadline: None

Issue #27: Release Gate Meeting Scheduling
  - Status: Not Started
  - Owner: Unassigned
  - Deadline: None

Issue #30: Standardize Defect Bug Tracker
  - Status: Not Started
  - Owner: Unassigned
  - Deadline: None
```

**Progress Notes (Excerpt):**
```
Week 10 Progress Notes:
- External integration core implementation finished
- Unit testing not yet started
- Test plan author finally designated this week; kickoff planned
- Only 3.5 weeks remaining until release; high anxiety regarding testing window
- Client Lead A submitted additional feature requests (batch export); policy unconfirmed
```

---

## Prompts for Claude Code

### Standard Prompt
```text
After loading .claude/skills/pm-review/SKILL.md and contexts/PM_CONTEXT.md,
perform a senior PM audit of the current state of this repository.

Review scope:
- README
- Issue backlog
- Progress notes
- Specification memos
- Pending client items

Structure your findings across:
1. Executive Situation Summary
2. Risk Level Rating & Rationale
3. Primary Critical Risks
4. Items PM Must Clarify Internally
5. Confirmations Needed from Client
6. Internal Managerial Decisions Required
7. Prioritized Immediate Action Plan
```

### Claude Structured XML Prompt
```text
<task>
Perform a senior PM review of this repository based on .claude/skills/pm-review/SKILL.md and contexts/PM_CONTEXT.md.
</task>
<input>
Review scope:
- README
- Issue backlog
- Progress notes
- Specification memos
- Pending client items
</input>
<constraints>
- Base findings strictly on evidence; tag inferences as "(Inferred)".
- Highlight unassigned issues as governance vulnerabilities.
- Format outputs as decision-support materials.
</constraints>
<output_format>
1. Executive Situation Summary
2. Risk Level Rating & Rationale
3. Primary Critical Risks
4. Items PM Must Clarify Internally
5. Confirmations Needed from Client
6. Internal Managerial Decisions Required
7. Prioritized Immediate Action Plan
</output_format>
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Executive Situation Summary
Project Alpha stands at ~70% completion with 3.5 weeks until the immovable release deadline. While integration implementation is complete, unit and integration testing remain pending. Test plan drafting is only now kicking off under an unassigned issue. Multiple critical governance tasks lack owners or deadlines, creating an acute risk of compressed QA sweeps and delivery failure.

---

### 2. Risk Level Rating

**🔴 High (Immediate Action Required)**

- Completing test planning, unit testing, partner integration, and UAT within 3.5 weeks is on the brink of failure.
- Multiple critical issues (#21, #24, #27, #30) lack assigned owners or deadlines.
- Unapproved client scope requests threaten to disrupt final release preparations.

---

### 3. Primary Critical Risks

| # | Critical Risk | Operational Rationale |
|---|---|---|
| 1 | Compressed Testing Window | Test plan is only starting; downstream integration and UAT windows are severely squeezed. |
| 2 | Pervasive Governance Vacuum | Issues #21, #24, #27, and #30 have no designated accountability. |
| 3 | Decision Latency on Scope Creep | Client batch export request remains unaddressed, risking last-minute injection. |
| 4 | QA Defect Tracking Absence | No standardized bug tracking register deployed prior to test execution. |

---

### 4. Items PM Must Clarify Internally

- Assign explicit owner and lock completion date for Issue #21 (Test Plan).
- Assign owners to Issues #24 (Partner Testing), #27 (Release Gate), and #30 (Bug Tracker).
- Re-estimate critical path timeline to confirm feasibility of the 3.5-week release date.

---

### 5. Confirmations Needed from Client

- Obtain formal sign-off deferring new batch export requests to Phase 1.1.
- Finalize date and attendee requirements for the formal Release Gate meeting.

---

### 6. Internal Managerial Decisions Required

- Authorize policy on client feature additions (reject for v1.0, queue for v1.1).
- Approve contingency plan for test window compression (test case prioritization).

---

### 7. Prioritized Immediate Action Plan

| Priority | Action Item | Assigned Role | Target Deadline |
|---|---|---|---|
| P1 - Critical | Assign owner and deadline to Issue #21 (Test Plan) | PM | Immediate |
| P1 - Critical | Recalculate critical path schedule with engineering leads | PM / Tech Lead | Today |
| P2 - High | Align with client on deferring new scope to v1.1 | PM | Tomorrow |
| P2 - High | Assign owners and dates to Issues #24, #27, #30 | PM | Tomorrow |
| P3 - Medium | Deploy standardized defect tracking board | Tech Lead | End of Week |

---

## Human Review Points

Before acting:
- Verify that issue owners assigned in the action plan reflect real team staffing availability.
- Ensure that the scope rejection message for the client is diplomatically framed.
