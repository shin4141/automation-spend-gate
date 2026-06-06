# V12 Context Signal Footer

This protocol is a lightweight V12-derived context signal for Automation Spend Gate.

It helps future agent sessions show whether the current work can continue, whether handoff should be prepared, or whether handoff is required now.

This is not a scoring system. This is not a brake. It is a context signal for knowing the cost of continuing and preserving restartability.

## Footer Format

At the end of every agent response in this repo, include:

```text
Context Signal: GREEN | YELLOW | RED
Context Load: low | medium | high
Risk Driver: <main reason the signal is not lower>
Restart Handles: <strong | weakening | missing>
Preserve: <what should not be changed>
Next Safe Action: <one action that preserves restartability and Rescale options>
```

Use plain language. Keep the footer short. Do not add numeric scores by default.

## Signal Meanings

`GREEN` means the current work can continue normally.

- Context is fresh enough to proceed.
- Restart handles are clear.
- File scope is bounded.
- The next safe action is obvious.
- No handoff is needed beyond the normal footer.

`YELLOW` means continue, but prepare handoff.

- The work can keep going, but restartability is becoming more expensive.
- Important constraints, file state, or decisions should be preserved explicitly.
- The next response should reduce ambiguity, write down the handle, or finish a bounded step.
- Yellow is the key preservation state.

`RED` means handoff now.

- Continuing risks losing key context, weakening restartability, or damaging Rescale options.
- The next response should stop expansion and leave a clear handoff.
- Do not add new scope while red.
- Capture what changed, what was not touched, unresolved items, verification, rollback, next step, and what the next self should not do.

## Yellow Stack

Yellow is cumulative. Treat the stack as increasing when multiple yellow conditions are present:

- Many files are open or implied.
- The user has given strict repository boundaries.
- Work depends on preserving exact wording or owner intent.
- There are uncommitted changes.
- Verification has not run yet.
- A decision has been made but not recorded.
- A future agent would need to infer the next safe action.
- The task is drifting toward CLI, web app, schema, or dependency work before the Markdown version is stable.

When yellow conditions stack, do one of the following:

- finish the bounded step and verify
- write down the decision handle
- narrow the next action
- prepare handoff

Do not treat yellow as failure. Yellow is the preservation state that keeps continuation cheap.

## Context Load

Use `Context Load` to describe how expensive it is for the next human or agent to continue.

`low`:

- Few files touched.
- Constraints are simple.
- Current state is easy to rediscover.

`medium`:

- Several constraints or files matter.
- There are uncommitted changes.
- The next step depends on remembered intent.

`high`:

- Many constraints are active.
- Restart handles are weakening.
- The next agent would need a handoff to avoid re-reading or guessing.

Context Load is descriptive. It is not a numeric score.

## Risk Driver Rule

The `Risk Driver` must name the main reason the signal is not lower.

Examples:

- `none`
- `uncommitted documentation changes`
- `strict standalone repo boundary`
- `owner wording must be preserved`
- `handoff fields need to be captured before stopping`
- `task is approaching app or tooling scope`

If more than one risk matters, name the dominant one. Do not list everything.

## Restart Handles

`Restart Handles` describe whether the next session can safely resume.

`strong`:

- Relevant files and next action are obvious.
- Verification has been run or is clearly pending.
- Constraints are recorded.

`weakening`:

- Some state exists only in the conversation.
- The next action is clear but not yet recorded.
- Verification, rollback, or scope boundaries need to be written down.

`missing`:

- A future session would need to guess.
- Important state has not been captured.
- Handoff is required before continuing.

## No Numeric Scores By Default

Do not use numeric scores by default.

The footer should communicate signal, context load, risk driver, restart handles, preservation target, and next safe action. Numbers invite false precision and can make the footer feel like a grading system.

Only use numeric thresholds if the owner explicitly calibrates them for this repo later.

## Owner-Calibrated Thresholds

Thresholds belong to the owner.

If the owner later defines thresholds, record them in this document before using them. Until then:

- do not invent numeric limits
- do not convert signals into scores
- do not use the footer to force stopping
- do use the footer to show the cost of continuing

## Yellow As The Key Preservation State

Yellow matters most.

Green is easy to continue. Red requires handoff. Yellow is where the project preserves optionality before context gets expensive.

When in yellow:

- make the next safe action smaller
- preserve the restart handle
- write down what should not change
- protect the standalone repo boundary
- protect the Rescale framing
- avoid expanding into tooling before the Markdown version is stable

## Example Footers

Green example:

```text
Context Signal: GREEN
Context Load: low
Risk Driver: none
Restart Handles: strong
Preserve: standalone repo boundary and EV framing
Next Safe Action: continue the requested Markdown edit
```

Yellow example:

```text
Context Signal: YELLOW
Context Load: medium
Risk Driver: uncommitted documentation changes
Restart Handles: weakening
Preserve: billing deadline, stop-loss line, and Rescale framing
Next Safe Action: run verification and leave a short handoff before stopping
```

Red example:

```text
Context Signal: RED
Context Load: high
Risk Driver: restart handles are missing
Restart Handles: missing
Preserve: do not merge this repo into V12 or import V12 schema/tools
Next Safe Action: stop expansion and write the handoff now
```
