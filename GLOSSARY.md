# skilz

A personal collection of Claude Code skills. The current effort is a family of
definition skills that turn a raw, low-fidelity product idea first into a
Business Definition, then into a Solution Definition, and only then into epics
a spec can be written against. The family composes `wayfinder` rather than
reimplementing it.

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

**Solution Definition**:
The settled account of what is built and how it holds together: the moving
parts, the seams between them, who owns each, what the outside permits, and how
it is run. Holds no implementation detail — schemas, frameworks and code belong
to a spec. Settled as the accumulated Decisions-so-far of a Solution Map, and
written out from there by `to-solution-definition`; the map is the source of
truth, so the rendered file is re-rendered rather than hand-edited.
_Avoid_: architecture, design doc, HLD, technical spec

**Solution Map**:
A `wayfinder` map whose Destination is a Solution Definition and whose Notes
install the solution lenses and the cross-cutting test. Admits a question that
constrains more than one capability or determines how the capabilities are
sliced; everything a single capability settles alone belongs to a spec.
_Avoid_: tech map, architecture board, phase two

**Lens**:
An angle a grill probes through — who pays and what's the job to be done on a
Business Map, where the seams fall and who runs it on a Solution Map. Prompts to
generate questions from, never slots to fill: the tree is emergent, so lenses
suggest where fog is likely, they do not enumerate it.
_Avoid_: dimension, category, section, checklist item

**Solution Design**:
The shape of an answer (an app, a dashboard, a model). Premature while the
business definition is unsettled: there it is an answer that has outrun its
question, and it is parked rather than argued with. Once the definition settles
the question has caught up, and solution design becomes the substance of a
Solution Definition. The term carries no judgement; the timing does.
_Avoid_: implementation, the how, technical requirement

**Parked Solution**:
A solution idea raised during a grill and written down verbatim on the map so it
is not lost, without entering the Business Definition. Premature, not out of
scope. Drained when a Solution Map is charted: each becomes a ticket there,
joins its fog, or is dismissed as a refusal. The same mechanism recurs one
altitude down, where a Solution Map parks implementation detail for a spec.
_Avoid_: backlog item, idea, parking lot

**Renderer**:
A skill that reads one or more completed maps and renders a single artifact
from them. `to-vision`, `to-solution-definition` and `to-epics` are renderers.
Renderers read maps, never each other's output: a rendered file is a leaf, so
every artifact is one hop from a map and nothing goes stale behind a copy.
_Avoid_: destination (wayfinder owns that word for what a map is finding its
way to), generator, output skill

## Inherited from wayfinder

These keep their `wayfinder` meanings exactly; this family adds nothing to them.

**Destination**: what a map is finding its way to. Here, a Business Definition.
**Fog**: in-scope questions sensed but not yet sharp enough to ticket.
**Frontier**: the open, unblocked, unclaimed tickets.
**Decisions so far**: the map's index of resolved tickets. This family's record
of business decisions; there is no separate decision log.
