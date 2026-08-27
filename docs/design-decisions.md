# Design decisions

Why things are the way they are. One entry per decision, with the actual reasoning we had
at the time — not a tidied-up version invented later. Where we didn't record a reason, it
says so instead of making one up.

If we revisit something, add a new entry and link back rather than editing the old one.

## D-001 — Fin planform

Frozen at 95 mm root chord, 40 mm tip, 55 mm semispan, 50 mm sweep. Three G10 fins, 1.6 mm
thick, on the 54 mm aft tube.

Reasoning: not recorded. <!-- ask whoever made the call, or just mark it as inherited -->
Date: TBD.

Don't change it casually. The 1.78 cal and 2.06 cal stability numbers assume this planform,
so touching it means re-running everything.

## D-002 — No printed fin can, use an external jig

We looked at printing a PETG fin can and decided against it.

PETG is 1.87× the density of the plywood already in the design, and every fin-can layout we
tried added somewhere between 14 and 22 g. At roughly 1.6 ft of altitude per gram that's
23–35 ft, and altitude scores a point per foot. Easier assembly wasn't worth paying that.

So the fins get held by an external jig that comes off once the epoxy has cured — zero
flight mass. That's what makes D-003 necessary.

Date: TBD.

## D-003 — Jig OD is 65 mm, not 100 mm

We considered a 100 mm jig and went with 65 mm instead.

Cant error is bounded by how *long* the slot is, not how *deep*. At 130 mm of slot length
and 0.15 mm of clearance you get ±0.066°, which is already far better than the 0.5° cant
we'd be trying to build in. Extra depth buys nothing. The 100 mm version just burned 5× the
filament for the same precision.

Prints in about 4 hours and uses roughly 50 g of PETG at 4 walls and 20% infill. Solid
volume would have been about 151 g.

Date: TBD.

## D-004 — Flight data logger deferred, PCB and firmware directories deleted

Revision G has no custom electronics, and we've removed the empty `PCB/` and `firmware/`
directories rather than leaving them sitting there.

A student-built flight data logger would be legal under ARC §4.11 as a non-scoring device
and would genuinely strengthen the project. But the egg capsule is still undesigned and
it's on the critical path, and empty directories in a funding submission look like scope
we gave up on rather than scope we're saving for later. Better to say plainly that we
deferred it. Worth revisiting once the capsule is built and weighed.

That leaves the avionics off-the-shelf: a PerfectFlite Pnut and a Jolly Logic Chute
Release, neither of which is programmable.

Date: 2026-08-25.

## Still open

### The egg capsule — this is the big one

At the moment the capsule is a single lumped mass in OpenRocket: 170 g, 130 mm long, 61 mm
envelope, sitting at top+20 mm, labelled "2 eggs + foam + bulkheads."

That's a mass budget, not a design. No bulkhead geometry, no foam picked, no retention
method, no CAD at all. And it's 170 g, which makes it the second heaviest thing in the
rocket. The CG, both stability margins and the 42 g of nose ballast all assume that number
holds. If the real thing comes in at 200 g once we build it, the CG moves, the margin
moves, and ballast we tuned to the foot is wrong.

This matters more than anything else on this page. The jig at least has CAD.

<!-- to close: design the bulkheads, pick the foam, build it, weigh it, put the measured
     mass back in the model, re-read apogee -->

### Fin cant

The sim has 0.0°. We're considering 0.5° but haven't committed. The jig's `cant` parameter
stays TBD until we decide, and D-003's reasoning already assumes 0.5° is the target the jig
has to beat.

<!-- to close: decide whether we want spin stabilisation, then re-run the sim at whatever
     cant we pick -->

### Jig slot clearance

`slot_clear` is TBD. The ±0.066° bound in D-003 was worked out at 0.15 mm, so a different
clearance changes that number.

<!-- to close: measure the actual G10 stock against its nominal 1.6 mm, then set clearance
     from the real fit -->

## Jig parameters

The jig is a Fusion 360 Hybrid Design part in mm/g. It holds the three fins in position and
at the right cant while the epoxy cures. It's a tool, not a flight part — no flight mass.

| Parameter | Value |
|---|---|
| `tube_od` | 54 |
| `fin_root` | 95 |
| `fin_thk` | 1.6 |
| `fin_count` | 3 |
| `jig_id` | 54.4 |
| `jig_od` | 65 |
| `jig_len` | 110 |
| `lip_t` | 3 |
| `lip_id` | 50 |
| `slot_clear` | TBD |
| `cant` | TBD |
