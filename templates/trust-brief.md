# TAG Trust Brief

One page per AI system. Attach it to the system's change control record and update it whenever the model, prompt, tools, data or owner changes.

**TAG = Transparency, Accountability, Guardrails.**

---

## System

| Field | Value |
| --- | --- |
| Name | |
| Inventory ID | |
| Risk tier | 1 / 2 / 3 ([tiers](risk-tiers.md)) |
| Business owner (one person) | |
| Technical owner (one person) | |
| Version (model, prompt, agent) | |
| Last reviewed | |
| Next review or retirement date | |

## Transparency: can we explain what it does?

- **Purpose:** what decision or task does it support, in one sentence?
- **Inputs:** what data does it read? Mark any untrusted input (customer text, documents, web pages, email).
- **Outputs:** what does it produce, and who or what uses the output?
- **Model and vendor:** which model, hosted where, under which contract?
- **Who is affected:** customers, employees, third parties?
- **How a person can see what it did:** where are its logs, and do they let you reconstruct a single decision?

## Accountability: who owns it when it fails?

- **When it is wrong, who notices?** (monitoring, sampling, user reports)
- **Who is paged, and who can switch it off?**
- **Which decisions need a person?** List them, and the authority limit of whoever approves.
- **What happens to an affected customer or employee?** (correction, appeal, notification)
- **Incident history:** date, what happened, what changed.

## Guardrails: what stops it from doing harm?

| Guardrail | In place? | Where it is enforced |
| --- | --- | --- |
| Goes through the LLM gateway | | |
| Approved model only, no silent fallback | | |
| Tools and data limited to what the approval names | | |
| Sensitive data redacted before the model sees it | | |
| Prompt-injection defences on untrusted input | | |
| A person approves consequential decisions | | |
| Evaluation and adversarial tests in CI | | |
| Re-test on any model or prompt change | | |
| Cost limit and alert | | |
| Off switch, tested | | |
| Fallback when the model is unavailable | | |

## Stress tests

List the edge cases that broke or nearly broke it, and the control that now catches each. For example, for an accounts-payable agent: *an approved vendor's bank account changes* → *any change to payee details routes to a person*.

| Edge case | Control |
| --- | --- |
| | |

## Sign-off

| Role | Name | Date |
| --- | --- | --- |
| Business owner | | |
| Technical owner | | |
| Governance reviewer | | |
