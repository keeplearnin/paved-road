# 90-Day AI Governance Plan

A plan for a new AI governance lead reporting to a Chief AI Officer (CAIO) in a regulated firm.

## Summary

In 90 days, AI governance moves from policy on paper to controls that run in the systems: every AI system inventoried and owned, every model call through one gateway, and every new use case passing one intake that checks risk and value together.

The goal is to make the safe path the fast path. Teams that build on the approved platform ship faster than teams that don't, so governance speeds the AI program up instead of slowing it down.

By day 90 the CAIO gets four things:

1. **A complete inventory** of AI systems, models, agents and vendor AI features, each with a named owner and a risk tier.
2. **A paved road:** an LLM gateway, approved architecture patterns and a sandbox, with guardrails enforced in code.
3. **One intake** that approves use cases on risk, process redesign and measurable value, with finance at the table.
4. **A monthly scorecard** of coverage, risk, cost and value for the executive committee and the board.

## Why AI governance is weak today

Most firms have an AI policy, a committee and an approval form, but no way to enforce any of it at the moment a model is called.

| Gap | What it looks like | What it costs |
| --- | --- | --- |
| No inventory | Nobody can list every model, agent and vendor AI feature in use | Shadow AI, data leaks, failed audits |
| No owner | When an AI system fails, no single person is accountable | Slow incident response, finger-pointing |
| Policy without enforcement | Rules live in documents; the systems don't check them | Controls that exist on paper only |
| No change control for models | A model or prompt changes and nobody re-tests | Silent drops in quality |
| No link to value | Use cases are approved on ambition, not on measured outcomes | Few use cases break even; pilot fatigue |
| Uncontrolled run cost | Frontier models used for simple tasks; no chargeback | Budget surprises on tokens and licences |
| Sprawl | Ten teams build ten versions of the same tool | Duplicate spend and inconsistent controls |

The common cause: governance is run by legal and risk teams with no engineering levers, while engineering teams ship without governance built into their platforms. This plan puts governance into the platform itself.

## Operating principles

1. **Make the safe path the fast path.** Approved patterns, a gateway and a sandbox ship faster than going around them. Exceptions are possible but slower.
2. **Enforce in code, document second.** A control the system enforces beats a policy someone must remember.
3. **Every AI system has one owner.** A named person is accountable for its behaviour, cost and retirement.
4. **Governance scales with risk.** Risk tiers decide how much review a use case gets.
5. **Equip people instead of policing tokens.** Defaults, training and champions do more than restrictions.
6. **TAG for every system: Transparency, Accountability, Guardrails.** Can we explain what it does, who owns it when it fails, and what stops it from doing harm?

## Days 1–30: See everything

No new policy is written until we know what we are governing.

**Listen and assess**
- [ ] Meet the CAIO, CISO, CIO, Chief Risk Officer, Legal, Compliance, Internal Audit, Finance and the heads of the main business lines
- [ ] Review existing AI policy, committee charters, approved use cases and any audit or regulatory findings
- [ ] Benchmark against NIST AI RMF, ISO/IEC 42001 and the regulations that apply

**Build the inventory** ([template](../templates/ai-inventory.csv))
- [ ] Find every AI system: internal builds, vendor AI features already switched on, browser tools and API keys in use
- [ ] Pull evidence from network, identity and billing logs, not only from surveys
- [ ] Record each system's owner, purpose, data, model and vendor, users affected and whether a person reviews its output

**Tier the risk** ([template](../templates/risk-tiers.md))
- [ ] Publish risk tiers based on impact: customer-facing, decisions about people or money, data sensitivity, autonomy
- [ ] Tier every inventoried system
- [ ] Flag the "lethal trifecta" first: systems that read untrusted input, can reach internal data and can send data out

**Quick wins**
- [ ] Name an owner for every high-risk system, or pause it
- [ ] Issue a one-page acceptable-use guide: which tools are approved and which data must never go into them
- [ ] Close any high-risk gap found, such as customer data in an unapproved tool

**By day 30:** the inventory and risk tiers are approved by the CAIO, and the top risks have owners and dates.

## Days 31–60: Build the paved road

**The LLM gateway** (with platform engineering and security)
- [ ] One entry point for all model traffic: authentication, an allow-list of approved models, data-loss prevention and redaction, logging and cost tracking per team
- [ ] Route by tier: cheaper models and lower effort by default, frontier models when the use case is approved for them
- [ ] A tool and MCP gateway for agents: each agent may use only the tools and data its approval names
- [ ] Move the top five highest-volume or highest-risk use cases onto the gateway first

