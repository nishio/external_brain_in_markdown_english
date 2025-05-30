---
title: "ABC170 E"
---

[[ABC170]] Issue E Smart Infants
200,000 numbers move around 200,000 times in a set of 200,000 numbers.
In this case, find the minimum value of the "set maximum" for each move [problem](https://atcoder.jp/contests/abc170/tasks/abc170_e).


Thoughts during the contest
Of course, if we did O(N) for each set for each move, we would TLE.
You want to quickly retrieve the minimum value, so [[heapq]] [[heap queue]].
[Prioritized queue - Wikipedia](https://ja.wikipedia.org/wiki/%E5%84%AA%E5%85%88%E5%BA%A6%E4%BB%98%E3%81%8D%E3%82%AD%E3%83%A5%E3%83%BC)
Is it?

However, as numbers are moved, values other than the minimum may be removed from the "set of maximum values". Example: {1}, {2}, {3} → {1}, {2, 3}, {}
Hmmm, a binary search against a sorted array to find the desired one... no, an add/delete to the array is O(N), so a repeated add/delete attack would make it a TLE.

Lower the cost of adding and deleting by making it a linked list... No, that makes it O(N) to find objects to delete... So make it a bi-directional list and index each object: ？？？？

Solution Discussion section. [multiset - C++ Reference](http://www.cplusplus.com/reference/set/multiset/)
[Equilibrium binary search tree - Wikipedia](https://ja.wikipedia.org/wiki/%E5%B9%B3%E8%A1%A1%E4%BA%8C%E5%88%86%E6%8E%A2%E7%B4%A2%E6%9C%A8)
I see...I tried to make O(1) out of O(N), and it was "if you make that one stand up, this one won't stand up", but should I make it O(logN) in general? I understand the direction.

So what's the specific implementation... hey, someone's using heapq?
[https://atcoder.jp/contests/abc170/submissions/14361676](https://atcoder.jp/contests/abc170/submissions/14361676)
I see. The cost of removing elements other than the head of the heap queue is high, but it's okay if we don't remove them; instead, we can add a mechanism to skip reading them.
- People away from the set are not removed if they are not at the front of the line.
    - Remove "the same person" and "the person who is in the other set at the moment" at the time of looking for the next person when the first person is removed.
- The "heap queue of maximum score per set" also does not remove old elements when updating
    - Instead, for each set, record "the time you last updated your maximum score".
    - When the first element is retrieved for output, discard it if it is old data.

So the code I wrote with reference to it became AC.
[https://atcoder.jp/contests/abc170/submissions/14371172](https://atcoder.jp/contests/abc170/submissions/14371172)

impressions
- I'm not convinced that this doesn't TLE...

I brought the appropriate AVL tree implementation and replaced it.
→ Code is simplified, but TLE
The order should be O(logN), but the constant times larger?

See 5 from the fastest PyPy implementers
- Four people heapq to have individual sets. the number is so large that tree construction is probably avoided because of the overhead. The approach of skipping reads instead of doing deletions seems to be widely used. Only one person was using a set, or hashmap approach. A surprising loophole.
- There are 3 [[segment trees]], 1 heapq, and 1 [[fennic tree]] to have the largest set of values. The Fennic tree looks interesting, but I'm inclined to be able to use the segment tree for now.

- [https://atcoder.jp/contests/abc170/submissions/14369529](https://atcoder.jp/contests/abc170/submissions/14369529)
    - Two heapq to store numbers in and out of the set
    - Find the minimum value in a segment tree
- [https://atcoder.jp/contests/abc170/submissions/14332420](https://atcoder.jp/contests/abc170/submissions/14332420)
    - I'm using shift to pack numbers without tuples.
    - Put in heapq, remove away person at first acquisition
    - The set of maximum values is also put into heapq
    - If the person with the smallest value is not the largest value in the set to which the person with the smallest value belongs, skip it.
        - Is that what you want?
- [https://atcoder.jp/contests/abc170/submissions/14338427](https://atcoder.jp/contests/abc170/submissions/14338427)
    - Put in heapq, remove away person at first acquisition
    - Put the maximum value of the source and destination into the segment tree
    - His segmented tree code is easy to read.
- [https://atcoder.jp/contests/abc170/submissions/14349092](https://atcoder.jp/contests/abc170/submissions/14349092)
    - Representation of a set by a set (set)
    - The maximum value of a set is normally calculated by max
        - And that doesn't make it TLE?
            - I simply imitated it and got a TLE in a test case such as handmade06, which is densely packed in a single set.
            - If you read carefully, there may be a good twist.
            - The unique thing about this one is that it only includes the rate, whereas other heapq approaches include the (rate, person ID) pairs.
    - The maximum value is put in the segment tree.
- [https://atcoder.jp/contests/abc170/submissions/14360320](https://atcoder.jp/contests/abc170/submissions/14360320)
    - Multiply [[coordinate compression]] against rate, why?
    - Sets are represented by heapq
    - The set of maximal values is a Binary Indexed Tree( [[Fennic tree]] )
        - Efficient updating
        - Coordinate compression contributes to reducing the size of the tree

based on this
- I expressed a set by [[heapq]], and then created its minimum value by [[segment tree]] (heapq is OK, but for the sake of study), and came to AC while falling into the trap of [[TLE on standard input/output]].


---
This page is auto-translated from [/nishio/ABC170 E](https://scrapbox.io/nishio/ABC170 E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.