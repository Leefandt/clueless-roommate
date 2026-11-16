# Mastery rubric (internal)

## Two layers

### Layer 1: Baseline S

When the user gives the complete teach-back, score each core concept:

- **0 Not mentioned**: absent from the whole explanation.
- **1 Name / definition only**: states the term or conclusion, but does not explain why.
- **2 Explains why or gives an example**: at least one causal explanation or one correct example.
- **3 Explains why + example + condition / boundary**: all three.

This layer counts only what the user produced spontaneously, not what they say after being asked. Record exact quotes.

### Layer 2: Defense D

Use the evidence table below, 0-3. Cross-examination questions can supply evidence, but mark it `prompted`.

| Evidence | Supports |
|---|---|
| States the definition / core conclusion | 1 |
| Explains the causal chain in their own words (not reciting the material, not repeating what you said in State 1) | 2 |
| Invents a correct example (not a slide example) | 2 |
| Correctly answers a question about scope / conditions | 2 |
| Identifies and corrects a misconception (the roommate's or their own), with a specific reason | 2 |
| Judges a new scenario / extreme case correctly | 3 |
| Corrects the error in a role reversal, with a specific reason | 3 |
| Answers or volunteers a boundary / failure condition | 3 |

**To 1**: 1 piece of level-1 evidence.

**To 2**: at least 2 different pieces of level-2 evidence, with no uncorrected hard error.

**To 3**: already at 2, plus at least 2 different pieces of level-3 evidence, with no uncorrected hard error.

Rules:

- The same piece of evidence does not count twice.
- Explaining what a term *means* = level 1; explaining *why the conclusion holds* = level 2.
- One answer can raise the level by at most one step; going from 1 to 3 requires separate turns.
- "Right / yeah / I don't know" is not evidence; neither is the roommate's paraphrase.
- Anything you explained in State 1, even if the user repeats it smoothly, is level 1 at most.
- No exact quote = no evidence; the score stays or drops.

## Final F and the verdict cap

- F = D (the defended level after cross-examination).
- Each concept carries three flags:
  - `spontaneous`: S ≥ 2
  - `prompted`: S < 2 and D ≥ 2
  - `unresolved`: D < 2

**Verdicts**:

- **Solid**: all core concepts have S ≥ 2 and D ≥ 2, at least one D=3, no uncorrected hard error, and at least one transfer / boundary attack passed.
- **Mostly solid**: all core concepts have D ≥ 2, but at least one core concept is `prompted`, or no D=3, or one small repaired gap.
- **Still shaky**: any core concept has D < 2, or an uncorrected hard error, or a wrong idea the user talked you into.

**Do not** let strong answers under cross-examination erase concepts the user never mentioned in the teach-back; `prompted` must appear in the debrief.

## Attack map

After the teach-back, build a finite attack map:

| Source | Minimum | Notes |
|---|---|---|
| Coverage of each core concept | 1 / concept | S=0/1: ask "you never mentioned / only named it"; S≥2: ask one why or example |
| Boundary / transfer for each concept | 1 / concept (optional) | Conditions, counterexamples, extreme cases |
| Errors / contradictions in the teach-back | 1 each (max 2 / concept) | Quote the claim and ask how it holds |
| Unexplained terms | max 2 total | "What does X mean?" |

Follow up on each attack point at most once; then mark it `resolved` or `unresolved`.

## When to stop

Any one:

1. The attack map is exhausted (every core concept has at least one attack point), and all hard errors / contradictions are resolved or recorded.
2. 12-18 cross-examination questions (3-5 concepts: 12-15; 6-7 concepts: 15-18).
3. The last 2-3 answers produced no new gaps.
4. The user says stop / is clearly tired.

- Cover every core concept and attempt at least one transfer / boundary question before the debrief, unless the user ends it.
- At the debrief you must be able to list: spontaneous coverage, prompted repairs, unresolved points.

## Hard errors and the correction window

- An error in the teach-back that is not corrected in 2B = a hard error.
- Agreeing with a wrong statement during cross-examination = a hard error; if the user discovers and corrects it before the concept closes, clear it and count one piece of level-2 evidence.
- Still uncorrected at the debrief → cap that concept at 1, and lower the overall verdict by at least one step.
- If the user never had a chance to discover it (it was never attacked), it is not a hard error, but write "unverified" in the material check.

Hard caps (any one caps the concept at 1):

- A key step is still unclear after two follow-ups.
- The user cannot translate the jargon into plain language.
- The user contradicts themselves and cannot explain it after being challenged.

## Recording

- Write the baseline immediately after the teach-back, before starting 2B.
- Update the session file every 4-5 cross-examination questions.
- Each entry: turn / attack ID / concept / D / the user's exact words / status.
- If the user says "don't log," do not write the file, but keep the quotes and scores in context.

## Debrief (≤10 lines)

- **Teach-back coverage**: 1-3 points; which core concepts the user explained spontaneously.
- **Defense under attack**: 1-3 points; what held, what was only filled in after asking, what stayed unresolved.
- **Material check**: places where the user was wrong but the ignorant roommate could not catch it. No material → "No course material; could not check the course's conventions." Unknowable → "Could not verify."
- **Verdict**: Solid / Mostly solid / Still shaky.
- **Next step**: one minimal restatement task ("Explain X in three sentences without using the word Y"); optional second round after 48 hours.

## Anti-inflation

- Never write "you've completely mastered it" to make the user feel good.
- Never treat "the roommate said they got it" as evidence of mastery; the roommate may have just given up.
- Every verdict must point to quoted evidence; if you cannot quote it, lower the verdict.
- Only answer "am I actually good?" in the debrief; mid-session, the roommate plays dumb.
- A concept the user never mentioned in the teach-back stays `prompted` no matter how well they answer under cross-examination.
