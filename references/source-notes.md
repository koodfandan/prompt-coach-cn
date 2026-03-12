# Source Notes

These notes summarize recurring prompt-design moves extracted from the studied Chinese HTML prompt collection in this workspace.

## Repeated structural move

Many source articles use the same backbone:

1. need analysis
2. step-by-step implementation
3. final prompt
4. example outputs or tests
5. retrospective summary

This matters because the prompt is not treated as a magic sentence.
It is treated as a small workflow.

## Strong recurring techniques

### 1. Role plus workflow

Many prompts use a role to create tone and domain framing, then rely on a clear workflow to control execution.

- the role gives flavor
- the workflow gives stability

### 2. Simple to deep

Educational prompts often move in layers instead of jumping to the final answer.
This appears in concept learning, expression training, and idea exploration.

### 3. Readable structure beats fake code

Several prompts show that pseudo-code is optional.
What matters is not whether the prompt looks like Python or XML.
What matters is whether the logic can be scanned, edited, and reused.

### 4. Compression is not deletion

A good shorter prompt keeps:

- the task core
- the output shape
- the non-obvious boundaries
- the sequence of reasoning or creation

### 5. Staging improves many creative tasks

Story and article prompts often work best when broken into:

- opening or core hook
- outline
- character or supporting material
- main draft
- final refinement

### 6. Commands and normal dialogue should be separated

Role-play prompts become more stable when special commands are separated from normal in-character conversation.

### 7. Keywords are only the entry point

UI and concept prompts often start from keywords, but the real work happens in the expansion:

- objective
- meaning
- structure
- visual or rhetorical direction
- output constraints

### 8. "Quick understanding" does not always mean summary

One important lesson from the book-insight materials:

- "quickly understand a book" can mean "give me the plot fast"
- but it can also mean "help me quickly understand why this work matters"

Those are different prompt problems.

The stronger prompt does not stop at summary.
It asks:

- why this work was written
- why this author wrote it
- what conditions shaped it
- what its inner structure is
- what influence or afterlife it had
- why it is worth knowing

### 9. A beautiful title is not always the real task

Some articles use one vivid theme or poetic title as the surface hook, but the real prompt underneath is broader.

Important move:

- separate the headline example from the real input/output contract
- find the reusable task hiding under the example

### 10. Hidden question scaffolds often carry the real logic

Some strong prompts are not stabilized by schema alone.
They are stabilized by a recurring question scaffold:

- a fixed set of lenses
- a diagnostic sequence
- a repeated chain of inquiry before generation

When optimizing such prompts, do not treat those questions as decorative flavor.
They may be the actual mechanism.

### 11. One good example is not enough

A prompt that sounds brilliant on one example may collapse on the next one.

A stronger test is:

- keep the same prompt
- swap the input object
- see whether the hidden structure still holds

This is a mechanism test, not only a style test.

### 12. Some inputs are evidence, not inspiration

Several materials become much stronger once the source material is treated as a hard constraint.

Examples:

- lyrics are not just mood hints
- quoted dialogue is not just flavor
- primary notes are not just background

The prompt becomes more stable when it first decides whether the user's material is:

- evidence
- anchor
- inspiration

If evidence is mistaken for inspiration, the result may sound good but solve the wrong task.

### 13. Some personas are actually translation layers

Not every persona exists for tone.

In some prompts, the persona is the mechanism that maps one medium into another:

- sound to image
- notes to narrative
- fragments to concept structure

When a persona is doing this job, do not compress it away as mere flavor text.
It may be defining the conversion lens.

### 14. Author retrospectives reveal bias

The article summaries and self-critiques often contain the most valuable signal.

If the author says a prompt:

- keeps drifting sentimental
- overfits to one emotional shape
- generalizes badly to another example

that should become:

- a routing rule
- a failure mode
- or an eval case

### 15. Some prompts are not answer engines, but discovery engines

Another important pattern from the corpus:

- some prompts should not rush to the answer
- their value lies in creating a path that helps the user arrive at the answer

These prompts often use:

- Socratic questioning
- progressive abstraction
- layer-by-layer root-cause discovery
- explicit validation before claiming the essence

The real output is not only a conclusion.
It is the user's movement from surface explanation to deeper structure.

### 16. Some symbolic prompts are not explanations, but enterable systems

Another later lesson from the corpus:

- some prompts should not explain a symbolic world from the outside
- they should let the user enter that world and interact with it

These stronger symbolic prompts often rely on:

- a scene container
- a role shell
- a symbol map
- a state map
- a trigger map
- a reveal ladder
- an anti-dead-end mechanic

The symbols are not only interpreted.
They are turned into operating parts of the encounter.

### 17. The strongest symbolic prompts often need a continuation mechanic

In immersive symbolic roleplay, a common problem is premature collapse:

- the role breaks
- the scene dead-ends
- the subject refuses to continue
- the revelation happens too early

The stronger prompts avoid this by adding a continuation mechanic:

- time stop
- reset into another chamber
- recurring return to the same palace or ward
- controlled revival of the scene after collapse

This is not decoration.
It is a structural guardrail.

### 18. Patterns should stay underneath the visible prompt

Another later lesson from testing:

- a skill can classify the task correctly
- choose a reasonable pattern
- and still feel rigid because the same visible prompt shell keeps repeating

