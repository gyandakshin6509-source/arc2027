# ARC 2027 Compliance Matrix

Every row maps one ARC 2027 rule constraint to the current revision G design value.

**Nothing on this page is computed.** Values are transcribed from the revision G
configuration and from the OpenRocket model. Any quantity that has not been read out of
the model or measured on hardware is marked **TBD**, not estimated.

Verdict key:

- **PASS** — a recorded design value satisfies the rule.
- **FAIL** — a recorded design value violates the rule.
- **TBD** — the design value is not yet known, so no verdict can be issued.
- **PARTIAL** — one part of a compound rule is satisfied and another is not yet evidenced.

---

## Vehicle

| # | Rule constraint | Rule value | Design value (rev G) | Verdict | Note |
|---|---|---|---|---|---|
| 1 | Max liftoff mass | 650 g | ~571–574 g | PASS | Sim mass, not a weighed mass. Re-verify on the scale before qualification, and see the egg capsule risk below. |
| 2 | Min overall length | 650 mm | 780 mm | PASS | 230 nose + 320 forward + 50 transition + 180 aft. |
| 3 | Max total impulse | 80 N·s | 47.0 N·s (AeroTech F30FJ-6) | PASS | |
| 4 | Staging | Single stage | Single stage | PASS | |
| 5 | Motor class | F or lower | F | PASS | AeroTech F30FJ-6, 24 × 95 mm. |
| 6 | Two different tube diameters | Required | 66 mm forward, 54 mm aft | PASS | |
| 7 | One section ≥66 mm OD | ≥66 mm OD | 66 mm forward section | PASS | Nose cone is Ø66 mm at its aft face, matching. |
| 8 | …and that section ≥300 mm long | ≥300 mm | 320 mm | PASS | Forward section length read from the model. |
| 9 | Other sections ≥9 mm different in OD | ≥9 mm difference | 66 mm vs 54 mm | PASS | The difference between the two recorded diameters exceeds the 9 mm minimum. |
| 10 | Payload — two raw hen's eggs | 2 eggs, 55–63 g each | Egg capsule: 170 g, 130 mm × 61 mm envelope, at station top+20 mm | PASS | Mass and envelope are allocated in the model and sized for two eggs. **This is a lumped mass, not a designed structure** — see the risk note below. |
| 11 | Payload fully enclosed | Required | Capsule defined as "2 eggs + foam + bulkheads" | PARTIAL | Enclosure is asserted by the capsule definition but **cannot be evidenced**: there is no bulkhead geometry, no foam spec, no retention method and no CAD. Closes when the capsule is designed. |
| 12 | Approved altimeter | Pnut / Firefly / Altimeter One / Altimeter Two | PerfectFlite Pnut, 7.4 g | PASS | |

## Flight performance

⚠ **The apogee and duration figures in circulation are revision E's.** They have not been
re-read from the revision G model. Rev G dropped 50 g of ballast and added ~42 g across
the Pnut, harness and finish, moving liftoff from 573 g to 571 g — so the rev E numbers are
probably close, but "probably close" is not a compliance verdict at 1 point per foot.

| # | Scored target | Rule value | Design value (rev G) | Verdict | Note |
|---|---|---|---|---|---|
| 13 | Qualification altitude | 800 ft | TBD | TBD | <!-- read apogee from the rev G model, not rev E --> Scored at 1 point per foot of error. |
| 14 | Finals altitude window | 775–825 ft | TBD | TBD | <!-- same rev G apogee figure as row 13, checked against the window --> |
| 15 | Duration band | 37–40 s, zero penalty inside | TBD | TBD | <!-- read flight duration from the rev G model --> Scored at 4 points per second outside the band. |

## Supporting figures (not themselves rule constraints)

| Quantity | Value (rev G) | Note |
|---|---|---|
| Nose cone | Ogive, 230 mm, Ø66 mm aft, 1.5 mm polystyrene, 35 mm shoulder | Fully specified in the model. |
| Static stability at liftoff | 1.78 cal | Recorded, not rule-bound. Depends on the 170 g capsule mass. |
| Static stability at burnout | 2.06 cal | Recorded, not rule-bound. Depends on the 170 g capsule mass. |
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

1. **The egg capsule is undesigned, and it is the largest open risk on this page.** It is
   170 g — the second-heaviest item in the vehicle — and it exists only as a lumped mass
   with an envelope. There is no bulkhead geometry, no foam specification, no retention
   method and no CAD. **Rows 1, 10 and 11 all lean on that 170 g figure, and so do the
   stability margins and the nose ballast.** If the built capsule comes in at 200 g, the CG
   shifts, the margin shifts, and ballast tuned to the foot is wrong. This is a bigger
   unknown than any jig parameter.
2. **Rows 13, 14 and 15** need apogee and duration re-read from the **revision G** model.
   The figures currently quoted anywhere are rev E's.
3. **Row 1** should be re-verified against a weighed airframe, not the sim mass, before the
   qualification window — and it cannot be trusted until item 1 resolves.
