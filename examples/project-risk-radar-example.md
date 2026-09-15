# Project Risk Radar — Practical Scenario

## Use Case

Utilizing `.claude/skills/project-risk-radar/SKILL.md` to detect latent, unstated project risks and blind spots from informal progress updates and team notes.

---

## Contexts & Skills Used

- `.claude/skills/project-risk-radar/SKILL.md`
- `contexts/PROJECT_HEALTH_CHECK.md`
- `contexts/ISSUE_RISK_CONTEXT.md`
- `contexts/DELAY_RECOVERY_CONTEXT.md`

---

## Sanitized Input

> **Notice:** All data below is completely fictitious. No real client, company, or individual names are used.

```
[Informal Progress Notes]
- Current Phase: Mid-development
- Core Feature A: Implementation underway, tracking ~70% completion
- Core Feature B: Suspended awaiting external third-party API specifications
- Staging Environment Setup: Deferred to next week due to devops bandwidth
- Pending Client Decisions: 2 UI screen layouts and 1 batch report format
- Issue Backlog: 3 out of 10 items currently lack assigned owners
- Next Weekly Sync: Next Wednesday
- Target Release Date: Currently unchanged on paper
(All client and company names have been masked.)
```

---

## Prompts for Claude Code

### Standard Prompt
```text
Based on .claude/skills/project-risk-radar/SKILL.md,
scan the progress notes above and detect latent, unstated delivery risks.
```

### Claude Structured XML Prompt
```text
<task>
Scan the provided progress notes using .claude/skills/project-risk-radar/SKILL.md to uncover latent delivery risks and blind spots.
</task>
<input>
[Paste Sanitized Input above]
</input>
<constraints>
- Anchor all identified risks in tangible evidence from the input; tag inferences as "(Inferred)".
- Do not assert definitive schedule failure; evaluate probability and potential delay objectively.
</constraints>
```

---

## Expected Output

An illustrative example of the expected AI evaluation:

---

### 1. Risk Radar Summary
While the official release date is nominally "unchanged on paper", the notes reveal four compounding latent risks that threaten to trigger an unrecoverable delivery crisis: external API specification stalls, environment setup delays, pending client UI approvals, and unowned backlog items.

---

### 2. Detected Latent Risk Register

| Priority | Latent Risk | Trigger Evidence | Impact Scope | Probability | Recommended Preventive Action |
|---|---|---|---|---|---|
| **High** | Schedule Slip via External API Blockage | "Feature B suspended awaiting external API specs" | Feature B implementation & integration testing | High | Request formal confirmation date for API specs; evaluate mock API implementation. |
| **High** | QA Test Window Compression | "Staging environment setup deferred to next week" | Integration testing kickoff & bug discovery | High | Lock in hard deadline for staging readiness; assign dedicated DevOps resource. |
| **Medium** | Decision Vacuum on Critical Issues | "3 out of 10 items lack assigned owners" | Operational issue resolution velocity | Medium | Immediately assign owners and deadlines to all 3 orphaned issues. |

---

### 3. Critical Investigative Questions for the PM

- When exactly will the third-party API specifications be formally finalized?
- Can engineering implement against a mock interface to prevent developer downtime?
- Will postponing the staging environment compress the total duration allocated for UAT?
- Who possesses the authority and accountability to resolve the 3 unassigned issues?
