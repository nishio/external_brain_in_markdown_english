---
title: "Zerofill's Linked List"
---

An array is given. I want to scan from the front. I want to delete.

requirement
- If the original sequence is of length N, but the deleted one is of length M, it must be possible to scan it with O(M).
    - The method of assigning dummy values and skipping readings is not acceptable.
- Deletion must be O(1)
    - Packing the elements is not an option.
    - Python list remove is not a good idea.


Prepare a zero-filled array next, prev of the same size as the given array
![image](https://gyazo.com/b47c0b5b99311be04ae196ae96bd02bd/thumb/1000)

When to delete
![image](https://gyazo.com/585a271028f339d5297727f2368c2dbf/thumb/1000)
python

```
prev[pos + 1 + next[pos]] += prev[pos] + 1
next[pos - 1 - prev[pos]] += next[pos] + 1
```


In short [[bi-directional linked list]].
If constructed simply, the initial value would be `next[pos] = pos + 1`, but by having only the difference from that value, it can be initialized with a zero fill.
If you only do deletions, this is fine because you don't need to have absolute addresses. If you also do insertions, a regular two-way list is better.

The first element is the guard. It should not be deleted.
We have not yet considered what would happen if it were deleted.

Random access in index at creation is O(1)

- [[Lists that only delete]]
- [[linked list]]

---
This page is auto-translated from [/nishio/ゼロフィルのリンクトリスト](https://scrapbox.io/nishio/ゼロフィルのリンクトリスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.