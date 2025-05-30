---
title: "Fifth Algorithm Practical Skills Test"
---

[[PAST5]] [[PAST202012]]  [[Algorithm Practical Skill Test]]
[Fifth Algorithm Practical Skills Test - AtCoder](https://atcoder.jp/contests/past202012-open)

It was 70 points, intermediate level.
The first time I took the test, the third time, and the following time, the fourth time, I was in the intermediate level, and I was hoping to get to the advanced level this time [[PAST Past Question Practice 202012]], but my score was rather low.
![image](https://gyazo.com/85686f0f9aea6837a7ee2e7a46ef64d5/thumb/1000)

I'll write down my thoughts during the exam. I can't check the question texts and explanations because they have not been published as past exams yet. Detailed solutions to individual questions will be written separately after they are available.
Past questions have been released and will be done in order.
- Explanation of E~.
    - [[PAST5E]]
    - [[PAST5F]]
    - [[PAST5G]]
    - [[PAST5H]]
    - [[PAST5I]]
    - [[PAST5J]] AC
    - [[PAST5K]]
- [[-Confirm the cause of TLE in H]].
- [[-Not seeing J's commentary, I'll rewrite it when I'm done]].
- Confirmation of LMNO's commentary
    - [[PAST5L]]
    - [[PAST5M]]
    - [[PAST5N]]
    - [[PAST5O]]

A〜D
- I solved it nonchalantly, without making any particular notes.

[E - stamp](https://atcoder.jp/contests/past202012-open/tasks/past202012_e)
![image](https://gyazo.com/96531e5dba571b147d99cf54cec7253f/thumb/1000)
- Just do a simple search for all of them.
- To search the whole area without overflowing, [[sentry]] is added to the non-stamped side to cover the width of the stamp.
- The code itself to attach the guard was already written.
        - [[Putting a guard on when loading a map]]
- I didn't expect rotation, so I wrote a new one this time.
- The length and width are exchanged when rotating, only the side of the stamp should be exchanged, but I got it wrong and WA'd.

[F - A Touch of Fiction](https://atcoder.jp/contests/past202012-open/tasks/past202012_f)
![image](https://gyazo.com/82689f73ea9cacb95a4584a9b4618956/thumb/1000)
- 2 ** 14 == 16384
- 14 * 13 * 12 == 364
- This is a good size to explore all
- WA by misunderstanding the problem conditions.
    - Not "the number of chemicals already mixed" at a touch of a button.
    - Nor is it "the number of rules in a state of flux."
    - Size of the set of "chemicals that have not yet been added to the set of rules of a state of flux".

[G - Snakes](https://atcoder.jp/contests/past202012-open/tasks/past202012_g)
![image](https://gyazo.com/3790c397c786b793094fb8a7167295bd/thumb/1000)
- Create a graph and DFS a "path through all vertices" starting at each vertex.
- When the length is 1, it is the corner case that is not graphed

So far, it has been one hour and 25 minutes. Here I decided to look through all the remaining questions first. The following "Initial Discussion" is it.

[H - Conveyor](https://atcoder.jp/contests/past202012-open/tasks/past202012_h)
![image](https://gyazo.com/f0e4b1e3e154ed74f38484fa80a6fd5a/thumb/1000)
- Initial Considerations
    - Determine if it can be moved
    - Construct a graph and DFS "can you reach the goal" from each starting point
    - 10^6 vertices, okay?
    - Many starts, one goal.
        - → [[Make the Goal the Start]]
    - The graph is made with inverted edges, and the search is made for reachable vertices with the goal as the starting point.
        - Each vertex has only 4 edges at most, so O(N) will do.
    - Consideration complete

[I - Evacuation Plan](https://atcoder.jp/contests/past202012-open/tasks/past202012_i)
![image](https://gyazo.com/01513f650068f7946cc04b839444666a/thumb/1000)
- Initial Considerations
    - You can only move from higher elevations to lower elevations.
        - directed graph
    - Lots of goals.
        - Bundling around cost 0?
                - [[One Goal.]]
        - One to all [[Dijkstra method]] from each goal?
        - Let's do the latter, and if not, let's do the former.
    - Consideration complete

[J - long long string](https://atcoder.jp/contests/past202012-open/tasks/past202012_j)
![image](https://gyazo.com/a30032ca3d2b05fc4156aed0ed48365c/thumb/1000)
- Initial Considerations
    - No naive output.
    - If we pre-calculate the size of the block for each iteration, we can solve the problem by gradually taking the value of the query as a remainder.
    - Consideration complete

[K - Targeted](https://atcoder.jp/contests/past202012-open/tasks/past202012_k)
![image](https://gyazo.com/6479e86b1c951eb67508032cd297072f/thumb/1000)
- Initial Considerations
    - The remaining target is 2^16
    - bit DP] since the domain of definition is a subset of the set
    - Use expected value as value range [[Expected DP]].
        - The same terms appear on the left and right side of the preceding paragraphs and need to be sorted out and eliminated.
    - Consideration complete

[L - T erase](https://atcoder.jp/contests/past202012-open/tasks/past202012_l)
![image](https://gyazo.com/9d3a4c94bb870908ddb459d35f181fb0/thumb/1000)
- Initial Considerations
    - There are multiple points of appearance, and the best result may or may not be achieved depending on which one is prioritized for elimination.
    - ![image](https://gyazo.com/b7c90ebc80943d64f71cf6ecc519c5df/thumb/1000)
    - Hmmm, is there some kind of greedy way of deciding?
    - If there is no overlap, does it make a difference which way you do it from?
        - Still, 33 overlaps at worst; you can't do 33 factorials.
    - I wonder if a non-decisional automaton could handle this in a nice way.
    - hold (e.g. telephone button)


[M - Shipping Bars](https://atcoder.jp/contests/past202012-open/tasks/past202012_m)
![image](https://gyazo.com/d4601d3337d3e2a1f3a3e17ce6c0b8da/thumb/1000)
- Initial Considerations
    - 2^N not to cut, because N is 10^5 or bigger.
    - Will it be a 2N DP?
        - (after neg. verb stem) seeming impossible
    - How about a style that ticks once for maximum length and then moves forward one tick at a time?
        - Shakitori-legal approach, searching only for likely solutions
        - I wonder if the lower limit will gradually increase, and if the search space will become rather small because it is not necessary to search for the area that becomes smaller than the lower limit...

[N - Travel Agent](https://atcoder.jp/contests/past202012-open/tasks/past202012_n)
![image](https://gyazo.com/c0b27c17755f5bd753462bf179457248/thumb/1000)

- Initial Considerations
    - The problem of finding the reachable range by assuming that the edge of the bus has an upper and lower age limit and that the edge exists only when the given age falls within that range.
    - Make the age axis a time axis
            - [[Make one of the two dimensions a time axis.]]
        - Connect at the lower limit and disconnect at the upper limit.
        - Queries are read ahead, mixed and sorted.
    - In [[PAST2N]] it was Range Add, but not this time, what to do?
        - We just need to get the right and left edges of the connected range fast.
        - We can have a phenic tree with the right end and a phenic tree with the left end.
        - Given a position, finding the nearest left edge to the left of it is a binary search of logarithmic order
        - Find the nearest right edge to the right of the left edge you found, and you'll get the range.
        - If the position given in the query is in that range, that's the answer.
    - Consideration complete

[O - Notice](https://atcoder.jp/contests/past202012-open/tasks/past202012_o)
![image](https://gyazo.com/9d380fa7f1c141460e331b7a7e7f8144/thumb/1000)
- Initial Considerations
    - Worst case scenario, whether it's a push or a pull, it's 10^5, so 10^5 queries will break the bank.
    - (Tip: In the case of "push", which changes the recipient's value when a notification occurs, it is not allowed if 10^5 people with 10^5 friends send the notification 10^5 times. Conversely, in the case of a "pull", where you go to check who among your friends sent the notification when you confirm the notification, it is not allowed if a person with many friends confirms the notification all the time).
    - Delay only the processing of people whose friends are on route N or higher.
        - These people are high route N people.
        - Only pull these people x when confirming notification
        - Total number of notifications generated by x with x
        - The total number of routes y has received from x. Highly route n
        - Subtract these two and you get the number of new notifications from x
    - Consideration complete

After a full consideration, there are three hours left.
- I don't understand L at all.
- I think that M, O can be solved, but I think it will be "a pattern that looks solvable at first glance, but when solved, an oversight is discovered".
    - Unlike contests, you don't get a higher rate if you solve harder problems first (rather, your score is lower).
- Let's do it with the policy of solving the puzzles in order from the beginning and then looking back at L again.

What happened next
- H, submitted in 18 minutes, WA, corrected, but it took 3 TLEs and 35 minutes to resolve the issue, so we put it on hold and moved on.
- I, Dijkstra, AC in 9 minutes.
- J, I'm confused when I should have been calm and implemented.
    - After solving one misalignment bug, the sample finally went through after 56 minutes.
    - However, TLE
    - I used to cut out the string that would be the unit of repetition, but I figure I can just wait and see where it starts in the original string.
    - Plus, we'll use 16 minutes and have another TLE, or even an MLE for that matter.
    - What does that mean?
    - For example, when there are a lot of 9s going on, the "size of the repeating block" becomes a very large number, the problem is that I was not aware of this and just did it.
    - In real time, I thought, "Does that mean the policy was totally wrong?" And I gave up.
        - When I woke up after a night's sleep, I realized that the number passed as a query is limited to less than 10^15, so I can terminate the string parsing process when it exceeds that number.
- K, expected DP, AC in 19 min.
- At this point, with 45 minutes left, we're in no condition to challenge L, which has no policy in place, let's resolve H, which is in TLE.
- H, used 30 minutes, TLE 3 more times, and finally AC with 15 minutes left.
    - Rewritten to a style that does not construct graphs explicitly.
    - I made a version of DFS that does not call recursively.

Organized by time
- J is terrible, using 72 minutes and not scoring.
- I spent 80 minutes and finally AC'd H. It's not good.
- The drop off is drastic compared to the I is 9 minutes and the K is 19 minutes.

---
This page is auto-translated from [/nishio/第五回 アルゴリズム実技検定](https://scrapbox.io/nishio/第五回 アルゴリズム実技検定) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.