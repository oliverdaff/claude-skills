# Claude Skills

Personal collection of [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skills.

## Skills

| Skill | Description |
|-------|-------------|
| [experts-review](skills/experts/review/) | Review code, architecture, product specs, or business decisions from a dynamically-selected panel of real, named experts. Supports `--devil` for adversarial pressure-testing and `--verbose` for flat output (agent consumption). |
| [experts-quickvote](skills/experts/quickvote/) | Fast gut-check — 3–5 relevant experts each cast a vote and one sentence. |
| [experts-bias-check](skills/experts/bias-check/) | Cognitive bias audit — surfaces hidden assumptions and blind spots before you commit to a direction. |

## Installation

### Symlink (recommended — gets updates on `git pull`)

```bash
mkdir -p ~/.claude/skills/experts
ln -s /path/to/claude-skills/skills/experts/review ~/.claude/skills/experts/review
ln -s /path/to/claude-skills/skills/experts/quickvote ~/.claude/skills/experts/quickvote
ln -s /path/to/claude-skills/skills/experts/bias-check ~/.claude/skills/experts/bias-check
```

### Copy

```bash
cp -r skills/experts ~/.claude/skills/
```

## Usage

### Expert Review

Deep multi-perspective critique with synthesis and action items:

```
/experts-review
```

Or ask naturally: "review this from expert perspectives"

The skill dynamically selects 4-8 real, named experts based on what you're reviewing — code gets systems and architecture experts, a product spec gets positioning and UX experts, a business plan gets finance and legal experts.

**Customise your panel:**

```
/experts-review add
```

This walks you through adding experts to your personal roster. Your roster (`roster.md`) is gitignored — it won't be overwritten by updates.

On first use, `default-roster.md` is copied to `roster.md` as your starting panel. The default includes experts across: systems & performance, architecture, security, production & observability, data & infrastructure, UX, product & business, and legal.

### Expert Quickvote

Fast gut-check — each expert votes and gives one sentence:

```
/experts-quickvote
```

Use this for quick sanity checks. Run `/experts-review` when you need depth.

### Expert Bias Check

Cognitive bias audit before committing to a direction:

```
/experts-bias-check
```

Scans for hidden assumptions, reasoning errors, and blind spots using a fixed panel of decision science experts (Kahneman, Annie Duke, Taleb, Parrish, Tetlock, Thaler). Use this *before* a review, not after.

### Devil's Advocate Mode

Adversarial pressure-testing of a decision or piece of work:

```
/experts-review --devil
```

Every expert argues *against* the work as forcefully as their philosophy allows. Use when you've already decided something and want to stress-test it before committing.

### Verbose Mode

Full flat output for agent consumption or when you want everything visible without expanding:

```
/experts-review --verbose
```

## The real-people question

This skill suite generates fictional critique *in the style of* real people, not quotes from them. Think of it as "what would this person's framework say about this?" rather than "what did this person say?". The experts on the roster have extensive public writing that makes their values and priorities clear — the skill applies that framework, it doesn't impersonate them.

If you share output from these skills, make clear it's simulated. The footer on each expert take is there for exactly this reason.

## License

MIT
