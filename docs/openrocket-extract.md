# Numbers from OpenRocket — revision G

These get read out of OpenRocket by hand and written down here. Nothing automates it, and
nothing else in the repo is allowed to be the source for them.

Fill in every field properly. If you don't know one, leave it as TBD rather than putting in
something approximate — a guessed number here ends up in [`compliance.md`](compliance.md)
and from there into a funding submission.

## Where this came from

| | |
|---|---|
| Source file | `sim/ARC2027_OPTIMISED_T80-forward.ork` |
| Revision | G |
| OpenRocket version | TBD <!-- Help > About --> |
| Motor in the sim | AeroTech F30FJ-6, 47.0 N·s, 24 × 95 mm |
| Conditions | TBD <!-- wind, temperature, site altitude, rail angle --> |
| Read by | TBD |
| Read on | TBD |

## Mass and balance

| | Value | Where to find it |
|---|---|---|
| CG from nose tip | TBD | The CG marker readout in the design view |
| CP from nose tip | TBD | The CP marker readout in the design view |
| Stability at liftoff | 1.78 cal | Already recorded for rev G, just confirm it still matches |
| Stability at burnout | 2.06 cal | Same |
| Liftoff mass | ~571–574 g | Rev G is quoted at 571 g against rev E's 573 g. Check which one the file actually has, then weigh the real thing |
| Overall length | 780 mm | 230 + 320 + 50 + 180. Covers compliance row 2 |
| Forward section length | 320 mm | Covers compliance row 8 |
| Nose cone | Ogive, 230 mm, Ø66 mm aft, 1.5 mm polystyrene, 35 mm shoulder | Fully specified in the model |
| Egg capsule | 170 g, 130 × 61 mm, at top+20 mm | A placeholder mass. Everything above moves when this becomes a real designed part, so re-read the lot once it's built and weighed |

## Aerodynamics

| | Value | Where to find it |
|---|---|---|
| Cd | TBD | Off the drag plot. Write down the Mach number or flight time you read it at, because Cd isn't constant and the bare number doesn't mean much on its own |
| Cd read at | TBD | e.g. "at max velocity" or "at t = X s" |

## Flight profile

Everything in this section is currently revision E's, so all of it needs re-reading from
the rev G model. Rev G dropped 50 g of ballast and added roughly 42 g back across the Pnut,
harness and finish, taking liftoff from 573 g to 571 g, so we'd expect these to land close
to where they were. Expected-to-land-close isn't good enough at a point per foot though.

| | Value | Where to find it |
|---|---|---|
| Apogee | TBD | Simulation results. Needed for compliance rows 13 and 14 |
| Flight duration | TBD | Simulation results. Needed for row 15 |
| Max velocity | TBD | Simulation results |
| Rail exit velocity | 14.0 m/s | Already recorded for rev G off a 6 ft rail, just confirm |
| Apogee delta vs rev E | TBD | Write rev E's apogee down next to rev G's, so the 573 → 571 g change is actually evidenced instead of assumed |
| Time to apogee | TBD | Matters for the F30FJ-**6** delay grain |
| Chute Release altitude | TBD | Not an OpenRocket output, it's a setting on the device. Recorded here because it drives duration |

## Notes

<!-- anything that changes how the numbers above should be read: a placeholder mass, an
     override left switched on, a sim run at non-default conditions -->

Two things worth knowing about the current file:

The comment header still says "rev E" even though the contents are revision G. Worth fixing
before anyone cites the file in a submission.

The egg capsule is a lumped 170 g mass rather than a modelled structure, so every
mass-and-balance number on this page inherits that placeholder.
