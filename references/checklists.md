# Checklists

Use these lists to diagnose a weak prompt before rewriting it.

## Fast diagnosis

Ask these five questions first:

1. What end result does the user really want?
2. What input will the model receive?
3. What exact shape should the output take?
4. What must the model not do?
5. Where is the current instability: facts, format, reasoning, style, persona, or task classification?

## Five-layer audit

If a prompt feels almost right but still wrong, audit these layers in order:

1. task type
2. input role: evidence, anchor, or inspiration
3. primary objective
4. intermediate representation
5. artifact unit and final prompt structure

Do not jump to wording fixes before checking these layers.

## Complexity-gate checklist

Use this before deciding how much hidden work to spend.

Ask:

1. Is the task already clear enough for Lite mode?
2. Is there meaningful ambiguity about task family or artifact unit?
3. Is generic-risk high enough to justify Standard or Deep mode?
4. Did the user explicitly ask for strongest, best, refined, comparative, or highly tailored output?
5. Can I likely solve this well without a multi-candidate pass?

Suggested mode:

- Lite: clear and low-risk
- Standard: normal default
- Deep: only when risk or value clearly justifies it

Choose the cheapest mode that is still likely to do the job well.

## Intent routing checklist

Before rewriting any prompt, silently verify:

1. Is the user asking for a prompt, or for the final content now?
2. Is this a summary task, insight task, generation task, transformation task, workflow task, or translation task?
3. Is this actually an essence-extraction or guided-inquiry task rather than a direct-answer task?
4. Did I mistake "quickly" for "shallowly"?
5. Did I mistake "make it better" for "rewrite everything from scratch"?
6. Is the user asking for a direct one-shot prompt, or a staged prompt?
7. Is the user asking for a one-off topic prompt, or a reusable engine prompt?
8. Am I following the real task, or just following the showcased title or example?
9. Did I treat source material as evidence, or accidentally downgrade it into inspiration?
10. Even if the task family is right, did I still choose the wrong finished-artifact unit?

If you get this layer wrong, the rest of the prompt will often be wrong even if it is well written.

## Summary vs insight checklist

### Summary cues

The user mainly wants:

- what happened
- the main plot
- key people and ending
- a short overview
- no extra background

### Insight cues

The user wants:

- why the work matters
- why it was written
- why this author wrote it
- what historical or personal conditions shaped it
- influence, controversy, afterlife
- why it is worth reading or knowing

### Routing rule

- If the user gives only summary cues, keep the prompt light.
- If the user gives multiple insight cues, do not collapse it into a summary prompt.

## Topic vs engine checklist

### Topic prompt cues

The user mainly wants:

- one concrete prompt for one vivid topic
- a prompt tied to one exact subject line or title
- immediate output for this specific case
- no need to reuse the structure across many future topics

### Engine prompt cues

The user wants:

- a reusable generator they can run again with different inputs
- a generic machine for a whole class of topics
- a stable framework for simulation, comparison, or worldbuilding
- a prompt that exposes variable slots and a repeatable workflow

### Routing rule

- If the user is focused on one topic only, do not over-abstract it into an engine.
- If the user asks for something reusable, repeatable, or "future topics should also work", do not answer with a one-off topic prompt.

## Source-constrained translation vs theme expansion checklist

### Source-constrained translation cues

The user mainly wants:

- the output to be built from provided lyrics, quotes, notes, dialogue, or scenes
- strong fit to the source material
- the source to act as evidence and boundary
- a transformed artifact such as story, MV concept, monologue, or article

### Theme expansion cues

The user mainly wants:

- a strong result built around a theme, title, hook, or mood
- creative freedom
- no strict obligation to stay faithful to source material
- inspiration rather than translation

### Routing rule

- If the user provides primary material and asks for a transformed result, default to source-constrained translation.
- If the user only gives a theme or hook, do not invent fidelity rules that the input cannot support.

## Example title vs actual task checklist

### Example-title cues

What you see first is:

- one vivid title
- one memorable theme
- one poetic showcase case

### Actual-task cues

The real task is broader and often appears in:

- explicit input/output lines
- demand analysis
- step-by-step implementation
- repeated testing across multiple examples
- author summary about what generalized and what did not

### Routing rule

- Do not assume the title is the task.
- If the source or user also defines reusable inputs and outputs, treat those as the real task contract.

