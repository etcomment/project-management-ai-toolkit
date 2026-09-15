# Client Communication Context

---

## Purpose

This context facilitates drafting professional, objective, and diplomatic communications, emails, and briefing memos for clients with AI assistance.

It helps structure situation briefings, consultation requests, delay notifications, and decision options, ensuring clarity while mitigating contractual risks.

**Never transmit AI-generated drafts directly to a client.** Statements regarding contractual scope, delivery milestones, pricing, or legal liabilities must always be rigorously reviewed and approved by human management.

---

## Use Cases

- Drafting situation update emails and briefing memos for client counterparts
- Framing discussions around schedule variance, technical trade-offs, or open issues
- Presenting structured decision options (Options A, B, C) for client arbitration
- Preparing talking points and agendas prior to client-facing alignment sessions
- Calibrating the tone, diplomacy, and firmness of customer communications

---

## Input (Information to Provide to the AI)

After loading this context, provide the following details with confidential identifiers masked:

```
### Communication Context
- Purpose of Communication: (e.g., Delay notification, scope clarification, option presentation)
- Target Recipient: (e.g., Client Project Sponsor, Working-Level Tech Lead)
- Current Relationship Dynamic: (e.g., Strong partnership, strained, formal contractual)

### Situation Overview (Sanitized)
- Core Background & Context:
- Verified Facts:
- Current Complications / Schedule Variance:
- Root Cause (Objective):

### What is Needed from the Client
- Required Approvals, Decisions, or Inputs:
- Desired Decision Deadline:

### Proposed Options (if applicable)
- Option A:
- Option B:
- Option C:
```

---

## Expected Output

### 1. Communication Strategy & Tone Calibration
Analysis of the psychological and contractual framing best suited for the situation.

### 2. Client-Facing Draft (Email / Briefing Memo)
Polished, respectful, and transparent communication text structuring facts, impact, and requests.

### 3. Key Talking Points (for Synchronous Meetings)
Concise bullet points for spoken alignment during steering meetings or conference calls.

### 4. Anticipated Client Objections & Countermeasures
Predicted pushback from the client alongside prepared, fact-based responses.

### 5. Mandatory Human Verification Checklist
Specific clauses, dates, and statements requiring verification against contracts and internal policy prior to sending.

---

## Caution & Operational Safeguards

> [!CAUTION]
> AI-drafted messages do not bind your organization and must not be treated as final legal or commercial statements.
>
> Always verify that no unapproved commitments on deadlines, free scope additions, or liability admissions are introduced.
>
> Ensure all client names, corporate identities, contract figures, and credentials are completely sanitized.

---

## Standard Prompt Template

```text
# Client Communication Drafting Request

Using the contexts below, draft a client-facing communication based on the provided project situation.

## Contexts

[Paste contents of PM_CONTEXT.md here]

[Paste contents of CLIENT_COMMUNICATION_CONTEXT.md here]

---

## Communication Details (Sanitized)

[Paste communication context and situation details here]

---

## Requested Deliverables

1. Communication Strategy & Tone Calibration
2. Client-Facing Draft (Email / Memo)
3. Synchronous Meeting Talking Points
4. Anticipated Objections & Suggested Countermeasures
5. Human Verification Checklist

*Note: AI output serves as analytical support. Final client communications require human validation.
```

---

## Claude Prompt Template (XML Tag Version)

```text
<task>
Draft a client-facing communication and meeting talking points based on the provided project situation.
</task>
<context>
<pm_context>
[Paste contents of PM_CONTEXT.md here]
</pm_context>
<specific_context>
[Paste contents of CLIENT_COMMUNICATION_CONTEXT.md here]
</specific_context>
</context>
<input>
[Paste communication context and situation details here]
</input>
<constraints>
- Maintain high diplomatic standards: professional, respectful, transparent, and firm.
- Never commit to firm dates or cost assumptions without flagging them for human verification.
- Clearly separate verified facts from proposed options and client requests.
</constraints>
<output_format>
1. Communication Strategy & Tone Calibration
2. Client-Facing Draft (Email / Memo)
3. Synchronous Meeting Talking Points
4. Anticipated Objections & Suggested Countermeasures
5. Human Verification Checklist
</output_format>
```
