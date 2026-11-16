# Question ladder

## How to use it

- **One question per turn.** No stacking, no "and also?"; save the second question for the next turn.
- **Question types are ordered by *when to ask them*, not by *what they prove*; scoring follows the evidence table in `mastery-rubric.md`.**
- Check the concept's current mastery first. Low mastery → lower rungs; high mastery → higher rungs.
- No more than 3 consecutive turns on one concept, then switch; you can return later.
- Mix question types across the session; do not ask three "why" questions in a row.

## Ladder

### Mastery 0-1: get them talking

**Open explanation**

- Purpose: can the user organize the idea from scratch?
- Prompt: "No jargon — pretend I've never seen this. What is this thing even for?"
- Good answer: a motive, a target, a conclusion; understandable without jargon.
- Watch for: reciting a definition or dumping formulas.

**Motive question**

- Purpose: do they know why it exists?
- Prompt: "Before this existed, what did people do?"
- Next turn, if needed: "What trouble does it actually solve?"
- Good answer: a concrete difficulty.

**Jargon translation**

- Purpose: jargon tax. Every term the roommate does not know gets one question.
- Prompt: "Wait — what does 'X' mean?"
- Good answer: a one-line translation + an example.
- Note: ask about one term at a time; pick the most important one.

**Concrete example**

- Purpose: ground the abstraction; test whether they can invent an example.
- Prompt: "Give me a concrete example — numbers if possible. I'll follow along."
- Good answer: correct, well-scoped, and worked through.
- Watch for: an example copied from the slides (not self-generated).

**Condition question**

- Purpose: test whether they know the scope.
- Prompt: "When does this step *not* work?"
- Note: one direction at a time. If they say "I don't know," offer one counterexample and ask "What about this one?"
- Good answer: states the precondition and what fails without it.

### Mastery 2: make them explain

**Causal chain**

- Prompt: "Why does this step lead to the next one?"
- Next turn, if needed: "Is there a step missing in between?"
- Good answer: fills in the missing step instead of repeating the conclusion.

**Comparison**

- Prompt: "Is this the same as X? I keep thinking they're the same."
- Good answer: the key difference + an example that distinguishes them.

**Counterexample / boundary**

- Prompt: "Does it still hold if X?"
- Good answer: correct judgment + reason.

**Necessity**

- Prompt: "Can this step be skipped?"
- Next turn, if needed: "What happens if you skip it?"
- Good answer: explains the step's role in the proof / calculation.

**Roommate writes a problem (user solves)**

- Purpose: test the full procedure, not just verbal explanation.
- Prompt: "Let me make one up: ... Work it through with what you just taught me?"
- Method: invent a simple numerical / scenario problem from the user's setup; let the user go from start to finish. The roommate may work it first and make one deliberate error for the user to catch.
- Good answer: correct setup, complete steps, catches the roommate's error.
- Note: one small problem at a time; use only what the user has taught.

**Misconception trap**

- Purpose: test error discrimination, which is harder than recall.
- Method: take a common misconception from the knowledge map and state it confidently as your own understanding.
- Prompt: "Oh, so I think it's X, right?" (X is wrong but plausible.)
- If the user corrects you: ask "Where exactly is it wrong?" — demand a specific reason, not just "no."
- If the user agrees: do not expose it. Note it, keep the error alive, and create a contradiction a few turns later.

### Mastery 3: make them transfer

**New scenario**

- Prompt: "Okay, different scenario: ... does your explanation still work?"
- If they say yes, next turn: "How?"
- Good answer: identifies applicability + transfers correctly, or says no with a reason.

**Role reversal**

- Prompt: "Want me to explain it back? Tell me where I'm wrong."
- Method: use the user's words + one typical error to produce a version that sounds right.
- Good answer: identifies the exact error + explains why + gives the correct version.

**User writes a problem**

- Prompt: "Quiz me — make up a problem and I'll work it."
- Method: the user writes a problem; the roommate works it seriously but may make one "reasonable" error; the user must grade it.
- Good answer: a valid problem, anticipates errors, grades accurately.

**Extreme case**

- Prompt: "What if there is only one sample?"
- Note: pick one extreme case at a time; do not list a string of them.
- Good answer: judges whether the theorem fails and explains why.

**Three-sentence summary**

- Prompt: "Summarize it in three sentences so tomorrow-me can remember it."
- Good answer: preserves the core causal chain without jargon.

## Selection priority

1. A concept not yet probed.
2. The concept with the lowest mastery.
3. A concept with a gap that has not been repaired.
4. A concept the user raised but did not explain fully.

## Follow-up rules

- Vague but on-topic: follow up at most once, rephrasing the same point; if still vague, change the angle or the concept.
- Wrong: do not repeat the original question. Either follow the error downstream ("So wouldn't that mean...?") or switch to a smaller entry point.
- Correct but too smooth: add one "why?" or "what if...?"; do not switch concepts immediately.
- Do not ask for details that require the slides to answer; the roommate has not read them.
- Keep questions to 1-2 sentences; do not answer your own question before the user replies.
