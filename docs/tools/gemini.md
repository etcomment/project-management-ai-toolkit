# Gemini Usage Guide

A guide for utilizing the toolkit within Google Gemini and Custom Gems.

---

## 1. Setting Up a Custom Gem

1. Open Gemini and navigate to **Gems Manager** -> **New Gem**.
2. Name the Gem (e.g., "PM Delivery Assistant").
3. In the **Instructions** field, paste the text from [`instructions/gemini-instructions.md`](../../instructions/gemini-instructions.md).
4. Save the Gem to make it readily accessible from your Gemini sidebar.

---

## 2. Standard Prompting in Gemini Sessions

When running ad-hoc sessions in Gemini:
1. Paste the relevant context file (e.g., [`contexts/PROJECT_HEALTH_CHECK.md`](../../contexts/PROJECT_HEALTH_CHECK.md)) at the beginning of your prompt.
2. Follow with your sanitized project updates.
3. Structure your prompt with clear headings: `[Context]`, `[Project Status]`, and `[Requested Outputs]`.

---

## 3. Enterprise Workspace Considerations

- Review your organization's Google Workspace data protection agreements regarding generative AI.
- Ensure that customer confidentiality and NDA terms are strictly preserved through sanitization.
