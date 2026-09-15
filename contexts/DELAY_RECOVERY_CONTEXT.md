# Delay Recovery Context

---

## Purpose

This context assists Project Managers in framing root causes, evaluating critical path impacts, generating schedule recovery options, and structuring customer communication when delivery slips occur.

**AI does not replace professional PM judgment.** AI assists in organizing facts and formulating recovery scenarios (crashing, fast-tracking, scope pruning). Final schedule and commercial commitments must be made by human leadership.

> [!CAUTION]
> Never submit unmasked client names, individual identities, contract terms, or credentials into the AI.
> Commitment to new deadlines or commercial terms requires human manager verification and approval.

---

## Use Cases

- Analyzing root causes and blast radius when schedule slippage emerges
- Evaluating recovery options: fast-tracking (parallelization), crashing (adding capacity), or scope descoping
- Drafting objective, professional explanations of variance for clients
- Structuring internal escalation briefings for senior executive leadership
- Creating an operational intervention plan for the next 24 to 72 hours

---

## Input (Information to Provide to the AI)

After loading this context, submit the delay data with confidential details masked:

```
### Project Metadata
- Project Name (Sanitized):
- Current Phase:
- Remaining Time to Final Release:

### Delayed Workstreams
- Specific activities experiencing slippage:
- Measured delay (days/weeks):
- Root causes (external dependency delays, staffing friction, technical blockers):

### Remaining Work & Critical Path
- Detailed list of remaining tasks:
- Workstreams located strictly on the critical path:

### Available Resources & Levers
- Current team capacity & bandwidth:
- Feasibility of external engineering reinforcement:
- Non-critical features potentially eligible for scope trade-offs:

### Constraints & Immovable Deadlines
- Contractual or client-announced hard delivery dates:
- Client counterpart notification status:
```

---

## Expected Output

### 1. Root Cause Diagnosis
Categorizing delay factors into external dependencies vs. internal execution challenges.

### 2. Critical Path Impact Assessment
Analyzing how upstream slippages compress downstream test windows and final release gates.

### 3. Structured Recovery Scenarios (Options A, B, C)
Evaluating actionable paths:
- Option A: Critical path focus & test case prioritization
- Option B: Capacity crashing (reinforcements)
- Option C: Scope pruning / descoping non-core features to v1.1

### 4. Operational Priority Ranking
Determining which workstreams must receive 100% focused capacity immediately.

### 5. Task Pruning & De-scoping Candidates
Identifying non-critical, secondary tasks that can be deferred or simplified safely.

### 6. Resource Support & Reinforcement Requirements
Pinpointing specific technical or testing resources required to compress timelines.

### 7. Client Communication Strategy
Framing transparent, constructive explanations for the customer focused on containment and reliable next dates.

### 8. Internal Escalation & Governance Alignment
Outlining required managerial sign-offs before communicating with clients.

### 9. Immediate Operational Plan (Next 24 to 72 Hours)
Concrete, hour-by-hour action plan to stabilize project velocity.

---

## Standard Prompt Template

```text
# Schedule Delay Recovery Request

Using the contexts below, structure an operational delay recovery strategy based on the provided project data.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of DELAY_RECOVERY_CONTEXT.md here]

---

## Delay Data (Sanitized)

[Paste sanitized schedule and delay details here]

---

## Requested Deliverables

1. Root Cause Diagnosis
2. Critical Path Impact Assessment
3. Structured Recovery Scenarios (Options A, B, C)
4. Operational Priority Ranking
5. Task Pruning & De-scoping Candidates
6. Resource Support Requirements
7. Client Communication Strategy
8. Internal Escalation & Governance Alignment
9. Immediate Operational Plan (Next 24 to 72 Hours)

*Note: AI output serves as analytical support. Final recovery commitments remain human responsibility.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Structure an operational schedule delay recovery plan based on the provided project situation.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of DELAY_RECOVERY_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized schedule and delay details here]
</input>
<constraints>
- Prioritize critical path feasibility and objective recovery options.
- Frame client explanations constructively without making premature schedule promises.
- Highlight risks associated with compressed testing or task pruning.
</constraints>
<output_format>
1. Root Cause Diagnosis
2. Critical Path Impact Assessment
3. Structured Recovery Scenarios (Options A, B, C)
4. Operational Priority Ranking
5. Task Pruning & De-scoping Candidates
6. Resource Support Requirements
7. Client Communication Strategy
8. Internal Escalation & Governance Alignment
9. Immediate Operational Plan (Next 24 to 72 Hours)
</output_format>
```
