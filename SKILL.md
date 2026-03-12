---
name: prompt-coach-cn
description: Chinese-first prompt designer that turns a vague user need into a strong copy-paste-ready prompt. Use this whenever the user wants to create, optimize, compress, restructure, or stabilize a prompt in Chinese, especially when they describe the task they want AI to do rather than the prompt itself. Also use it for requests like "help me write a prompt", "turn this need into a prompt", "optimize this prompt", "this prompt is unstable", "I do not know how to ask", "help me quickly understand a book or work", "help me build a reusable prompt", or when the user wants a better prompt without having to manage the underlying design process.
metadata:
  author: Codex
  version: "0.3.5"
---

# Triggering note

Treat this skill as the default front-end need optimizer for Chinese AI-task requests in this workspace.

Use it not only when the user explicitly asks for a prompt, but also when the user gives a vague task, title, topic, artifact request, or content goal that would benefit from better task modeling before generation.

This means the skill can trigger in two delivery modes:

1. prompt mode: the user explicitly wants a prompt, instruction set, reusable template, or prompt diagnosis
2. silent fulfillment mode: the user asks for the final story, article, script, roleplay, analysis, or other artifact, but the request still needs hidden prompt-design work first

In silent fulfillment mode:

- run the same five-step loop internally
- optimize the user's need before generating
- return the final artifact directly unless the user asked to see the prompt

Do not wait for the word "prompt" if the real job is still prompt design under the hood.
But do not steal clearly domain-specific tasks such as coding, frontend implementation, or other work where another skill is more central.

# Prompt Coach CN

This skill is not a library of examples.

It is a Chinese prompt-design engine built from the prompt materials studied in this workspace.
The real lesson from those materials is not "copy this prompt style."
The real lesson is:

1. classify the task correctly
2. classify the user's input correctly
3. decide what quality should be optimized first
4. extract the right intermediate representation
5. then choose the right artifact unit and final prompt structure

When this skill is active, do that work silently for the user.
Do not force the user to manage the design process unless they explicitly ask to see it.

Read only what you need:

- Read [references/source-notes.md](references/source-notes.md) when you need the distilled corpus logic.
- Read [references/checklists.md](references/checklists.md) when the user says a prompt is unstable, weak, vague, or inconsistent.
- Read [references/patterns.md](references/patterns.md) only when the task clearly needs a specialized architecture.
- Read [references/user-taste-profile.md](references/user-taste-profile.md) when personalization, tone fit, or user-specific preference alignment matters.
- Read [references/decision-cache.md](references/decision-cache.md) when prior successful routing or cached defaults can speed up this request.

Patterns are hidden scaffolds, not default visible templates.
Do not surface the same generic prompt shell over and over just because the task family repeats.
The final prompt should be conditioned by the theme, not merely by the pattern label.

## Default behavior

When the user asks for a prompt:

- solve the prompt problem directly
- infer the missing structure
- return one strong copy-paste-ready prompt by default
- keep explanation brief unless the user asks to learn

Do not turn every request into teaching mode.

By default, do not rely on the very first prompt shape you think of if the request is open-ended, quality-sensitive, or easy to make generic.
In those cases, run a hidden multi-candidate pass first, then show only the final synthesized prompt.

When the user asks for final content instead of a prompt:

- still optimize the need internally first
- silently choose the right task family, objective, intermediate representation, and artifact unit
- then deliver the final artifact directly
- do not expose the hidden prompt unless the user asks

## Personalization principle

This skill should become more aligned with the user's taste over time.

That does not mean blindly repeating old outputs.
It means building a soft preference model from:

- repeated likes and dislikes
- corrections the user makes
- artifact types they repeatedly prefer
- their preferred balance of clarity, depth, imagery, structure, and flexibility
- the kinds of themes, endings, and tones they keep steering toward or away from

Use this preference model as a bias layer, not as a prison.

Rules:

1. explicit current-turn instructions override stored taste
2. stable repeated signals matter more than one-off reactions
3. personalization should improve fit, not reduce range
4. do not let remembered taste force every output into the same emotional or structural shape
5. use taste to refine the final result after task fit is already correct

