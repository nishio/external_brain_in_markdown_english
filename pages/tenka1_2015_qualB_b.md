---
title: "tenka1_2015_qualB_b"
---

[B - Tenkaichi Literal](https://atcoder.jp/contests/tenka1-2015-qualb/tasks/tenka1_2015_qualB_b)
- The problem of parsing a subset-like language in Python to distinguish between dictionary literals and set literals.
- For a moment, I asked myself, "How seriously should I implement this?" I am lost.
    - If we exclude the empty dictionary, we can be sure that there is one literal after the second character of the input.
    - You can skip over it and identify the next character by whether it's a comma or a colon.
- If the use is to implement a serious programming language, parse the literals seriously in this "skip reading" section.
    - If you can skip reading it this time, it's OK.
    - Both set literals and dictionary literals are balanced by parentheses, so just skip to the point where they balance.
python

```
def parse(s, i):
    if s[i] in string.digits:
        while s[i] in string.digits:
            i += 1
    else:
        bracket = 1
        i += 1
        while bracket:
            if s[i] == "{":
                bracket += 1
            elif s[i] == "}":
                bracket -= 1
            i += 1
    if s[i] == ":":
        return "dict"
    else:
        return "set"


def solve(s):
    if s == "{}":
        return "dict"
    assert s[0] == "{"
    return parse(s, 1)
```



---
This page is auto-translated from [/nishio/tenka1_2015_qualB_b](https://scrapbox.io/nishio/tenka1_2015_qualB_b) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.