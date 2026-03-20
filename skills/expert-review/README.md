# expert-review

A Claude skill that simulates a panel of real, named experts reviewing your work.

## What it does

Selects 4-8 experts from a customisable roster whose documented philosophy is relevant
to what you're reviewing, then applies their known framework to your work. Each take is
grounded in their public writing — blog posts, papers, talks, interviews.

## The real-people question

This skill generates fictional critique *in the style of* real people, not quotes from them.
Think of it as "what would this person's framework say about this?" rather than "what did
this person say?". The experts on the roster have extensive public writing that makes their
values and priorities clear — the skill applies that framework, it doesn't impersonate them.

If you share output from this skill, make clear it's simulated. The footer on each expert
take is there for exactly this reason.

## Installation

Copy to `~/.claude/skills/expert-review/` or symlink from your skills repo.
On first use, `roster.md` is created from `default-roster.md` as your personal panel.

## Customising your panel

Run `/expert-review add` for a guided flow, or edit `~/.claude/skills/expert-review/roster.md` directly.
