# Security & Supply Chain Review — Project Management AI Toolkit

Comprehensive security architecture audit, threat model, and supply chain review for the **project-management-ai-toolkit** repository.

---

## 1. Executive Summary

This repository provides advisory AI Contexts, System Instructions, Claude Code Skills, and practical documentation designed for Project Managers, PMOs, and Tech Leads.

The repository strictly enforces a **"pure documentation / zero-executable"** security posture:
- **No executable code**: Contains no Python, JavaScript/Node.js, shell scripts, or binary files.
- **No active dependencies**: Zero `package.json`, `requirements.txt`, or third-party build packages.
- **No execution hooks**: Zero `.claude/settings.json` hook scripts, VS Code automation tasks, or auto-run workflows.
- **No network integrations**: Zero automated outbound connections, third-party MCP endpoints, or telemetry trackers.

---

## 2. Threat Modeling & Risk Assessment

### Vector 1: Malicious Command Execution & Hooks Injection
- **Threat**: Attackers introducing hidden hooks (`PreToolUse`, `PostToolUse`, `SessionStart`) in `.claude/settings.json` or automated tasks in `.vscode/tasks.json` to achieve Remote Code Execution (RCE).
- **Defense in Repository**:
  - The repository does not distribute `.claude/settings.json` or `.vscode/tasks.json`.
  - All Skills in `.claude/skills/` are strictly restricted to `.md` documentation.
  - `.github/pull_request_template.md` and `.github/SECURITY.md` prohibit the addition of executable scripts and hooks.

### Vector 2: Prompt Injection & Jailbreaking
- **Threat**: Malicious user inputs attempting to bypass safety rules, extract system prompts, or induce the AI to generate defamatory or binding contractual statements.
- **Defense in Repository**:
  - Negative constraints are enforced across all instructions and context files (`<constraints>`, `<do_not>`).
  - Mandatory human review notices are appended to all client-facing and contractual outputs.
  - Instructions explicitly prohibit substituting AI outputs for legal, tax, HR, or contractual decisions.

### Vector 3: Confidential Data Leakage (PII / NDA / Credentials)
- **Threat**: Project managers pasting real client names, credentials, or proprietary source code into AI models, leading to external disclosure.
- **Defense in Repository**:
  - Prompts explicitly instruct the AI to reject or flag unmasked confidential data.
  - Comprehensive sanitization guides provided in `docs/ai-safety.md`.
  - All scenario files in `examples/` strictly utilize fabricated, placeholder data.

---

## 3. Supply Chain Security Controls

| Component | Status | Security Control |
|---|---|---|
| NPM / Node.js Packages | Not Applicable | Zero runtime or build dependencies |
| Python / Pip Packages | Not Applicable | Zero runtime scripts |
| GitHub Actions | None | Zero automated workflow runners |
| Claude Code Skills | Safe | Pure Markdown guidance; no hooks or scripts |
| Markdown Files | Verified | Clean UTF-8 text; zero executable script tags |

---

## 4. Operational Best Practices for Users

When applying this toolkit in enterprise environments:
1. **Opt Out of Model Training**: Ensure commercial enterprise agreements with OpenAI, Google, or Anthropic opt out of training on submitted data.
2. **Mandatory Placeholder Sanitization**: Replace all client identities, project names, and financial figures with generic labels prior to prompting.
3. **Continuous AI Output Governance**: Run `.claude/skills/ai-output-governance-review/SKILL.md` before disseminating any AI-drafted document to stakeholders.
