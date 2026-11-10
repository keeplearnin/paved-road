# Field notes: cost, guardrails and context (November 2026)

Lessons from a set of industry sessions on enterprise AI in practice, written up in my own words. Figures are as presenters stated them, rounded, and not independently checked.

## 1. People, value and process come before models

- AI value starts with a clear problem statement, a defined outcome and the people who own it, not with the newest model.
- **Fix the process first.** Re-engineering a broken process delivers savings before any AI spend, and stops AI being bolted onto a legacy workflow. One team that fitted an agent to an unchanged process saw adoption stall around 20–25%, with staff correcting its output by hand.
- Executive pressure to "do something with AI" produces use cases that only needed a workflow fix.

## 2. The cost model has flipped

- AI moves spending from build (CapEx) to run (OpEx): tokens, inference, licences, support. Presenters described a shift from roughly 70% build and 30% run to the reverse.
- Break-even is rare. One estimate: a few years ago about 7 in 10 use cases paid off; now closer to 1 in 10.
- Business cases often leave out support, maintenance, governance, data preparation and the platform needed to build agents in-house (data foundation, knowledge and context graphs).
- **Bring finance in early.** Treat finance as a strategic ally, and treat AI as technology with a business case like any other.
- Count **cost savings** and **cost avoidance** separately. Avoidance is hard to prove unless the process or staffing actually changes.
- One firm requires high-six-figure savings before a project reaches CEO-level approval.

## 3. Match the tool to the task

- Work down a spectrum: frontier model → cheaper model → retrieval or fine-tuning → small internal model → no LLM at all (rules, RPA, existing systems).
- **Defaults matter.** A university found people burning tokens by leaving chat tools on the heaviest model and effort level for simple questions. It switched the default to a cheaper model and lower effort, and taught people when to turn it up.
- You don't have to be the token police: equip people with good defaults and celebrate value per dollar, not use of the most expensive tool.
- Chargeback through FinOps makes the teams that get the value see the cost.

## 4. Guardrails are what let people move fast

- Sandboxes, an LLM gateway and clear data rules give people confidence to experiment without fear of leaks or runaway bills. Grassroots experimentation shows what the business actually needs.
- **Solve it once for the enterprise.** Ten teams building ten versions of the same AI tool is the waste enterprise architecture was created to stop.
- Lock-in has layers: data and its cloud are hardest to move, compute is moderate, and the model and application layer is easiest to swap once data is clean and connected in your own cloud.

## 5. Visibility, context and TAG

- Every technology wave hits the same false start: pilots scale and operations is forgotten.
- **Visibility first.** You need line of sight to every model and agent in use. Unmonitored shadow AI is how compliance breaches happen.
- **AI is like a brilliant new PhD hire**: smart and capable, but without the institutional context a person carried in their head. Give it that context, including past decisions and the reasons for them. Presenters reported better answer confidence and lower cost once AI was grounded in organisational context, because rework burns tokens.
- **Treat model changes like change control.** Know when a model or version changes, re-test, and be able to roll back.
- Someone has to translate between business risk and technical risk.
- **TAG: Transparency, Accountability, Guardrails.** Can you explain what the AI is doing? Who owns it when it fails? What stops the edge case? Stress-test workflows: an accounts-payable agent looked fine until someone asked what happens when an approved vendor's bank account changes.
- Govern decisions, not just tools.

## 6. Security and resilience

- Know where each guardrail is deployed and who owns it: enterprise, MCP and agent guardrails.
- Watch for the **lethal trifecta**: an application with access to untrusted data, internal data and the ability to communicate outside.
- Test early, test often, test every layer, including adversarial testing. It is not a once-a-year exercise.
- Plan for failure: what happens when the model you depend on is no longer available?

## What I'm taking into the playbook

- The [TAG trust brief](../templates/trust-brief.md), with a stress-test table.
- Cheaper defaults and tiered model routing in the [90-day plan](../playbook/90-day-plan.md).
- Process redesign and finance sign-off in the [intake](../templates/use-case-intake.md).
- The lethal trifecta as an automatic tier 1 in the [risk tiers](../templates/risk-tiers.md).