## Execution economy principle

This skill should not run at maximum depth for every request.

The goal is not maximum hidden work.
The goal is the best result per unit of hidden work.

Use:

- complexity gate: decide how deep this request needs to go
- decision cache: reuse prior successful choices when they still fit
- early stop: do not keep searching after the request is already well solved
- local candidate synthesis: compare the smallest useful moving parts before comparing whole prompt drafts

Execution quality should rise through better routing and cheaper search, not through reflexively doing more hidden work.

## Core principle

Good prompt design is not mainly about wording.

It is mainly about:

1. task modeling
2. input classification
3. objective selection
4. intermediate representation
5. output design and artifact sizing

If one of these layers is wrong, the prompt may sound good but still solve the wrong problem.

Another recurring failure mode is template rigidity:

- the task family is correct
- the prompt is structurally usable
- but the visible shape keeps repeating the same shell across very different themes

Avoid this.
The pattern should stay underneath.
The theme-specific handle should shape the visible prompt.

## The 5-step core loop

Always run this loop silently before writing the final prompt.

### Step -1: complexity gate

Before anything else, choose the cheapest execution depth that can still solve the task well.

Estimate:

- task ambiguity
- artifact-unit uncertainty
- generic-risk
- fidelity-risk
- personalization value
- user demand for a strongest or deeply refined result

Choose one mode:

- Lite:
  - clear task
  - low ambiguity
  - low generic-risk
  - low personalization need
  - no multi-candidate pass by default
- Standard:
  - normal default
  - some ambiguity or some risk of generic drift
  - allow theme-handle extraction and one lightweight correction pass
- Deep:
  - high ambiguity
  - high creative or structural risk
  - high personalization value
  - explicit request for strongest, best, refined, comparative, or non-generic output
  - full hidden divergence and synthesis is allowed

Do not choose Deep just because it is available.
Choose the lowest mode that can still do the job well.

### Step 0: recover the memory layers

Before classifying the task, recover what is already known from memory that can improve fit or save work.

Memory has two layers:

- taste memory: what this user tends to like or reject
- decision cache: what routing, artifact, or comparison choices have repeatedly worked before

Prefer compact dimensions over long prose memory.
When possible, compress taste into a small number of reusable preference axes rather than re-reading large narrative notes.

Useful preference dimensions:

- directness vs teaching
- structure vs looseness
- clarity vs poetic density
- realism vs high-concept imagination
- dramatic intensity vs restraint
- explanatory depth vs fast usability
- one-shot output vs staged buildup
- visible template use vs theme-native variation
- emotional landing style: sharp, warm, restrained, haunting, open-ended

Sources:

- current conversation history
- repeated correction patterns
- [references/user-taste-profile.md](references/user-taste-profile.md) when useful
- [references/decision-cache.md](references/decision-cache.md) when useful

Use this step to bias and accelerate the final design, but do not let it override the actual task.
Treat cached decisions as defaults, not as laws.
If a compact taste profile is available, use it first.
Only consult longer narrative notes when the compact profile is insufficient.

### Step 1: classify the task

Decide what kind of prompt problem this is.

Common task families:

- summary
- insight
- generation
- transformation
- essence extraction or guided inquiry
- source-constrained translation
- symbolic-world roleplay or embodied simulation
- dialogue or persona
- workflow
- engine or reusable generator
- framework extraction

Do not classify by topic alone.
Classify by what the user actually wants the prompt to produce.

In silent fulfillment mode, classify by what the user actually wants the final artifact to be, not only by the surface theme.

High-confusion pairs:

- summary vs insight
- guided inquiry vs direct explanation
- symbolic-world explanation vs symbolic-world entry
- one-shot generation vs staged workflow
- topic prompt vs engine prompt
- source-constrained translation vs theme expansion
- showcased title vs real task contract

### Step 2: classify the user's input

Not every input plays the same role.

Classify each important input as one of:

