---
title: "Visualization of delay propagation segment trees"
---

- [[Segment tree visualization]]
- [Source code here:](https://github.com/nishio/atcoder/blob/master/memo/segment_tree/segment_tree_vis.py)
    - When there is a discrepancy between the explanation here and the source doc, the source is correct, because I'm regression testing with doctest.

- Visualization of [Delayed propagation segment tree
- Combine [[segment tree]] with range contraction and [[dual segment tree]] with range action
    - Become a range-action, range-contractible delay propagation segment tree
- Here we use the implementation so far as possible, managing the "table of actions not yet applied (delayed) to the values" in a dual segment tree and the "values" separately in a segment tree
    - The objective is to depict what kind of interaction between these two trees
    - As a result, range action and downward propagation are difficult to operate on each of the separate tables, so a mechanism was introduced to bundle the two tables together and treat them as a single table.


- Initialize the value segment tree normally
python

```
>>> set_depth(4)
>>> value_table = [""] * SEGTREE_SIZE
>>> set_items(value_table, [chr(i + ord("a")) for i in range(8)])
>>> full_up(value_table, lambda x, y: f"{x}{y}")
>>> debugprint(value_table)
|    abcdefgh   |
|  abcd |  efgh |
| ab| cd| ef| gh|
|a|b|c|d|e|f|g|h|
```

- Initialize the dual segment tree of the action with the unit action
python

```
>>> action_unity = PowAction(1)
>>> action_table = [action_unity] * SEGTREE_SIZE
>>> debugprint(action_table)
|           ^1          |
|     ^1    |     ^1    |
|  ^1 |  ^1 |  ^1 |  ^1 |
|^1|^1|^1|^1|^1|^1|^1|^1|
```

- Properly define the synthesis of actions
    - For example, the unit source could be an empty list, and the composite of the action could be a union of lists.
    - Here the action is a power square, so we can compose `(^n) + (^m) = (^(n*m))`.
python

```
def action_composite(new_action, old_action):
    return PowAction(new_action.value * old_action.value)
```

- I was mistakenly thinking that I could just update the range for the table in action here.
    - In fact, the value table needs to be updated at the same time.
- First define how the value is updated by the action
    - `def action_force(action, value): ...`
    - Next, for a table of action/value pairs, create a function that simultaneously composes the action and updates the value
python

```
def combined_action(new_action):
    def f(args):
        action, value = args
        return (
            action_composite(new_action, action),
            action_force(new_action, value))
    return f
```

- This allows for range action.
    - (It needs to be propagated from above first, but I'm skipping it because there's nothing to propagate right now.)
    - At first I misunderstood it as "first only the table of the action is written, then the value is updated and propagated to the children of the action as needed".
            - [[Design Differences]]
        - Even at the end of the tree, the value needs to be updated, but there are no children to propagate it, so a conditional branching is necessary.
python

```
>>> range_update(combined_table, L, R, combined_action(PowAction(2)))
>>> debugprint(action_table, 3)
|               ^1              |
|       ^2      |       ^1      |
|   ^1  |   ^1  |   ^2  |   ^1  |
| ^1| ^1| ^1| ^1| ^1| ^1| ^1| ^1|
>>> debugprint(value_table, 3)
|            abcdefgh           |
|    (abcd)^2   |      efgh     |
|   ab  |   cd  | (ef)^2|   gh  |
| a | b | c | d | e | f | g | h |
```

- Value updates propagate up segment-tree-like
    - Operation on only the table of values here, segment tree part
python

```
>>> up_propagate(value_table, up(L), lambda x, y: f"{x}{y}")
>>> up_propagate(value_table, up(R), lambda x, y: f"{x}{y}")
>>> debugprint(value_table, 3)
|        (abcd)^2(ef)^2gh       |
|    (abcd)^2   |    (ef)^2gh   |
|   ab  |   cd  | (ef)^2|   gh  |
| a | b | c | d | e | f | g | h |
```

    - See [maspy's article](https://maspypy.com/segment-tree-%E3%81%AE%E3%81%8A%E5%8B%89%E5%BC%B72) for why propagation from both ends instead of the entire range is fine.
            - [[Range of influence of propagation downwards]]
            - [[up operation]]
        - In the following implementation, the propagation path is calculated first and used both up and down.
            - Upward propagation merges in the middle, so this method is good because it eliminates the merging and beyond.
            - [RMQ and RUQ (Lazy Evaluated Segment Tree) - yaketake08's Implementation Memo](https://tjkendev.github.io/procon-library/python/range_query/rmq_ruq_segment_tree_lp.html)
- Next time a range action is performed (from here on, the full version of the range action without abbreviations)
    - First propagate the delayed action down with respect to both ends of the range
        - When the action goes down, the lower value is also updated.
        - To ensure that the action that came first is used to update the value first
    - I wondered if this could be expressed by propagating downwards in a twin-pair segmented tree, but it was difficult.
        - After propagation, the parent is implemented back to the unit action, but it is not appropriate for "action/value pairs".
            - The action returns to the unit action, but the value is not updated.
        - So I wrote exclusively for you.
python

```
def down_propagate_force(table, pos, action_composite, action_force, action_unity):
    max_level = pos.bit_length() - 1
    for level in range(max_level):
        i = pos >> (max_level - level)

        action, value = table[i]
        a, v = table[i * 2]
        table[i * 2] = (
            action_composite(action, a),
            action_force(action, v))
        a, v = table[i * 2 + 1]
        table[i * 2 + 1] = (
            action_composite(action, a),
            action_force(action, v))
        table[i] = (action_unity, value)
```

- Propagate down, then range, then propagate the value up, and so on, all together.
python

```
>>> L = 1
>>> R = 5
>>> down_propagate_force(
...    combined_table, up(L),
...    action_composite, action_force, action_unity)
>>> down_propagate_force(
...    combined_table, up(R),
...    action_composite, action_force, action_unity)

>>> debugprint(action_table)
|           ^1          |
|     ^1    |     ^1    |
|  ^1 |  ^2 |  ^1 |  ^1 |
|^2|^2|^1|^1|^2|^2|^1|^1|

>>> debugprint(value_table)
|        (abcd)^2(ef)^2gh       |
|    (abcd)^2   |    (ef)^2gh   |
| (ab)^2| (cd)^2| (ef)^2|   gh  |
|a^2|b^2| c | d |e^2|f^2| g | h |

>>> range_update(combined_table, L, R, combined_action(
...     PowAction(3), action_composite, action_force))
>>> debugprint(action_table, 3)
|               ^1              |
|       ^1      |       ^1      |
|   ^1  |   ^6  |   ^1  |   ^1  |
| ^2| ^6| ^1| ^1| ^6| ^2| ^1| ^1|

>>> debugprint(value_table, 3)
|                        (abcd)^2(ef)^2gh                       |
|            (abcd)^2           |            (ef)^2gh           |
|     (ab)^2    |   ((cd)^2)^3  |     (ef)^2    |       gh      |
|  a^2  |(b^2)^3|   c   |   d   |(e^2)^3|  f^2  |   g   |   h   |

>>> up_propagate(value_table, up(L), lambda x, y: f"{x}{y}")
>>> up_propagate(value_table, up(R), lambda x, y: f"{x}{y}")
>>> debugprint(value_table, 3)
|                a^2(b^2)^3((cd)^2)^3(e^2)^3f^2gh               |
|      a^2(b^2)^3((cd)^2)^3     |          (e^2)^3f^2gh         |
|   a^2(b^2)^3  |   ((cd)^2)^3  |   (e^2)^3f^2  |       gh      |
|  a^2  |(b^2)^3|   c   |   d   |(e^2)^3|  f^2  |   g   |   h   |
```

- range contraction
    - Propagate down and then range-contract normally for a table of values.
python

```
>>> L = 3
>>> R = 5
>>> down_propagate_force(
...     combined_table, up(L),
...     action_composite, action_force, action_unity)
>>> down_propagate_force(
...     combined_table, up(R),
...     action_composite, action_force, action_unity)
>>> debugprint(value_table)
|                a^2(b^2)^3((cd)^2)^3(e^2)^3f^2gh               |
|      a^2(b^2)^3((cd)^2)^3     |          (e^2)^3f^2gh         |
|   a^2(b^2)^3  |   ((cd)^2)^3  |   (e^2)^3f^2  |       gh      |
|  a^2  |(b^2)^3|  c^6  |  d^6  |(e^2)^3|  f^2  |   g   |   h   |
>>> value_unity = ""
>>> print(range_reduce(value_table, L, R, lambda x, y: f"{x}{y}", value_unity))
d^6(e^2)^3
```


Consider doing Range add, range sum
- Multiplication `a * b` and powers `(^ n)` are related by `(a * b) ^ n = (a ^ n) * (b ^ n)`.
        - Call it [[distributive law]].
- Range add, range sum, the distribution rule does not hold between `a + b` and `(+ n)`.
    - `(a + b) + n = (a + n) + (b + n)` not
    - If we do (+1) to a node with size 4, the value must increase by 4
- Programmatic solution: make the action take node size as an argument, not just value
- Mathematical solution: make the domain of the value the direct product of the node size
    - Since the parent node size is the sum of the child node sizes, it can be properly constructed by propagation upwards
        - (+) = `lambda (v1, s1), (v2, s2): (v1 + v2, s1 + s2)`
        - (+n) = `lambda (v, s): v + s * n`
- The approach we have taken so far of "expressing by pasting two trees together," only takes a mathematical approach to the table of action-value pairs, since the position and size of the nodes are not passed to the function (combined_action) that simultaneously synthesizes the action and updates the value.
    - It's about time we don't do it here because the gap between moving it at a realistic speed is getting too big.
    - The AOJ's four types of delayed propagation segment tree problems are solved by implementing the problem without creating a "table of action-value pairs" and passing both as arguments, so please refer to that.
            - [[General-purpose, practical implementation of delay propagation segment trees]]

---
This page is auto-translated from [/nishio/遅延伝搬セグメント木の可視化](https://scrapbox.io/nishio/遅延伝搬セグメント木の可視化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.