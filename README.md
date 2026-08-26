# ARC 2027 — Rocket Design Repository

Design, simulation, and build records for a American Rocketry Challenge 2027 entry.
The vehicle is a single-stage, dual-diameter airframe carrying two raw hen's eggs to a
target apogee of 800 ft, recovered under a parachute with a delayed-deployment release
so that total flight duration lands inside the scored 37–40 s band. This repository holds
the OpenRocket model, the CAD sources for printed and machined parts, the bill of
materials, a compliance matrix against the ARC 2027 rules, and a dated devlog. Vehicle
revision G is the current configuration; nothing has been flown yet.

---

## Competition constraints (ARC 2027)

| Constraint | Rule value |
|---|---|
| Max liftoff mass | 650 g |
| Min overall length | 650 mm |
| Max total impulse | 80 N·s |
| Staging | Single stage |
| Motor class | F or lower |
| Airframe diameters | Must use two different tube diameters |
| Primary section | ≥66 mm OD and ≥300 mm long |
| Other sections | ≥9 mm different in OD |
| Payload | Two raw hen's eggs, 55–63 g each, fully enclosed |
| Qualification altitude target | 800 ft |
| Finals altitude target | 775–825 ft |
| Duration target | 37–40 s (zero penalty inside the band) |
| Altitude score | 1 point per foot of error |
| Duration score | 4 points per second outside the band |
| Approved altimeters | PerfectFlite Pnut or Firefly; Jolly Logic Altimeter One or Two |

### Key dates

| Milestone | Date |
|---|---|
| Registration closes | 6 December 2026 |
| Qualification flights due | 4 April 2027 |
| Finals | 15 May 2027 |

---

## Current vehicle — revision G

| Item | Value |
|---|---|
| Overall length | 780 mm (230 nose + 320 forward + 50 transition + 180 aft) |
| Nose cone | Ogive, 230 mm, Ø66 mm aft, 1.5 mm polystyrene wall, 35 mm aft shoulder |
| Forward airframe | 66 mm, T-80, 320 mm |
| Aft airframe | 54 mm, 180 mm |
| Transition | 66 → 54 mm boattail, 50 mm |
| Motor mount | 24 mm |
| Motor | AeroTech F30FJ-6, 47.0 N·s, 24 × 95 mm |
| Fins | 3 × G10, 1.6 mm thick, mounted on the 54 mm aft tube |
| Fin planform | 95 mm root chord, 40 mm tip chord, 55 mm semispan, 50 mm sweep |
| Fin cant | 0.0° in the sim; 0.5° under consideration, **not committed** |
| Liftoff mass | ~571–574 g |
| Static stability | 1.78 cal at liftoff, 2.06 cal at burnout |
| Nose ballast | 42 g |
| Payload | Egg capsule, 170 g, 130 mm × 61 mm envelope, at station top+20 mm — **lumped mass only, undesigned** |
| Altimeter | PerfectFlite Pnut, 7.4 g |
| Recovery | 22 in nylon parachute with Jolly Logic Chute Release |
| Rail exit velocity | 14.0 m/s off a 6 ft rail |

---

## Repository layout

```
.
├── README.md                   this file
├── LICENSE                     MIT
├── .gitignore
├── BOM.csv                     bill of materials; costs and vendors not yet sourced
├── CAD/                        Fusion 360 sources and STEP exports
├── sim/                        OpenRocket model
├── docs/
│   ├── design-decisions.md     decision log
│   ├── compliance.md           ARC 2027 rule matrix
│   └── openrocket-extract.md   hand-read values from the sim
└── devlog/                     one YYYY-MM-DD.md per work session
```

---

## Build status

| Area | Status |
|---|---|
| OpenRocket model | Revision G simulated; values pending hand extraction |
| Airframe | Not built |
| Egg capsule | **Undesigned.** 170 g lumped mass in the sim; no geometry, no foam spec, no retention, no CAD. Largest open risk in the project. |
| Fin alignment jig | Designed in Fusion 360; slot clearance and cant parameters open; not printed |
| Fins | Not cut |
| Recovery | Components selected, not sourced |
| Electronics bay | Not started |
| Custom electronics | Deferred — see D-004. Avionics are off-the-shelf and non-programmable. |
| BOM sourcing | Not started — every cost, vendor, and link is TBD |
| Flight testing | None |

---

## Simulation and analysis

The flight model lives in [`sim/`](sim/) as an OpenRocket file. OpenRocket is the single
source of truth for apogee, duration, stability, and velocity; those numbers are read out
by hand and transcribed into [`docs/openrocket-extract.md`](docs/openrocket-extract.md),
which is currently an empty template. Nothing in this repository recomputes them.

Two scored quantities drive the design, and they trade against each other:

- **Altitude**, at 1 point per foot of error against the 800 ft target. Mass is the lever
  here — see the fin can decision in
  [`docs/design-decisions.md`](docs/design-decisions.md), where added mass was costed in
  feet of altitude directly.
- **Duration**, at 4 points per second outside the 37–40 s band, governed by the
  parachute and the Chute Release deployment altitude.

Rule conformance is tracked line by line in
[`docs/compliance.md`](docs/compliance.md). Rows that depend on numbers not yet extracted
from the sim are marked TBD rather than estimated.

---

## Screenshots and CAD links

<!-- PLACEHOLDER BLOCK — fill once renders are exported and the Fusion doc is shared -->

> **Screenshots — TBD.**
> Add: OpenRocket side profile, stability-vs-time plot, drag plot, and a render of the
> fin alignment jig. Commit images under `docs/img/` and link them here.

> **Fusion 360 public share link — TBD.**
> Requires the Fusion document to be published with a public link, then the URL pasted
> here and into [`CAD/README.md`](CAD/README.md).

<!-- END PLACEHOLDER BLOCK -->

---

## License

MIT — see [LICENSE](LICENSE).
