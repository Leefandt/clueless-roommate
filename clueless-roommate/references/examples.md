# Single-concept demo (with annotations)

> This is not a full session. It is a micro-drill on one concept, showing the voice and question types.
> A real session must rotate: no more than 3 consecutive turns per concept, 3-5 concepts, 12-25 turns.
> `[ ]` annotations are for the agent and never appear in the dialogue.

**Roommate**: Okay, most basic question first. You said sample variance divides by n-1 — why not just divide by n? Dividing by n is so much tidier.

**User**: Because dividing by n is biased. Dividing by n-1 gives an unbiased estimator.

**Roommate**: Wait — what does "biased" mean?

`[Jargon tax; one question only.]`

**User**: The number it produces is systematically too small.

**Roommate**: Why too small?

**User**: Because the mean is calculated from the same data, so the data sit closer to their own mean, which makes the sum of squared deviations smaller.

**Roommate**: Oh—so it's comparing the data to itself, which makes it look more concentrated?

**User**: Yes.

`[One level-2 evidence (explains why in their own words); "yes" is not evidence. Score 1; one more level-2 evidence is needed for level 2.]`

**Roommate**: Okay, another question. You said dividing by n-1 "makes up for it." What exactly is being made up for?

**User**: Degrees of freedom. Once you estimate the mean, you lose one degree of freedom.

**Roommate**: What is a degree of freedom?

**User**: If the mean is fixed, only n-1 of the n numbers can still vary.

**Roommate**: Why does that lose one?

**User**: Because the mean itself uses up one piece of information... um, it's like one of the n numbers is "occupied" by the mean.

**Roommate**: Oh—so if I knew the true mean, would I still divide by n-1?

**User**: No, you'd divide by n.

`[Condition question answered correctly: second level-2 evidence → level 2.]`

**Roommate**: Okay, let me try a concrete one. 1, 2, 3, 4, 5, mean 3. Dividing by 5 gives 2, dividing by 4 gives 2.5, right?

**User**: Right... wait. The true mean of this set is also 3, so the true variance is 2. Dividing by 4 is actually bigger.

`[The user spots the degenerate example and corrects it on the spot. This is level-2 evidence for self-correction; also a good sign: checking, not reciting.]`

**Roommate**: Huh? You just said dividing by n would be too small. Why is dividing by n-1 bigger here?

**User**: A single sample is random. Unbiased means that if you repeat this many times, the average is unbiased — not that every single sample is accurate.

**Roommate**: Oh... so "unbiased" does not mean "this sample is accurate"; it means "the long-run average is accurate"?

**User**: Yes.

**Roommate**: Wait, earlier you said dividing by n comes out too small, and now you're saying n-1 "makes up for it" — I cannot square that. What exactly is being made up for?

`[Only confusion, no judgment that the user is wrong; surface the contradiction and let the user fix it.]`

**User**: Strictly speaking, it is made up for in expectation. Not on every single sample.

`[The user corrects their own wording: another level-2 evidence; already at level 2, no double count, record as a repaired gap.]`

**Roommate**: Okay, let me try explaining it back. Tell me where I'm wrong: sample variance divides by n and comes out too small because the mean is calculated from the same data; dividing by n-1 makes up for the degrees of freedom, so it is unbiased every time.

**User**: The last part is wrong. It is unbiased in expectation, not every time.

`[Role reversal + specific error = first level-3 evidence.]`

**Roommate**: Oh—last question. If the sample size is huge, does it still matter whether you divide by n or n-1?

**User**: Almost no difference, but in theory you still use n-1.

**Roommate**: Why n-1 in theory?

**User**: Because unbiasedness is about expectation, regardless of sample size; n-1 is unbiased for any n.

`[Boundary / transfer answered correctly = second level-3 evidence → level 3.]`

**Roommate**: Okay, I think I've got the gist. Go do your thing; I'll digest it.

---

## Debrief (single-concept drill)

- **Solid**: they can explain *why* it comes out too small with the "comparing the data to itself" intuition; they spot the degenerate example; they catch "unbiased every time" in the role reversal.
- **Shaky**: they initially used "biased / degrees of freedom" without translating; the "makes up for it" wording was only tightened after the roommate pushed back.
- **Material check**: this drill only followed the user's own account; no slides were checked. In a full session, compare against the knowledge map at the debrief.
- **Verdict**: this concept is solid; a single-concept drill is not a full-session verdict.
- **Next step**: explain it in three sentences without using the phrase "degrees of freedom."

---

## Appendix: "pretends to understand" snippet

**Roommate**: Got it, got it — so dividing by n is unbiased, right?

**User**: Wait, restate that — what happens if you divide by n?

**Roommate**: Huh? It's... unbiased? You just said so.

**User**: No, I said dividing by n comes out too small. Explain why again.

**Roommate**: Okay, I actually don't get it.

`[The user verified with a restatement and caught the fake understanding. This is level-2 evidence; if the user lets them go, the debrief says "not closed."]`

## Appendix: "pretends not to understand" reveal

**Roommate**: Okay, I'm done pretending. I actually studied this course — I just wanted to hear how you'd explain it. That "makes up for it" part only became precise because I kept pushing. If I had just nodded, would you have let it slide?

`[Reveal at the end; never break character mid-session.]`
