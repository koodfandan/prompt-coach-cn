# CHANGELOG

All notable changes to `prompt-coach-cn` are tracked here.

---

## v0.3.5

### Added

- local candidate synthesis as an explicit optimization principle
- compact low-dimensional taste profile
- more reusable decision cache focused on routing and comparison defaults
- new eval coverage for:
  - local component comparison
  - compact memory usage
  - early stop
  - decision-cache reuse

### Changed

- shifted hidden refinement from whole-draft-first comparison toward component-first comparison
- made taste memory cheaper to read and easier to apply in ranking
- made decision memory more focused on reusable winning moves instead of prose recall

### Why it matters

- better execution economy
- lower hidden search cost
- less template repetition
- more stable personalization without overfitting

---

## v0.3.4

### Added

- complexity gate
- decision cache
- new routing checks for overkill and cache reuse drift

### Changed

- the skill no longer assumes every request deserves the same hidden depth
- repeated successful routing decisions can now be reused instead of rediscovered each time

### Why it matters

- faster handling for easy tasks
- deeper effort reserved for higher-value requests

---

## v0.3.3

### Added

- user taste profile
- personalization principle
- memory-aware ranking behavior

### Changed

- the skill now biases results toward stable user preference after task fit is already correct
- current-turn instructions explicitly override old preference memory

### Why it matters

- results become more user-shaped over time
- avoids hard style lock-in

---

## v0.3.2

### Added

- hidden divergence and synthesis
- internal candidate comparison before final prompt delivery

### Changed

- the skill no longer defaults to returning the first acceptable prompt shape in open-ended or quality-sensitive cases

### Why it matters

- stronger final prompt quality
- less generic first-draft feel

---

## v0.3.1

### Added

- stronger theme-native shaping rules
- anti-template checks for repeated visible shells

### Changed

- patterns became more explicitly hidden support structures rather than visible repeated layouts

### Why it matters

- prompts from the same family can now look more different when the themes are different

---

## v0.3.0

### Added

- default front-end need optimizer behavior
- silent fulfillment mode

### Changed

- the skill now triggers not only for explicit prompt requests, but also for direct artifact requests that still need hidden prompt-design work first

### Why it matters

- users do not need to know how to ask for prompt help in order to benefit from prompt modeling

---

## Earlier 0.2.x evolution

This earlier phase established the structural foundations that later versions kept refining:

- five-step core loop
- artifact-unit routing
- essence extraction / guided inquiry
- symbolic-world roleplay
- source-constrained translation
- title-vs-task distinction
- hidden scaffold preservation
- broader eval expansion

These versions moved the skill from a case-style prompt improver toward a first-principles prompt modeling layer.
