# ARC 2027 Compliance Matrix

Every row maps one ARC 2027 rule constraint to the current revision G design value.

**Nothing on this page is computed.** Values are transcribed from the revision G
configuration as recorded. Any quantity that has not been read out of OpenRocket or
measured on hardware is marked **TBD**, not estimated.

Verdict key:

- **PASS** — a recorded design value satisfies the rule.
- **FAIL** — a recorded design value violates the rule.
- **TBD** — the design value is not yet known, so no verdict can be issued.
- **PARTIAL** — one part of a compound rule passes and another part is TBD.

---

## Vehicle

| # | Rule constraint | Rule value | Design value (rev G) | Verdict | Note |
|---|---|---|---|---|---|
| 1 | Max liftoff mass | 650 g | ~571–574 g | PASS | Margin exists but the figure is a sim mass, not a weighed mass. Re-verify on the scale before qualification. |
| 2 | Min overall length | 650 mm | TBD | TBD | <!-- read overall length from OpenRocket; see openrocket-extract.md --> |
| 3 | Max total impulse | 80 N·s | 47.0 N·s (AeroTech F30FJ-6) | PASS | |
| 4 | Staging | Single stage | Single stage | PASS | |
| 5 | Motor class | F or lower | F | PASS | AeroTech F30FJ-6, 24 × 95 mm. |
| 6 | Two different tube diameters | Required | 66 mm forward, 54 mm aft | PASS | |
| 7 | One section ≥66 mm OD | ≥66 mm OD | 66 mm forward section | PASS | Meets the diameter half of the rule. |
| 8 | …and that section ≥300 mm long | ≥300 mm | TBD | TBD | <!-- read forward section length from OpenRocket --> Rows 7 and 8 together are **PARTIAL** until this is filled in. |
| 9 | Other sections ≥9 mm different in OD | ≥9 mm difference | 66 mm vs 54 mm | PASS | The difference between the two recorded diameters exceeds the 9 mm minimum. |
| 10 | Payload — two raw hen's eggs | 2 eggs, 55–63 g each | TBD | TBD | <!-- no payload bay is specified in rev G; needs a bay design before this can be assessed --> |
| 11 | Payload fully enclosed | Required | TBD | TBD | <!-- depends on the payload bay in row 10 --> |
| 12 | Approved altimeter | Pnut / Firefly / Altimeter One / Altimeter Two | PerfectFlite Pnut, 7.4 g | PASS | |

## Flight performance

| # | Scored target | Rule value | Design value (rev G) | Verdict | Note |
|---|---|---|---|---|---|
| 13 | Qualification altitude | 800 ft | TBD | TBD | <!-- read apogee from OpenRocket --> Scored at 1 point per foot of error. |
| 14 | Finals altitude window | 775–825 ft | TBD | TBD | <!-- same apogee figure as row 13, checked against the window --> |
| 15 | Duration band | 37–40 s, zero penalty inside | TBD | TBD | <!-- read flight duration from OpenRocket --> Scored at 4 points per second outside the band. |

## Supporting figures (not themselves rule constraints)

| Quantity | Value (rev G) | Note |
|---|---|---|
| Static stability at liftoff | 1.78 cal | Recorded, not rule-bound. |
| Static stability at burnout | 2.06 cal | Recorded, not rule-bound. |
| Rail exit velocity | 14.0 m/s off a 6 ft rail | Recorded, not rule-bound. |
| Fin cant | 0.0° in sim; 0.5° under consideration | **Not committed.** |
| Nose ballast | 42 g | Included in the liftoff mass above. |
| Recovery | 22 in nylon parachute + Jolly Logic Chute Release | Drives row 15. |

## Programme dates

| Milestone | Date | Status |
|---|---|---|
| Registration closes | 6 December 2026 | Not registered |
| Qualification flights due | 4 April 2027 | No flights made |
| Finals | 15 May 2027 | — |

---

## Open items blocking a full verdict

1. **Rows 2, 8, 13, 14, 15** all resolve the moment
   [`openrocket-extract.md`](openrocket-extract.md) is filled in by hand from the sim.
2. **Rows 10 and 11** need a payload bay to exist in the design. There is no egg
   containment specified in revision G.
3. **Row 1** should be re-verified against a weighed airframe, not the sim mass, before
   the qualification window.
