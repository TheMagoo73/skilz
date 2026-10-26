# A vision and a PRD, both rendered from the business map

The business definition lives as ticket resolutions on a tracker, and `to-vision`
renders only a thin, persuasive view of it — the wrong document to sign off
against or plan from. We add `to-prd`, a second renderer off the same map,
producing the complete account of every decision in business language. The two
overlap on purpose: both carry who it is for, the problem and why now.

## Considered Options

- **Two renderers, overlapping deliberately** (chosen).
- **One document.** Fold the PRD's completeness into the vision. Rejected
  because the vision's thinness is a feature, not an accident: a document that
  serves both a cold stranger and a budget holder serves neither, and the first
  thing anyone does with a merged one is extract the half they wanted.
- **Cross-linked, no overlap.** The PRD opens with a link to `vision.md` and
  carries only what the vision drops. Rejected because a PRD is circulated to
  people who have read nothing else, so a non-standalone one gets reassembled by
  hand before anyone sends it — and because either file may be rendered without
  the other ever existing.

The usual objection to duplication is drift, and it does not apply here. Both
files are re-rendered wholesale from one map, so the copies cannot disagree;
they can only be stale together, which is the same failure as the map being
stale. This is why the duplication is safe, and why it looks like a mistake to
anyone who does not know it.

## Consequences

- `to-prd` reads the **business map only** and never waits for a solution map.
  It is wanted most at the point where no solution design exists yet.
- The two renderers have **different readiness gates**. `to-vision` hard-stops
  on **Who**, **The Job** and **Do Nothing**; `to-prd` on **What It Lets People
  Do**, **The Boundary** and **How We'd Know**. A map can be ready for one and
  not the other, in either direction.
- They run independently and in either order. `to-prd` links `vision.md` when
  that file exists and is silent when it does not; it never gates on it.
- The PRD lists **capabilities, not epics**. Slicing is not a business decision,
  and renderers do not read each other's output (ADR 0002), so the cut stays
  with `to-epics` against the solution map. The two need not agree on a count.
- **Parked: solutions** never reach the PRD. A reader of a signed document
  treats them as commitments, which would deliver them to `/grill-the-solution`
  already half-decided.
- **PRD** becomes a term in `GLOSSARY.md` rather than a word to avoid. Business
  Definition's avoid-line now points at it: the PRD is a rendering of the
  definition, not the definition.
