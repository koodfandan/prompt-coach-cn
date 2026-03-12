# Patterns

These patterns are distilled from the studied Chinese prompt materials.
Pick one primary pattern first.
Only add a secondary pattern when it clearly improves the result.
Do not treat these patterns as visible menu templates by default.
They are hidden support structures.
The final prompt should usually feel shaped by the user's theme, not by the pattern heading.

## 0. Theme-handle extraction

Use when:

- the task family is already clear, but prompts still keep sounding too similar across different themes
- the risk is not wrong classification, but visible template repetition
- the user wants prompts that feel more alive, flexible, and theme-native

Skeleton:

```text
Role: hidden theme interpreter
Task: extract the visible handle that should organize the final prompt for this theme
Execution rules:
1. name the core tension of the theme
2. name the image system, object system, or rule system native to the theme
3. name what should dominate the final prompt visibly:
   - scene logic
   - symbol logic
   - relation logic
   - inquiry logic
   - world rule logic
4. let that handle reshape the prompt sections and wording
5. keep the pattern hidden unless the user explicitly wants a reusable shell
Output:
- hidden theme handle
- final prompt that feels custom to the theme
```

Design notes:

- This pattern does not replace the main pattern. It customizes how the main pattern becomes visible.
- The failure mode it fixes is not wrong structure, but repetitive visible structure.

## 1. Guided questioning

Use when:

- the user wants to understand a topic by thinking through better questions
- guided learning is more useful than one final answer
- the hidden value is the question path itself

Skeleton:

```text
Role: questioning guide or learning coach
Task: generate a layered question chain for [topic]
Execution rules:
1. organize questions from simple to deep
2. move through definition, use, principle, comparison, reflection
3. explain briefly why each layer comes before the next
Output:
1. topic breakdown
2. layered questions
3. suggested learning order
```

Design notes:

- This is better than direct explanation when the real goal is understanding.
- The quality comes from the sequence, not the number of questions.

## 2. Structured rewrite

Use when:

- the user already has a useful prompt but it is messy
- the prompt looks like pseudo-code and is hard to reuse
- the user wants to preserve the original logic and examples

Skeleton:

```text
Role: prompt editor
Task: rewrite the user's prompt into readable structured Chinese
Execution rules:
1. preserve the original goal
2. preserve the logic order
3. preserve examples unless the user asked to optimize them
4. rewrite into visible sections:
   - role
   - task
   - input
   - execution rules
   - output format
   - start instruction
```

Design notes:

- Readability is the first job here, not creativity.
- This is for operational clarity, not reinvention.

## 3. Compression and stabilization

Use when:

- the prompt is too long
- repeated instructions are causing unstable behavior
- the user wants a shorter prompt without losing quality

Skeleton:

```text
Role: prompt compressor
Task: shorten and stabilize the user's prompt without losing the real mechanism
Execution rules:
1. merge repeated instructions
2. keep hidden guardrails
3. keep the output schema
4. keep the stage logic if it truly changes quality
Output:
1. compressed prompt
2. what was preserved
3. what was removed or merged
4. remaining risk
```

Design notes:

- Compression is not word shaving.
- Stabilize first, then shorten.

## 4. Persona with command separation

Use when:

- the user wants a persistent character or persona
- output quality depends on keeping the voice stable
- the prompt also needs special commands or utility modes

Skeleton:

```text
Persona:
- identity
- background
- voice
- values
Task:
- continue interacting in-character
Behavior rules:
1. stay in voice during normal interaction
2. separate normal dialogue from special commands
3. define what persists across turns
Special commands:
- guidance
- summary
- record or recap
Exit rule:
- leave persona only when the user explicitly asks
```

Design notes:

- Some personas are decorative.
- Others are functional. Keep only the ones that stabilize output.

## 5. Interface and layout brief

Use when:

- the user wants a prompt for UI, layout, page, card, chart, HTML, or SVG generation
- the real need is a design brief, not a pile of style words

Skeleton:

```text
Role: interface strategist and visual designer
Task: turn the user's theme into a usable design-generation prompt
Execution rules:
1. define the experience goal
2. define content modules
3. define layout structure
4. define visual direction
5. define technical constraints
Output:
- experience goal
- information hierarchy
- layout suggestion
- visual keywords
- interaction guidance
- technical constraints
```

Design notes:

- Good UI prompts separate strategy from styling.
- Visual taste alone is not enough.

## 6. Staged creation

Use when:

- one prompt is trying to write everything at once
- the task includes outline, material, draft, and refinement
- the user is writing stories, articles, or long-form content

Skeleton:

```text
Role: creative workflow organizer
Task: break the work into stages and generate step by step
Stages:
1. define outcome and audience
2. produce structure or outline
3. add supporting material
4. generate draft
5. refine with style and constraints
Output:
- current stage goal
- current stage input
- current stage output
- next stage need
```

Design notes:

- Use stages only when they improve quality.
- Do not force them on users who clearly want one-shot output.

## 7. Work insight

Use when:

- the user wants to understand a book, film, article, or work
- a plain summary is not enough
- the real goal is to understand why the work matters

Skeleton:

```text
Role: work insight organizer
Task: generate an insight-oriented prompt for understanding a work
Execution rules:
1. decide whether the user wants summary or insight
2. if insight, include:
   - what the work is
   - what it is really about
   - creation background
   - author context
   - structure
   - impact or afterlife
   - why it matters
3. state uncertainty if information is missing
```

Design notes:

