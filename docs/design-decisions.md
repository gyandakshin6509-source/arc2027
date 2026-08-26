# Design Decisions

One entry per decision. Each entry records what was decided and the reasoning that was
actually given at the time. Reasoning is not reconstructed or extended after the fact — if
a decision was made without a recorded rationale, that is stated rather than filled in.

Entries are newest-last. When a decision is revisited, add a new entry rather than editing
the old one, and link back to it.

---

## D-001 — Fin planform frozen

**Date:** TBD <!-- date this decision was made is not recorded -->

**Decision.** The fin planform is frozen at 95 mm root chord, 40 mm tip chord, 55 mm
semispan, 50 mm sweep. Three fins, G10, 1.6 mm thick, mounted on the 54 mm aft tube.

**Reasoning.** Not recorded. <!-- capture the rationale from whoever made the call, or mark it as a frozen input -->

**Status.** Frozen. Changing the planform invalidates the revision G stability figures
(1.78 cal at liftoff, 2.06 cal at burnout).

---

## D-002 — Printed PETG fin can rejected in favour of an external alignment jig

**Date:** TBD <!-- date not recorded -->

**Decision.** No printed PETG fin can. The fins are aligned during epoxy cure with an
external jig, which is removed afterwards and carries no flight mass.

**Reasoning.** PETG is 1.87× the density of the plywood already in the design. Every
fin-can architecture evaluated added 14–22 g. At roughly 1.6 ft of altitude per gram, that
is 23–35 ft of altitude, and altitude is scored at 1 point per foot of error. The penalty
was not worth the assembly convenience.

**Consequence.** The alignment jig becomes a required tool rather than a flight part. See
D-003.

---

## D-003 — Jig outer diameter set to 65 mm, not 100 mm

**Date:** TBD <!-- date not recorded -->

**Decision.** The fin alignment jig's `jig_od` parameter is 65 mm. A 100 mm variant was
considered and rejected.

**Reasoning.** Cant error is bounded by slot **length**, not slot **depth**. At 130 mm of
slot length and 0.15 mm of clearance, the bound is ±0.066° — already far better than the
0.5° cant being built in, so extra depth buys no useful precision. The 100 mm diameter
cost 5× the filament for that non-gain.

**Consequence.** Jig prints in roughly 4 hours and consumes about 50 g of PETG at 4 walls
and 20% infill, against a solid volume of about 151 g.

---

## Open — not yet decided

### Fin cant angle

The sim currently carries **0.0°**. A **0.5°** cant is under consideration and is **not
committed**. The jig's `cant` parameter is TBD until this is resolved, and D-003's
reasoning already assumes 0.5° as the target the jig must beat.

<!-- resolve by: deciding whether spin stabilisation is wanted, then re-running the sim at the chosen cant -->

### Jig slot clearance

`slot_clear` is TBD. D-003's ±0.066° bound was computed at 0.15 mm of clearance, so
choosing a different clearance changes that bound.

<!-- resolve by: measuring actual G10 stock thickness against the nominal 1.6 mm, then setting clearance from the measured fit -->

---

## Fin alignment jig — parameter record

The jig is a Fusion 360 Hybrid Design part, mm/g units. It holds the three G10 fins at
exact position and cant while epoxy cures. **It is a tool, not a flight part — zero flight
mass.**

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

Print estimate: about 50 g of PETG at 4 walls / 20% infill, roughly 4 hours. Solid volume
is about 151 g in PETG.
