# prompt-coach-cn

A Chinese-first prompt design skill for Codex.

[中文 README](./README.md)

This repository is not a prompt-template collection.  
It is a prompt modeling layer that turns vague user needs into better prompts or better final artifacts through hidden task design.

---

## What problem it solves

Many prompts fail not because the wording is weak, but because the underlying task was modeled incorrectly.

Typical failure points:

- the task family is misclassified
- the user's input role is misunderstood
- the wrong objective gets optimized
- generation starts before the intermediate structure is clear
- the final artifact unit is wrong even when the topic is correct

`prompt-coach-cn` is designed to solve those deeper problems first.

---

## What makes it different

This skill does not simply see a request and output the first usable prompt.

Instead, it runs a hidden modeling loop:

1. classify the task
2. classify the input
3. choose the objective
4. extract the intermediate representation
5. choose the artifact unit and final structure

Then it improves quality through:

- complexity gate
- taste memory
- decision cache
- hidden local candidate synthesis
- early stop

In short:

> It behaves more like a prompt modeler than a prompt template writer.

---

## Current capabilities

### Prompt work

- prompt generation
- prompt optimization
- prompt compression
- prompt restructuring
- stable structured-output design
- Chinese-first instruction rewriting

### Routing work

- `summary` vs `insight`
- `topic prompt` vs `engine prompt`
- `source-constrained translation` vs `theme expansion`
- `guided inquiry` vs `direct explanation`
- `symbolic-world entry` vs `symbolic-world analysis`

### Artifact-unit selection

- analytical explainer
- character-driven short story
- scene-based slice essay
- case-driven article
- guided inquiry flow
- interactive symbolic transcript
- embodied mental-world simulation
- reusable generator / engine

### Advanced behavior

- theme-native shaping instead of visible template repetition
- hidden multi-candidate comparison with final single-output delivery
- user taste alignment without style lock-in
- cached winning decisions for faster routing
- cheaper execution for simpler requests

---

## When it is useful

When the user does not know how to ask well:

- “Help me write a prompt”
- “Turn this need into a prompt”
- “Why is this prompt unstable?”
- “Don’t answer directly; help me discover the essence step by step”
- “This topic keeps sounding template-bound; make it more native to the theme”

When the user asks for final content, but hidden prompt modeling is still needed first:

- “Write a story about visible emotional colors”
- “Write an article about seeing the essence of things through AI”
- “Design a roleplay that lets me enter a symbolic inner world”

---

## Design principles

This skill was not built by copying a few prompts.

It was distilled from a large body of Chinese prompt case studies and refined around first-principles prompt engineering:

- understand why a task needs staging
- distinguish evidence from inspiration
- distinguish a one-off topic prompt from an engine
- distinguish explanation from discovery
- distinguish describing a symbolic world from entering one
- avoid first-draft lock-in

The core belief is:

> Strong prompts come from correct modeling, not decorative complexity.

---

## Current version

- skill version: `0.3.5`
- eval count: `50`

This version especially strengthens:

- complexity gate
- decision cache
- hidden local candidate synthesis
- compact taste memory
- theme-native shaping

---

## Repository structure

- [SKILL.md](./SKILL.md)
- [CHANGELOG.md](./CHANGELOG.md)
- [ROADMAP.md](./ROADMAP.md)
- [evals/evals.json](./evals/evals.json)
- [references/checklists.md](./references/checklists.md)
- [references/decision-cache.md](./references/decision-cache.md)
- [references/patterns.md](./references/patterns.md)
- [references/source-notes.md](./references/source-notes.md)
- [references/user-taste-profile.md](./references/user-taste-profile.md)

---

## How to use it

Two common ways:

### 1. Explicit prompt requests

- “Help me write a prompt”
- “Optimize this prompt”
- “Turn this need into a stable prompt”

### 2. Direct artifact requests

The user does not need to know prompt engineering first.

They can simply say:

- “Write a story”
- “Write an article”
- “Design a roleplay”
- “Help me build a world”

The skill can optimize the hidden task structure first, then deliver the final result.

---

## Project direction

The long-term goal is not to become a bigger prompt library.

It is to become:

- more accurate at identifying task essence
- more efficient at hidden optimization
- more aligned with the current user over time
- faster on easy tasks and deeper on high-value ones

If you want a skill that increasingly feels like “your version” of prompt design, this repository is moving in that direction.
