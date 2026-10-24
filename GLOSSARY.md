# skilz

A personal collection of Claude Code skills. The current effort is a family of
business-definition skills that turn a raw, low-fidelity product idea into
business-focused artifacts, upstream of any technical work. The family composes
`wayfinder` rather than reimplementing it.

## Language

**Business Definition**:
The settled, non-technical account of what is to be built and why: customer,
problem, value, outcomes, boundaries. Holds no solution design. Lives as the
accumulated Decisions-so-far of a business map, not as a document of its own.
_Avoid_: brief, PRD, requirements, spec

**Business Map**:
A `wayfinder` map whose Destination is a Business Definition and whose Notes
install the business lenses and the no-technology rule.
_Avoid_: board, plan, backlog

**Lens**:
A business angle the grill probes an idea through (who pays, what's the job to
be done, what happens if we do nothing). Prompts to generate questions from,
never slots to fill: the tree is emergent, so lenses suggest where fog is
likely, they do not enumerate it.
_Avoid_: dimension, category, section, checklist item

**Solution Design**:
The shape of an answer (an app, a dashboard, a model) asserted before the
question it answers has been understood. Excluded from a Business Definition.
Technology is admissible only where it carries business context: an existing
stack, a standard stack, an estate or regulatory constraint.
_Avoid_: implementation, the how, technical requirement

**Parked Solution**:
A solution idea raised during a grill and written down verbatim on the map so it
is not lost, without entering the Business Definition. Premature, not out of
scope.
_Avoid_: backlog item, idea, parking lot

**Renderer**:
A skill that reads a completed Business Map and renders one business artifact
from it. `to-vision` and `to-epics` are renderers.
_Avoid_: destination (wayfinder owns that word for what a map is finding its
way to), generator, output skill

## Inherited from wayfinder

These keep their `wayfinder` meanings exactly; this family adds nothing to them.

**Destination**: what a map is finding its way to. Here, a Business Definition.
**Fog**: in-scope questions sensed but not yet sharp enough to ticket.
**Frontier**: the open, unblocked, unclaimed tickets.
**Decisions so far**: the map's index of resolved tickets. This family's record
of business decisions; there is no separate decision log.
