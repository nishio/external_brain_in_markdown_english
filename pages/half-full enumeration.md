---
title: "half-full enumeration"
---

Example 1
- I have a sequence of 4 numbers of length N=4000. We want to count the combinations where the elements are selected one by one and the sum is zero.
- If you naively search the whole area, you will not make it in 4000^4.
- Preprocessing: Enumerate the sum of all combinations in 4000^2 for the two sequences of numbers. Let X denote this.
- The whole search is done in 4000^2 for the remaining two sequences. The sum of the two values is s.
- Find the -s from X.
    - Sort X [[dichotomous search]] : O(N^2logN) in whole
    - When the value range of the sum is narrow, [[frequency table]] can be set to a constant order and O(N^2)

Example 2
- question (e.g. on a test)
    - Select some from a set of size N=40
    - The elements of the set are goods of weight wi, value vi
    - The weight of the selected item must not exceed W
    - Maximize the sum of your values.
    - w and v can take values up to 10^15
    - [[backpack]] Problem. Cannot be solved by DP due to large range of values.
- 2^40 is too big to search all of them; 2^20 can enumerate them all. Let X denote this.
- Do a full search in 2^20 for the other half. If the sum of weights is w, then the problem is to find the largest v from X whose weight does not exceed w-w.
        - [[Find the conditional maximum in logarithmic order]]
    - 2^(N/2)N as a whole
- When the range of values is small, O(NW) can be calculated by DP using the "weight→value" table.

[https://algo-logic.info/split-and-list/](https://algo-logic.info/split-and-list/)

[https://www.hamayanhamayan.com/entry/2018/01/06/112704](https://www.hamayanhamayan.com/entry/2018/01/06/112704)
    - [[Maximum Creek]]
    - [[maximal independent set]]

---
This page is auto-translated from [/nishio/半分全列挙](https://scrapbox.io/nishio/半分全列挙) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.