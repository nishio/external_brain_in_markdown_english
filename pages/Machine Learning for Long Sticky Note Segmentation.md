---
title: "Machine Learning for Long Sticky Note Segmentation"
---

![image](https://gyazo.com/b94a75c5bb94338cdbccabaa01b0e843/thumb/1000)
- With an approach that estimates for each word whether or not to erase it and whether or not to separate it with the right,
- There's an approach to generate a column containing delimited tokens with BERT or something like that.

I was thinking of the former, because I don't want to make it too heavy to run on a server, but this approach would be ruined the moment I try to support rewriting.

Should we try and not avoid the latter with "it might be heavy?"

What should happen to teacher data?
- So far, we've documented sporadic examples of bad or human-induced splits.
- If you want to put it in BERT, maybe a column of delimited token ticks.
- We thought it would be difficult to express rewriting in the current rule-based version, but we can do string substitution in the preprocessing
- Then after that, it's usually engraved on the token.
- Worst case, only rule-based pre-write can be left in the rule base.

2021/3/29
- Spit out the results of the split with the current rule-based one to a file.
- Put an x on a bad split result and an o on a good split result
    - You don't have to put anything on.
    - The ones with nothing on them can be o as being so-so acceptable.
- At least it's better than the current "failure cases are in the form of memos with no formatting".
- Hopefully the bad splits will be reduced when the rule is modified.
- I want to merge outputs.
- Machine learning?
    - I think it could be within the scope of parameter adjustment.
- Even if we feed BERT in the future, I'd like to wait until after a few hundred data have been collected.
- If you keep the data in this form, you can split it up and use it as teacher data if it does not contain "bad examples".

- I checked the code.
    - JSON output for regression testing to prevent unexpected breakage.
    - This one has a list of "split results."
    - It's a list, so you can't mark "this result is bad".
    - Regression testing itself will continue to be useful
    - You can have a separate ✅ dictionary.
    - Right now it's rule-based, so I'm chopping in order of highest score, but if the score is 0.5 or higher, I'll definitely split it up, and if something is still too long, should I chop it up separately?

- [[Assistance in dividing a long document into stickies: an example of a bad division]]

2021-03-30
- I get the feeling that the type of case particle alone doesn't seem to determine which case particle feels natural to me when I need to split with any of them.
    - I wonder if it depends on the type of case particle next to it and the distance...

---
This page is auto-translated from [/nishio/機械学習で長文付箋分割](https://scrapbox.io/nishio/機械学習で長文付箋分割) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.