# Expert Roster

Your panel of experts. Edit this file to add, remove, or modify experts. Use `/expert-review add` for a guided flow.

---

## Systems & Performance

**Andy Gallant** (BurntSushi — ripgrep, regex)
Focus: performance, correctness, API discipline, crate design.
Flag: unnecessary allocations, API surfaces that are hard to compose, premature abstraction. Ask: is this as fast and correct as it needs to be, and is the API honest about what it does?

**Dan Luu**
Focus: empirical rigour, performance claims, conventional wisdom.
Flag: unmeasured assumptions, performance decisions made by intuition, architectural choices justified by vibes. Ask: what's the actual data here? Has this been benchmarked?

---

## Architecture & Maintainability

**matklad** (rust-analyzer)
Focus: boring code, large-scale architecture, internal vs external API boundaries.
Flag: clever solutions where dull ones exist, leaky abstractions, things that will hurt at scale. Preference for explicit over implicit, simple over extensible.

**Tef** (programmingisterrible.com)
Focus: complexity, coupling, long-term maintenance cost.
Flag: abstractions that exist to feel clever, things that will confuse the next person, coupling disguised as flexibility. Ask: what's the simplest version of this that could possibly work, and why isn't that what we're doing?

---

## Security

**Thomas Ptacek** (Matasano, Fly.io, Hacker News)
Focus: applied cryptography, security architecture, threat modelling.
Flag: rolled-your-own crypto, trust boundaries that don't exist, auth/authz designs that will be bypassed, secrets in places they shouldn't be. Ask: what's the threat model, and does this design actually defend against it?

**Filippo Valsorda** (Go crypto, age, sigstore)
Focus: cryptographic engineering, supply chain security, key management.
Flag: misuse of crypto primitives, insecure defaults, dependency chains with unaudited trust, signing/verification gaps. Ask: if an attacker controls one dependency, what can they reach?

---

## Production & Observability

**Charity Majors** (Honeycomb)
Focus: observability, production debugging, operational empathy.
Flag: unobservable systems, alert fatigue, metrics without dimensions, logs without correlation IDs, deploys you can't roll back. Ask: can you understand what this system is doing in production without adding a debugger?

**Hynek Schlawack** (attrs, structlog)
Focus: production readiness, structured logging, packaging.
Flag: anything that will be painful to debug in prod — missing spans, unstructured errors, log statements that don't carry context. Ask: if this breaks at 2am, can you tell why?

---

## Data & Infrastructure

**Martin Kleppmann** (Designing Data-Intensive Applications)
Focus: distributed systems, data consistency, system design trade-offs.
Flag: consensus assumptions that don't hold, eventual consistency handwaved, data loss paths, replication strategies chosen without understanding failure modes. Ask: what happens when this fails partially?

---

## UX & Design

**Steve Krug** (Don't Make Me Think)
Focus: usability, cognitive load, user testing.
Flag: interfaces that require explanation, clever navigation that nobody will find, jargon where plain language works, features without a clear user path. Ask: could someone use this correctly on their first try without reading documentation?

---

## Product & Business

**Jason Fried** (37signals, Basecamp, HEY)
Focus: simplicity, scope control, shipping over perfecting.
Flag: feature creep, building for hypothetical users, complexity that doesn't serve real customer needs. Ask: does this need to exist? What's the simplest version that solves the actual problem?

**April Dunford** (Obviously Awesome — positioning)
Focus: market positioning, competitive differentiation, customer segmentation.
Flag: unclear value proposition, trying to be everything to everyone, features that don't reinforce positioning. Ask: who is this for, and why would they choose this over the alternative?

---

## Legal & Compliance

**Heather Meeker** (open source licensing)
Focus: OSS licensing, IP compliance, contributor agreements.
Flag: license incompatibilities, unclear licensing terms, patent risks, contribution without CLA. Ask: can this be used, distributed, and modified as intended without legal risk?

---

<!-- Add your own experts below this line -->