- This is for making a work feel three-dimensional.
- The hidden move is going from what happened to why it exists and why it matters.

## 8. Engine prompt

Use when:

- the user wants a reusable generator, simulator, or framework
- one vivid example is only demonstrating a broader class
- the prompt should still work after swapping the example input

Skeleton:

```text
Role: define what the engine is
Task: solve a class of problems, not one topic only
Inputs:
- variable setup
- conditions or branching point
- observation target
- presentation style
Execution rules:
1. define what the engine does
2. define changeable inputs
3. define the reasoning or simulation process
4. define output modules
5. define self-check logic
```

Design notes:

- The core move is to abstract the mechanism first.
- Some engines depend on hidden question scaffolds. Preserve them when they carry the real logic.

## 9. Source-constrained translation

Use when:

- the user provides primary material such as lyrics, quotes, dialogue, scenes, notes, or transcripts
- the output should be transformed from that material rather than freely invented from a theme
- the task converts one medium into another, such as song to story, lyrics to MV concept, notes to article, or scene to monologue
- fidelity to the source matters more than arbitrary originality

Skeleton:

```text
Role: define a translation lens, not just a decorative persona
Task: transform the provided source material into the target form while keeping its core meaning, emotional logic, and recurring images aligned
Input contract:
- source material
- optional metadata such as title, author, context, or intended format
Execution rules:
1. identify who is speaking, to whom, and why
2. extract the emotional core, recurring image, and non-negotiable source facts
3. decide what must stay faithful and where creative completion is allowed
4. map the source medium into the target medium without drifting away from the source logic
5. if the target should feel like a finished artifact, output the artifact directly with minimal meta explanation
Output:
- either the finished artifact only
- or a tightly specified structure when the user explicitly wants sections
```

Design notes:

- This is not normal creative expansion. The source material is evidence.
- The role is useful only if it stabilizes the translation lens.
- Hidden question scaffolds often carry the real mechanism here.
- A common failure mode is sentimental drift, where very different sources all get translated into the same emotional shape.

## 10. Artifact-unit selection

Use when:

- the task family is already clear, but the finished result still feels wrong
- the user is implicitly choosing between nearby units such as story vs setting sample
- the main risk is not misclassification, but wrong output size and density

Common unit pairs:

- worldbuilding sample vs character-driven short story
- scene-based slice essay vs single-arc story
- analytical explainer vs case-driven article
- broad recommendation list vs one-path actionable guide
- reflective monologue vs structured explainer

Skeleton:

```text
Role: choose the right finished-artifact unit
Task: write a prompt that produces the correct unit, not just the correct topic
Execution rules:
1. name the intended artifact unit explicitly
2. state what density should dominate:
   - dramatic
   - informational
   - experiential
3. state what neighboring unit the output must avoid drifting into
4. define whether depth should sit in one case, several slices, or a broad map
Output:
- intended artifact unit
- dominant density
- anti-drift constraint
- final prompt
```

Design notes:

- Many almost-right prompts fail here.
- When the unit is wrong, the result may sound strong but still feel mismatched.

## 11. Essence discovery

Use when:

- the user wants to find the real core of a need, conflict, repeated pattern, or phenomenon
- the user benefits more from a path of discovery than from a direct answer
- the task is to uncover the root, not just explain the surface

Skeleton:

```text
Role: Socratic guide or insight mentor
Task: help the user discover the essence of [problem, need, conflict, system]
Execution rules:
1. start from the surface problem or symptom
2. ask 1-2 open questions about goal, motive, or tension
3. after each answer, move one layer deeper:
   - current explanation
   - hidden driver
   - recurring pattern
   - candidate essence
4. avoid giving the conclusion too early
5. summarize the path and ask the user to confirm or refine the proposed essence
Output:
- guided question flow
- short interim summaries
- candidate essence
- validation question
```

Design notes:

- The point is not to sound wise. The point is to move the user from surface to root.
- This pattern is strongest when the AI resists premature closure.
- A common failure mode is forcing everything into one grand answer before the user has actually arrived there.

## 12. Symbolic-world roleplay

Use when:

- the user wants to enter a symbolic world rather than read an analysis of it
- the task involves a mental world, dream logic, interrogation room, ward, palace, archive, ritual chamber, or another staged container
- symbols such as fairy tales, houses, wolves, mirrors, dolls, monsters, or objects are meant to operate as system parts
- the output should feel like a playable transcript, roleplayed encounter, or staged revelation sequence

Skeleton:

```text
Role: symbolic-world operator or encounter designer
Task: build a prompt that lets the user enter and question a symbolic world
Container:
- define the stage where the encounter happens
- define why the encounter can continue
System map:
- role shell
- symbol map
- state map
- trigger map
- reveal ladder
- anti-dead-end mechanic
- safety boundary
Execution rules:
1. keep the user inside the scene
2. let questions trigger state changes or reveal shifts
3. use symbols as operating parts, not decorative metaphors
4. avoid premature full explanation
5. allow partial truths, denial, or contradiction before later disclosure
Output:
- copy-paste-ready prompt
- explicitly named artifact unit such as interactive symbolic transcript or embodied mental-world simulation
```

Design notes:

- This is not the same as a normal persona prompt. The scene container and switching logic are part of the mechanism.
- This is not the same as a literary analysis. The symbols should run the world, not only be explained after the fact.
- A common failure mode is producing gothic atmosphere without operational rules.
- Another common failure mode is turning the whole thing into diagnosis theater. Keep a literary-symbolic boundary unless the user clearly asks otherwise.
