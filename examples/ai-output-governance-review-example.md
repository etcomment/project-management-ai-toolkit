# AI Output Governance Review — Practical Scenario

## Use Case

Utilizing `.claude/skills/ai-output-governance-review/SKILL.md` to audit an AI-generated draft client announcement for premature commitments, data leaks, and contractual liabilities prior to sending.

---

## Contexts & Skills Used

- `.claude/skills/ai-output-governance-review/SKILL.md`
- `contexts/CLIENT_COMMUNICATION_CONTEXT.md`
- `contexts/STATUS_REPORT_CONTEXT.md`
- `docs/ai-safety.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
[Draft Message for Review]
"At this stage, there is absolutely no impact on the target delivery date.
As soon as external API specifications are finalized, we will implement the features as scheduled.
Regarding your additional feature requests, we will accommodate them all within the current project schedule.
Quality is completely under control, and the production release will proceed without issue on the planned date."

[Intended Use]
Draft text for the weekly progress report email to Client Lead A.
(All company and client names have been masked.)
```

---

## Prompts for Claude Code

### Standard Prompt
```text
Based on .claude/skills/ai-output-governance-review/SKILL.md,
audit the draft message above for dangerous overcommitments, unverified claims, and contractual liabilities.
```

### Claude Structured XML Prompt
```text
<task>
Audit the provided draft client communication using .claude/skills/ai-output-governance-review/SKILL.md.
</task>
<input>
[Paste Sanitized Input above]
</input>
<constraints>
- Evaluate the communication assuming it will be sent directly to the customer.
- Flag statements that create premature commercial or legal liability.
- Provide professional, protective alternative phrasings for all flagged statements.
</constraints>
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Governance Review Verdict

| Criterion | Assessment |
|---|---|
| **Ready for External Dissemination?** | **❌ Revision Required (Do Not Send As-Is)** |
| **Primary Risk Drivers** | Definitive promises regarding timeline integrity, unapproved absorption of scope additions without change orders, and unqualified quality warranties. |

---

### 2. Flagged Statements & Corrective Rewrites

| Original AI Statement | Governance & Commercial Risk | Recommended Protective Phrasing |
|---|---|---|
| *"There is absolutely no impact on the target delivery date"* | Premature commitment creating commercial liability if external API stalls persist | *"At this stage, no major schedule variance has been confirmed, pending final stabilization of the external API specifications which remains under close monitoring."* |
| *"Regarding your additional feature requests, we will accommodate them all within the current project schedule"* | Uncompensated scope concession binding the team to unestimated work | *"Regarding the requested additions, we are finalizing operational impact assessments to determine the appropriate delivery path and options with you."* |
| *"Quality is completely under control, and the release will proceed without issue"* | Unqualified warranty implying zero-defect liability | *"Quality gates are actively being executed, and preliminary checks have identified no critical blockers to proceeding with scheduled test phases."* |

---

### 3. Pre-Dissemination Verification Checklist

- [ ] Obtain technical validation of the revised wording from the Lead Developer.
- [ ] Confirm alignment with Account Executive regarding feature addition policy.
- [ ] Ensure all dates and milestones referenced match approved contract schedules.
