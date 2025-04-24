---
title: "Design Differences"
---

![image](https://gyazo.com/b5efdabe825093b38e43f773873a9441/thumb/1000)


old
- Enforces the application of delayed action to a range
    - This is an operation that updates both the value and action tables
        - Values are updated as the action is applied
        - Action disappears and is transmitted to the child
python

```
>>> force_range_update(value_table, action_table, 0, 6, PowAction(1))
>>> debugprint(value_table, minsize=3)
|            abcdefgh           |
|    (abcd)^2   |      efgh     |
|   ab  |   cd  | (ef)^2|   gh  |
| a | b | c | d | e | f | g | h |

>>> debugprint(action_table)
|           ^1          |
|     ^1    |     ^1    |
|  ^2 |  ^2 |  ^1 |  ^1 |
|^1|^1|^1|^1|^2|^2|^1|^1|
```


    - First propagate the delayed action down with respect to both ends of the range
        - This is an operation on the action table only
        - When you act on a range, you need the value of the current action, so you put down as much as you need.
        - This is the same as a dual segment tree, which propagates down when the terminal value is needed
python

```
>>> down_propagate(action_table, up(1), lambda x, y: x(y), PowAction(1))
>>> down_propagate(action_table, up(5), lambda x, y: x(y), PowAction(1))
>>> debugprint(action_table)
|           ^1          |
|     ^1    |     ^1    |
|  ^1 |  ^2 |  ^1 |  ^1 |
|^2|^2|^1|^1|^2|^2|^1|^1|
```


---
This page is auto-translated from [/nishio/設計の違い](https://scrapbox.io/nishio/設計の違い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.