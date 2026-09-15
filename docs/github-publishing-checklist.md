# GitHub Publishing & Release Checklist

A mandatory pre-release audit checklist to verify security, licensing, and supply chain integrity before publishing repository updates.

---

## 1. Confidentiality & Security Audit

- [ ] **No Real Client or Personal Data**: All examples, tests, and documentation use fictitious data.
- [ ] **No Credentials or Secrets**: Verified absence of API keys, tokens, passwords, private SSH keys, and connection strings.
- [ ] **No Proprietary Code**: No internal production source code or customer artifacts included.
- [ ] **Supply Chain Safety**:
  - No executable hooks or background commands in `.claude/`.
  - No executable shell scripts (`.sh`, `.ps1`) or untrusted binaries.
  - No unvetted GitHub Actions workflows or third-party MCP configs.

---

## 2. Documentation & Technical Quality

- [ ] **UTF-8 Encoding**: All Markdown files verified in clean UTF-8 encoding.
- [ ] **Link Integrity**: All relative links across `contexts/`, `docs/`, `examples/`, and `.claude/skills/` resolve correctly.
- [ ] **XML Tag Well-Formedness**: All `<task>`, `<context>`, `<input>`, `<constraints>`, `<output_format>` tags properly matched and formatted.
- [ ] **Legal & Disclaimer Notices**: Mandatory human review and liability disclaimer notices present in all key entry files.

---

## 3. Licensing & Repository Metadata

- [ ] **License Notice**: `LICENSE.md` present and aligned with `docs/legal/TERMS.md`.
- [ ] **Security Policy**: `.github/SECURITY.md` and vulnerability reporting protocol confirmed.
- [ ] **Contributing Guide**: `.github/CONTRIBUTING.md` and issue templates active.
