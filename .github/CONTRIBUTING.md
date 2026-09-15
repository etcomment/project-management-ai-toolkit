# Contributing Guidelines

This repository is official educational and reference content maintained by TechAide Inc. (TechAide Co., Ltd.).

While bug reports, typo fixes, security notices, and improvement suggestions are welcome, this project does not actively solicit external Pull Requests for feature development.

Improvement proposals should be submitted via GitHub Issues. Decisions on adoption and integration are made exclusively by the repository maintainers. Architectural restructurings, commercial pathway updates, and modifications to terms or disclaimers remain under the exclusive authority of the maintainers.

Please review the policies and guidelines below prior to submitting an Issue or Pull Request.

---

## Welcome Contributions

The following contributions are appreciated (evaluated via Issues by the maintainers):

- Fixing typographical errors or grammatical issues
- Refining phrasing and improving clarity
- Strengthening security warnings, disclaimer language, or data safety notes
- Improving the clarity of practical scenarios and use cases

---

## Strict Rules Before Contributing

> [!CAUTION]
> Never include any of the following information in Pull Requests or Issues:

- Real client names, corporate identities, personal names, or real project titles
- Client contracts, NDA-restricted information, full meeting transcripts, or internal business secrets
- API keys, passwords, access tokens, or security credentials
- Proprietary source code or trade secrets
- Confidential internal documents or non-public information

**All examples and pull requests must use strictly fabricated, fictitious data.**

If submitting AI-generated text, ensure a human has thoroughly verified, edited, and validated the content prior to submission.

---

## Contributions Unlikely to Be Accepted

The following types of contributions do not align with repository principles and will generally not be accepted:

- Adding executable hooks, background commands, shell scripts, or automated commit/deploy mechanisms
- Adding MCP server configurations, GitHub Actions pipelines, or automated daemon workflows
- Adding examples that require real commercial API keys or external service integrations
- Weakening disclaimers, liability limitations, or data safety warnings
- Adding excessive promotional links or commercial pathways
- Incorporating details from real, confidential client projects

This repository is an advisory AI toolkit (AI Contexts, Prompt Templates, Claude Code Skills) and deliberately avoids becoming an automated execution environment.

---

## Contribution Workflow

```text
Have an improvement idea
│
├─ Contains confidential information?
│    ├─ Yes → Do not submit / Sanitize thoroughly
│    └─ No
│
├─ Type of change?
│    ├─ Typo / Minor wording fix → Pull Request
│    ├─ New feature / Context proposal → Open an Issue
│    └─ Security concern → Consult SECURITY.md
│
├─ Complete the Safety Checklist
│
├─ Maintainer Review
│
└─ Integration Decision
```

---

## Pull Request Submission Process

1. Share your proposal in an Issue or describe the PR thoroughly.
2. Summarize the changes clearly.
3. List added or modified files along with the rationale.
4. Personally verify that no confidential data or credentials are included.
5. Verify clean Markdown formatting.

Ensure you complete and check all items in the Pull Request Safety Checklist.

---

## Example Commit Messages

```
Fix typo in README
Improve risk review context
Add example for stakeholder report
Clarify AI safety notice
Update meeting minutes prompt
```

---

## Legal & Responsibility

- All submitted contributions are reviewed prior to integration; acceptance is not guaranteed.
- Contributors assume full responsibility for ensuring their submissions do not infringe on third-party intellectual property or violate confidentiality agreements.
- Accepted contributions become subject to the repository license (`LICENSE.md`).

For details, refer to `docs/legal/TERMS.md`, `docs/legal/DISCLAIMER.md`, and `.github/SECURITY.md`.
