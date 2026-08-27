# ARC 2027

We're building a rocket for the American Rocketry Challenge 2027. It carries two raw hen's
eggs to 800 feet and brings them back unbroken, and it has to be back on the ground
somewhere between 37 and 40 seconds after launch. Every foot off the altitude target costs
a point. Every second outside the time band costs four. Most of the design is a fight
between those two numbers.

This repo has the OpenRocket model, CAD for the parts we make ourselves, the parts list, a
rule-by-rule compliance check, and a build log. The current design is revision G. Nothing
has flown yet.

## The rules we're designing against

| Constraint | Value |
|---|---|
| Max liftoff mass | 650 g |
| Min overall length | 650 mm |
| Max total impulse | 80 N·s |
| Staging | Single stage |
| Motor class | F or lower |
| Airframe diameters | Two different tube diameters required |
| Primary section | ≥66 mm OD, ≥300 mm long |
| Other sections | ≥9 mm different in OD |
| Payload | Two raw hen's eggs, 55–63 g each, fully enclosed |
| Qualification altitude | 800 ft |
| Finals altitude | 775–825 ft |
| Duration | 37–40 s, no penalty inside the band |
| Altitude scoring | 1 point per foot of error |
| Duration scoring | 4 points per second outside the band |
| Allowed altimeters | PerfectFlite Pnut or Firefly, Jolly Logic Altimeter One or Two |

Dates that matter: registration closes 6 December 2026, qualification flights are due
4 April 2027, and the finals are 15 May 2027.

## Revision G

| | |
|---|---|
| Overall length | 780 mm (230 nose + 320 forward + 50 transition + 180 aft) |
| Nose cone | Ogive, 230 mm, Ø66 mm at the aft end, 1.5 mm polystyrene wall, 35 mm shoulder |
| Forward airframe | 66 mm T-80, 320 mm |
| Transition | 66 → 54 mm boattail, 50 mm |
| Aft airframe | 54 mm, 180 mm |
| Motor mount | 24 mm |
| Motor | AeroTech F30FJ-6, 47.0 N·s, 24 × 95 mm |
| Fins | Three G10 fins, 1.6 mm thick, on the 54 mm tube |
| Fin planform | 95 mm root chord, 40 mm tip, 55 mm semispan, 50 mm sweep |
| Fin cant | 0.0° in the sim. We're thinking about 0.5° but haven't committed |
| Liftoff mass | ~571–574 g |
| Stability | 1.78 cal at liftoff, 2.06 cal at burnout |
| Nose ballast | 42 g |
| Payload | Egg capsule, 170 g, 130 × 61 mm, at top+20 mm — a mass placeholder, not a real design yet |
| Altimeter | PerfectFlite Pnut, 7.4 g |
| Recovery | 22 in nylon chute with a Jolly Logic Chute Release |
| Rail exit | 14.0 m/s off a 6 ft rail |

## Layout

```
README.md
LICENSE                     MIT
.gitignore
BOM.csv                     parts list, nothing sourced yet
CAD/                        Fusion sources and STEP exports
sim/                        the OpenRocket model
docs/
  design-decisions.md       why things are the way they are
  compliance.md             rule-by-rule check
  openrocket-extract.md     numbers read out of the sim by hand
devlog/                     one file per work session
```

## Where we are

| | |
|---|---|
| OpenRocket model | Rev G is built. Apogee and duration still need re-reading |
| Egg capsule | Not designed. 170 g placeholder in the sim, nothing else. Biggest open problem we have |
| Airframe | Not built |
| Fin jig | Modelled in Fusion. Slot clearance and cant still open. Not printed |
| Fins | Not cut |
| Recovery | Parts chosen, none bought |
| Electronics bay | Not started |
| Custom electronics | Deferred, see D-004. The avionics we're using aren't programmable |
| Parts sourcing | Not started. Every price, vendor and link in the BOM is still TBD |
| Flights | None |

## Simulation and analysis

The flight model is in [`sim/`](sim/). It's the only place apogee, duration, stability, CG,
CP and Cd come from. We read those out by hand into
[`docs/openrocket-extract.md`](docs/openrocket-extract.md) and everything else reads from
that. Nothing in this repo recalculates them, so if a number shows up somewhere without a
matching line in the extract file, assume it's wrong.

The extract file is mostly empty right now, and there's a catch worth knowing about: the
apogee and duration figures we've been quoting are revision E's, not G's. Rev G dropped
50 g of ballast and added about 42 g back across the Pnut, harness and finish, so liftoff
went 573 → 571 g. That should only move apogee a few feet. But "should only move it a few
feet" isn't a number you put on a submission when the scoring is a point per foot, so it
needs re-reading properly.

The rule-by-rule check lives in [`docs/compliance.md`](docs/compliance.md). Anything that
depends on a number we haven't pulled out of the sim yet is marked TBD rather than guessed.

## Pictures

<!-- fill this in once we have renders exported and the Fusion doc shared -->

Screenshots — TBD. We want the OpenRocket side profile, the stability-vs-time plot, the
drag plot, and a render of the fin jig. Put images in `docs/img/` and link them here.

Fusion 360 public link — TBD. Needs the document published with a public link, then the
URL pasted here and in [`CAD/README.md`](CAD/README.md).

Before committing any image, crop out title bars and file paths — they usually have a
username in them — and check nothing shows faces, signage or addresses. There's more on
this in [`devlog/README.md`](devlog/README.md).

## License

MIT, see [LICENSE](LICENSE).
