# Security Policy

---

## 1. Security Philosophy of This Repository

The **project-management-ai-toolkit** repository provides AI Contexts, Prompt Templates, Claude Code Skills, and practical documentation designed for project management operations.

It is managed and operated according to the following security standards.

---

## 2. Components Intentionally Excluded by Design

This repository deliberately excludes the following components:

- Executable hooks (`PreToolUse`, `PostToolUse`, `SessionStart`)
- Shell scripts (`.sh`) or PowerShell scripts (`.ps1`)
- GitHub Actions CI/CD workflows
- MCP server configuration files
- `package.json` files or workflow scripts
- API keys, access tokens, passwords, or authentication credentials
- Automated commit or deployment mechanisms
- Automated outbound network communication configurations

Claude Code Skills in `.claude/skills/` are pure Markdown documentation files illustrating how to frame PM evaluations, providing zero autonomous command execution.

---

## 3. Rules for Issues & Pull Requests

Never submit the following information into Issues or Pull Requests:

- Personally Identifiable Information (names, email addresses, phone numbers)
- Client identities, corporate names, or customer project details
- API keys, access tokens, passwords, or credentials
- Contract terms, NDA-restricted data, or proprietary business details
- Non-public internal corporate documents

**If you inadvertently post comments containing confidential information, do not update the public issue; immediately contact repository maintainers via the private channel below.**

---

## 4. Reporting Security Vulnerabilities

If you discover any of the following security concerns within repository files, do not open a public issue. Contact us immediately using the private channel below:

- Accidental inclusion of confidential data or personal information
- Vulnerable, dangerous, or unsafe prompt recommendations
- Supply chain vulnerabilities or malicious configuration files

**Contact Information:**

TechAide Inc. (TechAide Co., Ltd.)  
Contact Form: https://techaide.jp/contact/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit

*(Please reach out via our official website contact form. Never post vulnerability details or sensitive data in public Issues or comments.)*

---

## 5. Security Guidance for End Users

When utilizing toolkit contexts or prompts within generative AI platforms:

- Never input client identities, personal data, contract terms, or credentials.
- Comply with your organization's Information Security and Acceptable Use policies.
- Verify compliance with client Non-Disclosure Agreements (NDAs).
- Review data retention and privacy policies of your generative AI vendor.

For complete guidelines, see [docs/ai-safety.md](../docs/ai-safety.md).

---

## 6. Safe Handling of Configuration Files & External Scripts

While this repository contains no executable code or hooks, observe the following precautions when importing external configurations (`.claude/settings.json`, `.vscode/tasks.json`, `package.json`):

### Hooks in `.claude/settings.json`
- This repository distributes no `.claude/settings.json` and includes zero hooks.
- **If importing `.claude/settings.json` from external sources, thoroughly inspect all `hooks`.**
- Scrutinize any hook invoking curl, wget, powershell, npm, npx, bash, or python before execution.
- `.claude/settings.local.json` is a personal local configuration; never commit or share it publicly.

### Automated Tasks in `.vscode/tasks.json`
- This repository distributes no `.vscode/tasks.json`.
- **Inspect any imported `.vscode/tasks.json` for tasks configured with `runOn: folderOpen`.**
- Never add untrusted tasks to your workspace configuration.

### Executing External Scripts & Packages
- **`npx <package>` or `npm exec` without locked versions pose severe supply chain risks.**
- Never execute untrusted scripts directly via `curl URL | sh` or `wget URL | sh`.
- Inspect `preinstall`, `postinstall`, and `prepare` scripts before running `npm install`.

### GitHub Actions Security
- Workflows using `pull_request_target` expose repositories to privilege escalation risks from external PR code.
- Be vigilant of cache poisoning risks in `actions/cache` when using `restore-keys`.
- Restrict `id-token: write` permissions strictly to jobs that require it.

---

## 7. Related Documents

- Disclaimer: [docs/legal/DISCLAIMER.md](../docs/legal/DISCLAIMER.md)
- Terms of Use: [docs/legal/TERMS.md](../docs/legal/TERMS.md)
- AI Safety Guidelines: [docs/ai-safety.md](../docs/ai-safety.md)

---

*TechAide Inc. (TechAide Co., Ltd.)*  
*https://techaide.jp/*
