# Complete teach-back + cross-examination demo (with annotations)

> This is the skeleton of a full session: 2A teach-back → 2B cross-examination → 3 debrief.
> A real session has 3-5 concepts and 12-18 cross-examination turns; this one goes deep on a single concept so the structure is easy to see.
> `[ ]` annotations are for the agent and never appear in the dialogue.

## 2A Complete teach-back

**Roommate**: Okay, don't worry about me for a second. Take 5-10 minutes and explain this whole thing — from "why sample variance divides by n-1" to "when it holds" — as if I've never seen it. If you get stuck, skip it and keep going. Say "done" when you're finished.

**User**: Sample variance measures how spread out a sample is. If we knew the true population mean μ, the variance would be the sum of squared deviations from μ divided by n. But in practice μ is unknown, so we use the sample mean x̄. The problem is that the sum of squared deviations from x̄ comes out too small — because the data are always closer to their own mean than to the true mean. So dividing by n underestimates the population variance. To fix it, we divide by n-1: estimating x̄ uses up one degree of freedom, so only n-1 of the n data points carry independent information. That gives an unbiased estimator of the population variance. For large samples the difference between n and n-1 is tiny, but in theory we still use n-1.

**Roommate**: Done?

**User**: Done.

`[Do not interrupt the teach-back. The user covered the definition, why /n is too small, degrees of freedom, unbiasedness, and large samples. But "unbiased" was only named, not explained; "the data are always closer" is an overstatement. S: definition 2, bias 2, degrees of freedom 2, unbiased 1, large sample 2.]`

## 2B Cross-examination

**Roommate**: Okay, I wrote down a few things. One at a time. First: you said "the data are always closer to their own mean than to the true mean" — I can't make that work. Give me actual numbers; is every point closer?

`[Attack 1: quote + example. Anchor = the overstatement in the teach-back.]`

**User**: Strictly, it's not every point; the sum of squares is smaller overall. For example, 1, 2, 3, 4, 5, mean 3. If the true mean is also 3, every point is equally close to both means. But if the true mean is 4 and the sample mean is 3, the sum of squares would... hmm, I'd have to compute it.

`[The user notices the "every point" wording is imprecise and starts repairing it. Good sign.]`

**Roommate**: Don't compute it yet. Just tell me: why is the sum smaller overall?

`[Attack 1 follow-up: pull the user from the numbers back to the causal explanation.]`

**User**: Because x̄ is computed from this same batch of data, the data get "pulled" toward it, so the sum of squared deviations is smaller than if we used the true μ. On average, not for every point.

`[Attack 1 resolved: repaired the overstatement and gave the right causal story. D=2.]`

**Roommate**: Second: you said n-1 is unbiased. What does "unbiased" actually mean? Does it mean accurate every time?

`[Attack 2: jargon / definition. Anchor = the teach-back only named it. S=1.]`

**User**: Not every time. It means if you repeat this many times, the average is unbiased — unbiased in expectation.

**Roommate**: Oh—so "unbiased" doesn't mean "this sample is accurate"; it means "the long-run average is accurate"?

**User**: Yes.

`[The user explained "unbiased" (level-2 evidence), but only after being asked: mark prompted. S=1, D=2.]`

**Roommate**: Third: you never mentioned this — if I knew the true mean μ, would we still divide by n-1?

`[Attack 3: coverage omission / condition. Anchor = a condition in the knowledge map that the teach-back omitted.]`

**User**: No, we'd divide by n.

**Roommate**: Why?

**User**: Because n-1 is there to make up for the degree of freedom used to estimate μ; if μ is known, there's no loss.

`[Condition answered correctly + explained why: D=2, and this was never in the teach-back, so mark prompted.]`

**Roommate**: Fourth: you said "degrees of freedom." I don't know what that means. Where exactly does one go missing out of n?

`[Attack 4: jargon.]`

**User**: Once the mean is fixed, only n-1 of the n numbers can still vary; the last one is determined by the mean.

`[Jargon explained clearly: D=2.]`

**Roommate**: Okay, let me explain it back the way you did. Tell me where I'm wrong: dividing by n comes out too small because the data are closer to the sample mean; dividing by n-1 makes up for the degrees of freedom, so it's unbiased every time.

`[Attack 5: role reversal.]`

**User**: The last part is wrong. It's unbiased in expectation, not every time.

`[Specific error identified: level-3 evidence for D.]`

**Roommate**: Last one: if the sample size is huge, does it still matter whether you divide by n or n-1?

`[Attack 6: transfer / boundary.]`

**User**: Almost no difference, but in theory n-1 is still unbiased.

**Roommate**: Why n-1 in theory?

**User**: Because unbiasedness is about expectation, regardless of sample size.

`[Transfer answered correctly: second level-3 evidence for D.]`

**Roommate**: Okay, I think I've got the gist. Go do your thing; I'll digest it.

## 3 Debrief

- **Teach-back coverage**: definition, why /n is too small, degrees of freedom, and large samples were all explained spontaneously; "unbiased" was only named, not explained; "the data are always closer" was an overstatement.
- **Defense under attack**: repaired the "always closer" claim; "unbiased" and the known-μ condition were only filled in after asking (`prompted`); role reversal and transfer held.
- **Material check**: this demo only followed the user's own account; no slides were checked. In a full session, compare against the knowledge map at the debrief.
- **Verdict**: Mostly solid ("unbiased" was prompted and not explained in the teach-back, so it cannot be "Solid").
- **Next step**: explain "unbiased" in three sentences without using the word "expectation"; next time, include one concrete numerical example in the teach-back.
