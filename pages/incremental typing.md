---
title: "incremental typing"
---

[[Gradual Typing]]
Concise and very good explanation
- [What is Gradual Typing | Jeremy Siek](https://wphomes.soic.indiana.edu/jsiek/what-is-gradual-typing/)
- Japanese translation [What is Gradual Typing: Gradual Typing - Qiita](https://qiita.com/t2y/items/0a604384e18db0944398).

[https://mypy-play.net/?mypy=latest&python=3.11](https://mypy-play.net/?mypy=latest&python=3.11)
python

```
def foo(x: int):
    y: str = x  # NG
```

- `error: Incompatible types in assignment (expression has type "int", variable has type "str")  [assignment]`
- Explicitly state implicit Any
python

```
import typing

def foo(x: typing.Any):
    y: str = x  # OK
```

python

```
def foo(x: int):
    y: typing.Any = x  # OK
```


- Difference between Any and object
python

```
def foo(x: int):
    y: object = x  # OK
```

python

```
def foo(x: object):
    y: str = x  # NG
```

- `error: Incompatible types in assignment (expression has type "object", variable has type "str")  [assignment]`
- Unlike Any, object is just a top type, so trying to assign a value of type object to a value of type str (implicit downcast) is not allowed.
    - This is normal type behavior.
    - That Any is a special type that can implicitly perform both upcasts and downcasts.

- No guessing the return type.
python

```
def foo(x: int):
    return x

print(typing.reveal_type(foo))
```

- `note: Revealed type is "def (x: builtins.int) -> Any"`
- This is a different behavior from TypeScript
    - ![image](https://gyazo.com/485b1234b2e40fa0839bf9379e8ddce3/thumb/1000)
python

```
def foo(x: int) -> int:
    return x

print(typing.reveal_type(foo))
```

- `note: Revealed type is "def (x: builtins.int) -> builtins.int"`
    - It is expected that humans will explicitly state in this way


[The Expression Problem](https://homepages.inf.ed.ac.uk/wadler/papers/expression/expression.txt)

![image](https://gyazo.com/9ea5aa1dec79c546747debfa28db2621/thumb/1000)


---
This page is auto-translated from [/nishio/漸進的型付け](https://scrapbox.io/nishio/漸進的型付け) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.