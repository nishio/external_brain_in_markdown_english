---
title: "await and call/cc"
---

[[call/cc]] and [[await]] in [[Promise]] are very similar, but call/cc does not stop the process and Promise cannot be re-executed
await only connects the current continuation after the given Promise, but does not expose the continuation to the user
It seems possible to mimic the behavior of await with call/cc, but not vice versa.
[[JavaScript]] [[Scheme]]
There was this article.
- [Implement Maybe, Either, Promise, Continuation Monad and do syntax in JavaScript + generator and compare with async-await - Qiita [https://qiita.com/legokichi/items/0582e71f4e](https://qiita.com/legokichi/items/0582e71f4e) 6984548933]
- [Relationship between async, generator, Promise, CPS, and monad in ES2017 - Qiita](https://qiita.com/legokichi/items/77a36b7d2b75d8278f9d)

ts

```typescript
let p = new Promise((resolve) => {
  console.log("promise called", resolve);
  // @ts-ignore
  window.resolve = resolve;
});

(async () => {
  console.log("before await")
  console.log(await p);
  console.log("after await")
})()
// display before await and abort processing

window.resolve(42)
// 42
// after await // Suspended processing is resumed
// undefined
window.resolve(53)
// undefined // nothing happens after the second time
```



scheme

```
(define resolve #f)
(define (p c)
	(print "promise called")
	(print c)
	(set! resolve c))

gosh> (begin
    (print "before call/cc")
    (print (call/cc p))
    (print "after call/cc"))
;before call/cc
;promise called
;#<subr "continuation">
;#<subr "continuation">
;after call/cc
;#<undef>
Processing is executed to the end.

gosh> resolve
#<subr "continuation">

gosh> (resolve 42)
42
after call/cc
#<undef>
; Runs again.

gosh> (resolve 53)
53
after call/cc
#<undef>
; Runs as many times as you want.

```


---
This page is auto-translated from [/nishio/awaitとcall/cc](https://scrapbox.io/nishio/awaitとcall/cc) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.