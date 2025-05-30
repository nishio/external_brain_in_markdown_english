---
title: "Right-branch decomposition of ordered trees"
---

![image](https://gyazo.com/593c51247733e3ea85187bbd4d3dd6b0/thumb/1000)
- ref. "A Fast Algorithm Using Suffix Arrays for the Partial Word Counting Problem" [PDF](http://www-ikn.ist.hokudai.ac.jp/mthesis/H11_tohru_kasai_mastersthesis99_feb1999.pdf).

- All search in depth-first, return-order order in the suffix tree without explicitly constructing a [suffix tree
    - This "without explicitly building the tree" is important
    - If the tree is already constructed, we just need to explore it honestly.
    - The paper calls it a posteriori order cycle.

- If the parent-child relationship of two vertices and the nearest common ancestor to a neighboring leaf can be given, then a posterior order cycle can be performed.
    - In the case of a suffix array, the vertices of a tree can be represented by "a pair of start points and lengths".
        - Leaves have length to end of string
        - If w is an ancestor of v, then the length of w is less than v
            - The reverse is not necessarily true, but it's OK because we only make comparisons between recent common ancestors.
        - The nearest common ancestor can be obtained by changing the length to one pre-computed by [LCP array
            - The paper describes it as "high."
                - It has nothing to do with so-called tree height, etc.

python

```
def test_travase_tree():
    """
    >>> test_travase_tree()
    [6, 1]
    * 1
    [6]
    [6, 3]
    [6, 3, 2]
    * 2
    [6, 3]
    * 3
    [6]
    [6, 5]
    [6, 5, 4]
    * 4
    [6, 5]
    * 5
    [6]
    * 6
    []
    """
    ROOT = 0
    TOP = 6
    parent = [TOP, 3, 3, 5, 5, 0, TOP]
    leafs = [1, 2, 4]
    stack = [TOP]
    nearest_common_ancestors = [None, 3, 5, None, 6, None]

    def is_ancestor_of(anc, x):
        while True:
            x = parent[x]
            if x == anc:
                return True
            if x == 6:
                return False

    for leaf in leafs:
        stack.append(leaf)
        print(stack)
        v = stack[-1]
        w = nearest_common_ancestors[leaf]
        while is_ancestor_of(w, v):
            print("*", v)
            stack.pop()
            print(stack)
            if not stack:
                return
            v = stack[-1]
        if v != w and is_ancestor_of(v, w):
            stack.append(w)
            print(stack)
```



---
This page is auto-translated from [/nishio/順序木の右枝分解](https://scrapbox.io/nishio/順序木の右枝分解) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.