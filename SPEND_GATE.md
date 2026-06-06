# Automation Spend Gate

Core question:

> Before you pay, what must be true in 7 days for this spend to be justified?

## Spend Summary

- Spend:
- Amount:
- Billing period:
- Payment or renewal date:
- Tool, service, person, or infrastructure:

## Why Pay Now?

- Why is this spend needed now?
- What breaks, stalls, or slows down if you do not pay?
- What happens if you wait 7 days?

## Durable Asset Target

What durable asset should this spend create?

- Prototype:
- Merged PR:
- Published demo:
- Paper:
- Dataset:
- Workflow:
- Automation:
- Documentation:
- Other:

## KPI Window

Define the 7-day KPI.

- Start date:
- End date:
- KPI:
- Minimum acceptable result:
- Evidence required:

## Stop-Loss Line

When do you cancel, downgrade, pause, or stop?

- Stop-loss date:
- Stop-loss condition:
- Next billing or renewal date:
- Cancellation owner:

## Rescale Option

What cheaper, smaller, reversible, or manual option exists?

- Free tier:
- Trial:
- One-time credit:
- Manual workaround:
- Cheaper plan:
- Shorter commitment:
- Open-source alternative:

## Decision

Choose one:

- `GO`
- `WAIT`
- `RESCALE`
- `STOP`

## Decision Rationale

Why is this the correct decision given the durable asset target, KPI window, stop-loss line, and Rescale option?

-

## Next Safe Action

What is the next action that preserves optionality?

-

## Mini Example: Render Subscription

Spend target:
Render hosting / service subscriptions

Cost:
About $30/month

Situation:
The related MMAR project has not been touched for about two weeks, but the billing cycle is still active.

Decision:
WAIT / RESCALE

7-day KPI:
Produce one concrete artifact, such as a working demo, deployment check, or documented MMAR workflow decision.

Stop-loss line:
If no concrete artifact is produced before the next billing cycle, cancel or downgrade.

Rescale option:
Use the remaining paid month as an observation window. Do not let the next billing cycle renew by default.

Why:
The problem is not that $30 is catastrophic. The problem is that the billing cycle can move faster than the decision process.