## Hidden scaffold checklist

Some prompts look rich because of style. Others look rich because a hidden question scaffold is doing real work.

Check:

1. Is there a recurring question set before generation?
2. Does that question set define the lens, not just the tone?
3. If I remove it, does the prompt lose transferability or depth?

If the answer is yes, preserve it.

## Essence-extraction checklist

Use this when the user is trying to find the real core of a need, conflict, system, or repeated problem.

Check:

1. Does the user want AI to ask its way toward the essence instead of announcing the answer immediately?
2. Is the true value in a sequence of progressively deeper questions?
3. Does the task need movement from symptom to explanation to hidden driver to recurring pattern to candidate essence?
4. Does the final answer need user confirmation rather than one-shot AI certainty?
5. Is there a risk of over-compressing many causes into one grand conclusion too early?

If yes, prefer guided inquiry over polished explanation.

## Symbolic-world entry checklist

Use this when the user is not asking to explain a symbolic world, but to enter and interact with it.

Check:

1. Does the user want a staged encounter, transcript, interrogation, guided entry, or roleplayed exploration?
2. Is the symbolic material meant to function as an operating system rather than a topic of commentary?
3. Is there a stable container such as a room, chamber, archive, palace, ward, or dream site?
4. Are there explicit internal states, personas, or modes that can take over?
5. Is there a trigger logic for state changes or reveal shifts?
6. Is there a reveal ladder instead of one-shot explanation?
7. Is there an anti-dead-end mechanic so the scene can continue after denial, collapse, or refusal?
8. Is there a clear literary-symbolic safety boundary rather than pseudo-diagnostic certainty?

If yes, prefer symbolic-world roleplay over analysis or ordinary persona chat.

## Artifact unit checklist

Many prompts fail after the big routing decision is already correct.
The remaining error is that the finished artifact is the wrong size or wrong unit.

Ask:

1. Does the user want a worldbuilding sample, a character-driven story, or a scene-based slice?
2. Does the user want a broad explainer, one concrete case path, or an actionable guide?
3. Does the user want multiple examples, or one representative sample developed more deeply?
4. Should information density dominate, or should dramatic density dominate?
5. Is the current prompt drifting into a neighboring unit because that unit is easier to generate?

If this layer is wrong, the output can feel polished but still feel "off."

## Theme-native prompt checklist

Use this when the prompt is not exactly wrong, but keeps feeling generic or too similar to previous prompts.

Ask:

1. What is unique about this theme beyond its task family?
2. What image system, object system, or scene logic belongs to this theme?
3. Is the visible prompt shaped by that theme, or by the last reused shell?
4. If I swap only the theme, does the prompt still look almost identical?
5. Am I exposing the pattern too visibly instead of letting it stay underneath?

If the answer to 3, 4, or 5 is yes, extract a stronger theme handle before rewriting.

## Hidden candidate synthesis checklist

Use this when the prompt is technically usable, but often feels like the first decent draft rather than the best one.

Ask:

1. Did I stop after the first acceptable prompt shape?
2. Are there at least 2 plausible prompt directions worth internally testing?
3. Does one version have better constraints while another has better theme fit?
4. Could the final prompt be improved by recombining the strongest parts of multiple drafts?
5. Would showing only one early draft make the result feel more generic than necessary?
6. Can I compare only the key moving parts instead of drafting several whole prompts?
7. Is whole-draft comparison actually necessary, or would local component comparison solve this faster?

If yes, run a hidden divergence-and-synthesis pass before finalizing.

## Personalization checklist

Use this when the goal is not only to be correct, but to fit this user's evolving taste better over time.

Ask:

1. What stable preferences has the user shown repeatedly?
2. Which of those preferences actually matter for this task?
3. Which current-turn instructions override older taste signals?
4. Am I using taste as a bias layer, or am I forcing the whole output into an old style?
5. Will this result feel more like "this user's version of the task" rather than a generic version?

If personalization matters, use taste to refine after task fit is correct.

## Compact-memory checklist

Use this when taste memory or decision cache begins to feel heavy.

Ask:

1. Can this preference be expressed as one compact dimension instead of a long narrative note?
2. Do I really need full historical wording, or only the current reusable weight?
3. Is the memory helping ranking, or just repeating prose?
4. Would a smaller set of stable axes be enough for this request?

