---
name: to-epics
description: Cut epics from a completed business map and publish them to the issue tracker.
disable-model-invocation: true
---

# To Epics

**Partly grilled.** The map inputs and the gate rule below were settled against
a real business map and a real set of epics. The epic **template** was not: its
shape is coupled to what `/to-spec` wants as a parent, and that is still a
guess. Grill it once a spec has been written from one of these.

Cut the epics implied by the two maps for an effort — the business map charted
by `/grill-the-business` and the solution map charted by `/grill-the-solution`
— and publish them. No interview: the grills already happened.

An **epic** is a coherent slice of business capability, stated as an outcome
for a named audience. Big enough to be worth delivering on its own, small
enough for `/to-spec` to work in one pass. It is an outcome, not a feature, and
not a wayfinder ticket.

The issue tracker should have been provided to you. If not, tell the user to
run `/setup-matt-pocock-skills`.

## Process

1. **Load both maps.** They have a division of labour, and reading only one produces a predictable defect.
   - The **business map** supplies the voice and the value: the outcome, why it matters, how we'll know, and the boundary. Zoom into **What It Lets People Do**, **The Boundary**, **Who Must Say Yes** and **How We'd Know**.
   - The **solution map** supplies **the cut**: what the slices are and in what order. Zoom into **The Shape** and **What Must Come First**. A solution map reached from the business map's Notes; if there isn't one, say so — the cut will be made before the facts that determine it.

2. **Check they are ready.** Two hard stops: **What It Lets People Do** unresolved means there are no epics to cut, and **The Shape** unresolved means there are no slices to cut them into. Say so rather than inventing them. Open tickets or remaining fog on either map mean the cut is provisional; say which lenses are dark and ask whether to cut anyway.

3. **Cut the epics.** The slice comes from the solution map: **The Shape** says what the moving parts are, **What Must Come First** says what order they can land in, and **Make, Buy or Borrow** says which parts are not built here at all and so get no epic. The *wording* comes from the business map — an epic names what someone can now do, in business language, and leaves the inside of one slice open for `/to-spec`.

4. **Quiz the user.** Present them as a numbered list of titles and outcomes. Ask whether the granularity is right, whether any should merge or split, and whether anything on the map has been missed. Iterate until approved.

5. **Publish.** One issue per epic, labelled `epic`, created if the tracker lacks it. No triage label: an epic becomes implementation work when `/to-spec` runs on it, not before. Link each back to the map.

<epic-template>

## Outcome

As a <audience>, I can <capability>, so that <value>.

## Why it matters

The business case, traced to the map: the problem it closes and the value it
unlocks.

## In scope

The capability's edges, in business terms.

## Out of scope

What this epic consciously refuses, each line tracing to a decision: **The
Boundary** on the business map, or **What We Refuse to Build** on the solution
map. An epic cites a refusal; it does not make one.

## How we'll know

The observable outcome that says this epic landed.

## Gates

What this epic waits on from someone else: approvals, budget and regulatory
steps from **Who Must Say Yes**, and external lead times from **What the
Outside Permits**.

A gate is a thing another party must do. An undecided question of our own is
not a gate — it is a hole in the solution map wearing a gate's clothes, and
writing it here is how an epic comes to depend on a decision nobody ever makes.
Report it as a dark lens and leave the gate out.

## Source

Links to both maps.

</epic-template>