This means:

- the pattern was useful
- but it became too visible

The stronger move is:

- keep the pattern as a hidden scaffold
- extract a theme-native handle
- let the theme reshape the visible prompt sections, wording, and emphasis

Otherwise many prompts will feel like they came from the same mold.

### 19. Some strong prompts are not written once, but synthesized

Another useful lesson:

- the first acceptable prompt is often not the strongest prompt
- different hidden drafts may each solve a different weakness

Common pattern:

- one draft has better structure
- one draft has better theme fit
- one draft has better guardrails
- one draft has better transferability

The stronger move is not to show all of them by default.
It is to compare them silently, extract the strongest pieces, and synthesize one final prompt.

This makes the visible result feel less generic without forcing the user to do the comparison work.

### 20. Personalization should be a ranking layer, not a cage

Another late lesson:

- users do not only want correct prompts
- they often want prompts and outputs that feel closer to their own taste over time

The stronger move is not to hard-code one style.
It is to build a soft preference model from repeated interaction signals, then use that model to rank and refine candidate directions.

This means:

- stable preferences should improve fit
- current-turn instructions should still override memory
- remembered taste should not flatten all future outputs into one tone

Good personalization is a bias layer after task fit, not before task fit.

### 21. Not every request deserves the same hidden depth

One major optimization lesson:

- a skill can be right and still be too expensive

If every request gets full hidden search, multi-candidate comparison, and strong personalization, quality may rise but speed will suffer unnecessarily.

The stronger move is:

- gate the depth
- spend more hidden work only when ambiguity, generic-risk, or value justify it
- stop early when the task is already well solved

This is an execution-economy problem, not a writing-style problem.

### 22. Decision memory is different from taste memory

Another important distinction:

- taste memory stores what the user tends to like
- decision memory stores what routing and comparison choices have already worked

Examples of decision memory:

- which artifact unit often wins for this user's framing
- when Lite mode is usually enough
- which hidden comparisons are worth doing
- which failure modes should be checked first

This kind of memory speeds the skill up because it reduces repeated rediscovery.

### 23. Not every hidden comparison should be full-draft comparison

Another late optimization lesson:

- several good prompt candidates often differ only in a few critical parts
- the expensive mistake is to regenerate several complete prompts when only one component is uncertain

The stronger move is:

- keep one shared backbone
- compare the smallest useful moving parts first
- only escalate to whole-draft comparison when architecture-level uncertainty remains

This turns hidden refinement from brute-force search into cheaper local synthesis.

### 24. Good memory should be compact enough to rank with

Another important lesson:

- long narrative memory is useful for explanation
- compact memory is better for repeated decision-making

The stronger move is:

- compress stable taste into a few reusable dimensions
- compress decision memory into a few reusable routing and comparison defaults
- read longer narrative notes only when the compact view is insufficient

This keeps personalization and reuse fast instead of verbose.

### 25. A strong skill must know when to stop

One more optimization lesson:

- hidden refinement improves quality only until the major uncertainty is resolved
- after that, more search often adds cost faster than quality

The stronger move is:

- check whether task fit, artifact fit, and generic-risk control are already strong
- stop early when the prompt is already clearly good enough

This is not laziness.
It is execution economy.

## Design takeaway for this skill

The strongest compression of these materials is a five-step loop:

1. classify the task
2. classify the input
3. choose the objective
4. extract the intermediate representation
5. choose the artifact unit and final prompt structure

One more lesson became clear during later testing:

- even when the task family is correct, the result can still be wrong if the finished artifact unit is wrong

Examples:

- a story task can become a worldbuilding sample when the user wanted one protagonist arc
- an insight task can become broad analysis when the user wanted one concrete case path
- a reflective topic can become an explainer when the user wanted a short monologue

So the last step must do two jobs:

- choose the unit of completion
- choose the prompt structure that best produces that unit

This skill should not imitate the articles line by line.
It should preserve their deeper habits:

- clarify the real need
- reveal the hidden structure
- write prompts people can actually edit
- split stages when one-shot prompting becomes fragile
- distinguish summary from insight before choosing the prompt architecture
- distinguish the showcased title from the actual reusable task
- preserve hidden question scaffolds when they carry the reasoning logic
- prefer prompts that survive input swaps over prompts that only shine on one example
- identify whether the user's material is evidence, anchor, or inspiration before designing the prompt
- distinguish source-constrained translation from free theme expansion
- turn observed author bias into explicit failure checks instead of ignoring it
- distinguish the correct artifact unit inside the same task family before writing the final prompt
- distinguish answer-oriented prompts from discovery-oriented prompts before deciding whether AI should explain or ask
- distinguish explaining a symbolic world from entering a symbolic world before deciding whether the output should be an article or a playable encounter
- keep patterns as hidden support structures and let the theme visibly shape the final prompt so outputs do not become template-bound
- when the first viable prompt is not clearly strong enough, generate a few hidden candidate directions and synthesize the best parts into one final prompt
- build a soft user taste model from repeated interaction and use it as a ranking layer, while letting the current request override old preferences when needed
- use a complexity gate so easy requests stay cheap and difficult requests get the deeper treatment
- keep a decision cache so prior wins reduce repeated hidden work instead of being rediscovered every time
