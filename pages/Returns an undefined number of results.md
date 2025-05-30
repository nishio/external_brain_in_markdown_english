---
title: "Returns an undefined number of results"
---

- Case 1: Return an indefinite number of items from a fixed N, with no duplicates and in no particular order
    - Just make [[Softmax]], which returns 1 out of N, a binary identification of N "to choose or not to choose".
- Case 2: Returns indefinite number of items from fixed N with duplicates and in order
    - Introduced N+1th indicating EOS
    - [[RNN]] configuration and repeat until EOS
- Case 3: Return N indefinite A-dimension vectors from N indefinite A-dimension vectors, with no duplicates and in no order
    - Learning to map from dimension A to dimension D
    - Construct an RNN that produces an indefinite number of D-dimensional outputs in the manner of Case 2.
    - Binary identification of "to select or not to select" by inner product between D-dimensional outputs
- Case 4: Selecting a subset of a set
    - This is equivalent to returning an indefinite number of elements from the set in no overlap and in no particular order.
        - That is, a binary identification of "to choose or not to choose" for each
        - Case 1 if the set size is fixed, Case 3 if not.
- Case 5: What if I want to select an indefinite subset from a set?
    - If the set is small enough, enumerating subsets leads to case 1.
        - It will be 2^N enumerations.
    - If the set size is fixed and the subset columns are ordered, then we can turn case 1 into the RNN configuration of case 2.
        - Case 1 is a configuration that produces an N-dimensional vector, so we can make it an RNN that stops softmaxing it.
    - What if the subset columns are unordered?
        - Hmmm, difficult
            - Is it a reasonable option to define [[order]] to sort the teacher data?
- Case 6: To select an indefinite number of "indefinite, duplicate, ordered" columns from a set
    - Just introduce an N+2th to represent the element delimitation and make it an RNN.
    - In unordered case
        - It would be good to introduce an order

---
This page is auto-translated from [/nishio/不定個の結果を返す](https://scrapbox.io/nishio/不定個の結果を返す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.