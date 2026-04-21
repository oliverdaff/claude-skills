# File Formats

## idea.md

```yaml
---
status: exploring  # exploring | testing | paused | killed | committed
created: YYYY-MM-DD
---
```

Sections: Problem, User, Evidence, Hypothesis, Signals, Decision.

## experiment (e.g. `experiments/001-name.md`)

```yaml
---
status: planned  # planned | running | complete
type: behaviour  # does-anyone-care | will-they-engage | will-they-commit | fake-product | concierge | behaviour
effort: low      # low | medium | high
signal: ~        # ~ | weak | moderate | strong
created: YYYY-MM-DD
---
```

Sections: Design, Results, What Now.
