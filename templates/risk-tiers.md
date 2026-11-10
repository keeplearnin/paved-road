# Risk Tiers

Tier every AI system by its highest-impact trait. Review effort follows the tier, so most low-risk work never waits for a committee.

| Tier | Typical traits | Examples | Review | Who approves |
| --- | --- | --- | --- | --- |
| **1 — High** | Makes or shapes decisions about customers, employees or money; customer-facing; acts autonomously; reads untrusted input *and* reaches sensitive data *and* can send data out | Claims or underwriting recommendations, credit or hiring screens, agents that move money or send customer messages | Full intake, trust brief, adversarial and fairness tests, a person approves consequential decisions, council review | CAIO, after council review |
| **2 — Medium** | Internal use on confidential data; output reviewed by a person before it is used; limited tool access | Internal knowledge assistant on policy documents, document extraction with human review, code assistants on proprietary code | Intake, trust brief, evaluation tests in CI | AI governance lead |
| **3 — Low** | Internal, no sensitive data, on an approved pattern, output used only as a draft | Drafting help on public information, summarising non-confidential notes | Light intake; register in the inventory | Business-line owner |

## Rules that apply to every tier

- Registered in the [inventory](ai-inventory.csv) with one named owner.
- Model traffic goes through the LLM gateway.
- No customer or employee personal data in tools that are not approved for it.
- An off switch and a review date.

## Moving between tiers

A system moves up a tier when its data, users, autonomy or tools change. Moving down needs the governance lead's approval and a note in the inventory.

## The lethal trifecta

Treat any system that combines all three of the following as tier 1, whatever else is true:

1. It reads untrusted input (customer text, documents, email, web pages).
2. It can reach internal or sensitive data.
3. It can communicate outside (send email, call external APIs, write to shared locations).
