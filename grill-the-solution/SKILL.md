---
name: grill-the-solution
description: Grill a settled business definition into a solution definition, charted as a wayfinder map. Use when epics or specs are blocked on cross-cutting decisions, when charting a solution map, and when a map's Notes name this skill.
---

# Grill the Solution

A business definition has settled: who it is for, what problem it solves, where
it stops. The shape of the answer has not. Find the **solution definition** —
the moving parts, the seams between them, who owns each, what the outside
permits, how it is run — while implementation detail stays out.

The machinery is `wayfinder`: a second map, each cross-cutting question a
ticket, each resolution a line in Decisions-so-far. Wayfinder owns fog,
frontier, blocking, claims and resume. This skill supplies the **lenses** that
say where fog gathers in a shape, and the **test** that keeps epic-local
decisions out.

## Two ways in

- **Charting**: the user invokes with a finished business map. Run [Chart the map](#chart-the-map), then stop.
- **Consulted**: a `/wayfinder` session loaded this skill because the map's Notes name it. Skip charting. Work the claimed ticket through the cross-cutting test, the lenses and the conversion rule below.

## The cross-cutting test

A question belongs here if it **constrains more than one capability, or
determines how the capabilities get sliced**. Capabilities come from the
business map's **What It Lets People Do** lens.

Everything a single capability settles alone belongs to `/to-spec`, which does
architecture for one slice: modules, interfaces, schemas, API contracts. This
map does what crosses slices.

The challenge question for every candidate ticket is *which capabilities does
this constrain?* — and "only this one" sends it to `/to-spec`. That there is one
shared API contract, and who owns it, crosses slices. What is in it does not.

## Convert implementation into questions

A solution definition holds the shape. Implementation detail is an answer that
has outrun its question, one altitude down. Convert it into the question
underneath, and ticket that question if it passes the test above.

| They said | The question underneath |
| --- | --- |
| "We'll cache it in Redis" | What has to be fast, how fast, and what does serving a stale fact cost? |
| "It should be a microservice" | Which parts change on different clocks, and who owns each? |
| "A visual rule builder, like Zapier" | Which decisions must the author express, and what is the smallest vocabulary that covers them? |
| "We'll just sync it nightly" | Where does this fact come from, who keeps it true, and what does one wrong fact cost? |

Sometimes the question underneath is itself implementation: "Postgres, not
MySQL" has no shape question beneath it. That is the honest case — park the line
and move on.

Either way, write their original line verbatim under **Parked: implementation**
on the map. It is kept for `/to-spec`, and it enters no decision here.

`prototype` tickets on a solution map are **spikes**: throwaway code that
answers a shape question and is deleted once it has. A business map re-scopes
`prototype` away from code; this map restores it.

## The lenses

Eight angles on a shape. Each one says where fog is likely and generates the
questions that become tickets.

| Lens | Attacks the shape by asking |
| --- | --- |
| **The Shape** | What kind of thing this is, what the moving parts are, and where the seams between them fall |
| **Make, Buy or Borrow** | For each part: build it, buy it, partner for it, or already have it — and what each choice costs us later |
| **What the Outside Permits** | What platforms, carriers, vendors and regulators actually allow, and on whose timeline. A lead time, not a decision |
| **Who Runs It** | The operating model. Who maintains what, how often it changes, how a change propagates, and what it costs to stand up every day |
| **Where It Breaks** | Wrong, slow, or down. What a single bad fact costs when it reaches a customer, and who carries the loss |
| **What We Refuse to Build** | The deliberate shape refusals. Generality, expressiveness, configurability — each one a cost disguised as a feature |
| **The Riskiest Bet** | What must be true for this shape to hold, and what would falsify it. Where `prototype` tickets come from |
| **What Must Come First** | Ordering constraints that change the slice. Not a roadmap — the facts that say what cannot be decided yet |

Lenses point at fog; they do not enumerate it. The tree is emergent, so a
narrow shape may justify four of them and nothing more. A map carrying one
ticket per lens has used them as a checklist, which is the failure mode.

## Before charting

Read the business map. Three of its lenses are load-bearing here:

- **What It Lets People Do** — a hard stop. The cross-cutting test measures against the capability list; with no capabilities there is nothing to be cross-cutting across.
- **The Boundary** — without it, **What We Refuse to Build** becomes a scope argument instead of a shape decision.
- **Follow the Money** — without it, **Make, Buy or Borrow** and **Who Runs It** have no criterion.

Thin elsewhere is workable. Say which lenses are dark and ask whether to chart
anyway.

## Chart the map

`wayfinder` is user-invoked, so no skill can call it. Read its `SKILL.md`
from your skills directory and follow its **Chart the map** mode, with these
five deltas:

1. **Title and Destination**: title it `Map: <effort> — solution definition`, mirroring the business map's title, so the two are told apart on sight. The Destination is a solution definition of the settled business definition: the parts, the seams, who owns each, and how it is run, sharp enough to cut epics from and write specs against. Implementation detail is not the destination.

2. **Map the frontier** breadth-first **through the lenses**: sweep the shape against each in turn, ticketing what is already sharp and leaving the rest as fog. Done when every lens has been swept and each has produced a ticket, a patch of fog, or a reasoned pass.

3. **Sweep the business map.** Two passes, both of which annotate that map's **margins** — a pointer, a disposition note, a struck-through fog item. Its Decisions-so-far is closed.
   - **Parked: solutions.** Each entry becomes a ticket here, joins this map's fog, or is dismissed with a reason — and a dismissal is a refusal, so record it under **What We Refuse to Build** rather than letting it vanish. Annotate each entry in place with where it went; the text stays on the business map, which is the record of what was said.
   - **Not yet specified.** Migrate the fog that belongs here, striking it through there. An item may migrate only if answering it **cannot change a business decision** — if the answer could move the customer, the boundary, or where the money comes from, it is business fog and it stays.

4. **Notes**: use the block below verbatim. It is the hook that reloads this skill on every later session.

5. **Write the redirect.** Add a line to the business map's Notes naming this map: *this definition is settled; solution design continues on `<link>`*. Both maps carry the label `wayfinder:map` for the same effort, so a session that loads the finished one must be told where the live work is.

```markdown
## Notes

Solution definition map. Every session: call the Skill tool with
"grill-the-solution", and work the ticket through its lenses, its cross-cutting
test and its convert-implementation-into-questions rule.

Decisions here are shape decisions: the parts, the seams, who owns each, what
the outside permits, how it is run. Implementation detail goes to Parked:
implementation, below.

Business definition: <link to the business map>. Its decisions are closed.

## Parked: implementation

<!-- schemas, frameworks and code raised in passing, kept verbatim, premature
rather than out of scope; they enter no decision -->
```

## When the map is done

No tickets remain and no fog is left. Decisions-so-far is now the solution
definition. Hand off: `/to-solution-definition` writes it out, and the epics
that `/to-spec` works from are cut from this map. Neither of those skills exists
yet: the epic cutter is being rebuilt from the ground up against this map.
