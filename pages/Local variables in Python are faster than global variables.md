---
title: "Local variables in Python are faster than global variables"
---

Accessing local variables in raw Python is faster than accessing global variables
- It's a well-known story for those who use Python for competitive programming.
- Only useful in situations where a single variable is accessed 10 million times and where a difference of a few hundred milliseconds can make the difference between pass and fail.

python

```
def main():
  j = 0
  for i in range(10_000_000):
    j = i
  return j

print(main())
```

224msec
python

```
j = 0
for i in range(10_000_000):
  j = i
print(j)
```

573 ms

---
This page is auto-translated from [/nishio/Pythonでローカル変数はグローバル変数より速い](https://scrapbox.io/nishio/Pythonでローカル変数はグローバル変数より速い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.