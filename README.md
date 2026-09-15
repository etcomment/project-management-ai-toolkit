# Project Management AI Toolkit

An AI enablement toolkit designed for Project Managers (PMs), PMOs, and Tech Leads. Provides production-ready AI Contexts, operational workflows, Claude Code Skills, and practical templates compatible with ChatGPT, Gemini, Claude, and Claude Code.

## Getting Started

This repository equips delivery leadership with structured AI Contexts, operational prompts, and specialized skills to integrate generative AI safely and effectively into daily software engineering workflows.

For an overarching view of the platform and curriculum:

- [Explore the PM AI Toolkit Platform](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_top_ai_toolkit)
- [Diagnostic Career & Course Assessment](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_top_course_diagnosis)
- [Join the PM & AI Community Lab](https://techaide.jp/community/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_top_community)
- [Security & Governance Guidelines](docs/ai-safety.md)

## First Time Here: Recommended Path

If you are exploring this toolkit for the first time, follow this sequence:

1. Review [`docs/use-case-map.md`](docs/use-case-map.md) to select the right AI Context for your immediate challenge.
2. Examine practical scenario walk-throughs in [`examples/`](examples/).
3. Study [`docs/ai-safety.md`](docs/ai-safety.md) to master mandatory data sanitization standards.
4. Follow the progressive learning curriculum in [`docs/learning-roadmap.md`](docs/learning-roadmap.md).
5. For structured professional development, explore masterclasses on the [TechAide Official Website](https://techaide.jp/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_next_official_site).
6. Take the [Course Diagnostic](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_next_course_diagnosis) to identify relevant training tracks.
7. Connect with peers and receive updates via the [PM & AI Community Lab](https://techaide.jp/community/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_next_community).

---

## What This Toolkit Enables

- Structure and frame the PM mental model (AI Contexts) before querying models.
- Test production-grade contexts for status reporting, risk audits, client communication, and crisis triage.
- Explore realistic implementations through sanitized, fabricated project scenarios.
- Master pre-prompting sanitization protocols to safeguard enterprise confidentiality.

## What Requires In-Depth Training

Core managerial competencies that extend beyond prompting templates and require methodical study include:
- Understanding the underlying organizational reasons behind specific evaluation dimensions.
- Sequenced decision modeling: prioritizing trade-offs between timeline, budget, and scope.
- Calibrating diplomacy and communication across clients, sponsors, and engineering leads.
- Critically reviewing AI outputs to translate draft recommendations into binding business arbitrations.
- Standardizing and governing AI adoption across distributed enterprise PMOs.

Advanced training programs covering these disciplines are offered on the TechAide platform.

---

## Repository Structure

```text
contexts/       → Core AI Contexts: PM mental models, evaluation criteria, and prompt templates
instructions/   → System Instructions: Ready-to-copy prompts for ChatGPT, Gemini, and Claude
docs/tools/     → Tool Guides: Practical integration guides for each generative AI platform
examples/       → Real-World Scenarios: Fully worked examples on fabricated project data
.claude/skills/ → Claude Code Skills: Specialized CLI skills for automated PM audits
.github/        → GitHub Governance: Issue templates, PR checklists, and security policies
```

## Quick Start

### 1. Review `contexts/PM_CONTEXT.md`
Contains universal operating principles and baseline criteria for all PM-assisted AI tasks.

### 2. Choose the Matching Context File

| Operational Need | Recommended Context File |
|---|---|
| Review and evaluate overall project health | `contexts/PROJECT_HEALTH_CHECK.md` |
| Draft tailored status reports | `contexts/STATUS_REPORT_CONTEXT.md` |
| Audit issue registers and manage risks | `contexts/ISSUE_RISK_CONTEXT.md` |
| Prepare diplomatic client communications | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| Triage a project crisis during the first 72 hours | `contexts/FIRE_RESPONSE_FIRST_72H.md` |

### 3. Supply Context and Sanitized Data to Your AI Model

```
Based on the project management context below, evaluate our current delivery status from a senior PM perspective.

[Paste content of selected context file]

[Paste sanitized project metrics and status data]
```

### 4. Human Verification & Decision Sign-Off
AI outputs are working drafts. Never disseminate or commit to AI-generated dates, costs, or scope changes without thorough human review.

## Additional Operational Contexts

| Operational Need | Context File |
|---|---|
| Converting meeting notes into minutes & action items | `contexts/MEETING_MINUTES_CONTEXT.md` |
| Preparing time-boxed weekly meeting agendas | `contexts/WEEKLY_MEETING_CONTEXT.md` |
| Evaluating scope changes and feature additions | `contexts/SCOPE_CHANGE_CONTEXT.md` |
| Formulating schedule delay recovery plans | `contexts/DELAY_RECOVERY_CONTEXT.md` |
| Root-cause analysis for quality regressions | `contexts/QUALITY_ISSUE_CONTEXT.md` |
| Facilitating sprint retrospectives and post-mortems | `contexts/RETROSPECTIVE_CONTEXT.md` |
| Preparing executive steering committee briefings | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` |
| Structuring pre-estimation technical assumptions | `contexts/ESTIMATION_CONTEXT.md` |
| Cross-portfolio delivery reviews under PMO | `contexts/PMO_REVIEW_CONTEXT.md` |
| Translating engineering blockers for PM arbitration | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` |

## Tool Integration Guides

Refer to `docs/tools/` for platform-specific integration guides:

| Platform | Integration Guide |
|---|---|
| ChatGPT | `docs/tools/chatgpt.md` |
| Gemini | `docs/tools/gemini.md` |
| Claude | `docs/tools/claude.md` |
| Claude Code | `docs/tools/claude-code.md` |

System instruction templates are available in `instructions/`.

## Claude Code Skills

Specialized Claude Code Skills reside in `.claude/skills/`.

For new users, explore these foundational skills first:
- `.claude/skills/pm-ai-diagnosis/SKILL.md`: Triages delivery friction and navigates Contexts/Skills.
- `.claude/skills/project-risk-radar/SKILL.md`: Uncovers latent risks and blind spots from informal notes.
- `.claude/skills/pm-decision-support/SKILL.md`: Structures trade-off evaluations and managerial decisions.
- `.claude/skills/stakeholder-strategy/SKILL.md`: Calibrates communication plans across diverse audiences.
- `.claude/skills/ai-output-governance-review/SKILL.md`: Audits AI drafts for overcommitments and data leaks.

For the full catalog, see [`.claude/skills/README.md`](.claude/skills/README.md). All skills are pure documentation; zero executable scripts or hooks are included.

## Caution & Operational Safeguards

> [!CAUTION]
> This toolkit provides reference methodologies and prompt templates to support project managers.
>
> AI outputs never replace professional managerial judgment, legal counsel, contractual determinations, labor relations advisory, or cybersecurity assessments.
>
> All outputs must be reviewed, adapted, and approved by qualified human managers prior to operational use.

## Strictly Prohibited Information

Never enter any of the following into AI platforms:
- Real client names, corporate identities, or partner organization names
- Personally Identifiable Information (PII), contract terms, or full meeting transcripts
- Unreleased business plans, proprietary algorithms, or source code
- Security credentials (API keys, passwords, access tokens, connection strings)
- Information restricted under Non-Disclosure Agreements (NDAs)

Always sanitize and abstract project data before prompting.

## Claude Code Operational Boundaries

Skills under `.claude/skills/` are purely advisory documents. This repository intentionally excludes:
- Executable hooks or automated background scripts
- Third-party MCP configurations or automated GitHub Actions
- Sample scripts requiring live commercial API keys
- Automated commit or auto-deployment mechanisms

## Community & Engagement

The PM & AI Community Lab shares updates, prompt engineering tips, and learning pathways:
- Receive release notes for new Contexts and Skills
- Learn practical prompting patterns across ChatGPT, Gemini, Claude, and Claude Code
- Access curated articles and video masterclasses

[Join the PM & AI Community Lab](https://techaide.jp/community/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_discord_community)

See [`docs/community.md`](docs/community.md) for participation guidelines.

---

## Related Resources

Published and maintained by TechAide Inc. (TechAide Co., Ltd.).

- [Official Website](https://techaide.jp/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_official_site)
- [PM AI Toolkit Platform](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_ai_toolkit)
- [PM & AI Community Lab](https://techaide.jp/community/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_community)
- [Course Diagnostic Assessment](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_course_diagnosis)
- [Instructor Discount Coupons](https://techaide.jp/coupons/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_coupons)
- [Course Catalog](https://techaide.jp/courses/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_courses)
- [Learning Roadmaps](https://techaide.jp/learning-roadmaps/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_learning_roadmaps)

## Disclaimer

TechAide Inc. provides this repository and AI outputs generated using it on an "as-is" basis, without warranties of accuracy, completeness, or fitness for purpose. See [`docs/legal/DISCLAIMER.md`](docs/legal/DISCLAIMER.md).

## License

Usage terms are defined in `LICENSE.md` and [`docs/legal/TERMS.md`](docs/legal/TERMS.md).

## Security Policy

For vulnerability reporting, consult [`.github/SECURITY.md`](.github/SECURITY.md).

## Contributions

Report bugs and propose improvements via Issues. See [`.github/CONTRIBUTING.md`](.github/CONTRIBUTING.md).
