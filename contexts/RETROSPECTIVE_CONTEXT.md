# Retrospective Context

---

## Purpose

This context assists Project Managers in facilitating post-project, post-sprint, or post-incident retrospectives. It supports structuring lessons learned, categorizing Keep / Problem / Try (KPT) elements, conducting root-cause reviews, and institutionalizing continuous improvement.

**AI does not replace professional PM judgment.** AI assists in organizing feedback and synthesizing takeaways. Retrospectives must foster psychological safety and team trust without assigning individual blame.

> [!CAUTION]
> Never input real client names, corporate identities, individual identities, or credentials into the AI.
> Do not use AI to conduct individual performance reviews or attribute personal culpability.

---

## Use Cases

- Structuring project closeout retrospectives or sprint reviews (Scrum / Agile)
- Organizing post-mortem analyses following project crises or major delivery milestones
- Synthesizing feedback from team members into Keep, Problem, and Try frameworks
- Formulating actionable organizational lessons learned for the PMO knowledge base
- Developing continuous improvement initiatives for future delivery cycles

---

## Input (Information to Provide to the AI)

```
### Retrospective Metadata
- Project / Sprint Name (Sanitized):
- Delivery Cycle Duration:
- Team Composition (Roles):

### What Went Well (Keep / Positives)
- Successful technical choices, processes, or teamwork dynamics:

### What Encountered Friction (Problem / Challenges)
- Difficulties in scope, schedule, quality, communication, or tooling:

### Team Ideas & Suggestions (Try / Experiments)
- Proposals from team members for future sprints:

### Key Metrics & Delivery Outcomes
- Variance against original schedule/budget:
- Final defect counts & velocity:
```

---

## Expected Output

### 1. Retrospective Executive Synthesis
Balanced summary highlighting key achievements, core bottlenecks, and overall trajectory.

### 2. Structured KPT Matrix (Keep / Problem / Try)
Categorized feedback organized into clear operational themes (Engineering, Process, Governance, Collaboration).

### 3. Systemic Root-Cause Insights
Underlying organizational dynamics contributing to recurring friction points.

### 4. Prioritized Action Items for Next Cycle
Top 3 to 5 high-impact process improvements with designated owners and measurable success criteria.

### 5. Institutional Lessons Learned (PMO Knowledge Asset)
Key principles to add to the organizational playbook for future projects.

---

## Standard Prompt Template

```text
# Project Retrospective & Lessons Learned Request

Using the contexts below, structure the team's retrospective notes into an actionable continuous improvement plan.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of RETROSPECTIVE_CONTEXT.md here]

---

## Retrospective Input Data (Sanitized)

[Paste sanitized retrospective notes here]

---

## Requested Deliverables

1. Retrospective Executive Synthesis
2. Structured KPT Matrix (Keep / Problem / Try)
3. Systemic Root-Cause Insights
4. Prioritized Action Items for Next Cycle (Owners & Success Metrics)
5. Institutional Lessons Learned for the PMO Playbook

*Note: AI output serves as analytical support. Final retrospective actions are decided by the team.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Structure the provided retrospective notes into a comprehensive KPT matrix, root-cause analysis, and continuous improvement plan.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of RETROSPECTIVE_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste sanitized retrospective notes here]
</input>
<constraints>
- Maintain a blameless, growth-oriented, and constructive tone.
- Group disparate comments into overarching systemic themes.
- Ensure action items are concrete, measurable, and realistically scoped.
</constraints>
<output_format>
1. Retrospective Executive Synthesis
2. Structured KPT Matrix (Keep / Problem / Try)
3. Systemic Root-Cause Insights
4. Prioritized Action Items for Next Cycle
5. Institutional Lessons Learned for the PMO Playbook
</output_format>
```
