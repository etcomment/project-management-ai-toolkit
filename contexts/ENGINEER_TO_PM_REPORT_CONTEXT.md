# Engineer to PM Report Context

---

## Purpose

This context assists Tech Leads, Senior Engineers, and Architects in translating technical blockers, architectural constraints, technical debt, and engineering trade-offs into business-impact language that Project Managers and business stakeholders can readily understand and arbitrate.

**AI does not replace engineering leadership judgment.** AI assists in framing and translating technical complexity. Technical recommendations and architectural decisions must be owned by the engineering leads.

> [!CAUTION]
> Never enter proprietary source code, secrets, API keys, passwords, or detailed technical credentials into the AI.
> Do not input real client names, corporate identities, or contractual figures.
> Abstract technical challenges into concepts, dependencies, delivery risks, and business impacts.

---

## Use Cases

- Translating complex technical blockers into business risk and schedule impact for the PM
- Structuring escalation memos when technical debt or infrastructure issues threaten milestones
- Presenting clear technical decision options (e.g., Quick Patch vs. Clean Refactor) with schedule/cost trade-offs
- Requesting PM assistance to unblock client-side technical dependencies or API access
- Aligning engineering realities with commercial project commitments

---

## Input (Information to Provide to the AI)

```
### Technical Issue Metadata
- Module / Feature Name (Sanitized):
- Nature of Challenge: (Architectural bottleneck, external API defect, performance degradation, technical debt)
- Delivery Target at Risk:

### Technical Details (Abstracted / Conceptual)
- What is happening technically:
- Why it cannot be resolved with standard development effort:
- Estimated time/effort to resolve under different approaches:

### Impact on Schedule & Quality
- Features or dependencies blocked:
- Impact on upcoming test cycles or release dates:

### Potential Options / Solutions
- Option 1 (e.g., Quick workaround / high technical debt):
- Option 2 (e.g., Proper architectural refactor / requires schedule extension):
```

---

## Expected Output

### 1. Executive Problem Summary (PM-Friendly)
Translating the technical blocker into plain, concise business terminology without jargon.

### 2. Business & Milestone Blast Radius
Explicitly showing how the engineering challenge translates into schedule delays, testing compression, or budget risks.

### 3. Structured Solution Options Matrix
Comparing Option A, Option B, and Option C across Effort, Timeline Impact, Quality/Debt Risk, and Feasibility.

### 4. Action Requested from PM
Concrete steps requested from management (e.g., renegotiate API deadline with client, authorize 3-day schedule buffer).

### 5. Synchronous Alignment Talking Points
Concise talking points for the Tech Lead to use during the next 1-on-1 with the PM.

---

## Standard Prompt Template

```text
# Engineer to PM Technical Escalation Request

Using the contexts below, translate the engineering challenge into a structured, business-aligned escalation memo for the Project Manager.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of ENGINEER_TO_PM_REPORT_CONTEXT.md here]

---

## Technical Challenge Data (Sanitized)

[Paste sanitized engineering details here]

---

## Requested Deliverables

1. Executive Problem Summary (PM-Friendly)
2. Business & Milestone Blast Radius
3. Structured Solution Options Matrix (Trade-Offs)
4. Specific Action Requested from the PM
5. 1-on-1 Meeting Talking Points

*Note: AI output serves as communication support. Technical evaluations remain engineering leadership responsibility.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Translate the provided technical engineering challenge into a structured, business-aligned escalation memo for the PM.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of ENGINEER_TO_PM_REPORT_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized engineering details here]
</input>
<constraints>
- Avoid raw technical jargon; emphasize business impact, critical path risk, and quality implications.
- Present clear, balanced trade-offs for each proposed technical option.
- Keep recommendations actionable and respectful of PM delivery constraints.
</constraints>
<output_format>
1. Executive Problem Summary (PM-Friendly)
2. Business & Milestone Blast Radius
3. Structured Solution Options Matrix (Trade-Offs)
4. Specific Action Requested from the PM
5. 1-on-1 Meeting Talking Points
</output_format>
```
