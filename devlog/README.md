# Devlog

One file per work session, named `YYYY-MM-DD.md`.

Two sessions on the same day go in the same file. Don't backfill sessions you didn't write
down at the time — a gap is honest, an invented entry isn't.

The reason this exists: six months from now someone will find a number in this repo and
want to know where it came from and why it changed. That's what these entries are for.

## Keep personal stuff out

This repo is public, and the devlog is the most likely place for something personal to slip
in, because it's the one part written quickly and informally. Before committing, check
there are no full legal names — first names or initials are fine — no school name, no home
or launch site address, no phone numbers or emails, and no photos showing faces, house
numbers, plates or school signage.

Screenshots give away more than people expect. An OpenRocket or Fusion window usually has a
full file path in the title bar with a username in it, and a desktop capture picks up
whatever else was open. Crop them.

None of this is about hiding the work. The work is the thing we're publishing. Our personal
details just aren't part of it.

## Template

```markdown
# YYYY-MM-DD

## What we did

## What we decided

Anything substantial also gets an entry in ../docs/design-decisions.md — link it from here.
If nothing was decided, say so.

## Numbers that changed

| What | Was | Now | Where it came from |
|---|---|---|---|
|  |  |  |  |

Say where each new number came from: a sim run, a scale, a measurement off a printed part,
a datasheet. If it doesn't have a source it doesn't go in the table.

If a flight number changed, update ../docs/openrocket-extract.md in the same commit.

## Screenshots

## Next

What's blocked, and what to pick up next session.
```

## A few conventions

Keep it short. Record the numbers that *changed*, not every number that exists — current
values live in the design docs, not here. And link out instead of copying things across, to
[`../docs/design-decisions.md`](../docs/design-decisions.md),
[`../docs/compliance.md`](../docs/compliance.md) and
[`../docs/openrocket-extract.md`](../docs/openrocket-extract.md).
