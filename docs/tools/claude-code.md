# Claude Code Usage Guide

A comprehensive guide for integrating Claude Code with the specialized PM Skills in `.claude/skills/`.

---

## 1. How Claude Code Discovers Skills

Claude Code natively scans the `.claude/skills/` directory within the workspace root. Each subdirectory containing a `SKILL.md` with standard YAML frontmatter is automatically indexed as a recognized capability.

No manual registration, executable hooks, or background daemon scripts are required.

---

## 2. Practical Execution Examples

### Example 1: Full Repository PM Audit
```bash
claude "Review the current state of this repository using .claude/skills/pm-review/SKILL.md"
```

### Example 2: Detecting Latent Delivery Risks
```bash
claude "Scan recent git commits, issue notes, and README updates using .claude/skills/project-risk-radar/SKILL.md"
```

### Example 3: Auditing Issue Backlogs for Governance Gaps
```bash
claude "Audit open issue files for missing owners and deadlines using .claude/skills/issue-risk-review/SKILL.md"
```

### Example 4: Auditing Draft Communications
```bash
claude "Audit this draft client announcement using .claude/skills/ai-output-governance-review/SKILL.md before sending"
```

---

## 3. Strict Supply Chain Safety Rules

To maintain the highest security posture:
- Never add executable hooks (`PreToolUse`, `PostToolUse`, `SessionStart`) to `.claude/settings.json`.
- Never execute arbitrary shell scripts or untrusted third-party binaries.
- Keep all Skills as pure Markdown guidance documents.
