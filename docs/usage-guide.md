# Usage Guide

A comprehensive guide explaining how to integrate and apply the AI Contexts, System Instructions, and Claude Code Skills across your project management workflows.

---

## 1. What Are AI Contexts?

In standard prompts, users often provide fragmented information without establishing clear operational framing. This frequently results in superficial, generic, or overly optimistic AI responses that are unsuitable for executive decision-making.

**AI Contexts** solve this by supplying the AI model with the professional mental model of a senior project manager:
- Structured analytical categories (Progress, Issues, Risks, Stakeholders, Scope, Quality, Governance)
- Behavioral constraints (Differentiating verified facts from speculation, blameless analysis)
- Clear expectations on deliverable structure (Executive summaries, prioritized action matrices)

---

## 2. Core Workflow: How to Use This Toolkit

```text
1. Select the Context File
   Select the matching file in contexts/ based on docs/use-case-map.md.
   ↓
2. Sanitize Project Information
   Strip all real client names, corporate identities, personal names, and credentials.
   ↓
3. Supply Context & Input to AI
   Load the context file and your sanitized status into ChatGPT, Gemini, or Claude.
   ↓
4. Receive Structured Output
   The AI generates structured situation summaries, issue triage, and draft communications.
   ↓
5. Human Review & Verification (Mandatory)
   A qualified human manager reviews, edits, and validates all findings and commitments.
```

---

## 3. Tool-Specific Integration Patterns

### ChatGPT (Projects / Custom GPTs)
- **Projects**: Paste instructions from [`instructions/chatgpt-project-instructions.md`](../instructions/chatgpt-project-instructions.md) into the Project Custom Instructions field.
- **Custom GPTs**: Follow the step-by-step setup in [`instructions/custom-gpt-instructions.md`](../instructions/custom-gpt-instructions.md).
- **Tool Guide**: See [`docs/tools/chatgpt.md`](tools/chatgpt.md).

### Claude & Claude Projects
- **Claude Projects**: Paste [`instructions/claude-project-instructions.md`](../instructions/claude-project-instructions.md) into Project Instructions.
- **XML Prompting**: Utilize the `<task>`, `<context>`, `<input>`, `<constraints>`, and `<output_format>` templates included in each context file.
- **Tool Guide**: See [`docs/tools/claude.md`](tools/claude.md).

### Claude Code (CLI)
- Claude Code automatically recognizes Skills placed under `.claude/skills/`.
- Run commands like: `claude "Review this repository using .claude/skills/pm-review/SKILL.md"`.
- **Tool Guide**: See [`docs/tools/claude-code.md`](tools/claude-code.md).

### Gemini (Gems)
- Create a Custom Gem and paste [`instructions/gemini-instructions.md`](../instructions/gemini-instructions.md) into the Gem Instructions.
- **Tool Guide**: See [`docs/tools/gemini.md`](tools/gemini.md).

---

## 4. Human-in-the-Loop Principles (Mandatory Review)

AI outputs are **draft working materials and decision-support inputs**, never autonomous operational actions.

Before distributing any AI-generated deliverable:
1. **Verify Factual Accuracy**: Ensure dates, numbers, and completed tasks match ground reality.
2. **Check for Unapproved Commitments**: Eliminate statements promising free scope additions or firm delivery dates without prior management approval.
3. **Calibrate Diplomacy**: Adjust tone according to client organizational politics and relationship dynamics.
4. **Sanitize Data**: Ensure no confidential data, credentials, or proprietary intellectual property was inadvertently included.

For detailed security rules, refer to [`docs/ai-safety.md`](ai-safety.md) and [`docs/legal/DISCLAIMER.md`](legal/DISCLAIMER.md).
