# Claude Usage Guide

A guide for leveraging the toolkit within Anthropic's Claude chat interface and Claude Projects.

---

## 1. Setup in Claude Projects

1. Open Claude and select **Projects** -> **Create Project**.
2. Name your project (e.g., "PM Delivery Governance").
3. Paste the contents of [`instructions/claude-project-instructions.md`](../../instructions/claude-project-instructions.md) into the **Project Instructions** field.
4. Upload relevant sanitized context files (such as `contexts/PM_CONTEXT.md` and `contexts/ISSUE_RISK_CONTEXT.md`) into Project Knowledge.

---

## 2. XML Prompting Best Practices for Claude

Claude models are specifically optimized to process structured XML delimiters. Each file in `contexts/` includes a dedicated XML template:

```text
<task>
Analyze the provided project status and structure a 72-hour crisis response plan.
</task>
<context>
[Paste contents of specific context file here]
</context>
<input>
[Paste sanitized project data here]
</input>
<constraints>
- Base findings strictly on facts; tag inferences as "(Inferred)".
- Highlight unassigned tasks as governance gaps.
</constraints>
<output_format>
1. Executive Situation Summary
2. Risk Level Rating & Rationale
3. Action Plan
</output_format>
```

---

## 3. Benefits of Claude's Large Context Window

- Claude's extensive context window allows loading multiple context files simultaneously (e.g., `PM_CONTEXT.md` + `STATUS_REPORT_CONTEXT.md` + `CLIENT_COMMUNICATION_CONTEXT.md`).
- Enables cross-referencing past meeting minutes with current issue backlogs to detect creeping delays.
