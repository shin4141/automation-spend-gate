# AutoSpend Short Prompt

Use this before paying for or renewing an AI/SaaS/tool subscription.

Use it for an AI tool, SaaS plan, API cost, image/video tool, or recurring subscription before paying, renewing, down-planning, or canceling.

## Questions

1. Did this turn into an output in the last 14 days?
2. Is there a specific use in the next 7 days?
3. Do I need the current plan, or would a lower plan/free tier/API-on-demand work?
4. Is this spend creating profit, saved time, reusable assets, or lower failure risk?
5. If I stop or downgrade, what condition would justify rejoining or upgrading?

## Human Labels

- `KEEP`
- `DOWNPLAN`
- `PAUSE`
- `CANCEL`

## Repo Labels

- `KEEP` = `GO`
- `DOWNPLAN` = `RESCALE`
- `PAUSE` = `WAIT`
- `CANCEL` = `STOP`

Canceling or down-planning should preserve a rejoin condition. Cut the unused spend, not the underlying Aspire.
