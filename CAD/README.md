# CAD

Fusion 360 sources and STEP exports for anything we design ourselves.

That means the fin alignment jig, and any airframe part we make rather than buy. Bought
parts don't get modelled unless we need one for a fit check.

Nothing is committed yet.

| Part | Where it's at |
|---|---|
| Fin alignment jig | Modelled in Fusion. `slot_clear` and `cant` still TBD. Not exported |
| Everything else | Not started |

## How to export

Every part goes in twice:

**`.step`** — the reviewable one. Opens anywhere, no Autodesk account needed, no version
lock. This is what a reviewer or a machinist actually opens.

**`.f3d`** — the editable one. This is what you open in six months when you need to change
a parameter.

Export the *component*, not the whole document. A whole-document export drags in unrelated
bodies, makes a big opaque file, and turns a one-part tweak into a diff that looks like you
rebuilt the entire assembly. Right-click the component in the browser and export from
there.

Name files after the component in Fusion — lowercase, hyphens, no revision letter. Git
already tracks the revisions.

Everything is mm/g, same as the Fusion documents.

## Fusion public link

TBD <!-- publish the document with a public link, then paste the URL here and in the root README -->

## Parameters

The jig's driving parameters are written down in
[`../docs/design-decisions.md`](../docs/design-decisions.md) rather than repeated here, so
there's only one place to change them.
