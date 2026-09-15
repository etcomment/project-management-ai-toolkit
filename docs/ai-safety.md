# AI Safety & Governance Guidelines

This document outlines mandatory data protection standards, operational safeguards, and governance principles for using generative AI in project management operations.

---

## 1. Strictly Prohibited Information (Never Input to AI)

Do not enter any of the following information into public or commercial generative AI platforms:

- **Client & Corporate Identifiers**: Real client names, corporate identities, partner company names, project code names.
- **Personally Identifiable Information (PII)**: Full names, email addresses, phone numbers, employee IDs.
- **Commercial & Contract Terms**: Financial figures, hourly rates, profit margins, confidential contract clauses, NDA materials.
- **Security Credentials**: API keys, access tokens, passwords, database connection strings, private SSH keys.
- **Proprietary Intellectual Property**: Unreleased source code, core proprietary algorithms, internal business strategies.

---

## 2. Sanitization & Anonymization Protocols

Always sanitize your project information prior to submitting prompts:

| Sensitive Category | Original Real Data | Sanitized / Abstracted Placeholder |
|---|---|---|
| Client Name | MegaCorp Global Logistics | Client A / Enterprise Customer |
| Stakeholder Name | John Doe (VP of Operations) | Client Sponsor A / Executive Stakeholder |
| Feature / Module | Automated High-Frequency FX Execution | Critical Financial Processing Engine |
| Delay Cause | Third-party vendor failed SOC2 audit | External compliance review bottleneck |
| Financial Terms | 120,000 USD Fixed-Price Avenant | Fixed-Price Change Order |

---

## 3. Operational Risk Categories in PM AI Applications

### 1. Premature Commercial Commitments
- **Risk**: AI generating phrasing like "We will absorb this change within the existing timeline at no extra cost."
- **Mitigation**: Run [`ai-output-governance-review`](../.claude/skills/ai-output-governance-review/SKILL.md) to detect and neutralize unauthorized scope or schedule concessions.

### 2. Hallucinated or Inferred Claims
- **Risk**: AI filling gaps with plausible-sounding domain assumptions that contradict the actual software architecture.
- **Mitigation**: Enforce the constraint: *"Explicitly tag unverified assumptions as (Inferred). If data is insufficient, state: Insufficient information to make an assessment."*

### 3. Diplomatic Friction & Blame Placement
- **Risk**: AI generating defensive, argumentative, or accusatory language in client drafts.
- **Mitigation**: Use blameless, fact-focused templates like [`contexts/CLIENT_COMMUNICATION_CONTEXT.md`](../contexts/CLIENT_COMMUNICATION_CONTEXT.md).

---

## 4. Organizational AI Usage Checklist

Before deploying AI across your PM or delivery team:
- [ ] Confirm your organization's IT Security Policy regarding enterprise AI tools (opt-out of model training).
- [ ] Review client contracts and Non-Disclosure Agreements (NDAs) for clauses governing third-party data processing.
- [ ] Establish team-wide sanitization protocols (mandatory placeholder usage).
- [ ] Mandate that no AI-generated document is sent externally without explicit senior PM review.
