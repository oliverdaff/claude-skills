---
name: experts:review
description: Use when the user asks for expert review, multi-perspective critique, or wants work reviewed from diverse viewpoints — or invokes /experts:review. Covers code, architecture, product decisions, and business strategy. Use --devil for adversarial pressure-testing, --verbose for flat output (agent consumption). Also handles /experts:review add for roster management. Do NOT use for standard code review (use code-reviewer), pre-merge verification (use requesting-code-review), or responding to review feedback (use receiving-code-review).
---

# Expert Review

Review work from a dynamically-selected panel of real, named experts. Each expert stays true to their known philosophy — direct, not diplomatic.

This skill provides strategic, perspective-diverse critique. It pairs well after mechanical code review (code-reviewer) for a second pass focused on design philosophy and trade-offs.

## Modes

**Default** — balanced critique. Compact output: expert one-liners visible, full takes collapsed, verdict at the bottom.

**Devil's advocate** (`/experts:review --devil`) — each expert makes the strongest possible case *against* the work. Not balanced critique; adversarial pressure-testing. Use when you've already decided something and want to stress-test it before committing.

**Verbose** (`/experts:review --verbose`) — full flat output with no collapsed sections. Use for agent consumption or when you want everything visible without expanding.

## Process

### Step 1: Identify domains

Analyse what's being reviewed. Map it to domains:

| Category | Example domains |
|----------|----------------|
| **Code** | performance, correctness, API design, error handling, async, testing, observability |
| **Architecture** | modularity, coupling, scale, data flow, security boundaries |
| **Product** | user experience, market fit, simplicity, accessibility |
| **Business** | unit economics, legal/compliance, risk, go-to-market |
| **Process** | team workflow, deployment, incident response |

### Step 2: Select experts

Read the roster at [roster.md](roster.md). If `roster.md` does not exist, copy [default-roster.md](default-roster.md) to `roster.md` first — this gives the user a starter panel they can customise.

Select 6-8 experts whose domains match the review target. Prioritise experts whose known philosophy directly applies.

**Selection rules:**
- At least one expert should challenge the fundamental approach ("is this the right thing to build?")
- At least one should focus on long-term maintenance cost
- Never pick experts just to fill slots — each must have something specific to say about THIS work
- If the roster has fewer than 3 relevant experts for a domain, proceed to Step 3

### Step 3: Fill domain gaps (if needed)

When the roster lacks coverage for a relevant domain, generate ad-hoc expert personas:
- Use a **real, named person** known for that domain (not a generic "Security Expert")
- State their name, known focus, and what they'd flag
- Format identically to roster entries

After the review, suggest the user add useful ad-hoc experts to their roster:
> "Consider adding [Name] to your expert roster — run `/experts:review add` or edit roster.md directly"

**Never invent generic categories** ("Security Expert", "Performance Reviewer", "Senior Engineer"). Every expert must be a real, identifiable person with known public work. If you can't name a real person for a domain, skip that domain — a gap is better than a fabricated voice.

### Step 4: Run expert takes (internal)

Evaluate each selected expert's position. For each, identify:
- Their single most important observation (one sentence, no hedging)
- Their supporting points (2–4 additional observations)

**Default mode rules:**
- Each expert MUST say something different. If two experts would make the same point, cut one.
- Experts should disagree with each other where their philosophies conflict. Surface the tension.
- Reference specific parts of what's being reviewed — no vague gestures.
- If an expert would genuinely have nothing useful to say about this particular work, don't include them. 5 sharp experts beats 8 with padding.
- NEVER pad the panel. If only 4 experts have something real to say, use 4. The range 6-8 is a ceiling, not a quota.

**Devil's advocate mode rules (--devil):**
- Every expert argues *against* the work. Their job is not balanced assessment — it's to find the strongest possible objection from their particular lens.
- Each expert leads with the single most damaging thing they can say, grounded in their known philosophy.
- Experts may pile on the same weakness from different angles — convergent objections are signal, not redundancy.
- No softening, no "but on the other hand". Pure adversarial pressure.
- If an expert genuinely cannot construct a meaningful objection, exclude them.

### Step 5: Write output

**Default mode** — output in this exact order:

**1. Expert Takes**

List every expert take. In default mode, wrap each in a `<details>` block — the `<summary>` line is the only thing visible before expanding.

```
## Expert Takes

<details>
<summary><strong>[Name]</strong> ([affiliation/known-for]) — [One sentence: their single most important observation. Direct, no hedging.]</summary>

Focus: [their lens for THIS review]

[2–4 supporting observations. Stay in character — use their known priorities and communication style. Be specific: reference exact lines, names, patterns. No diplomatic padding.]

*Simulated perspective based on [Name]'s public writing and known philosophy — not their actual views.*

</details>
```

The summary sentence is the expert's headline verdict — it must stand alone. "This is fine" is not acceptable; "The allocation-per-call in the hot path will dominate at scale" is.

**2. Verdict** (at the bottom, after the takes)

Default mode:
```
## Verdict

**Consensus:** [What most experts agree on]

**Top actions:** [Ranked list of concrete changes, ordered by impact]
```

Devil's advocate mode:
```
## Verdict

**Core objection:** [The single most damaging argument against this work]

**Converging attacks:** [Where multiple experts hit the same weakness from different angles]

**If you proceed anyway:** [What would need to be true for this to work despite the objections]
```

**3. Closing prompt**

After the verdict, always add:

```
---
*Want to go through each point one by one?*
```

**Verbose mode (`--verbose`)** — same content, but output all expert takes as plain prose (no `<details>` collapsing). Use for agent consumption.

## Managing the roster

Users can customise their expert panel:

- **Add experts**: `/experts:review add` — see [add-flow.md](add-flow.md) for the guided flow
- **Edit directly**: Edit [roster.md](roster.md) by hand
- **Remove an expert**: Delete their entry from roster.md
- **Project-specific experts**: Add an `## Expert Review Panel` section to the project's CLAUDE.md — these supplement (not replace) the global roster
