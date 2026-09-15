# Meeting Minutes Context

---

## Purpose

This context assists Project Managers in transforming raw meeting notes, rapid jottings, tentative agreements, and open questions into structured meeting minutes, actionable TODO lists, and next-session agendas.

**AI does not replace professional PM judgment.** AI serves as a force multiplier for structuring notes and highlighting action items. Final minutes and stakeholder distributions must be reviewed and approved by human management.

> [!CAUTION]
> Never submit real participant names, client identities, corporate names, or personally identifiable information into the AI.
> Mask or remove all contract financials, credentials, or sensitive commercial details before submission.

---

## Use Cases

- Structuring raw meeting notes from client steering committees or internal standups
- Delineating verified decisions from unconfirmed discussion points
- Creating an actionable TODO list with assigned owners and clear deadlines
- Identifying blind spots: action items discussed without explicit owners or target dates
- Setting up the agenda and follow-up items for the subsequent meeting

---

## Input (Information to Provide to the AI)

After loading this context, submit the meeting notes with all confidential data masked:

```
### Meeting Metadata
- Meeting Purpose / Type: (e.g., Weekly Client Steering, Technical Architecture Sync)
- Date / Cycle: (e.g., Week 10, Wednesday)
- Roles of Attendees: (e.g., PM, Tech Lead, Client Sponsor, Operations Lead)

### Raw Meeting Notes (Jottings / Bullet Points)
- Key topics discussed:
- Tentative decisions:
- Open issues / items carried over:
- Technical or timeline concerns raised:
```

---

## Expected Output

### 1. Executive Meeting Summary
Concise synthesis of core achievements, major discussions, and primary outcomes.

### 2. Confirmed Decisions
Formal table of agreed-upon decisions and approved orientations.

### 3. Open Issues & Pending Arbitrations
Items remaining in discussion, along with the designated party responsible for providing clarification.

### 4. Action Item Register (TODOs)
Structured matrix containing Action Item, Owner (Role), Deadline, and Deliverable.

### 5. Unassigned Actions & Governance Gaps
Actionable tasks identified in conversation that lack an assigned owner or deadline.

### 6. Agenda Items for Next Meeting
Topics queued for formal review or sign-off during the subsequent session.

### 7. Emergent Risks & Concerns
Underlying risks or unstated dependencies surfaced during discussions.

---

## Standard Prompt Template

```text
# Meeting Minutes Structuring Request

Using the contexts below, convert the raw meeting notes into professional meeting minutes and an actionable TODO register.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of MEETING_MINUTES_CONTEXT.md here]

---

## Meeting Notes (Sanitized)

[Paste sanitized raw meeting notes here]

---

## Requested Deliverables

1. Executive Meeting Summary
2. Confirmed Decisions
3. Open Issues & Pending Arbitrations
4. Action Item Register (TODOs with Owner & Deadline)
5. Unassigned Actions (Governance Blind Spots)
6. Agenda Items for Next Meeting
7. Emergent Risks & Concerns

*Note: AI output serves as analytical support. Final meeting minutes require human validation prior to distribution.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Structure the provided raw meeting notes into executive meeting minutes, a decision log, an action item register, and a follow-up agenda.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of MEETING_MINUTES_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized raw meeting notes here]
</input>
<constraints>
- Clearly distinguish confirmed decisions from open issues.
- Flag any discussed action that lacks a definitive owner or deadline.
- Ensure the tone is objective, professional, and ready for human executive review.
</constraints>
<output_format>
1. Executive Meeting Summary
2. Confirmed Decisions
3. Open Issues & Pending Arbitrations
4. Action Item Register (TODOs with Owner & Deadline)
5. Unassigned Actions (Governance Blind Spots)
6. Agenda Items for Next Meeting
7. Emergent Risks & Concerns
</output_format>
```
