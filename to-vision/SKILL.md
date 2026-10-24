---
name: to-vision
description: Render a vision statement from a completed business map.
disable-model-invocation: true
---

# To Vision

**Rough cut.** Written before any real business map existed, so the template
below is a guess at what Decisions-so-far yields. Grill it properly once a map
has been through it.

Render the vision statement for a business map charted by
`/grill-the-business`. No interview: the grill already happened, and every
answer is on the map.

## Process

1. **Load the map.** Take it from the argument, or find the `wayfinder:map` issue for this effort. Read Decisions-so-far, then zoom into the tickets behind any line whose one-line gist is too thin to write from.

2. **Check it is ready.** Open tickets or remaining fog mean the definition is unfinished. Say which lenses are still dark and ask whether to render anyway. **Who**, **The Job** and **Do Nothing** are load-bearing: with any of those unresolved there is no vision to write yet.

3. **Write `docs/business/vision.md`** using the template below, in the vocabulary of `GLOSSARY.md`. Every claim traces to a decision on the map; where you would need to invent one, write the gap instead.

4. **Report** the path and anything you had to leave as a gap.

A vision never closes, which is why it is a file and not an issue. Rewrite this
file on later runs rather than appending.

<vision-template>

# <Name>

## In one line

The sentence a stranger understands. No jargon, no solution.

## Who this is for

The specific human, from the **Who** lens. Name who it is not for: a vision
that serves everyone describes nothing.

## The problem today

From **The Job** and **Do Nothing**: what they are trying to get done, what
they do instead, and what that costs them. Concrete enough to picture.

## What changes

The world with this in it, from the customer's side of the table.

## Why now

From **Why Now**: what changed, and why waiting is a decision with a cost.

## How the value flows

From **Follow the Money**: what the customer gets, what the business gets back.

## Where this stops

From **The Boundary**: what is consciously refused. The explicit no that keeps
the yes meaningful.

## How we'll know

From **How We'd Know**: observable outcomes, with numbers and a horizon,
including what would tell us we were wrong.

## What we're still betting on

From **Proof**: the riskiest assumption still unproven.

</vision-template>