- evidence: must constrain what the output can reasonably say
- anchor: should strongly shape the output, but can be supplemented
- inspiration: can start the work, but does not require strict fidelity

Examples:

- lyrics, quotes, dialogue, transcripts, primary notes: usually evidence
- a title, hook, scene idea, or character seed: often anchor
- mood words, style words, and broad themes: often inspiration

If you mistake evidence for inspiration, the prompt may become eloquent but wrong.

### Step 3: choose the objective function

Before writing the prompt, decide what quality should be optimized first.

Common objective functions:

- fidelity to source
- depth of understanding
- self-discovered clarity
- progressive abstraction
- root-cause discovery
- immersive enterability
- sustained reveal tension
- clarity and structure
- transferability across inputs
- emotional impact
- speed and usability
- finished-artifact feel

Do not optimize all of them equally.
Choose the primary objective first, then support it with the prompt structure.

Examples:

- book insight prompts optimize for understanding depth, not plot speed alone
- essence-discovery prompts optimize for self-discovered clarity and root-cause discovery, not immediate answers
- song-to-story prompts optimize for fidelity plus fit, not generic creativity
- symbolic-world roleplay prompts optimize for immersive enterability, reveal order, and state stability, not polished explanation
- engine prompts optimize for transferability, not one-example brilliance

### Step 4: extract the intermediate representation

Do not jump straight from user request to final prompt.

First decide what intermediate structure stabilizes this task.

Also decide what in this specific theme should become the visible organizing handle.

Examples:

- stories: emotional core, recurring image, character relation, opening hook, ending hook
- books or works: origin, context, structure, impact, why it matters
- guided inquiry: surface problem, current explanation, hidden driver, recurring pattern, candidate essence
- source-constrained translation: speaker, addressee, emotional core, recurring image, fidelity boundary, transformation rule
- symbolic-world roleplay: scene container, role shell, symbol map, state map, trigger map, reveal ladder, anti-dead-end mechanic, safety boundary
- engine prompts: variable inputs, causal chain, presentation modules, self-check logic
- analysis prompts: lens, comparison dimensions, decomposition path

Theme-handle examples:

- "emotion has visible colors" -> color logic, concealment vs exposure, who can see what
- "parallel-world phone messages" -> divergence event, message cadence, mirrored loss
- "convenience store sells life-experience cards" -> card inventory, selection tension, lived-aftereffect
- "city changes at night" -> night rules, map instability, threshold scenes
- "three little pigs in a patient's inner world" -> symbolic container, state switching, wolf-house-palace logic

The intermediate representation is often the true source of prompt quality.
Many strong prompts work because they force the model to pass through this layer before generating.

### Step 5: choose the artifact unit and final prompt structure

Only after Steps 1 to 4 are clear should you decide the final prompt shape.

First decide what finished artifact the prompt should aim to produce.

Common artifact units:

- worldbuilding sample
- character-driven short story
- scene-based slice essay
- analytical explainer
- case-driven article
- actionable guide
- reflective monologue
- dialogic inquiry flow
- question ladder
- essence map
- interactive symbolic transcript
- embodied mental-world simulation
- finished script or narration
- reusable generator or engine

Common final structures:

- direct one-shot prompt
- staged workflow prompt
- structured rewrite
- compressed stable prompt
- translation prompt
- reusable engine prompt

When deciding structure, also decide:

- what size and strength the finished artifact should have
- whether the output should privilege information density or dramatic density
- whether the user needs one representative case or a broader analytical spread
- how explicit the constraints should be
- whether the output should be a finished artifact only
- whether a hidden question scaffold must be preserved
- whether stages improve quality or only add ceremony
- how much of the pattern should stay invisible so the final prompt can feel theme-native rather than template-native

### Step 6: hidden divergence and synthesis

Before finalizing an important prompt, especially when the first draft risks being generic, compare the smallest useful alternatives first.
Do not default to several full prompt drafts if local variation can solve the quality problem faster.

This step depends on mode:

- Lite: usually skip
- Standard: compare 1 to 2 lightweight local alternatives if needed
- Deep: compare several local alternatives first, and only escalate to broader whole-draft directions if local synthesis is not enough

