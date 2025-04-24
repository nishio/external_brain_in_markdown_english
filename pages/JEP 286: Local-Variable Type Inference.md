---
title: "JEP 286: Local-Variable Type Inference"
---

[JEP 286: Local-Variable Type Inference](https://openjdk.org/jeps/286)

java

```
var list = new ArrayList<String>();  // infers ArrayList<String>
var stream = list.stream();          // infers Stream<String>
```

released in [[Java 10]]
- March 20, 2018

---
This page is auto-translated from [/nishio/JEP 286: Local-Variable Type Inference](https://scrapbox.io/nishio/JEP 286: Local-Variable Type Inference) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.