# Simulation

The OpenRocket flight model for the ARC 2027 vehicle.

## Contents

| File | Description |
|---|---|
| `ARC2027_OPTIMISED_T80-forward.ork` | Revision G flight model. |

## This directory is the source of truth for flight numbers

Apogee, flight duration, max velocity, CG, CP, and Cd come from this model and nowhere
else. They are read out **by hand** into
[`../docs/openrocket-extract.md`](../docs/openrocket-extract.md), and
[`../docs/compliance.md`](../docs/compliance.md) reads from that transcription.

Nothing in this repository recomputes or re-derives those values. If a number appears in
a document without a matching line in the extract file, it is unsourced and should be
treated as wrong.

## Model configuration — revision G

| Item | Value |
|---|---|
| Overall length | 780 mm (230 + 320 + 50 + 180) |
| Nose cone | Ogive, 230 mm, Ø66 mm aft, 1.5 mm polystyrene, 35 mm shoulder |
| Forward airframe | 66 mm, T-80, 320 mm |
| Aft airframe | 54 mm, 180 mm |
| Transition | 66 → 54 mm boattail, 50 mm |
| Motor mount | 24 mm |
| Motor | AeroTech F30FJ-6, 47.0 N·s, 24 × 95 mm |
| Fins | 3 × G10, 1.6 mm, on the 54 mm aft tube |
| Fin planform | 95 / 40 / 55 / 50 mm (root / tip / semispan / sweep) |
| Fin cant in the model | 0.0° — the 0.5° variant is **not committed** and is **not** in this file |
| Liftoff mass | ~571–574 g |
| Static stability | 1.78 cal liftoff, 2.06 cal burnout |
| Nose ballast | 42 g |
| Egg capsule | 170 g, 130 mm × 61 mm, at top+20 mm — **lumped mass component, not a modelled structure** |
| Altimeter | PerfectFlite Pnut, 7.4 g |
| Recovery | 22 in nylon parachute + Jolly Logic Chute Release |
| Rail | 6 ft, 14.0 m/s exit velocity |

## Known issues with the current file

- **The comment header says "rev E" but the contents are revision G.** Fix before the file
  is cited in a submission.
- **Apogee, duration and max velocity have not been re-read since rev E.** Rev G dropped
  50 g of ballast and added ~42 g across the Pnut, harness and finish (573 g → 571 g), so
  the change is expected to be small — but it has not been measured.
- **The egg capsule is a lumped 170 g mass**, so every mass-and-balance output inherits a
  placeholder.

## Working rules

- Commit the `.ork` itself. `*.ork.bak` is gitignored — never commit a backup as if it
  were the model.
- One configuration per commit. If you simulate a variant (a different cant, a different
  chute), say so in the commit message and in a [devlog](../devlog/) entry.
- When the model changes in a way that moves any number in
  [`../docs/openrocket-extract.md`](../docs/openrocket-extract.md), re-extract in the same
  commit. A stale extract is worse than an empty one.
