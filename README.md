# Ruthless simplicity

One skill that makes subtraction the default for every coding agent: product, interface, code, reviews, git surfaces, process.

Models get smarter and add more. More code is more bugs. More words is more confusion. More features is less retention. This skill puts the burden of proof on whoever adds.

The whole skill is [SKILL.md](SKILL.md).

## Install

Claude Code, global:

```sh
git clone https://github.com/compounder-dev/ruthless-simplicity ~/code/ruthless-simplicity
mkdir -p ~/.claude/skills/ruthless-simplicity
ln -s ~/code/ruthless-simplicity/SKILL.md ~/.claude/skills/ruthless-simplicity/SKILL.md
```

Add one line to `~/.claude/CLAUDE.md` so it loads every session:

```
Ruthless simplicity is the standing gate: cat ~/.claude/skills/ruthless-simplicity/SKILL.md at the start of every session and at the top of every subagent brief.
```

oh-my-pi, always on (the frontmatter carries `alwaysApply: true`):

```sh
mkdir -p ~/.omp/agent/rules
ln -s ~/code/ruthless-simplicity/SKILL.md ~/.omp/agent/rules/ruthless-simplicity.md
```

pi:

```sh
ln -s ~/code/ruthless-simplicity/SKILL.md ~/.pi/agent/skills/ruthless-simplicity.md
```

Any other agent: put the file where it reads instructions and tell it to read the file at the start of every session.

## Sources

Bending Spoons on radical simplicity, Steve Jobs on one window and one button, Akar Sumset's first principles for product design, the Vercel web interface guidelines, Emil Kowalski's design engineering notes, and the thermonuclear code quality review.

## Change it

Edit SKILL.md. Shorter is better. A rule earns its line by changing a decision.
