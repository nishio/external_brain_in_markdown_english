---
title: "Unexpected token o in JSON"
---

Deno 1.20.4

```
> JSON.parse({})
Uncaught SyntaxError: Unexpected token o in JSON at position 1
    at JSON.parse (<anonymous>)
```


The error occurred when JSON.parse was done again by mistake when JSON.parse had already been done.
- (In [[Next.js]], I assumed that req.body contained a string and did JSON.parse, but it was kindly already parsed, so there was no need.)

Why "token o" because it is implicitly toString.
Deno 1.20.4

```
> {}.toString()
"[object Object]"
```


On Chrome, the error is a little more obvious.
Chrome 105.0.5195.102

```
JSON.parse({})
VM366:1 Uncaught SyntaxError: "[object Object]" is not valid JSON
    at JSON.parse (<anonymous>)
    at <anonymous>:1:6
```


---
This page is auto-translated from [/nishio/Unexpected token o in JSON](https://scrapbox.io/nishio/Unexpected token o in JSON) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.