# PM × AI Diagnosis — Practical Scenario

## Use Case

Utilizing `.claude/skills/pm-ai-diagnosis/SKILL.md` to triage multi-faceted project delivery friction, distinguish PM challenges from AI workflow issues, and select the exact AI Contexts and Skills needed.

---

## Contexts & Skills Used

- `.claude/skills/pm-ai-diagnosis/SKILL.md`
- `contexts/PM_CONTEXT.md`
- `contexts/PROJECT_HEALTH_CHECK.md`
- `contexts/STATUS_REPORT_CONTEXT.md`
- `contexts/ISSUE_RISK_CONTEXT.md`
- `contexts/CLIENT_COMMUNICATION_CONTEXT.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
We are currently in mid-development.
Implementation is proceeding, but several specification decisions awaiting client confirmation remain blocked. I am struggling with how to frame these delays in our weekly client status report without sounding defensive.
Additionally, our issue backlog contains 10 items, but several lack assigned owners or deadlines.
I want to use AI to clean up and structure this situation, but I am overwhelmed by the options and unsure which Context file to start with.
(All client names, corporate identities, and personal data have been sanitized.)
```

---

## Prompts for Claude Code

### Standard Prompt
```text
Based on .claude/skills/pm-ai-diagnosis/SKILL.md,
diagnose the situation described above and guide me to the most effective Context files and Skills to resolve it.
```

### Claude Structured XML Prompt
```text
<task>
Diagnose the project situation below and recommend the primary Contexts and Claude Code Skills needed based on .claude/skills/pm-ai-diagnosis/SKILL.md.
</task>
<input>
[Paste Sanitized Input above]
</input>
<constraints>
- Clearly distinguish pure PM challenges from AI workflow bottlenecks and communication hurdles.
- Provide concrete operational rationales for each recommendation.
</constraints>
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Diagnostic Summary
The situation exhibits three interrelated challenges: an operational issue tracking vulnerability (unassigned blockers), a client communication dilemma (how to report delays diplomatically), and an AI workflow question (which toolkit resources to deploy first).

---

### 2. Challenge Categorization Matrix

| Category | Identified Friction | Urgency |
|---|---|---|
| **PM Delivery Issue** | Multiple specifications pending client sign-off; backlog contains unowned and open-ended items | High |
| **Communication Issue** | Uncertainty over tone and framing for weekly client reporting | High |
| **AI Workflow Issue** | Uncertainty over which toolkit Contexts and Skills to deploy | Medium |

---

### 3. Recommended Primary Contexts (`contexts/`)

| Priority | Context File | Operational Purpose |
|---|---|---|
| **High** | `contexts/ISSUE_RISK_CONTEXT.md` | Clean up the 10 backlog issues, assign clear owners, and evaluate critical path impact. |
| **High** | `contexts/STATUS_REPORT_CONTEXT.md` | Generate separate internal and diplomatic client-facing progress reports. |
| **Medium** | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` | Draft a targeted follow-up email establishing a firm response deadline for pending specs. |

---

### 4. Recommended Claude Code Skills (`.claude/skills/`)

| Priority | Skill Name | Operational Purpose |
|---|---|---|
| **High** | `issue-risk-review` | Audit the issue log and surface governance blind spots. |
| **High** | `status-report` | Structure the weekly report with an executive summary and risk table. |
| **Medium** | `stakeholder-strategy` | Calibrate messaging between client management and internal engineering leads. |

---

### 5. Implementation Roadmap (Step-by-Step)
1. **Step 1**: Load `contexts/ISSUE_RISK_CONTEXT.md` and audit your 10-item backlog to assign owners and deadlines.
2. **Step 2**: Use `contexts/STATUS_REPORT_CONTEXT.md` to draft the weekly report, framing client delays objectively.
3. **Step 3**: Use `contexts/CLIENT_COMMUNICATION_CONTEXT.md` to send a diplomatic reminder regarding the pending specifications.
