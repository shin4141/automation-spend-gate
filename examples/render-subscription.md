# Example: Render Subscription

## Spend Summary

- Spend: Render subscription
- Amount: $30/month
- Billing period: Monthly
- Payment or renewal date: Before next billing cycle
- Tool, service, person, or infrastructure: Hosting for MMAR-related infrastructure

## Why Pay Now?

MMAR has not been touched for two weeks. Paying again only makes sense if the remaining paid month becomes an observation window that produces a concrete asset or proves the deployment is still needed.

If the user waits, nothing important breaks immediately. The existing paid period can be used before making the next payment decision.

## Durable Asset Target

The spend should produce at least one durable asset:

- a deployed MMAR artifact
- a merged PR that improves the hosted app
- a public demo
- usage evidence showing the hosted service is still worth keeping
- documentation that makes the deployment reproducible elsewhere

## KPI Window

- Start date: Today
- End date: 7 days from today
- KPI: Produce a concrete MMAR asset or usage signal tied to the Render deployment
- Minimum acceptable result: One merged PR, published demo, reproducible deployment note, or measurable usage signal
- Evidence required: Link to PR, demo, deployment note, or usage screenshot/export

## Stop-Loss Line

- Stop-loss date: Before the next billing cycle
- Stop-loss condition: No concrete asset or usage signal is produced during the remaining paid month
- Next billing or renewal date: Next Render billing date
- Cancellation owner: User

## Rescale Option

- Use the remaining paid month as the observation window
- Downgrade to a cheaper plan if available
- Pause or cancel the service before renewal
- Move the demo to a cheaper or free hosting option if usage is low

## Decision

`WAIT` or `RESCALE`

## Decision Rationale

Do not renew reflexively. The tool may still be useful, but MMAR inactivity means the next payment needs evidence. The remaining paid period is enough to test whether Render is creating option value.

## Next Safe Action

Set a cancellation reminder before the next billing cycle and define one concrete MMAR asset to produce inside the remaining paid month.
