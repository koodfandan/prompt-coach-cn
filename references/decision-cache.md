# Decision Cache

This file stores reusable routing and comparison decisions that can speed up future requests.
It is not a template library and not a repository of old outputs.

Rules:

1. Current-turn instructions override this cache.
2. Reuse only the smallest useful decision.
3. Cache decisions, not full old prompts.
4. If reuse increases template feel or stale repetition, do not reuse it.

## Mode defaults

- structure_rewrite_or_prompt_compression: Lite by default
- single_topic_creative_prompt_design: Standard by default
- strongest_or_non_generic_request: Deep candidate
- symbolic_world_entry_or_guided_inquiry: Standard or Deep depending on ambiguity

## Reusable winning moves

- Choose the artifact unit early for creative tasks; this usually saves more time than wording polish later.
- For high-concept story prompts, compare theme handle and artifact-unit framing before comparing whole prompt drafts.
- For explanation-heavy topics, cleaner artifact-unit choice often wins over broader analysis.
- Theme-handle extraction is usually worth keeping for this user; skipping it often causes generic drift.

## Local comparison defaults

Prefer local comparison first.

Typical comparison order:

1. theme handle
2. artifact-unit framing
3. constraint block
4. output structure
5. opening task sentence

Escalate to whole-draft comparison only when:

- multiple fundamentally different architectures remain plausible
- artifact unit is still uncertain
- local recombination cannot resolve the main quality risk

## Early-stop heuristics

Stop when the current assembly is already strong on:

- task fit
- artifact fit
- generic-risk control
- enough theme specificity

Do not keep searching just because Deep mode is available.

## Common failure priorities

Check these early in this order unless the current request clearly changes the risk:

1. template rigidity
2. wrong artifact unit
3. first-draft lock-in
4. taste-memory drift

## User-specific speed hints

- This user often values anti-template behavior, so theme-handle extraction is rarely wasted effort.
- This user usually prefers hidden synthesis over visible multiple options.
- Deep mode is justified only when ambiguity, generic-risk, or explicit refinement demand is high.
- Repeated whole-draft generation is usually less efficient than component-level comparison for this user's creative prompt requests.

## Reuse boundaries

Do not reuse old decisions when:

- the user explicitly asks for a different depth
- the task family has changed
- the artifact unit has changed
- the user wants a plainer or more direct result than usual
- the reused choice would visibly force the same shell again
