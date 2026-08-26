# OpenRocket Extract — revision G

Values in this file are **read out of OpenRocket by hand** and transcribed here. Nothing
recomputes them and nothing else in this repository is allowed to be the source of truth
for them.

Fill every field. Leave a field as `TBD` rather than estimating it — a guessed number here
propagates straight into [`compliance.md`](compliance.md) and into funding submissions.

---

## Provenance

| Field | Value |
|---|---|
| Source file | `sim/ARC2027_OPTIMISED_T80-forward.ork` |
| Vehicle revision | G |
| OpenRocket version | TBD <!-- Help > About --> |
| Motor selected in sim | AeroTech F30FJ-6, 47.0 N·s, 24 × 95 mm |
| Simulation conditions | TBD <!-- wind speed, temperature, launch site altitude, rod/rail angle --> |
| Extracted by | TBD |
| Extracted on | TBD |

---

## Mass and balance

| Quantity | Value | Where to read it |
|---|---|---|
| CG from nose tip | TBD | Rocket design view, CG marker readout |
| CP from nose tip | TBD | Rocket design view, CP marker readout |
| Static stability at liftoff | 1.78 cal | Already recorded for rev G — confirm it still matches the file |
| Static stability at burnout | 2.06 cal | Already recorded for rev G — confirm it still matches the file |
| Liftoff mass | ~571–574 g | Rev G is stated at **571 g** against rev E's 573 g — confirm which figure the file carries, then weigh it |
| Overall length | **780 mm** | 230 nose + 320 forward + 50 transition + 180 aft. Satisfies compliance row 2 |
| Forward section length | **320 mm** | Satisfies compliance row 8 |
| Nose cone | Ogive, 230 mm, Ø66 mm aft, 1.5 mm polystyrene, 35 mm shoulder | Fully specified in the model |
| Egg capsule | 170 g, 130 mm × 61 mm, at top+20 mm | **Lumped mass placeholder.** Re-read after the capsule is actually designed and weighed — every row above moves with it |

## Aerodynamics

| Quantity | Value | Where to read it |
|---|---|---|
| Computed Cd | TBD | Read off the drag plot — record the value **and the Mach number / flight time it was taken at**, since Cd is not constant |
| Cd read at | TBD | e.g. "at max velocity" or "at t = X s" — state which |

## Flight profile

⚠ **Any apogee, duration or velocity figure currently in circulation is revision E's.**
Re-read all of them from the revision G model. Rev G dropped 50 g of ballast and added
~42 g across the Pnut, harness and finish (573 g → 571 g), so the values are expected to
land close — but at 1 point per foot, "expected to land close" is not a number you submit.

| Quantity | Value | Where to read it |
|---|---|---|
| Apogee | TBD | Simulation results — needed for compliance rows 13 and 14 (800 ft target, 775–825 ft window) |
| Flight duration | TBD | Simulation results — needed for compliance row 15 (37–40 s band) |
| Max velocity | TBD | Simulation results |
| Rail exit velocity | 14.0 m/s | Already recorded for rev G off a 6 ft rail — confirm against the file |
| Apogee delta vs rev E | TBD | Record rev E's apogee beside rev G's so the 573 → 571 g change is evidenced rather than assumed |
| Time to apogee | TBD | Relevant to the F30FJ-**6** delay grain |
| Chute Release set altitude | TBD | Not an OpenRocket output — this is a device setting, recorded here because it drives duration |

---

## Notes

<!-- Record anything that would change how the numbers above should be read: a component
     whose mass is a placeholder, an override left switched on in the model, a simulation
     that was run under non-default conditions, etc. -->

- **The `.ork` comment header still reads "rev E" while its contents are revision G.**
  Fix this before the file is cited in a submission.
- **The egg capsule is a lumped 170 g mass component, not a modelled structure.** Every
  mass-and-balance figure on this page inherits that placeholder.
