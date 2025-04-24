---
title: "Bifurcated search for time-consuming causes"
---

I was writing code to remove tags from [[Wikipedia]] using regular expressions, but it takes a long time for some pages.
What part of the input is the problem?

Determine an appropriate timeout period and do a [[dichotomous search]] on "whether the function times out or not".
You can use [[multiprocessing]] to determine whether or not to time out.

python

```
def binarySearchBadInput(s):
    import multiprocessing
    left = 0
    right = len(s)
    while left + 1 < right:
        print(left, right)
        mid = (left + right) // 2
        p = multiprocessing.Process(target=cleanWikiTag, args=(s[mid:], ))
        p.start()
        p.join(1)
        if p.is_alive():
            left = mid
        else:
            right = mid
    return s[left:]
    
print(binarySearchBadInput(getOnePage(2764)["text"])[:100])
```


Output Example
:

```
0 14161
0 7080
0 3540
0 1770
0 885
442 885
...
878 881
879 881
<! --- elevation(<ref>) ---> ...
```


I see..., `<! -- ... -->` must be processed before `<ref>... </ref>` needs to be processed before `<ref>...

---
This page is auto-translated from [/nishio/時間のかかる原因を二分探索](https://scrapbox.io/nishio/時間のかかる原因を二分探索) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.