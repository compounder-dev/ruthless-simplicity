---
name: ruthless-simplicity
description: The house standard for every product, interface, code, review, and git decision. Load at the start of every session and before any build, review, PR, or design. Trigger words - simplify, simplicity, review, thermonuclear, first principles, design, PR, ship.
alwaysApply: true
---

# Ruthless simplicity

Models get smarter and add more: more code, more features, more words on
screen, more layers. More code is more bugs. More words is more confusion.
More features is less retention. Simplicity is fast for the customer, cheap
to maintain, and easy to reason about. This skill makes subtraction the
default in everything: product, interface, code, reviews, and git.

## The stance

- Complexity must earn its place with evidence. Simplicity never has to
  justify itself. The burden of proof sits on whoever adds.
- The best products do one or two things flawlessly. One window, one
  button, done.
- Maximise the work not done. The best code is the code that does not exist.
- Ask why, then answer with a test, not with an idea.
- Do not reinvent the wheel. Use the pattern, the helper, the stdlib, the
  platform, the installed dependency. Novelty is a cost.
- Design behaviours, not things. Every screen exists to get one action done.
- Reversible decisions get made fast. Only irreversible ones get deliberation.

## The one question

Before adding anything, ask: what happens if we do not?

If the answer is "nothing much", do not add it. Then, in order:

1. Delete. Remove the thing that made the addition feel necessary.
2. Reuse. Find what already exists in the repo, stdlib, or platform.
3. Write the shortest thing that works. Boring over clever.

Never trim validation at a trust boundary, error handling that guards
data, or security to get there.

## Product and interface

The reference is the best consumer apps: fast, visual, obvious, quiet.

- One screen, one job. If a screen needs a paragraph to explain itself,
  the screen is wrong.
- Fewest words that work. No sentence under a heading. No subtext restating
  a control. No copy that explains what the user can already see. Headings
  name the thing plainly. Sentence case everywhere.
- Visual over verbal. A logo, an icon, a number, a card beats a sentence.
- Taps to value is the metric. Count them. Cut them.
- Progressive disclosure: show the next step, not every step.
- No modals or sheets for flows. A flow is a screen with a back arrow and a
  URL. Overlays are for a single confirm or a tiny picker at most.
- Every state designed: empty, loading, sparse, dense, error. Skeletons
  mirror the final layout. No dead ends, always a next step.
- Consumer copy: active voice, second person, plain words, no jargon, no
  invented labels. Real numbers only in marketing.
- Motion earns its place. Press feedback on every tappable thing (scale
  0.97, 100 to 160 ms). Enter and exit with ease-out, under 300 ms, transform
  and opacity only, never `transition: all`. Frequent actions do not animate.
  Honour reduced motion.
- Touch: targets 44 px, `touch-action: manipulation`, safe area insets,
  16 px inputs on mobile, no zoom disabling.
- Forms: labels on every control, correct `type` and `inputmode`,
  `autocomplete` set, paste never blocked, submit stays enabled until the
  request starts, errors inline next to the field.
- Links are links, buttons are buttons. Icon-only buttons carry
  `aria-label`. Focus is visible. Keyboard works everywhere.
- URL is state. Tabs, filters, steps, expanded panels all deep link.
- Numbers in tables are tabular. Ellipsis is `…`. Quotes are curly.
- Verify on a phone frame and on desktop before calling it done. Then let
  a real user test it on prod.

## Code

- Look before writing. A helper in the repo, the stdlib, the platform, or
  an installed dependency beats new code every time.
- Delete before adding. A PR that grows the codebase needs a reason. Report
  lines removed and added.
- Code judo. Before restructuring, look for the reframe that makes whole
  branches, modes, helpers, or layers disappear. Prefer the solution that
  feels inevitable in hindsight.
- No spaghetti growth. A new `if` in an unrelated flow is a design problem,
  not a nit. Push the logic into the model, the type, or the module that
  owns it.
- No thin wrappers, identity abstractions, or pass-through helpers.
- No `any`, no casts, no optional parameters that hide a real invariant.
  Make the boundary explicit and the control flow gets simpler.
- Logic lives in its canonical layer. Feature code never leaks into shared
  paths. Duplicated helpers get folded into the one that exists.
- No file crosses 1000 lines. Decompose first.
- Fix bugs at the root: find every caller and fix the shared function once.
  Never add a workaround, a fallback, or a "temporary" branch.
- Comments near zero. The rationale goes in the PR body.
- Lint stays clean. Complexity and effect ratchets only go down.
- Independent work runs in parallel. Related updates land atomically.
- Tests cover behaviour, not implementation. One clear test beats five
  brittle ones.

## Reviews

Every review is a subtraction pass first, a correctness pass second.

1. What can be deleted from this diff with no loss? List it.
2. Is there a code judo move that makes the change dramatically simpler?
3. Did a file, a component, or a function get harder to hold in one head?
4. Did the diff add branching, optionality, casts, or wrappers?
5. Is the logic in the right layer, reusing the canonical helper?
6. For interfaces: fewer words, fewer taps, every state, phone verified?

Report a small number of high-conviction findings, structural first.
Do not flood with cosmetic notes. Approval bar: no structural regression,
no missed obvious simplification, no unjustified growth, no spaghetti
branch, no unnecessary abstraction, no boundary leak.

Good phrases: "this works, but makes the surrounding code messier; keep the
behaviour, restructure the implementation", "this abstraction is not earning
its keep, keep the direct flow", "I think there is a code judo move here that
deletes these branches".

## Git surfaces

- One PR, one change. Small diffs, reviewed by a person who reads every line.
- Commit title: plain words, what changed, under 70 characters.
- PR body: three to five plain sentences. What was wrong, what changes,
  what was removed. No checklists, no headings, no AI mentions, no vendor
  or customer names, no design references.
- Branch in a worktree. Squash merge. Delete the branch.
- No process ceremony: no lifecycle labels, no templates, no gates that a
  person does not read. The review itself is the gate.

## Process

- No invented gates, no status theatre, no meetings without a decision.
- Build one flow at a time. Ship it, verify it visually, let a real user
  test it, then the next.
- Say what happened in plain sentences. Lead with the result. No slogans,
  no drama, no lecturing.

## The scorecard

Every PR and every design answers these in one line each:

- Lines removed vs added.
- Screens, steps, or taps removed vs added.
- Words on screen removed vs added.
- Concepts a reader must hold: fewer or more?

If every line says "more", start again.

## How to apply

- Load this skill at the start of every session. It is the standing gate.
- Every subagent brief opens with `cat ~/.claude/skills/ruthless-simplicity/SKILL.md`
  and the brief says the final report must show the scorecard.
- For interface work also load `emil-design-eng` and
  `web-interface-guidelines` in full. This skill carries their spine, not
  their detail.
- For a deep code review also load `thermo-nuclear-code-quality-review`.
- Before every push: the scorecard, a phone and desktop screenshot for
  interface work, lint clean, types green.
