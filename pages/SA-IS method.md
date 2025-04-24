---
title: "SA-IS method"
---

A simple implementation is to create a [[suffix array]] of $O(N^2\log N)$ with [$ O(N)

- What is a suffix array?
python

```
data = "abracadabra$"

buf = []
for i in range(len(data)):
    buf.append((data[i:], i))

buf.sort()

for x in buf:
    print(x)
```

- Suffix arrays can be made to efficiently discover the location of the occurrence of a particular keyword in a dichotomous search.
- Use bucket sorting on the first character

difficult (e.g. customer, guest, child)

A Bite-Sized Explanation
[http://shogo82148.github.io/homepage/memo/algorithm/suffix-array/](http://shogo82148.github.io/homepage/memo/algorithm/suffix-array/)

Easy to understand? Explanation
[https://mametter.hatenablog.com/entry/20180130/p1](https://mametter.hatenablog.com/entry/20180130/p1)

---
This page is auto-translated from [/nishio/SA-IS法](https://scrapbox.io/nishio/SA-IS法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.