# Simulation

The OpenRocket model for the rocket.

| File | |
|---|---|
| `ARC2027_OPTIMISED_T80-forward.ork` | Revision G |

## This is where flight numbers come from

Apogee, duration, max velocity, CG, CP and Cd all come out of this model and nowhere else.
We read them by hand into [`../docs/openrocket-extract.md`](../docs/openrocket-extract.md),
and [`../docs/compliance.md`](../docs/compliance.md) reads from that.

Nothing in the repo recalculates any of it. So if you find a number somewhere without a
matching line in the extract file, treat it as wrong until someone checks.

## What's in the model

| | |
|---|---|
| Overall length | 780 mm (230 + 320 + 50 + 180) |
| Nose cone | Ogive, 230 mm, Ø66 mm aft, 1.5 mm polystyrene, 35 mm shoulder |
| Forward airframe | 66 mm T-80, 320 mm |
| Transition | 66 → 54 mm boattail, 50 mm |
| Aft airframe | 54 mm, 180 mm |
| Motor mount | 24 mm |
| Motor | AeroTech F30FJ-6, 47.0 N·s, 24 × 95 mm |
| Fins | Three G10, 1.6 mm, on the 54 mm tube |
| Fin planform | 95 / 40 / 55 / 50 mm (root / tip / semispan / sweep) |
| Fin cant | 0.0°. The 0.5° version isn't committed and isn't in this file |
| Liftoff mass | ~571–574 g |
| Stability | 1.78 cal liftoff, 2.06 cal burnout |
| Nose ballast | 42 g |
| Egg capsule | 170 g, 130 × 61 mm, at top+20 mm — a lumped mass, not a modelled structure |
| Altimeter | PerfectFlite Pnut, 7.4 g |
| Recovery | 22 in nylon chute, Jolly Logic Chute Release |
| Rail | 6 ft, 14.0 m/s exit |

## Things wrong with the file right now

The comment header inside it still says "rev E" even though the contents are rev G. Fix
that before it gets cited anywhere.

Apogee, duration and max velocity haven't been re-read since rev E. The change should be
small — 50 g of ballast came out, about 42 g went back in across the Pnut, harness and
finish, so 573 g became 571 g — but small-and-unmeasured is still unmeasured.

The egg capsule is a 170 g lumped mass, so everything the model says about mass and balance
is sitting on a placeholder.

## How to work on it

Commit the `.ork` itself. `*.ork.bak` is gitignored, so don't commit a backup thinking it's
the model.

One configuration per commit. If you simulate a variant — a different cant, a different
chute — say so in the commit message and write it up in a [devlog](../devlog/) entry.

If you change the model in a way that moves any number in
[`../docs/openrocket-extract.md`](../docs/openrocket-extract.md), re-read it in the same
commit. A stale extract is worse than an empty one, because an empty one is obviously
empty.
