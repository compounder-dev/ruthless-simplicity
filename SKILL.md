---
name: ruthless-simplicity
description: Subtraction is the default in product, code, reviews and git. Read at the start of every session.
alwaysApply: true
---

# Ruthless simplicity

Simplicity is how we go faster, not how we do less. Every line of code,
word on a screen and feature carries weight, so extra weight earns its
place. Ambition never has to: the boldest capability, built in its
simplest form, is the goal.

## The one question

> Is this the most efficient, simple and tasteful way of doing this?

Ask it before you start, while you work and before you ship. Efficient:
fastest for the user, cheapest to run. Simple: the fewest parts, lines and
words. Tasteful: it reads as inevitable.

Before adding anything, ask what happens without it. If the answer is
"nothing much", leave it out. Otherwise, in this order:

1. Delete the thing that made the addition feel necessary.
2. Reuse what exists: the repo helper, the stdlib, the platform, the
   installed dependency.
3. Write the shortest boring thing that works.

Validation at a trust boundary, error handling that guards data, and
security always stay.

## Interfaces

One screen, one job. Fewest words that work: no sentence under a heading,
no copy explaining what the user can see. Count taps to value and cut them.
Visual beats verbal. Verify on a phone before calling it done.

## Code

Look before writing. Delete before adding. Prefer the reframe that makes
whole branches, modes or layers disappear over a tidier version of the same
idea. Wrappers earn their keep by clarifying. Types state the real
invariant. New behavior gets its own home instead of an `if` in an
unrelated flow. Logic lives in the layer that owns it. Fix a bug at the
root, once, for every caller.

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
