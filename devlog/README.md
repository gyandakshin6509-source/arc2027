# Devlog

One file per work session: `YYYY-MM-DD.md`.

If two sessions land on the same day, append to that day's file rather than creating a
second one. Do not backfill sessions you did not record — a gap is honest, an invented
entry is not.

The point of this log is that six months from now, a number in the repo can be traced back
to the session that changed it and the reason it changed.

## Template

Copy this into a new `YYYY-MM-DD.md`:

```markdown
# YYYY-MM-DD

## Worked on

- What was actually done this session.

## Decisions made

- Decision, and the reasoning behind it.
- Anything substantial gets its own entry in ../docs/design-decisions.md; link it here.
- If nothing was decided, write "None."

## Numbers that changed

| Quantity | Was | Now | Source |
|---|---|---|---|
|  |  |  |  |

<!-- "Source" means where the new number came from: an OpenRocket run, a scale reading,
     a measurement off a printed part, a datasheet. A number with no source does not go
     in the table. -->

If a flight number changed, update ../docs/openrocket-extract.md in the same commit.

## Screenshots

<!-- Commit images under docs/img/ and link them. Say what each one shows. -->

## Open / next

- What is blocked, and what the next session should pick up.
```

## Conventions

- Present tense for what you did, past tense for what you found. Keep it short.
- Record the numbers that *changed*, not every number that exists — the current value of
  anything lives in the design documents, not here.
- Link out rather than duplicate: [`../docs/design-decisions.md`](../docs/design-decisions.md),
  [`../docs/compliance.md`](../docs/compliance.md),
  [`../docs/openrocket-extract.md`](../docs/openrocket-extract.md).
