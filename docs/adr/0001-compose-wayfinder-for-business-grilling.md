# Compose wayfinder rather than build a business-grill engine

The business-definition family needs to explore a low-fidelity idea as an
emergent tree, durably, across many sessions. `wayfinder` already provides
exactly that: a map on the issue tracker, a frontier of open unblocked tickets,
fog for questions not yet sharp enough to ticket, and Decisions-so-far as the
record of what was settled. We compose it instead of building a parallel engine,
so `grill-the-business` carries only the business lenses and the
no-solution-design rule, and every mechanism has one implementation.

## Considered Options

- **Compose wayfinder** (chosen).
- **A standalone engine**: one living markdown document, no tracker. Lighter at
  napkin stage and works with no repo, but reimplements fog, blocking, claims
  and resume, and leaves two copies to maintain.
- **Hybrid**: standalone until fog grows, then escalate to a map. Rejected as
  two engines plus a migration between them; wayfinder already stops and asks
  when charting surfaces no fog.

## Consequences

- Charting a business idea creates issues on the tracker for questions as soft
  as "who actually pays for this?". That overhead is accepted deliberately.
- A separate `decision-log` skill is unnecessary: the map's Decisions-so-far is
  the record, written as each ticket resolves.
- The word **Destination** belongs to wayfinder (what a map is finding its way
  to). Skills that render artifacts from a finished map are **Renderers**.
- Wayfinder's `prototype` ticket type admits "UI/logic code", which conflicts
  with the no-solution-design rule. Business maps re-scope it to business
  artifacts: press release, pricing table, landing-page headline, journey sketch.
