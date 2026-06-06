# AGENTS.md

This repository is Automation Spend Gate.

Automation Spend Gate is a pre-payment EV gate for AI automation costs. It is the "before you pay" gate.

Decision-OS V12 Gate is the "before you say done" gate. This repo imports only the minimal control-room discipline from V12: before saying done, leave enough handoff information for the next human or agent to safely continue.

## Core Purpose

Before paying for an AI automation tool, API, SaaS, model credit, hosting plan, ad test, freelancer, or external service, ask:

> What must be true in 7 days for this spend to be justified?

This repo protects future Rescale options by forcing spending decisions to include:

- KPI window
- stop-loss line
- billing deadline
- durable asset target
- cheaper or reversible option
- decision label: `GO` / `WAIT` / `RESCALE` / `STOP`

## Non-Goals

Do not turn this into:

- generic budgeting advice
- personal finance advice
- tax advice
- investment advice
- subscription tracker
- savings app
- profit guarantee
- lifestyle advice
- broad life coaching

## Preserve

Keep the following intact as the project evolves:

- EV framing
- Rescale option protection
- stop-loss line
- billing deadline
- durable asset target
- 3-day / 7-day / 30-day KPI windows
- Render example
- Overleaf example
- Claude Pro / Codex example
- distinction from generic budgeting

## Decision Labels

- `GO`: pay only with KPI, timebox, billing deadline, and stop-loss line
- `WAIT`: do not pay yet; test manually, free, or cheaper first
- `RESCALE`: reduce scope, cheaper plan, shorter trial, lower usage cap, or smaller commitment
- `STOP`: do not pay; EV, recovery path, or Rescale safety is too weak

## Next Agent Must Not

- make this only about saving money
- expand into general personal finance
- remove the Rescale framing
- remove the billing deadline requirement
- remove stop-loss logic
- add CLI/web app before the Markdown version is stable
- merge this repo into V12
- import V12 schema/tools
- claim this guarantees profit

## Before Saying Done

Leave a short handoff with:

- `what_changed`
- `what_was_not_touched`
- `unresolved_items`
- `verification`
- `rollback`
- `next_step`
- `next_self_should_not`

Use the handoff to make continuation safe, not ceremonial.