**Approved patterns**
- [ ] Publish three or four pre-approved architecture patterns (for example a RAG assistant on internal documents, a human-reviewed agent, a document-extraction pipeline, a vendor copilot)
- [ ] Each pattern comes with its controls built in, so a team that uses it skips most of the review
- [ ] A sandbox with synthetic or masked data for safe experimentation

**Change control and testing**
- [ ] Register each model, prompt and agent version; a change triggers re-testing before release
- [ ] Evaluation and adversarial tests (prompt injection, data leakage, bias) run in CI for tier 1 and 2 systems, not once a year
- [ ] A resilience plan: what happens when a model is withdrawn, degraded or unavailable

**The TAG trust brief** ([template](../templates/trust-brief.md))
- [ ] A one-page brief for every tier 1 and 2 system, attached to its change control record
- [ ] Every system gets an off switch and a review or retirement date

**By day 60:** the gateway is live for the first use cases, the patterns are published, and every high-risk system has a trust brief.

## Days 61–90: Prove value and scale

**One intake for every new use case** ([template](../templates/use-case-intake.md))
- [ ] A single review that checks risk tier, data, process redesign and expected value together
- [ ] Low-risk use cases on an approved pattern are approved within days; high-risk ones go to the AI governance council
- [ ] No approval without a named owner, a redesigned process and measures of success agreed with finance
- [ ] Count cost savings and cost avoidance separately, with evidence of a changed process for each

**Run cost and FinOps**
- [ ] Cost per use case and per team from the gateway, charged back to the business lines
- [ ] Usage-based forecasts reviewed monthly with finance
- [ ] Retire or merge duplicate tools found in the inventory

**Literacy and champions**
- [ ] Role-based training: everyone, builders, approvers and executives
- [ ] One AI champion per business line who translates between business risk and technical risk
- [ ] Short, reusable materials instead of one-off sessions

**Federate**
- [ ] Business lines own their use cases and budgets within the central standards
- [ ] The central team owns the inventory, the gateway, the patterns, the tiers and the scorecard

**By day 90:** the first monthly scorecard goes to the CAIO and the executive committee, with a 12-month roadmap and a budget for year one.

## Operating model

| Who | Owns | Decides |
| --- | --- | --- |
| CAIO | AI strategy and risk appetite | Tier 1 approvals; exceptions to the standards |
| AI Governance Lead | Inventory, risk tiers, intake, trust briefs, scorecard | Tier 2 approvals; which patterns are pre-approved |
| AI governance council: risk, legal, compliance, security, privacy, finance, business lines | Policy and cross-functional review | High-risk use cases; incidents and pauses |
| Platform engineering | Gateway, approved patterns, sandbox, evaluation tooling | How controls are built |
| Business-line owners | Their AI systems: behaviour, cost, results, retirement | Tier 3 approvals on approved patterns |
| AI champions | Training and first-line advice in each business line | Escalations to the governance team |
| Internal Audit | Independent assurance | Audit scope and findings |

The council meets every two weeks for the first 90 days, then monthly.

## Scorecard

Targets are set once the first baseline is in.

| Area | Measure |
| --- | --- |
| Coverage | Share of known AI systems in the inventory with an owner and a risk tier |
| Coverage | Share of model traffic going through the gateway |
| Risk | Tier 1 and 2 systems with a current trust brief and passing tests |
| Risk | Shadow AI found and resolved; open high-risk findings and their age |
| Risk | AI incidents and time to contain them |
| Speed | Days from intake to approval, by risk tier |
| Speed | Share of new use cases built on an approved pattern |
| Cost | Run cost per use case and per team, against forecast |
| Cost | Share of traffic on lower-cost models |
| Value | Measured savings and cost avoidance, checked with finance |
| Value | Pilots moved to production, and pilots stopped |
| People | Staff trained, by role; champions active in each business line |

## Risks

| Risk | Mitigation |
| --- | --- |
| Governance seen as a blocker | Lead with the paved road; publish time to approval every month |
| Inventory is incomplete | Use network, identity and billing evidence; run discovery every quarter |
| No engineering capacity for the gateway | Start with a bought or open-source gateway; move the top five use cases first |
| Business lines resist chargeback | Show cost transparently for one quarter before charging back |
| Rules and regulations change | Keep controls mapped to NIST AI RMF and ISO/IEC 42001; review quarterly |
| Vendor AI features switch on silently | Add AI clauses and notification duties to procurement and vendor risk reviews |

## What the governance lead needs from the CAIO

1. A mandate that all new AI goes through intake and all model traffic through the gateway by an agreed date.
2. Platform engineering capacity for the gateway and patterns for the first 90 days.
3. A seat for finance and Internal Audit on the council from day one.
4. Authority to pause a high-risk system that has no owner or no trust brief.
5. A standing slot on the executive committee agenda for the monthly scorecard.