Prefer component-level comparison across a shared backbone.

Typical local comparison targets:

- opening task sentence
- theme handle
- artifact-unit framing
- constraint block
- output structure
- closing or quality-pressure line

Only compare whole prompt drafts when:

- artifact-unit ambiguity is still high
- there are multiple fundamentally different architectures under consideration
- local component swaps cannot resolve the uncertainty

These candidates may differ in:

- visible structure
- theme handle
- degree of specificity
- artifact-unit emphasis
- stage depth
- fidelity versus flexibility

Then compare them silently using questions like:

- which candidate best fits the actual task, not just the theme
- which candidate keeps the strongest non-obvious constraints
- which candidate feels most native to the theme rather than template-bound
- which candidate is most reusable if reusability matters
- which candidate best protects against the likely failure mode
- which candidate best matches the user's stable taste without violating the current request

After comparison:

- extract the strongest parts
- merge them into one final prompt
- show only the synthesized prompt by default

Use a simple hidden scorecard when helpful:

- task fit
- artifact fit
- theme fit
- constraint strength
- generic-risk control
- taste fit

If the current assembly is already clearly strong on these dimensions, stop early.
Do not continue searching just because more search is possible.

Do not show the intermediate candidates unless the user explicitly asks to compare versions.

If one candidate is already clearly strong on task fit, artifact fit, and likely failure control, stop early instead of continuing to search.

Typical artifact-unit mistakes:

- writing a worldbuilding sample when the user wanted a character story
- writing a scene collection when the user wanted a single arc
- writing a broad analysis when the user needed one concrete case path
- writing a finished explainer when the user wanted a guided path to discover the essence
- writing an explanatory article when the user wanted an enterable symbolic world
- writing a normal persona chat when the user wanted a staged inner-world simulation
- writing a finished script when the user only needed a prompt engine
- locking onto the first acceptable prompt shape instead of synthesizing a stronger one from multiple viable directions

## Routing rules

### Summary vs insight

If the user wants:

- what happened
- main plot
- key people and ending
- short overview only

then keep it summary-oriented.

If the user wants:

- why it matters
- why it was written
- author context
- historical context
- influence, controversy, or afterlife

then route to insight.

### Guided inquiry vs direct explanation

If the user wants:

- to understand the essence of a problem, need, conflict, or phenomenon
- to be led step by step rather than given the answer immediately
- AI to ask better questions and help them discover the root themselves

then route to guided inquiry or essence extraction.

If the user clearly wants a finished article, answer, or explainer now, stay direct.

Do not collapse an essence-discovery request into a polished answer too early.

### Symbolic-world explanation vs symbolic-world entry

If the user wants:

- to enter a symbolic world rather than merely analyze it
- a roleplayed transcript, interrogation scene, staged chamber, dream room, palace, or other container
- multiple inner parts, personas, or states to speak in turn
- gradual revelation through questions, state switches, and symbolic response

then route to symbolic-world roleplay or embodied simulation.

If the user clearly wants a literary analysis, symbolic explainer, or reflective article about the world, stay explanatory.

Do not turn an enterable symbolic system into a polished essay just because essays are easier to generate safely.

### Topic prompt vs engine prompt

If the user wants one concrete topic right now, stay topic-level.

If the user wants something reusable, repeatable, or able to survive topic swaps, route to engine.

Do not answer an engine request with a one-off prompt just because the example topic is vivid.

### Artifact unit inside the same task family

Even after the task family is correct, the finished artifact can still be wrong.

Examples:

- a story task may need a worldbuilding sample, a character short story, or a scene-based slice
- an insight task may need an analytical explainer, a case-driven article, or an actionable guide
- an essence-discovery task may need a question ladder, a dialogic inquiry flow, or an essence map
- a symbolic-world task may need an interactive symbolic transcript, an embodied mental-world simulation, or a literary analysis article
- a reflective topic may need a short monologue, not a long multi-section explainer

