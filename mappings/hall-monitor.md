# Playbook ↔ hall-monitor

[hall-monitor](https://github.com/keeplearnin/hall-monitor) is a reference implementation of governed AI agents for insurance claims triage. This page maps each playbook control to the hall-monitor control that shows it in code, and names what hall-monitor does not cover. Control IDs and statuses are from hall-monitor's [`docs/controls.md`](https://github.com/keeplearnin/hall-monitor/blob/main/docs/controls.md) as of November 2026.

## Where the playbook is shown in code

| Playbook control | hall-monitor | Status there |
| --- | --- | --- |
| Inventory with one owner and a risk tier per system | HM-01 Agent registry and approvals (owner is a person, never a team) | built, for its own agents |
| Change control for models and prompts | HM-01 (pinned manifest digest and prompt hash, CI fails on an unapproved change), HM-02 Pinned models, no silent fallback | built |
| LLM gateway: approved models, logging, cost per call | `run_agent()` call path, HM-16 Cost per claim | built |
| Tools and data limited to what the approval names | HM-03 Tool gateway with allow-list and claim scope | built |
| Tiered model routing, cheaper by default | HM-16 Economy model routing | built, off until evaluated |
| A person approves consequential decisions | HM-04 Routing to a person, decided in code; HM-05 Adjuster approval gate | built |
| Guardrails stress-tested on facts, not AI labels | HM-04 (a $0 payout is a denial whatever the AI says) | built |
| Sensitive data redacted before the model | HM-10 Identifier redaction and data minimisation; HM-11 Telemetry without claim content | built |
| Prompt-injection defences | HM-09 | built, results pending |
| Evaluation and adversarial tests in CI | HM-12 Eval harness, HM-15 Adversarial suite, HM-17 CI checks and the eval gate | built; adversarial results pending |
| Fairness testing for tier 1 | HM-14 Counterfactual fairness test | built, results pending |
| Transparency: reconstruct any single decision | HM-06 Tamper-evident audit log, HM-13 Grounding checks and evidence | built |
| Off switch | HM-19 Kill switch | built |
| Read-only view for risk and audit | HM-20 Read-only control panel | built |
| Controls mapped to frameworks | every control mapped to NIST AI RMF and FINOS AIGF | built |
| Failures stop and go to a person | HM-08 | built |

## What hall-monitor does not cover

These are enterprise practices the playbook needs that a single reference application cannot show.

| Playbook control | Gap |
| --- | --- |
| Enterprise-wide inventory and shadow-AI discovery | The registry governs hall-monitor's own agents; it does not discover AI elsewhere |
| One intake that checks value with finance | No business-value measures (adjuster hours saved, cycle time, baseline) |
| Process redesign before AI | Triage speeds up the existing claims flow; no redesign is modelled |
| FinOps forecasting and chargeback | Cost is tracked per claim, not forecast or charged back |
| Institutional context and decision history | Agents look up policy and claim history, but adjuster overrides and their reasons are not fed back |
| Monitoring in production | Evaluation is offline; no drift or quality monitoring on live traffic |
| TAG trust brief | Evidence for each section exists, but no one-page brief is generated from the manifests yet |
| Literacy, champions, federated operating model | Out of scope for code |

## Possible next steps in hall-monitor

1. Generate a [TAG trust brief](../templates/trust-brief.md) from each agent manifest and its control evidence.
2. Record adjuster overrides with reasons, and use them as context and as evaluation cases.
3. Add value measures to the eval results: time per claim against a baseline.
