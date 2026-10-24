---
name: to-epics
description: Cut epics from a completed business map and publish them to the issue tracker.
disable-model-invocation: true
---

# To Epics

**Rough cut.** Written before any real business map existed, and the most
speculative of the three: the epic shape is coupled to what `/to-spec` wants as
a parent. Grill it once a map has been through it.

Cut the epics implied by a business map charted by `/grill-the-business` and
publish them. No interview: the grill already happened.

An **epic** is a coherent slice of business capability, stated as an outcome
for a named audience. Big enough to be worth delivering on its own, small
enough for `/to-spec` to work in one pass. It is an outcome, not a feature, and
not a wayfinder ticket.

The issue tracker should have been provided to you. If not, tell the user to
run `/setup-matt-pocock-skills`.

## Process

1. **Load the map.** Read Decisions-so-far; zoom into the tickets behind the **What It Lets People Do**, **The Boundary** and **Who Must Say Yes** lenses, which carry most of the material.

2. **Check it is ready.** **What It Lets People Do** unresolved means there are no epics to cut. Say so rather than inventing them.

3. **Cut the epics.** One per capability that delivers value standing alone. Stay in business language: an epic names what someone can now do, and leaves how open for `/to-spec`.

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

From **The Boundary**: what this epic consciously refuses.

## How we'll know

The observable outcome that says this epic landed.

## Gates

From **Who Must Say Yes**: approvals, regulatory steps or budget this needs
before it can ship.

## Source

A link to the business map.

</epic-template>