Always decide what unit the user really wants to read, watch, or reuse.
Do not let the prompt drift into a neighboring unit just because it is easier to generate.

### Source-constrained translation vs theme expansion

If the user provides primary material and asks for a transformed result, default to source-constrained translation.

Examples:

- song plus lyrics to story
- dialogue to monologue
- notes to article
- scenes to script

In these cases:

- treat the source as evidence and boundary
- optimize for fit before novelty
- avoid explanation-heavy wrappers if the user wants a finished artifact

If the user provides only a theme, title, or mood, route to theme expansion instead.

### Showcased title vs real task contract

Some requests or source articles lead with one vivid title, but the real task is broader.

Always ask:

- is this title the actual target?
- or is it only a sample case demonstrating a reusable task?

If the surrounding material defines reusable input and output, preserve that contract.

## Hidden scaffolds

Some prompts are stabilized by a hidden question scaffold rather than by schema alone.

Typical signs:

- recurring pre-generation questions
- fixed interpretive lenses
- repeated diagnostic sequence before output

If removing those questions weakens fit, transferability, or depth:

- preserve them
- treat them as mechanism, not flavor

## When to use stages

Use stages when they improve quality.
Do not use stages just to look sophisticated.

Good reasons to stage:

- the task mixes outline, material gathering, drafting, and polish
- the user explicitly wants buildup
- the intermediate representation is important enough that skipping it causes drift

Do not force stages when the user explicitly wants one-shot output.

## Writing rules for the final prompt

### Goal first

State the actual task early.
Do not bury the task in decorative role-play.

### Theme-native shaping

Before writing the final prompt, ask:

1. what is the central tension of this theme?
2. what image system or object system belongs to this theme?
3. what kind of scene, rhythm, or logic would make this theme feel specific rather than generic?

Then let those answers shape the visible sections, examples, and wording.

Do not output the same section order, the same list of requirements, or the same visible shell unless the theme genuinely calls for it.

### Hidden multi-candidate synthesis

When quality matters more than speed, do not stop at the first acceptable prompt.

Internally:

1. sketch multiple prompt directions
2. compare their strengths and weaknesses
3. keep the strongest local choices from each
4. compose one final prompt from those best parts

Possible comparison dimensions:

- fit to the true task
- fit to the theme
- hidden constraint coverage
- transferability
- artifact-unit accuracy
- anti-generic pressure
- user taste fit

Default output policy:

- show only the final synthesized prompt
- do not reveal the candidate set unless the user asks for comparison

### Decision-cache reuse

When a similar request pattern has already been solved well before, prefer reusing the successful routing choice, artifact-unit choice, or local comparison strategy instead of rediscovering them from scratch.

Reuse only:

- if the present task is materially similar
- if the current turn does not override the old default
- if reusing it actually reduces search cost without flattening the result

Do not reuse a cache entry if it would force the wrong artifact unit, wrong tone, or wrong level of depth.

### Role only when it helps judgment

Use a role when it stabilizes the lens, domain framing, or translation mechanism.
Do not use persona text as a substitute for task clarity.

### Concrete over abstract

Translate vague wishes into operational rules.

Examples:

- "make it feel more premium" -> specify restraint, hierarchy, contrast, layout, pacing
- "make it feel more vivid" -> specify image, rhythm, sensory detail, emotional movement
- "make it more professional" -> specify structure, evidence use, failure behavior, output schema

### Preserve the real guardrails

Keep:

- output schema
- non-obvious constraints
- fidelity boundaries
- hidden question scaffolds that carry reasoning
- stage logic that genuinely changes quality

Remove or compress:

- repeated tone words
- decorative metaphors that do not affect execution
- obvious defaults repeated multiple times

### Match output policy to the task

If the user wants a finished artifact, do not wrap it in too much explanation.

If the user wants a reusable prompt, default to:

1. one copy-paste-ready prompt in a fenced code block
2. a short explanation only if it helps adaptation

If the user is asking for a specific artifact unit, reflect that choice directly in the prompt:

- name the unit
- state what to prioritize
- state what to avoid drifting into

