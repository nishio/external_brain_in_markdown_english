---
title: "Conflict between motion extraction and question naturalness determination"
---

2021-02-09 [[pKeicho-done]] [[pKeicho]]
The context before and after the key phrase is retrieved in "[[Determining the naturalness of a question]]".
When a keyphrase containing a verb is extracted by "[[Motion Extraction]]", it may have been converted to its original form, in which case a string search for the keyphrase from the previous input will not find a match.

solution
- A: Change string-based processing to word-based processing.
    - Teacher data created in the past will no longer be available, so training data must be created again.
- B: Putting the information of "not found" on the feature
    - New situations can be taken care of while preserving past teacher data.
    - However, none of the study data on this new situation is available to begin with
- C: Upstream with a naturalness of 0.5 when an exception occurs in feature extraction.
    - If there is no data, I'll just leave it at 0.5.

I'll go with C this time.

Devise features at a time in the future when more data will be available.
- Active learning with existing data while accumulating data for new feature calculation methods
- Discard old format data when new data is accumulated.

---
This page is auto-translated from [/nishio/動きの抽出と質問自然度判定の衝突](https://scrapbox.io/nishio/動きの抽出と質問自然度判定の衝突) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.