---
name: to-prd
description: Render a business-oriented PRD from a completed business map.
disable-model-invocation: true
---

# To PRD

**Grilled, unrendered.** The shape below was settled in a design grill — what a
PRD is, what it reads, what it refuses — but the template has not been run
against a real business map. Grill it again once it has.

Render the PRD for a business map charted by `/grill-the-business`. No
interview: the grill already happened, and every answer is on the map.

A **PRD** is the complete rendering of a Business Definition as a document:
every decision on the business map, in business language, organised for someone
who must sign it off or plan against it. A vision persuades; a PRD commits. The
two read the same map and differ in completeness and register, not in content.

## What it reads, and what it refuses

The **business map only**. A PRD is renderable the moment
`/grill-the-business` finishes and it never waits for a solution map — it is
wanted most at exactly the point where no solution design exists yet.

Three things it therefore refuses:

- **No epics.** Capabilities appear as business outcomes; how they are grouped and sequenced is a slicing decision, and slicing is not a business decision. `/to-epics` cuts the slices from the solution map. The two never need to agree on a count.
- **No parked solutions.** They are premature solution design, queued for `/grill-the-solution`. A reader of a signed document treats them as commitments, and they would reach the solution map already half-decided.
- **No shape.** Parts, seams, operating model and ownership are the solution map's decisions. A PRD that carries them is waiting for a map it was designed not to need.

## Process

1. **Load the map.** Take it from the argument, or find the `wayfinder:map` issue for this effort — the business map, not the solution map, if both exist. Read Decisions-so-far, then zoom into the tickets behind any line whose one-line gist is too thin to write from.

2. **Check it is ready.** Three lenses are load-bearing, and the document fails without each for a different reason: **What It Lets People Do** (no capabilities means there is nothing to specify), **The Boundary** (a commitment with no edge is not a commitment — it is where scope arrives later as an assumption) and **How We'd Know** (sign-off with no acceptance criteria is sign-off on vibes). With any of those unresolved there is no PRD to write yet.

   Thin elsewhere is workable. Name the dark lenses and ask whether to render anyway. Note that a map can be ready for a vision and not for a PRD, or the reverse: they are different documents with different failure modes.

3. **Write `docs/business/prd.md`** using the template below, in the vocabulary of `GLOSSARY.md`. Every claim traces to a decision on the map; where you would need to invent one, write the gap instead.

   The document is self-contained — it is circulated to people who have read nothing else. Link `docs/business/vision.md` from **Context** if that file exists, and say nothing about it if it does not. The two renderers run independently and either may run without the other.

4. **Report** the path, every gap you wrote, and every dark lens. Do not offer to fill a gap in conversation: an answer given in chat is a decision that never reached the map. The fix for a gap is a ticket on the map and another render.

This is a render, not a negotiation. There is no approval loop and no second
grill — every section is a decision that was already settled.

Later runs rewrite this file wholesale rather than merging hand edits: an edit
made here and not on the map is a decision nobody made.

<prd-template>

# <Name> — Product Requirements

> Rendered from <link to the business map>. Re-rendered on each run, not
> hand-edited: change the map.

## Context

The one line a stranger understands, then what the person is trying to get done
and what they do today instead, from **The Job**. Then **Why Now**: what
changed, and what waiting costs. A few sentences, not the full narrative — link
`vision.md` for that, if it exists.

## Who this is for

From **Who**: the buyer, the user and the beneficiary where they differ, named
specifically. Then who this is deliberately not for. Buyer and user being the
same person is itself worth stating; it is the distinction the vision blurs and
a signer most needs.

## The case

From **Follow the Money**: what the customer gets, who pays, out of whose
budget, and what the business gets back — revenue, cost avoided, risk reduced.
Then from **Do Nothing**: what this costs if it never exists, and what they use
instead today.

## Capabilities

From **What It Lets People Do**. Each one states what someone can now do, for
whom, and the value it creates, in business language. No grouping, no
sequencing, no epic numbers — the cut belongs to `/to-epics` and is made against
the solution map.

## Where this stops

From **The Boundary**: what is consciously refused, each line a decision rather
than an omission. The explicit no that keeps the yes meaningful.

## Success measures

From **How We'd Know**: observable outcomes with numbers and a horizon,
including what would tell us we were wrong.

## Approvals and constraints

From **Who Must Say Yes**: budget holders, regulators and brand gatekeepers, and
the money and time actually available. Each is a thing another party must do, on
their timeline.

## Open questions and bets

From **Proof**: the riskiest assumption still unproven, and what would falsify
it. Then any fog still open on the map at render time, and a pointer to every
gap written above — a gap stays where the missing decision belongs, and is
listed here so a reader sees the whole set in one place.

A PRD that hides its open questions is signed off on a false premise, and the
signer is the person who most needs to see them.

## Source

Link to the business map.

</prd-template>
