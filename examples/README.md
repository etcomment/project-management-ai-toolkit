# Examples — Practical Use Cases

This directory contains concrete, real-world practical scenarios illustrating how to apply the toolkit's AI Contexts and Claude Code Skills.

---

## Purpose of This Directory

Explore how to use each context file effectively through realistic input data, tailored prompts, and expected AI outputs.

---

## Critical Notices & Safeguards

> [!IMPORTANT]
> **All examples are strictly based on fabricated, fictitious data.** No real client names, corporate identities, personal information, or credentials are included.
>
> Never enter confidential operational data (client names, contract figures, proprietary source code, credentials) into AI services.
> Always sanitize and abstract project data prior to prompting. See [`docs/ai-safety.md`](../docs/ai-safety.md).

> [!WARNING]
> **AI outputs never substitute for professional project management judgment.** All generated outputs must be reviewed, verified, and adapted by a human manager.
> Always validate content before transmitting to clients, submitting to leadership, or committing to deadlines and budgets.

---

## Practical Scenarios Catalog

| Scenario File | Operational Focus |
|---|---|
| [project-health-check-example.md](project-health-check-example.md) | Comprehensive diagnostic audit of project health |
| [status-report-example.md](status-report-example.md) | Progress reporting tailored for management and clients |
| [issue-risk-review-example.md](issue-risk-review-example.md) | Backlog audit, gap detection, and risk reprioritization |
| [meeting-minutes-example.md](meeting-minutes-example.md) | Converting raw meeting notes into structured minutes & TODOs |
| [fire-response-first-72h-example.md](fire-response-first-72h-example.md) | Crisis triage and containment during the first 72 hours |
| [scope-change-example.md](scope-change-example.md) | Scope change impact assessment and trade-off options |
| [delay-recovery-example.md](delay-recovery-example.md) | Schedule delay recovery planning (crashing / fast-tracking) |
| [claude-code-pm-review-example.md](claude-code-pm-review-example.md) | Utilizing Claude Code Skills to audit project repositories |
| [pm-ai-diagnosis-example.md](pm-ai-diagnosis-example.md) | Diagnosing delivery friction and navigating Contexts/Skills |
| [project-risk-radar-example.md](project-risk-radar-example.md) | Detecting latent, unstated project risks from raw updates |
| [ai-output-governance-review-example.md](ai-output-governance-review-example.md) | Auditing AI-drafted messages before external transmission |

---

## File Mapping Matrix

| Scenario | Associated Contexts & Skills |
|---|---|
| project-health-check-example.md | `contexts/PM_CONTEXT.md`, `contexts/PROJECT_HEALTH_CHECK.md` |
| status-report-example.md | `contexts/PM_CONTEXT.md`, `contexts/STATUS_REPORT_CONTEXT.md` |
| issue-risk-review-example.md | `contexts/PM_CONTEXT.md`, `contexts/ISSUE_RISK_CONTEXT.md` |
| meeting-minutes-example.md | `contexts/PM_CONTEXT.md`, `contexts/MEETING_MINUTES_CONTEXT.md` |
| fire-response-first-72h-example.md | `contexts/PM_CONTEXT.md`, `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| scope-change-example.md | `contexts/PM_CONTEXT.md`, `contexts/SCOPE_CHANGE_CONTEXT.md` |
| delay-recovery-example.md | `contexts/PM_CONTEXT.md`, `contexts/DELAY_RECOVERY_CONTEXT.md` |
| claude-code-pm-review-example.md | `contexts/PM_CONTEXT.md`, `.claude/skills/pm-review/SKILL.md` |
| pm-ai-diagnosis-example.md | `.claude/skills/pm-ai-diagnosis/SKILL.md`, `contexts/PM_CONTEXT.md`, `contexts/PROJECT_HEALTH_CHECK.md`, `contexts/STATUS_REPORT_CONTEXT.md`, `contexts/ISSUE_RISK_CONTEXT.md`, `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| project-risk-radar-example.md | `.claude/skills/project-risk-radar/SKILL.md`, `contexts/PROJECT_HEALTH_CHECK.md`, `contexts/ISSUE_RISK_CONTEXT.md`, `contexts/DELAY_RECOVERY_CONTEXT.md` |
| ai-output-governance-review-example.md | `.claude/skills/ai-output-governance-review/SKILL.md`, `contexts/CLIENT_COMMUNICATION_CONTEXT.md`, `contexts/STATUS_REPORT_CONTEXT.md`, `docs/ai-safety.md` |

---

## Human Review Points

Every scenario includes a dedicated **Human Review Points** section highlighting critical operational checkpoints that human managers must inspect before adopting AI-generated outputs.

Refer to [`docs/usage-guide.md`](../docs/usage-guide.md) and [`docs/legal/DISCLAIMER.md`](../docs/legal/DISCLAIMER.md) for full governance details.
