---
title: "ppoi improvement plan"
---

- [[ppoi improvement 2021-02-05]]

2018-10-24
[[ppoi]]'s suggestions for improvement, I'll note them here because it's distracting if I start fixing them while I'm using it.

- I don't understand why you want me to put unknown.txt.
    - I don't know what exactly you're going to do.
    - OCR'd data for 5 books cat 5 OCR'd scanned PDFs of book cuttings.
    - `$ wc unknown.txt `
    - >  35203  110327 2069652 unknown.txt

python

```
>>> lines = open("unknown.txt").readlines()
>>> lines = [line for line in lines if line != "\n"]
>>> len(lines)
25762
>>> open("unknown.txt", "w").writelines(lines)
>>> from collections import Counter
>>> c = Counter()
>>>> for line in lines:
        c.update(line)
>>> c.most_common(100)
...
>>> len(c)
2851
>>> len([1 for k in c if c[k] > 9])
1513
>>> open("chars.txt", "w").write("".join([k for (k, v) in c.most_common() if v > 9]))
1513
```


- (Future feature to be added) It says to put at least one positive and one negative at initialize, but you don't have to put them, you can just assume that "if no data is entered for both sides, then everything is 0.5" and proceed to active learning.
    - done in  [[ppoi improvement 2021-02-05]]
- (consideration) I assume it's supposed to be run on the command line, but it could have been run on ipython?
    - Can ipython take input?
- I don't think you can tell them to put ppoi/unknown.txt.

Since it is an OCR-ized judgment this time
:

```
$ cat ppoi/positive.txt
|11111'「 11
$ cat ppoi/negative.txt
Without good interviews, no matter how deftly you put them together, you will never know how to reach a good decision.
```


Change feature creation in user.py
python

```
CHARS = open("chars.txt").read()
def make_features(s):
    "take a string, return np.array"
    x = np.array([s.count(c) for c in CHARS], dtype=np.float)
    # normalize                                                                                                                            
    x =	x / x.sum()
    return x
```


It would be nice to have undo in case of wrong input during active learning
- Now I have to open and edit two files.

During active learning, you want to add more clusters.
- In this case, besides Yes/No, there's also "This is too short to make a decision.

---
This page is auto-translated from [/nishio/ppoi改善案](https://scrapbox.io/nishio/ppoi改善案) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.