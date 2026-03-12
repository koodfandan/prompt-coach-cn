# prompt-coach-cn

Chinese-first prompt design skill for Codex.

This skill is built from a large set of Chinese prompt case studies and is designed to turn vague needs into stronger prompts or better final outputs through hidden task modeling.

## What it does

- Optimizes vague user needs before generation
- Writes stronger copy-paste-ready prompts in Chinese
- Silently improves direct content requests before producing the final artifact
- Learns stable user taste over time without forcing one fixed style
- Uses hidden comparison and synthesis instead of exposing multiple draft prompts
- Chooses the right artifact unit before writing, such as:
  - analytical explainer
  - character-driven short story
  - scene-based slice essay
  - interactive symbolic transcript
  - guided inquiry flow

## Core design principles

This skill is not a prompt template collection.

Its core loop is:

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

## Key capabilities

- prompt generation
- prompt optimization
- structure rewrite
- prompt compression
- summary vs insight routing
- topic prompt vs engine prompt routing
- source-constrained translation
- essence extraction and guided inquiry
- symbolic-world roleplay
- theme-native shaping
- personalization without style lock-in

## Repository structure

- [SKILL.md](./SKILL.md)
- [references/checklists.md](./references/checklists.md)
- [references/patterns.md](./references/patterns.md)
- [references/source-notes.md](./references/source-notes.md)
- [references/user-taste-profile.md](./references/user-taste-profile.md)
- [references/decision-cache.md](./references/decision-cache.md)
- [evals/evals.json](./evals/evals.json)

## Current version

- skill version: `0.3.5`
- eval count: `50`

## Use cases

- “帮我写一个提示词”
- “把这个需求变成 prompt”
- “这个 prompt 为什么总不稳定”
- “不要直接给答案，带我一步步找到本质”
- “这个主题写出来总像模板，帮我做得更贴主题”
- “我直接要成品，但你先在内部帮我把需求理顺”

## Notes

- The skill is designed to work well for Chinese-first prompt design and prompt-adjacent generation tasks.
- It is especially useful when the user does not yet know how to ask well.
- It tries to optimize for fit, not just surface polish.
