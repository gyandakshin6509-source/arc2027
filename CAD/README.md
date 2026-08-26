# CAD

Fusion 360 sources and neutral-format exports for every designed part.

## What lives here

Parts modelled for this vehicle: the fin alignment jig (tooling), and any airframe
component that is fabricated rather than bought. Purchased components are not modelled
here unless a fit check needs them.

Current contents: nothing committed yet.

| Part | Status |
|---|---|
| Fin alignment jig | Modelled in Fusion 360; `slot_clear` and `cant` still TBD; not exported |
| Everything else | Not started |

## Export convention

**Every part is committed twice:**

| Format | Purpose |
|---|---|
| `.step` | Reviewable. Opens anywhere, no Autodesk account, no version lock. This is what a reviewer or a machinist reads. |
| `.f3d` | Editable source. This is what future-you opens to change a parameter. |

**Export the individual component, not the whole document.** A whole-document export
bundles unrelated bodies, produces a large opaque file, and makes a one-part change look
like a full-assembly diff. Right-click the component in the browser and export that.

Naming: `<part-name>.step` / `<part-name>.f3d`, lowercase, hyphen-separated, matching the
component name in Fusion. Do not put a revision letter in the filename — git holds the
history.

Units are mm/g throughout, matching the Fusion documents.

## Fusion 360 public share link

TBD <!-- publish the Fusion document with a public link, then paste the URL here and in the root README -->

## Parameters

Driving parameters for the fin alignment jig are recorded in
[`../docs/design-decisions.md`](../docs/design-decisions.md) rather than duplicated here,
so there is one place to change them.
