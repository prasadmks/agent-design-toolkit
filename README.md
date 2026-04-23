# Agent Design Toolkit

A live tool for generating structured agent requirements from a user story.

Paste a description of what you want your agent to do. Get back a complete working document covering seven dimensions of agent design — ready to hand to an engineering team.

**Live tool:** [v0-agent-design-toolkit.vercel.app](https://v0-agent-design-toolkit.vercel.app)

---

## What It Produces

| # | Section | Owner | What it defines |
|---|---|---|---|
| 1 | Requirement Interpretation | PM + Dev | Agent goal, scope, step-by-step flow, gap analysis |
| 2 | Open Decisions | PM | Blocker questions that must be answered before build starts |
| 3 | Knowledge Base Design | PM specifies · Data eng implements | What data the agent needs, where it lives, freshness requirements |
| 4 | Memory Design | PM decides · Engineer implements | Session memory, cross-session persistence, what to retain vs. discard |
| 5 | Tool Contracts | PM specifies · Engineer implements | Tool name, inputs/outputs, idempotency, failure handling |
| 6 | Logging Schema | PM defines · Engineer builds | What to log, retention policy, alerting queries |
| 7 | Eval Design | PM writes cases · QA implements | Happy path, edge cases, failure cases, adversarial cases |

---

## How To Use

1. Open the [live tool](https://v0-agent-design-toolkit.vercel.app)
2. Enter your Anthropic API key (`sk-ant-...`)
3. Describe what you want your agent to do — or pick one of the example chips
4. Hit **Generate Spec** — output appears in under 30 seconds

Your API key is used client-side only. It is never sent to any server other than Anthropic's API directly.

---

## Example Inputs

- `Agent should process credit for internet outage`
- `Agent should handle billing disputes end to end`
- `Patients should reschedule appointments through the agent`
- `Agent should help customers with flight disruptions`
- `Agent handles product returns and refunds`

---

## Why This Exists

Writing requirements for non-deterministic systems is a different skill than writing requirements for deterministic software. An agent that "handles billing disputes" can mean ten different things depending on:

- What confidence threshold triggers autonomous action vs. human review
- What the agent does when a backend system is down
- What it logs so you can reconstruct what happened after the fact
- What your eval cases are before you ship

This toolkit makes those decisions explicit before build starts — not after the first production incident.

Built from the methodology used on Spectrum Aura — Charter's agentic AI platform serving 32M+ customers across 250M annual contacts.

---

## Running Locally

Single HTML file — no build step, no dependencies.

```bash
git clone https://github.com/prasadmks/agent-design-toolkit
open index.html
```

Enter your Anthropic API key in the toolbar and start generating specs.

---

## Built by
Prasad MK · [linkedin.com/in/prasadmk](https://linkedin.com/in/prasadmk) · prasad.mks@gmail.com
