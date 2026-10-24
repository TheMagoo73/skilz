---
name: grill-the-business
description: Grill a raw product or business idea into a business definition, charted as a wayfinder map. Use when an idea is too vague to spec, when charting a business map, and when a map's Notes name this skill.
---

# Grill the Business

An idea has arrived at napkin fidelity. Find the **business definition** hiding
inside it (who it is for, what problem it solves, what value it creates, where
it stops) while solution design stays out.

The machinery is `wayfinder`: the
idea becomes a **map**, each business question a ticket, each resolution a line
in Decisions-so-far. Wayfinder owns fog, frontier, blocking, claims and resume.
This skill supplies the two things it is agnostic about: the **lenses** that say
where fog gathers in a business idea, and the rule that keeps the answer out
until the question is understood.

## Two ways in

- **Charting**: the user invokes with an idea. Run [Chart the map](#chart-the-map), then stop.
- **Consulted**: a `/wayfinder` session loaded this skill because the map's Notes name it. Skip charting. Work the claimed ticket through the lenses and the rule below.

## Convert solutions into questions

A business definition holds the problem. Technology belongs in it wherever it
carries business context: the stack they already run, the standard stack for
their sector, the estate, the regulator. Those are constraints on the problem,
and they are part of the definition.

A **solution** is different: an answer that has outrun its question. Convert it
into the question underneath, and ticket that.

| They said | The question underneath |
| --- | --- |
| "It'll be a mobile app" | Who needs this away from a desk, how often, and what breaks today when they cannot? |
| "We'll use AI" | What judgement is made today, by whom, and what does getting it wrong cost? |
| "There'll be a dashboard" | Which decision is being made blind, and who makes it? |
| "It integrates with their CRM" | What do they re-key by hand today, and what does that cost them? |

Then write their original line verbatim under **Parked: solutions** on the map.
It is kept, not argued with, and it stays out of Decisions-so-far: premature
rather than out of scope.

`prototype` tickets on a business map produce an artifact a customer or a board
member could react to: a press release, a pricing table, a landing-page
headline, a customer journey.

## The lenses

Ten angles on a business idea. Each one says where fog is likely and generates
the questions that become tickets.

| Lens | Attacks the idea by asking |
| --- | --- |
| **Who** | Which specific human. Buyer, user and beneficiary where they differ, and who this is deliberately not for |
| **The Job** | What they are trying to get done, and what they do today instead. Forced concrete: a named person, a real Tuesday morning |
| **Do Nothing** | Inertia is the strongest competitor. What happens if this never exists? Then substitutes and rivals |
| **Follow the Money** | Who pays, how much, out of whose budget, and what the business gets back: revenue, cost avoided, risk reduced |
| **Why Now** | What changed. Why this is possible or urgent now and was not three years ago |
| **Proof** | Separates what is known from what is believed. Names the riskiest assumption and what would falsify it |
| **The Boundary** | What this is not, and what is being consciously refused |
| **What It Lets People Do** | The capabilities, in business language. Feeds `to-epics`, and the lens where solutions arrive most often |
| **Who Must Say Yes** | Budget holders, regulators, brand gatekeepers; the money and the time actually available |
| **How We'd Know** | Observable outcomes, with numbers and a horizon, including how you would know you were wrong |

Lenses point at fog; they do not enumerate it. The tree is emergent, so a thin
idea may justify four of them and nothing more. A map carrying one ticket per
lens has used them as a checklist, which is the failure mode.

## Chart the map

`wayfinder` is user-invoked, so no skill can call it. Read its `SKILL.md`
from your skills directory and follow its **Chart the map** mode, with these
four deltas:

1. **Destination**: a business definition of the idea, sharp enough to write a vision from and cut epics out of. No solution design.
2. **Map the frontier** breadth-first **through the lenses**: sweep the idea against each in turn, ticketing what is already sharp and leaving the rest as fog. Done when every lens has been swept and each has produced a ticket, a patch of fog, or a reasoned pass.
3. **Notes**: use the block below verbatim. It is the hook that reloads this skill on every later session.
4. Add a **Parked: solutions** section to the map body, between *Not yet specified* and *Out of scope*.

```markdown
## Notes

Business definition map. Every session: call the Skill tool with
"grill-the-business", and work the ticket through its lenses and its
convert-solutions-into-questions rule.

Decisions here are business decisions: customer, problem, value, boundary.
Solution design goes to Parked: solutions, below.

## Parked: solutions

<!-- solution ideas raised in passing, kept verbatim, premature rather than
out of scope; they enter no decision -->
```

## When the map is done

No tickets remain and no fog is left. Decisions-so-far is now the business
definition. Hand off: `/to-vision` renders the vision statement, `/to-epics`
cuts the epics that `/to-spec` then works from.
