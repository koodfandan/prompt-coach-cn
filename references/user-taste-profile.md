# User Taste Profile

Use this as a compact ranking aid, not as a hard law.

Rules:

1. Explicit current-turn instructions override this profile.
2. Repeated signals matter more than one-off reactions.
3. Use taste after task fit is correct, not before.
4. If this profile makes the output feel stale or overfit, loosen it.

## Compact dimensions

These axes are meant to be fast to read and easy to apply.

- template_aversion: very high
- theme_native_preference: very high
- hidden_synthesis_preference: high
- direct_delivery_preference: high
- reasoning_depth_preference: very high
- visible_teaching_tolerance: low
- artifact_fit_sensitivity: very high
- personalization_preference: high
- dramatic_temperature_default: balanced
- language_preference: Chinese-first

## Stable narrative hints

Use only when the compact dimensions are not enough.

- Prefers bottom-layer reasoning over shallow comparison.
- Wants prompts and outputs to feel shaped by the theme itself.
- Responds well to iterative refinement when it clearly improves quality.
- Dislikes generic shells, premature conclusions, and first-draft lock-in.
- Usually wants the final result directly unless prompt design itself is the deliverable.

## Override and drift control

- Current-turn constraints always win.
- Do not force every task into the same emotional temperature.
- Keep remembered taste as a bias layer, not a style prison.

## Ranking order when uncertain

1. task fit
2. artifact fit
3. theme-native specificity
4. hidden synthesis quality
5. user taste fit
