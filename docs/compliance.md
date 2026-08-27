# Compliance check

Every ARC 2027 rule constraint against what revision G actually is.

Nothing here is calculated. The numbers are transcribed from the rules and from the
OpenRocket model. If we haven't read something out of the model or measured it on hardware
yet it says TBD, because a guess in this table is worse than a blank.

PASS means a real design value satisfies the rule. FAIL means it doesn't. TBD means we
don't know the design value yet. PARTIAL means part of a compound rule is satisfied and the
rest isn't evidenced.

## Vehicle

| # | Rule | Required | Rev G | Verdict | Notes |
|---|---|---|---|---|---|
| 1 | Max liftoff mass | 650 g | ~571–574 g | PASS | This is the sim mass, not a weighed one. Needs checking on a scale before qualification, and see the capsule problem below |
| 2 | Min overall length | 650 mm | 780 mm | PASS | 230 nose + 320 forward + 50 transition + 180 aft |
| 3 | Max total impulse | 80 N·s | 47.0 N·s | PASS | AeroTech F30FJ-6 |
| 4 | Staging | Single stage | Single stage | PASS | |
| 5 | Motor class | F or lower | F | PASS | 24 × 95 mm |
| 6 | Two tube diameters | Required | 66 mm and 54 mm | PASS | |
| 7 | One section ≥66 mm OD | ≥66 mm | 66 mm forward section | PASS | The nose cone is Ø66 mm at its aft face, so it matches |
| 8 | That section ≥300 mm long | ≥300 mm | 320 mm | PASS | Read off the model |
| 9 | Other sections ≥9 mm different | ≥9 mm | 66 mm vs 54 mm | PASS | Comfortably more than 9 mm apart |
| 10 | Two raw hen's eggs | 55–63 g each | Capsule: 170 g, 130 × 61 mm, at top+20 mm | PASS | Mass and envelope are allocated in the model and sized for two eggs. It's a lumped mass though, not a built structure — see below |
| 11 | Payload fully enclosed | Required | Capsule is defined as "2 eggs + foam + bulkheads" | PARTIAL | The definition says enclosed but we can't show it. There's no bulkhead geometry, no foam spec, no retention method, no CAD. Closes as soon as the capsule is actually designed |
| 12 | Approved altimeter | Pnut / Firefly / Altimeter One / Two | PerfectFlite Pnut, 7.4 g | PASS | |

## Flight performance

Before reading this section: the apogee and duration numbers we've been quoting are
revision E's, not G's. Rev G dropped 50 g of ballast and added about 42 g back across the
Pnut, harness and finish, moving liftoff from 573 g to 571 g. That should barely move
apogee. But "should barely move it" isn't a compliance verdict when the scoring is a point
per foot, so these stay blank until someone re-reads them from the rev G model.

| # | Target | Required | Rev G | Verdict | Notes |
|---|---|---|---|---|---|
| 13 | Qualification altitude | 800 ft | TBD | TBD | <!-- read apogee from the rev G model, not rev E --> 1 point per foot of error |
| 14 | Finals altitude | 775–825 ft | TBD | TBD | <!-- same apogee figure as row 13, checked against the window --> |
| 15 | Duration | 37–40 s | TBD | TBD | <!-- read flight duration from the rev G model --> 4 points per second outside the band |

## Other numbers

Not rule constraints, but they come up.

| | Rev G | |
|---|---|---|
| Nose cone | Ogive, 230 mm, Ø66 mm aft, 1.5 mm polystyrene, 35 mm shoulder | Fully specified in the model |
| Stability at liftoff | 1.78 cal | Depends on the capsule being 170 g |
| Stability at burnout | 2.06 cal | Same |
| Rail exit velocity | 14.0 m/s | Off a 6 ft rail |
| Fin cant | 0.0° in the sim | 0.5° is under consideration, not committed |
| Nose ballast | 42 g | Already counted in the liftoff mass |
| Recovery | 22 in nylon chute, Jolly Logic Chute Release | This is what drives row 15 |

## Dates

| | | |
|---|---|---|
| Registration closes | 6 December 2026 | Not registered yet |
| Qualification flights due | 4 April 2027 | No flights yet |
| Finals | 15 May 2027 | |

## What's actually blocking a clean sheet

**The egg capsule, by a long way.** It's 170 g — the second heaviest thing in the rocket —
and it exists only as a lumped mass with an envelope around it. No bulkhead geometry, no
foam spec, no retention method, no CAD. Rows 1, 10 and 11 all lean on that 170 g, and so do
both stability margins and the nose ballast. If the built capsule turns out to be 200 g,
the CG shifts, the margin shifts, and ballast tuned to the foot is wrong. This is a much
bigger unknown than anything to do with the jig.

**Rows 13, 14 and 15** need apogee and duration read out of the revision G model. Whatever
figures are floating around are rev E's.

**Row 1** should be checked against a weighed airframe rather than the sim, and it can't
really be trusted until the capsule is sorted out.