Prefer compact reusable weights over long descriptive memory when possible.

## Decision-cache checklist

Use this when similar requests or repeated user corrections suggest prior wins can be reused.

Ask:

1. Have I solved a materially similar request before?
2. Which part of that success is reusable:
   - routing choice
   - artifact-unit choice
   - theme-handle strategy
   - local comparison strategy
3. Is the current request close enough that reuse is likely to help?
4. Does the current turn override the old cached tendency?
5. Will reusing the cache reduce work without flattening the output?

If yes, reuse the smallest useful part of the cache rather than the whole old solution.

## Common failure modes

### Output format instability

Symptoms:

- fields appear in different order
- optional fields sometimes disappear
- output length drifts heavily

Fix first:

- specify exact section names or keys
- define empty-value behavior
- define length expectations

### Hallucination or false certainty

Symptoms:

- model invents facts
- model fills in missing context confidently

Fix first:

- require uncertainty to be stated explicitly
- tell the model what to do when information is insufficient
- if sources exist, say they are evidence, not instructions

### Prompt looks rich but is structurally weak

Symptoms:

- many role descriptions but weak task clarity
- poetic setup hides operational rules
- pseudo-code makes it look precise but remains ambiguous

Fix first:

- pull out the real task sentence
- rebuild with visible labels
- keep decorative language only where it helps tone

### Beautiful headline, wrong task

Symptoms:

- the rewritten prompt sounds good but follows only the title case
- the actual reusable input/output pattern disappears
- the result fits one sample and fails the next

Fix first:

- inspect the real input/output contract
- inspect how the original author tested the prompt
- rewrite around the mechanism, not the headline

### Source treated as vibe instead of evidence

Symptoms:

- the output sounds good but could fit many different sources
- the rewritten prompt ignores the user's lyrics, quotes, or primary material
- the result becomes generic creation rather than faithful transformation

Fix first:

- state that the source material is evidence and boundary
- identify the speaker, addressee, emotional core, and recurring image
- define what must remain faithful during transformation

### One prompt is doing too many jobs

Symptoms:

- the user wants idea generation, selection, drafting, and formatting all together
- quality falls differently in different parts

Fix first:

- split the workflow into stages
- define the output of each stage
- only merge stages again if needed

### Task misclassification

Symptoms:

- the prompt answers a neighboring task well, but not the actual task
- output is clear, but still feels "not what I meant"
- the result is too shallow or too heavy
- the prompt is reusable when the user wanted one vivid topic, or one-off when the user wanted an engine
- the prompt follows the article title but misses the real generalized task
- the prompt keeps the flavor text but deletes the question scaffold that carried the logic
- the prompt solves a theme-expansion task while the user actually asked for source-constrained translation

Fix first:

- re-check the user's real understanding goal
- identify the actual result type
- identify whether the result should be one-shot or reusable
- identify whether the visible example is only a demo of the real task
- identify whether the given material is evidence, anchor, or inspiration
- rewrite from the correct branch rather than patching the wrong branch

### Premature essence claim

Symptoms:

- the prompt announces the essence before the inquiry has earned it
- the model sounds deep but skips the user's actual reasoning path
- the result becomes philosophical performance rather than discovery
- many possible drivers are collapsed into one root too early

Fix first:

- switch from declaration to guided questioning
- force at least one layer each of symptom, hidden driver, and candidate essence
- keep a validation step where the user can confirm or revise the proposed root
- avoid claiming one ultimate answer too early if the evidence is mixed

### Correct family, wrong artifact unit

Symptoms:

- the piece is well written but feels like the wrong kind of finished result
- the story reads like a world-setting sample when the user wanted one protagonist arc
- the article reads like broad analysis when the user wanted one concrete case path
- the piece contains many good observations but lacks the unit of completion the user expected

Fix first:

- name the intended artifact unit explicitly
- decide whether depth should sit in one example or across many examples
- decide whether the user needs dramatic progression, analytical coverage, or scene accumulation
- rewrite around that unit before polishing tone

### Pattern is correct, but the prompt still feels template-bound

Symptoms:

- the prompt technically works, but looks too much like the last few prompts
- different themes keep producing nearly identical section order and wording
- the visible structure reflects the pattern heading more than the theme itself
- the user says the prompt feels rigid, generic, or too formulaic

Fix first:

