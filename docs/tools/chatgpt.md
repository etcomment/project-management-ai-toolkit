# ChatGPT Usage Guide

A comprehensive guide for integrating the toolkit's AI Contexts and Prompts within ChatGPT Projects and Custom GPTs.

---

## 1. Setup in ChatGPT Projects

1. In ChatGPT, select **Projects** from the sidebar and create a new Project (e.g., "PM Delivery Assistant").
2. In the Project's **Custom Instructions** field, paste the text from [`instructions/chatgpt-project-instructions.md`](../../instructions/chatgpt-project-instructions.md).
3. Upload foundational toolkit files (such as `contexts/PM_CONTEXT.md` and `contexts/PROJECT_HEALTH_CHECK.md`) into the Project Files storage.
4. When initiating chat sessions within the Project, submit sanitized project updates to receive structured PM evaluations.

---

## 2. Setup as a Custom GPT

To create a dedicated Custom GPT for your delivery team:
1. Open the **GPT Builder** in ChatGPT.
2. Follow the detailed step-by-step instructions in [`instructions/custom-gpt-instructions.md`](../../instructions/custom-gpt-instructions.md).
3. Paste the provided prompt into the **Instructions** tab.
4. Configure the recommended conversation starters and upload the approved sanitized Knowledge files.

---

## 3. Practical Prompting Patterns

### Prompting Pattern A: Single-Turn Review
Paste `contexts/PM_CONTEXT.md` followed by your sanitized status report directly into a standard chat turn.

### Prompting Pattern B: Multi-Turn Collaborative Triage
1. Turn 1: Establish baseline assumptions with the selected context file.
2. Turn 2: Provide raw sanitized issue logs and ask for issue categorization.
3. Turn 3: Ask the model to draft a diplomatic customer-facing delay notification based on Turn 2.

---

## 4. Operational Safety Reminders

- Never upload files containing unmasked client names, proprietary source code, or credentials to ChatGPT Knowledge.
- Verify enterprise workspace privacy settings to ensure chat data is not used for model training.
- All client deliverables require human PM verification prior to sending.
