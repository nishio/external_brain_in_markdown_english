---
title: "linkSuggest0907"
---

[[pLinkSuggest]]
- Algorithm that performs the equivalent of a tree search without constructing a tree
    - Must be able to "determine if they are ancestors" and "obtain a recent common ancestor."
    - For suffix arrays
        - Consider the position-length pair to be the top of the tree.
        - Length comparisons are substituted to determine if they are ancestors or not,
        - To obtain the most recent common ancestor, we can use the values previously calculated in the construction of the LCP array, which can be done in O(1).
- I can do a post-order tour of the tree nodes.
    - Because it cannot be traced back to the child,
    - Information on "which document it appeared in" needs to be communicated to the parent during the patrol process.
    - If the number of occurrences per document ID is calculated, it would be good to determine the keyword-like quality using the concentration of occurrences, and to cut off words with too high frequency using DF.

- Now the word is an object, and it has a document ID and its own location.
    - but
        - This is then grouped together into multiple documents, converted into a word ID, and the document ID can be pulled by its position in the grouped column.
        - Then we can SAIS that long string together and do a frequency count.
    - I'd like to put the frequency counts aside and implement the same functionality as we have now and compare speeds.

- I wonder if it needs a twist that the existing algorithm is "statistics within a given set of documents" while this one is "statistics between new documents and the existing set of documents".
    - Maybe it would be better to convert it to a suffix tree?
    - It seems to me that a top-down search would have a smaller search area?
    - Can I mix and match and build SA and look at the nodes before and after?

---
This page is auto-translated from [/nishio/linkSuggest0907](https://scrapbox.io/nishio/linkSuggest0907) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.