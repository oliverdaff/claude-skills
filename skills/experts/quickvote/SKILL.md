---
name: experts:quickvote
description: Use when you want a fast gut-check from multiple perspectives without a full review — sanity checks, quick decisions, "does this feel right?" moments, or when you invoke /experts:quickvote. For deep critique with synthesis and action items, use experts:review instead.
---

# Expert Quickvote

A fast gut-check from the experts most relevant to what you're evaluating. Each expert casts a vote and one sentence. Total output fits on a screen.

## Process

### Step 1: Select

Read [roster.md](../review/roster.md). If it doesn't exist, read [default-roster.md](../review/default-roster.md).

Pick **3–5 experts** whose domain is most directly relevant. Fewer is fine — don't fill slots. Skip experts who'd just echo each other.

No ad-hoc additions. No gap-filling. If the roster doesn't cover a domain, leave it uncovered.

### Step 2: Vote

For each expert:

```
**[Name]** — ✓ Looks good / ⚠ Concern / ✗ Object
*[One sentence. The single most important thing they'd say. No elaboration.]*
```

Votes:
- **✓ Looks good** — no significant issue from their lens
- **⚠ Concern** — something worth watching or addressing
- **✗ Object** — a real problem they'd push back on

### Step 3: Tally

```
**Tally: [N ✓] [N ⚠] [N ✗]** — [One sentence: the overall read]
```

### Step 4: Escalation (if needed)

If one expert voted ✗:
> "**[Name]** objected — want me to expand their take into a full review?"

If multiple experts voted ✗:
> "Multiple objections — want me to run `/experts:review` on this?"

No escalation prompt if all votes are ✓ or ⚠.
