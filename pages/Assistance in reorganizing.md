---
title: "Assistance in reorganizing"
---

- The reason [[hierarchical classification]] falls apart is that it should update the classification method when something appears that doesn't fit the first classification method, but it doesn't do that,
Scrapbox's philosophy that "that's why all hierarchical classification is out of order and shouldn't be done" is going a bit too far,
The plain "[[Container Metaphor]]" is easy for many people to catch on to, and I don't think it's right that kintone should be "there is no such thing as space, all posts are flat".
If [[rearrange]] is systematically supported when the container metaphor is broken, then there is no problem doing hierarchical classification.

[https://twitter.com/nishio/status/1334051841680699392](https://twitter.com/nishio/status/1334051841680699392)
- I am beginning to feel that "support for reorganizing information" is needed, further developed from the discussion the other day, so I will write a series of posts about it.
- The story of "hierarchical classification will eventually fail," and even if that were true, "we should not do hierarchical classification at all" is not true, and there is a logical leap here.
- There were two major causes for the breakdown of hierarchical classification. (1) the appearance of items that cannot be classified well using the classification method assumed in advance, and (2) discrepancies in classification methods when used by multiple people.
- If the former is also seen as "a discrepancy between past and new classification methods," this is "a problem with a system that can only have one classification method.
- Because there is only one way to classify information, when information that does not fit well is found, it is necessary to "discard the past classification method and reclassify it using the new method," which most people find troublesome and force information into the old classification method.
- Reclassification" is not done because the cost of "reclassification" is too high. If this is the case, why not design a system that facilitates reclassification, or a system that supports reclassification?
- For example, when "something you don't know where to put" appears, it is often put in an appropriate place because the user feels pressure to "put it somewhere right away. To prevent this, we should prepare a "place to put things you don't know where to put" in advance.
    - This is a common operation in comic book cafes. It is better to put them in the category of "unclassified items" than to ignore the classification and put them in an appropriate place.
- Next, we need assurance that "reclassification" will not destroy anything. What is wrong with simple hierarchical classification by folders and files is that if they are moved to a different location after reorganization, they will not be found in their original location. The system should be designed to take care of this.
- For example, a system of container metaphors in which "tags" are virtual folders and items with those "tags" are shown in them.
- If you move file X from folder A to folder B, "X that should have been in A is gone!" However, even if tag B is added to file X with tag A, it will not lose its "virtual state of being in A". With this guarantee, you can add tags with peace of mind.
- The two tools I have given so far are not enough at all. For example, if one person puts X in A and another person moves it to B, saying "it is wrong that this is in A," if X is gone from A, the person who thinks it is in A is lost, and if it is not gone, the expression of the intention "it is wrong that it is in A" is not possible.
- One solution is to add a "trash box" to A that contains "deleted or moved items from A". Another solution is to search for "items that were in A in the past".
- Just as it is difficult to determine an appropriate classification method in advance for hierarchical classification, it is also difficult to determine appropriate tagging criteria in advance for tagging. As a result, a single tag may appear on 100 pages, making it difficult to list them.
- It is natural to think, "If all occurrences of the word X are made into tags, it will be no different from the search results with X, so you should not do that.
- An analogy to software development is that it is difficult to properly design in advance what references what. What to do, then, is to "refactor when inconveniences become apparent. Refactoring means "rewriting the current functionality so that it does not break.

---
This page is auto-translated from [/nishio/整理し直すことの支援](https://scrapbox.io/nishio/整理し直すことの支援) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.