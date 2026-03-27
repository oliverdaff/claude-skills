---
name: experts-bias-check
description: Use when you want pre-decision scrutiny, a plan feels too comfortable, you're about to commit to a direction, or when you invoke /experts-bias-check. Surfaces hidden assumptions, blind spots, and reasoning errors — not "is this good?" but "what are you not seeing?". Different from experts-review (quality critique) and experts-quickvote (fast gut-check).
---

# Expert Bias Check

A cognitive bias audit. Experts scan the work for flawed reasoning, hidden assumptions, and blind spots — not to judge quality but to surface what you might not be seeing.

Use this *before* committing to a direction. Run `experts-review` after to evaluate whether the direction is well-executed.

## Built-in panel

This skill uses a fixed bias-specialist panel rather than the domain roster. Check roster.md for any user-added decision science experts and include them; otherwise draw from:

| Expert | Known for | Bias lens |
|--------|-----------|-----------|
| **Daniel Kahneman** | Thinking Fast and Slow | System 1 vs System 2, planning fallacy, availability heuristic, overconfidence |
| **Annie Duke** | Thinking in Bets | Resulting, hindsight bias, motivated reasoning, decision quality vs outcome quality |
| **Nassim Taleb** | The Black Swan, Antifragile | Narrative fallacy, tail risk blindness, turkey problem, confirmation via non-events |
| **Shane Parrish** | Farnam Street, The Great Mental Models | Second-order effects, map vs territory, inversion |
| **Phil Tetlock** | Superforecasting | Overconfidence, scope insensitivity, failure to update on evidence |
| **Richard Thaler** | Nudge, Misbehaving | Status quo bias, mental accounting, loss aversion framing |

Select 3–5 whose lens is most relevant to the work being checked. Don't use all six — pick the sharpest angles for this specific piece.

## Process

### Step 1: Identify the decision or commitment

What is the work actually deciding, assuming, or betting on? State it explicitly before auditing. This anchors the bias check to the real stakes.

### Step 2: Select experts

Pick 3–5 from the panel above whose frameworks are most diagnostic for this type of decision. A technical architecture decision needs different lenses than a product strategy or a go-to-market plan.

### Step 3: Audit (internal)

For each expert, identify:
- The single most dangerous bias or blind spot they'd flag (one sentence)
- What specifically in the work triggers it — reference exact claims, framing, or omissions
- What a debiased version of that thinking would look like

### Step 4: Write output (scan-first)

**1. TL;DR**

```
## TL;DR

[One paragraph: the most dangerous reasoning error in this work and what it's causing you not to see.]
```

**2. Blind spots**

```
## Blind Spots

**The hidden assumption:** [The most load-bearing thing being taken for granted]

**The missing scenario:** [The plausible outcome the work doesn't account for]

**The reframe:** [If the opposite of your assumption were true, what would you do differently?]
```

**3. Expert Audits**

```
## Expert Audits

<details>
<summary><strong>[Name]</strong> — [One sentence: the specific bias or blind spot they'd flag in this work.]</summary>

[2–3 observations. Ground every point in what's specifically written — not generic bias descriptions. What in *this* work triggers the bias? What would debiased thinking look like here?]

*Simulated perspective based on [Name]'s public writing and known framework — not their actual views.*

</details>
```

**Rules:**
- Every observation must reference something specific in the work — no generic "watch out for confirmation bias"
- Each expert flags something different. If two experts would flag the same bias, cut one and find a more distinctive angle for the other
- The goal is not to say the work is wrong — it's to surface what the author cannot see from inside their current frame
