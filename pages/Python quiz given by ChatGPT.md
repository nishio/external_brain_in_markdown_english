---
title: "Python quiz given by ChatGPT"
---

> [@tokoroten](https://twitter.com/tokoroten/status/1691819049770955219?s=20): ugh... never used decorator...
> ![image](https://gyazo.com/ade54a80490ce69a33145d8522f54faf/thumb/1000)

That's a pretty good problem to have.

python

```
# fill here
func()
func()
func()
```

output

```
func called
1 times called
func called
2 times called
func called
3 times called
```


answer

python

```
def deco(func):
    count = 0

    def wrapper():
        nonlocal count
        func()
        count += 1
        print(count, "times called")

    return wrapper


@deco
def func():
    print("func called")


func()
func()
func()
```




---
This page is auto-translated from [/nishio/ChatGPTが出したPythonクイズ](https://scrapbox.io/nishio/ChatGPTが出したPythonクイズ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.