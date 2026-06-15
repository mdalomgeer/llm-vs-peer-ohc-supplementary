# Pilot Prompt-Variation Example

This file documents one question from the dataset, posed to one model in two wordings. It illustrates the prompt sensitivity that motivated our decision to fix prompts to the original user-posted questions. The post is anonymized. The lab values are retained because they carry no identifying information.

Both variants hold the clinical content and the model constant. Variant A is the original post as used in the study. Variant B restructures the same case and removes two cues: the symptom framing and the clinician's mention of central hypothyroidism. Changing only the prompt isolates the prompt as the source of the difference.

---

## Variant A (original post, as used in the study)

I recently had thyroid levels tested because of numerous hypothyroid symptoms. The results are: TSH: 1.8, Free T4: 0.79 L (0.8-1.7), Free T3: 244 (210-440). Negative on antibodies. My question is, with a low Free T4 should my TSH be higher? My doctor mentioned Central Hypothyroidism and to retest in 4 weeks. What are your thoughts about my levels along with hypo symptoms?

### Model response to Variant A (verbatim, used in analysis)

Hi Lynn,
Your test results and symptoms suggest a complex situation that needs careful evaluation. Normally, when the thyroid hormone levels (Free T4 and Free T3) are low, the pituitary gland releases more Thyroid Stimulating Hormone (TSH) to stimulate the thyroid to produce more hormones. In primary hypothyroidism, you would typically see a high TSH level along with low Free T4.

However, your TSH level is normal, and your Free T4 is slightly below the normal range. This could suggest central (or secondary) hypothyroidism, where the problem lies not with the thyroid gland itself but with the pituitary gland, which may not be producing enough TSH. In central hypothyroidism, you can have low or normal TSH levels despite low thyroid hormone levels.

Your doctor's recommendation to retest in a few weeks is sensible. Thyroid hormone levels can fluctuate, and repeating the tests can provide more clarity. It might also be helpful to assess other pituitary hormone levels to rule out any broader pituitary issues.

Since you are experiencing hypothyroid symptoms, it is important to address these concerns with your doctor. They might consider starting treatment if your symptoms persist and your thyroid function tests continue to suggest an issue. Additionally, discussing any other symptoms that might suggest pituitary dysfunction could be useful.

Keep monitoring how you feel, and make sure to communicate any changes or persistent symptoms to your healthcare provider. They can provide the most accurate advice tailored to your specific situation.

---

## Variant B (restructured, cues removed)

Are these thyroid results normal? TSH 1.8, Free T4 0.79 (range 0.8-1.7), Free T3 244 (range 210-440), thyroid antibodies negative. With a low Free T4, shouldn't my TSH be higher?

### Model response to Variant B (verbatim)

Your labs are mostly normal except for a very slightly low Free T4.
You're correct that in classic primary hypothyroidism, a low Free T4 should usually raise TSH. Since your TSH is normal at 1.8, this pattern is not typical primary hypothyroidism.
Common explanations:

* Normal lab variation. Your Free T4 is barely below range.
* Temporary suppression from illness, stress, low calories, poor sleep, or medications/supplements.
* Less commonly, central hypothyroidism, where TSH stays "normal" despite low thyroid hormone.

Your normal Free T3 and negative antibodies are reassuring.
Most doctors would:

* Repeat TSH and Free T4 in 6 to 12 weeks
* Review symptoms and medications/supplements
* Investigate further only if Free T4 stays low or symptoms are significant

By itself, this pattern is borderline, not clearly abnormal.

---

## Observed difference

Holding the clinical content and the model constant and changing only the prompt produced a different response.

The differential emphasis shifted. Variant A carried the poster's own mention of central hypothyroidism, and the model foregrounded central (secondary) hypothyroidism as the leading explanation and discussed further pituitary testing. Variant B removed that cue, and the model listed central hypothyroidism last, under "less commonly," behind normal laboratory variation and temporary suppression.

The overall framing also shifted. Variant A treated the result as a complex situation requiring careful evaluation. Variant B concluded the pattern was borderline and not clearly abnormal.

Personalization differed. Variant A engaged the poster's stated hypothyroid symptoms directly. Variant B, lacking any symptom cue, recommended reviewing symptoms in general.

This example shows how prompt wording shapes the content, the differential emphasis, and the framing of the response, which is why we fixed prompts to the original questions for the main analysis. [Insert the actual codebook scores for each dimension and variant.]

## Reproduction details

- Model and version: [name and version string of the model used here]
- Date queried: [date]
- Settings: default, single standalone interaction, no system prompt, no follow-up
