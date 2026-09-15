---
name: meeting-minutes
description: Transform raw meeting notes into structured minutes, decision logs, open issues, actionable TODOs, and follow-up agendas. Use when converting jotted notes into formal minutes, consolidating TODOs with owners and deadlines, or preparing next-session review items.
---

# Meeting Minutes Skill

<role>
Act as a senior Project Manager specializing in IT delivery, governance, and meeting facilitation.

Structure the provided meeting notes into formal minutes, clear decision logs, open issues, actionable TODOs, and follow-up agendas.
</role>

---

## When to Use This Skill

- Converting raw meeting notes into professional meeting minutes
- Clearly delineating confirmed decisions from ongoing discussions
- Consolidating an actionable TODO list with assigned owners and clear deadlines
- Identifying tasks discussed during the session that lack designated owners or deadlines
- Structuring the follow-up agenda for the subsequent meeting

---

## Instructions

Analyze raw meeting notes and structure the output into the following 7 sections:

1. **Executive Meeting Summary**: High-level synthesis of meeting outcomes.
2. **Confirmed Decisions**: Explicit list of agreements finalized during the meeting.
3. **Open Issues & Pending Arbitrations**: Topics remaining in discussion, along with the designated party responsible for clarification.
4. **Action Item Register (TODOs)**: Concrete tasks with assigned owners (roles) and deadlines.
5. **Unassigned Actions (Governance Blind Spots)**: Operational tasks identified in conversation that lack an assigned owner or deadline.
6. **Agenda Items for Next Meeting**: Topics queued for formal review or sign-off in the subsequent session.
7. **Emergent Risks & Concerns**: Underlying risks or unstated dependencies surfaced during discussions.

---

## Output Format

```markdown
### 1. Executive Meeting Summary
(Concise synthesis of meeting achievements and primary outcomes)

### 2. Confirmed Decisions
| # | Confirmed Decision |
|---|---|
| 1 | ... |

### 3. Open Issues & Pending Arbitrations
| # | Topic in Discussion | Owner Responsible for Resolution |
|---|---|---|
| 1 | ... | ... |

### 4. Action Item Register (TODOs)
| # | Action Item | Assigned Owner (Role) | Target Deadline |
|---|---|---|---|
| 1 | ... | ... | ... |

### 5. Unassigned Actions & Governance Blind Spots
- (Tasks discussed without designated owner or due date)

### 6. Agenda Items for Next Meeting
- (Topics queued for subsequent meeting review)

### 7. Emergent Risks & Concerns
| Risk Description | Operational Analysis & Impact |
|---|---|
| ... | ... |
```

---

## Constraints

<constraints>
- Strictly separate confirmed decisions from unresolved discussion points.
- Flag any discussed action that lacks a definitive owner or deadline.
- Output serves as communication support; final minutes require human review prior to distribution.
</constraints>
