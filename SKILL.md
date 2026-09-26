---
name: ruthless-simplicity
description: Subtraction is the default in product, code, reviews and git. Read at the start of every session.
alwaysApply: true
---

# Ruthless simplicity

Models get smarter and add more. More code is more bugs. More words on a
screen is more confusion. More features is less retention. So the burden
of proof sits on whoever adds. Simplicity never has to justify itself.

## The one question

Before adding anything: what happens if we do not? If the answer is
"nothing much", do not add it. Otherwise, in this order:

1. Delete the thing that made the addition feel necessary.
2. Reuse what exists: the repo helper, the stdlib, the platform, the
   installed dependency.
3. Write the shortest boring thing that works.

Then ask of whatever stays: is this the most efficient, simple and
tasteful way of doing this? Keep asking it as the work goes on.

Never strip validation at a trust boundary, error handling that guards
data, or security to get there.

## Interfaces

One screen, one job. Fewest words that work: no sentence under a heading,
no copy explaining what the user can see. Count taps to value and cut them.
Visual beats verbal. Verify on a phone before calling it done.

## Code

Look before writing. Delete before adding. Prefer the reframe that makes
whole branches, modes or layers disappear over a tidier version of the same
idea. No wrappers that only pass through, no `any`, no casts hiding a real
invariant, no new `if` bolted onto an unrelated flow. Logic lives in the
layer that owns it. Fix a bug at the root, once, for every caller.

Every fact has one owner. Compute the rest from it. A stored copy needs
sync code, so a copy must earn its place like a cache: named, with an owner
that repairs it.

Nothing ships ahead of its first user. Name what runs this code the day it
merges: a caller, a config value, a real request. If nothing does, do not
merge it. Version control keeps it until someone needs it.

## Reviews

Subtraction pass first: what can be deleted from this diff with no loss?
Reachable is not used. For every flag, optional field or mode, find what
turns it on in production. If nothing does, the fix is deletion.
Then a few high conviction structural findings. No nit flood.

## Git

One PR, one change. Plain commit title. PR body of three to five plain
sentences: what was wrong, what changed, what was removed. No ceremony.

The detail lives in the sibling skills: emil-design-eng and
web-interface-guidelines for interfaces, thermo-nuclear-code-quality-review
for deep code reviews.