- extract the theme-native handle
- let the theme reshape the visible structure
- keep the main pattern underneath
- only expose a reusable shell when the user explicitly wants one

### First-draft lock-in

Symptoms:

- the prompt is usable, but feels like the first thing that came to mind
- the result covers the basics but misses stronger phrasing or better hidden constraints
- one version seems more specific while another seems more stable, but they never get combined
- repeated use produces "fine" prompts more often than genuinely sharp ones

Fix first:

- sketch 2 to 4 hidden candidate directions
- compare them by task fit, theme fit, constraint strength, and likely failure modes
- merge the strongest parts into one final prompt
- show only the synthesized result unless the user asks for the comparisons

### Whole-draft comparison when local comparison would do

Symptoms:

- several complete prompt drafts are generated even though only one or two moving parts were uncertain
- the result is thoughtful but slower than necessary
- most candidate drafts differ only in a few lines
- the skill keeps paying full comparison cost for small structural uncertainty

Fix first:

- compare the theme handle, artifact-unit framing, constraint block, or output structure locally
- keep a shared backbone and swap only the uncertain parts
- escalate to full-draft comparison only if architecture-level uncertainty remains

### Full-power overkill

Symptoms:

- simple requests still trigger heavy hidden work
- the result is fine, but generation took more search than the task justified
- deep comparison is used where a direct one-pass answer would have been enough
- the skill feels thoughtful but sluggish

Fix first:

- run the complexity gate
- drop to Lite or Standard mode when possible
- skip full candidate synthesis unless risk clearly justifies it
- stop early once task fit and artifact fit are already strong

### Cache reuse drift

Symptoms:

- the skill keeps rediscovering the same routing choices from scratch
- or reuses old decisions too aggressively and makes new tasks feel stale
- repeated task types do not get faster over time
- cached defaults start overriding current-turn specificity

Fix first:

- cache only the reusable decision, not the whole old output
- check similarity before reuse
- let current-turn instructions override old defaults
- keep cache as acceleration, not as a new template source

### Taste-memory drift

Symptoms:

- the result ignores stable user preferences that should have improved fit
- or the result overuses remembered taste and makes different tasks feel too similar
- the user says "this still doesn't feel like me" or "you always write it the same way"
- personalization turns into style lock-in

Fix first:

- separate stable preference from one-off request
- keep the task family and artifact unit primary
- use remembered taste only as a soft ranking signal in candidate comparison
- let the current theme and current instruction still reshape the visible result

### Symbolic world explained instead of entered

Symptoms:

- the piece sounds thoughtful but stays outside the world
- the output explains what the symbols mean instead of letting them operate
- a request for interrogation, encounter, or staged revelation becomes a polished article
- the result contains atmosphere but no switching logic, no trigger logic, and no reveal order

Fix first:

- define the container
- define the role shell and state map
- define the trigger map and reveal ladder
- define an anti-dead-end mechanic
- keep a literary-symbolic safety boundary so the prompt does not drift into diagnosis theater

## Transferability checklist

Before declaring a prompt strong, ask:

1. Would it still work if I swap the example input?
2. Does the same structure hold across at least 2-3 different objects?
3. Is the prompt only eloquent on one case, or stable across cases?
4. Does it collapse different source materials into the same emotional pattern?

If it fails after input swap, it is probably overfit to the example.

If very different songs, scenes, or sources all turn into the same sentimental shape, it is probably biased rather than transferable.

## Persona instability

Symptoms:

- persona leaks
- command mode and chat mode interfere

Fix first:

- separate persona rules from tool-like commands
- define trigger words for special functions
- remind the model what persists across turns

## Compression checklist

Keep:

- hidden guardrails
- output schema
- non-obvious constraints
- workflow stages that actually change quality

Remove or merge:

- repeated tone words
- duplicate warnings
- model-default behavior written three times
- decorative metaphors that do not change execution

## Structure rewrite checklist

When converting a messy prompt to structured Chinese:

1. Preserve the goal.
2. Preserve the logic order.
3. Preserve examples unless the user asked to optimize them.
4. Replace implicit requirements with visible section labels.
5. End with a copy-paste-ready final prompt, not just commentary.

## Teaching checklist

If the user wants to learn prompting, explain only the highest-value fixes:

- one missing piece
- one source of instability
- one rewrite principle they can reuse

Avoid turning the answer into a lecture.
