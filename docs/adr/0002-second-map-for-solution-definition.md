# A second map for solution definition, bounded by a cross-cutting test

Running `to-epics` against the first real business map produced epics that
gated on decisions nobody had made: an epic whose platform constraints "may
feed back into epics 01 and 02", an epic blocked on whether a data asset is
supplied, derived or maintained by hand, and an epic ruling out a general-purpose
rules engine on its own authority. The slice was being made before the facts
that determine the slice. We add a **solution map**: a second `wayfinder` map,
charted by `grill-the-solution` after the business definition settles, whose
Destination is a Solution Definition and whose Notes install the inverted
guardrail. `to-epics` then cuts from both maps.

## Considered Options

- **A second map** (chosen).
- **A second phase of the business map**: rewrite its Notes once the business
  lenses are swept and open a solution wave on the same map. Rejected because
  wayfinder reloads Notes every session, so a single block cannot both ban
  solution design and require it; mid-map rewriting would leave every closed
  ticket settled under a rule the map no longer states. It also denies the
  business definition a clean "done", and gives the two artifacts one lifecycle
  when the whole point is that one goes stable while the other churns.
- **An interview that writes a document**, no tracker. Rejected for the reason
  in ADR 0001: it loses the durable multi-session exploration wayfinder
  provides, which solution design needs at least as much, because its answers
  arrive from outside on someone else's timeline.

The ceiling against `/to-spec` was the second real choice. The obvious line is
**subject matter** — no schemas, no frameworks, no code — and we rejected it as
leaky: a shared API contract is a technical commitment that plainly belongs
above a spec, so a ban on "technical" excludes it wrongly, and any particular
framework choice can be argued into being strategic. The line is **structural**
instead: a question is admitted if it **constrains more than one capability, or
determines how the capabilities get sliced**. `/to-spec` already does
architecture — modules, interfaces, schemas, API contracts — for one slice;
this map does what crosses slices. The challenge question is "which capabilities
does this constrain?", and "only this one" is disqualifying rather than
debatable.

## Consequences

- Two maps per effort share the `wayfinder:map` label, so they are told apart
  by a title convention and by reciprocal Notes links. Charting the solution map
  writes a redirect into the business map's Notes, because an agent that loads
  the finished map would otherwise be told by its own Notes to resume grilling a
  settled definition.
- Charting may annotate the business map's **margins** — a pointer, a
  disposition note against a parked solution, a struck-through fog item — and
  never its decisions. Decisions-so-far is closed once the solution map exists.
- `grill-the-solution` soft-gates on three business lenses: **What It Lets
  People Do** (a hard stop, since the admission test measures against the
  capability list), **The Boundary**, and **Follow the Money**. Business fog that
  cannot change a business decision migrates rather than blocking.
- `to-epics` reads both maps: the business map for the outcome and its value,
  the solution map for the cut. Its **Gates** section narrows to approvals,
  budget, regulatory steps and external lead times; a would-be gate that is an
  undecided solution question is now a reported failure, not a line in an epic.
- The solution map carries **Parked: implementation**, draining to `/to-spec`.
  That inbox is write-only until `/to-spec` learns to read it — accepted on the
  same terms as **Parked: solutions**, which was an inbox for this map before
  this map existed.
- Renderers read maps and never each other's output. A rendered file is a leaf,
  one hop from a map, so a Solution Definition is re-rendered rather than
  hand-edited.