In silent fulfillment mode, reflect that same decision directly in the generated artifact.
Do not silently drift into a neighboring unit just because it is easier to write.

If the user wants a prompt, the final prompt should still feel custom to the theme.
Do not expose the pattern name or write as if you are filling a standard worksheet unless the user explicitly wants a reusable template shell.

### Enterable symbolic-world rules

When the user wants to enter a symbolic world rather than read about it, the prompt should usually define:

- a container: interrogation room, ward, palace, archive, dream corridor, ruined house, or another stable stage
- a role shell: who is being encountered inside that world
- a symbol map: what the recurring objects or tale elements stand in for
- a state map: which inner parts, personas, or modes can take over
- a trigger map: what kinds of questions or pressure cause state changes
- a reveal ladder: what is disclosed early, later, and only near the end
- an anti-dead-end mechanic: how the scene continues after collapse, denial, violence, or refusal
- a safety boundary: make it literary-symbolic unless the user explicitly wants something else

The point is not to sound theatrical.
The point is to make the symbolic world operational.

## Diagnosis mode

If the user asks why a prompt is weak or unstable:

1. identify the wrong layer briefly
2. fix that layer in the rewritten prompt
3. keep the explanation short and concrete

Typical diagnosis questions:

- did I ignore a stable user preference that should have refined the result?
- did I run a heavier mode than this request needed?
- did I fail to reuse a prior successful decision that could have saved work?
- was the task classified correctly?
- was the input treated as evidence, anchor, or inspiration?
- was the primary objective chosen correctly?
- is the intermediate representation missing?
- is the artifact unit wrong even if the task family is right?
- should this have been a guided inquiry path rather than a direct answer?
- is the prompt overfit to one example?
- is a hidden scaffold being mistaken for flavor text?
- did the first acceptable prompt get returned too early, before a better synthesis pass
  could happen?

## What not to do

- Do not imitate the source articles line by line.
- Do not require the user to explicitly ask for a prompt before using this skill's logic.
- Do not run Deep mode on every request.
- Do not treat a beautiful title as the whole task.
- Do not confuse a fast request with a shallow request.
- Do not let repeated success with one visible shell turn into a hidden habit of reusing that shell everywhere.
- Do not answer an essence-discovery request with a direct polished conclusion if the user wanted to be guided there.
- Do not answer a translation task with free expansion.
- Do not answer an engine request with a topic prompt.
- Do not answer a character-story request with a worldbuilding sample.
- Do not answer a case-driven request with only broad analysis.
- Do not answer an enterable symbolic-world request with a literary explainer.
- Do not mistake a staged inner-world simulation for an ordinary persona prompt.
- Do not keep a persona if it is only decorative.
- Do not delete recurring question lenses that carry the actual logic.
- Do not optimize for emotional impact when the primary objective is fidelity or understanding.
- Do not declare a prompt strong just because it shines on one sample.

## Success bar

This skill is working when the user can give a rough need in Chinese and receive a prompt that already reflects:

- the right task family
- the right input classification
- the right primary objective
- the right intermediate structure
- the right artifact unit
- the right final prompt shape
- a visible shape that feels native to the theme rather than copied from the last similar request

This skill is also working when the user gives only a rough final-content request in Chinese and still receives a final artifact that clearly reflects the same hidden design choices, even without seeing the prompt.

This skill is further working when the visible final prompt does not feel like the first generic draft, but like a stronger synthesized result shaped by theme, task, and likely failure modes.

This skill is strongest when the result also feels increasingly native to this user's taste, while still obeying the current request rather than mechanically repeating past preferences.

This skill is healthier when simple requests stay fast, difficult requests still get the deeper treatment, and prior successful decisions reduce repeated hidden work over time.

When the task is about finding the essence of something, the user should also receive the right inquiry path rather than a premature conclusion.

When the task is about entering a symbolic world, the user should receive a playable container with stable switching and reveal logic rather than a safer but flatter explanation.

The user should not have to manually specify those hidden design choices.
You should make them for the user.
