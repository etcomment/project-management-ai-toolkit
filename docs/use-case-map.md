# Use Case Map

A guide to selecting the right AI Context or Claude Code Skill based on your immediate project challenge or delivery phase.

---

## 1. Select by Operational Goal

| Your Immediate Goal | Recommended Context File | Recommended Claude Code Skill | Key Output |
|---|---|---|---|
| Review and diagnose overall project health | `contexts/PROJECT_HEALTH_CHECK.md` | `project-health-check` | Risk level rating (🔴/🟡/🟢), overlooked risks, next 24-72h actions |
| Structure a progress or status report | `contexts/STATUS_REPORT_CONTEXT.md` | `status-report` | Dual internal & client reports, 3-line executive summary |
| Audit issues and reprioritize blockers | `contexts/ISSUE_RISK_CONTEXT.md` | `issue-risk-review` | Issue categorization, priority realignment, governance gap identification |
| Draft a client communication or briefing | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` | `client-communication` | Diplomatic client-facing draft, talking points, counter-objection strategy |
| Triage a project crisis or severe outage | `contexts/FIRE_RESPONSE_FIRST_72H.md` | `fire-response-first-72h` | Separation of facts vs. speculation, blast radius, Day 1-3 triage roadmap |
| Convert raw meeting notes into minutes | `contexts/MEETING_MINUTES_CONTEXT.md` | `meeting-minutes` | Executive minutes, decision log, TODO register with owners and deadlines |
| Prepare a weekly meeting agenda | `contexts/WEEKLY_MEETING_CONTEXT.md` | — | Time-boxed agenda, critical decision points, pre-meeting checklist |
| Evaluate a scope change or new feature | `contexts/SCOPE_CHANGE_CONTEXT.md` | `scope-change-review` | Baseline scope variance, effort estimation, trade-off options (A/B/C) |
| Structure a schedule delay recovery plan | `contexts/DELAY_RECOVERY_CONTEXT.md` | `delay-recovery` | Root-cause analysis, critical path crashing/fast-tracking options |
| Analyze causes and solutions for a defect | `contexts/QUALITY_ISSUE_CONTEXT.md` | — | Direct vs. systemic root causes, CAPA plan, client briefing draft |
| Run a sprint retrospective or post-mortem | `contexts/RETROSPECTIVE_CONTEXT.md` | — | Keep/Problem/Try (KPT) matrix, systemic takeaways, continuous improvements |
| Prepare an executive sponsor briefing | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` | `stakeholder-strategy` | 1-page executive summary, milestone tracker, strategic decision memo |
| Frame assumptions before formal estimation | `contexts/ESTIMATION_CONTEXT.md` | — | Pre-estimation assumption register, scope boundary exclusions, questionnaire |
| Conduct cross-portfolio delivery reviews | `contexts/PMO_REVIEW_CONTEXT.md` | — | Portfolio delivery health matrix, systemic risk patterns, PMO triage plan |
| Translate tech blockers into business terms | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` | — | Business-impact translation, trade-off matrix, specific PM actions requested |
| Unsure where to start / Multi-issue triage | — | `pm-ai-diagnosis` | Triaged problem breakdown, recommended Contexts and Skills roadmap |
| Detect unstated, latent project risks | — | `project-risk-radar` | Early warning signals, unstated dependencies, blind spots |
| Structure a complex managerial decision | — | `pm-decision-support` | Boundary constraints, comparative trade-off matrix, strategic rationale |
| Audit an AI-drafted message before sending | — | `ai-output-governance-review` | Overcommitment detection, data leak checks, protective rewrites |

---

## 2. Select by Project Delivery Phase

### Requirements & Proposal Phase
- `contexts/ESTIMATION_CONTEXT.md`: Establish technical assumptions, exclusions, and clarification questions before sizing.
- `contexts/CLIENT_COMMUNICATION_CONTEXT.md`: Structure diplomatic consultation memos and scope alignment messages.

### Architecture & Design Phase
- `contexts/SCOPE_CHANGE_CONTEXT.md`: Detect early scope creep and establish clear baseline boundaries.
- `contexts/WEEKLY_MEETING_CONTEXT.md`: Coordinate weekly architectural syncs and stakeholder reviews.

### Development Phase
- `contexts/STATUS_REPORT_CONTEXT.md`: Generate weekly status reports for engineering leadership and clients.
- `contexts/ISSUE_RISK_CONTEXT.md`: Audit active issues, eliminate unassigned tasks, and manage dependencies.
- `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md`: Bridge communication gaps between Tech Leads and Project Managers.
- `contexts/DELAY_RECOVERY_CONTEXT.md`: Formulate recovery plans (fast-tracking/crashing) when delays emerge.

### Testing & QA Phase
- `contexts/PROJECT_HEALTH_CHECK.md`: Multi-dimensional check on test progress, defect spikes, and release readiness.
- `contexts/QUALITY_ISSUE_CONTEXT.md`: Conduct root-cause analyses on QA escapes or critical defect spikes.
- `contexts/FIRE_RESPONSE_FIRST_72H.md`: Triage severe blockers discovered immediately before release gates.

### Release & Project Closeout Phase
- `contexts/STAKEHOLDER_REPORT_CONTEXT.md`: Prepare final delivery summaries for executive sponsors and SteerCos.
- `contexts/RETROSPECTIVE_CONTEXT.md`: Facilitate blameless post-mortems and consolidate institutional lessons learned.

---

## 3. Recommended Next Actions

1. Review practical implementation examples in [`examples/`](../examples/).
2. Follow the learning progression in [`docs/learning-roadmap.md`](learning-roadmap.md).
3. Review safety and data protection guidelines in [`docs/ai-safety.md`](ai-safety.md).
