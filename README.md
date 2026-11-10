# AI Governance Playbook

A practitioner's playbook for AI governance that runs in the systems, not in binders.

Most firms have an AI policy, a committee and an approval form. Few can enforce any of it at the moment a model is called. This repo is a working playbook for closing that gap in a regulated enterprise: what to do in the first 90 days, the templates to do it with, and the lessons behind them.

It pairs with [hall-monitor](https://github.com/keeplearnin/hall-monitor), a reference implementation that shows the same controls in code.

> **Status:** early, built in public (started November 2026). Expect it to change.

## The idea in one line

**Make the safe path the fast path.** One gateway, one inventory, approved patterns and one intake: teams that build on them ship faster than teams that go around them.

## What's here

| Path | What it is |
| --- | --- |
| [`playbook/90-day-plan.md`](playbook/90-day-plan.md) | A 90-day plan for a new AI governance lead: see everything, build the paved road, prove value |
| [`templates/trust-brief.md`](templates/trust-brief.md) | TAG trust brief: Transparency, Accountability, Guardrails on one page per AI system |
| [`templates/risk-tiers.md`](templates/risk-tiers.md) | Risk tiers and what review each tier gets |
| [`templates/use-case-intake.md`](templates/use-case-intake.md) | One intake that checks risk, process and value together |
| [`templates/ai-inventory.csv`](templates/ai-inventory.csv) | Starter AI inventory with the fields that matter |
| [`field-notes/`](field-notes/) | Lessons from practice and from industry sessions, written up in my own words |
| [`mappings/hall-monitor.md`](mappings/hall-monitor.md) | How each playbook control maps to hall-monitor code, and where the gaps are |

## Principles

1. Make the safe path the fast path.
2. Enforce in code, document second.
3. Every AI system has one named owner.
4. Governance scales with risk.
5. Equip people instead of policing tokens.
6. TAG for every system: Transparency, Accountability, Guardrails.

## Frameworks referenced

[NIST AI RMF 1.0](https://www.nist.gov/itl/ai-risk-management-framework), [ISO/IEC 42001](https://www.iso.org/standard/81230.html), [FINOS AI Governance Framework](https://air-governance-framework.finos.org/). This playbook is not a substitute for them; it is a way to put them into practice.

## Use and contributions

Use, adapt and share freely. Issues and pull requests with your own lessons are welcome.

This is personal work. It contains no confidential material from any employer, and nothing here is legal advice.

## License

Text and templates: [CC BY 4.0](LICENSE).
