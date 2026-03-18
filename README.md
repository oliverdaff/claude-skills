# Claude Skills

Personal collection of [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skills.

## Skills

| Skill | Description |
|-------|-------------|
| [expert-review](skills/expert-review/) | Review code, architecture, product specs, or business decisions from a dynamically-selected panel of real, named experts. |

## Installation

### Symlink (recommended — gets updates on `git pull`)

```bash
ln -s /path/to/claude-skills/skills/expert-review ~/.claude/skills/expert-review
```

### Copy

```bash
cp -r skills/expert-review ~/.claude/skills/
```

## Usage

### Expert Review

Ask for a review in any Claude Code session:

```
/expert-review
```

Or just ask naturally: "review this from expert perspectives"

The skill dynamically selects 4-8 real, named experts based on what you're reviewing — code gets systems and architecture experts, a product spec gets positioning and UX experts, a business plan gets finance and legal experts.

**Customise your panel:**

```
/expert-review add
```

This walks you through adding experts to your personal roster. Your roster (`roster.md`) is gitignored — it won't be overwritten by updates.

On first use, `default-roster.md` is copied to `roster.md` as your starting panel. The default includes experts across: systems & performance, architecture, security, production & observability, data & infrastructure, UX, product & business, and legal.

## License

MIT
