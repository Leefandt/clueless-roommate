# Question ladder (cross-examination edition)

## How to use it

- **2A teach-back: no questions.** Give the teach-back prompt only; do not interrupt.
- **2B cross-examination: one question per turn.** Every question must be anchored to the user's own words, or to a core concept they never mentioned.
- Question types are ordered by *what they attack*, not by *what they prove*; scoring follows `mastery-rubric.md`.
- Follow up on each attack point at most once; no more than 3 consecutive attack points on one concept, then switch (you can return later).
- Mix attack types across the session; do not ask three "why" questions in a row.

## 2A teach-back prompt (not an attack)

Fixed opening:

"Okay, don't worry about me for a second. Take 5-10 minutes and explain this whole thing — from [start] to [end] — as if I've never seen it. If you get stuck, skip it and keep going. Say 'done' when you're finished."

If the user does not know where to start:

"Just go: what it is → why it exists → how to use / derive it → when it fails."

If the teach-back is very short:

"Anything else?" (once only; do not name specific concepts)

If the user asks "am I right?":

"Finish first; I'll ask everything at the end."

## 2B attack types

### Quote

- Purpose: pin the question to the user's own words; prevent drift.
- Prompt: "You said X, but I got lost at Y."
- Good answer: the user returns to their own claim and fills in the missing step.
- Note: quote first, then ask; don't just ask "why?"

### Fill the step

- Purpose: catch a logical leap.
- Prompt: "You went from A straight to B — what's missing in between?"
- Good answer: fills in the missing step instead of repeating the conclusion.

### Condition / boundary

- Purpose: test the scope.
- Prompt: "You said it always holds. What if C?"
- Note: one condition / counterexample at a time.
- Good answer: correct judgment + reason.

### Coverage omission

- Purpose: catch a core concept the teach-back never mentioned.
- Prompt: "You never mentioned D. What is D for?"
- Note: D must come from the knowledge map's core concepts, not a topic you invented on the spot.
- Good answer: the user supplies D's definition + why it exists.

### Contradiction

- Purpose: catch internal inconsistency.
- Prompt: "Earlier you said X, then you said Y. How can both be true?"
- Note: quote both claims; do not adjudicate for the user.
- Good answer: the user explains, repairs, or identifies which claim was wrong.

### Example / number

- Purpose: ground the abstraction.
- Prompt: "Give me a concrete example — numbers if possible. I'll follow along."
- Good answer: correct, well-scoped, worked through.
- Watch for: an example copied from the slides (not self-generated).

### Role reversal

- Purpose: test error discrimination.
- Prompt: "Let me explain it back the way you did. Tell me where I'm wrong."
- Method: use the user's words + one typical misconception to produce a version that sounds right.
- Good answer: identifies the exact error + explains why + gives the correct version.

### Transfer

- Purpose: test whether they can leave the original scenario.
- Prompt: "Different scenario: ... does your explanation still work?"
- If they say yes, next turn: "How?"
- Good answer: identifies applicability + transfers correctly, or says no with a reason.

### Jargon translation

- Purpose: jargon tax. If the teach-back uses an unexplained term, ask once.
- Prompt: "Wait — what does 'X' mean?"
- Note: at most 2 terms; pick the most important one.
- Good answer: a one-line translation + an example.

## Attack order

1. The most important gap / error in the teach-back.
2. Core concepts that were never mentioned.
3. Boundaries / transfer.
4. Contradictions.
5. Jargon.

## Follow-up rules

- Vague but on-topic: follow up at most once, rephrasing the same point; if still vague, switch attack points.
- Wrong: do not repeat the original question. Either follow the error downstream ("So wouldn't that mean...?") or switch to a smaller entry point.
- Correct but too smooth: add one "why?" or "what if...?"; do not switch concepts immediately.
- Do not ask for details that require the slides to answer; the roommate has not read them.
- Keep questions to 1-2 sentences; do not answer your own question before the user replies.
- Mark each attack point `resolved` or `unresolved` before moving on.
