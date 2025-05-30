---
title: "Promise"
---

[Promise - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

[How do Promises Work? - Quil's Fluffy World](https://robotlolita.me/articles/2015/how-do-promises-work/)
- Japanese translation: [How Promise works - Implementing Promise | POSTD](https://postd.cc/how-do-promises-work/)
Good commentary, but the Japanese translation is not very good.



For [Promise - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) on 6/2019
- > The term "resolve is called asynchronously" is ambiguous.
I wrote, but now that I look at it, I couldn't find that expression.
As of 2021/2, it is written more clearly.
- > Note that promises are guaranteed to be asynchronous. Thus, an action on a promise that has already been "resolved" will be executed only after the stack has been cleared and a clock tick has elapsed. This effect is very similar to setTimeout(action,10)
---old
The term "resolve is called asynchronously" is ambiguous.
- The first argument of Promise, (resolve, reject) => {...} Whether you call resolve synchronously or asynchronously in

:

```
create promise start
promise body start
sync body start
sync body end
promise body end
create promise end
specify promise.then start
specify promise.then end
resolved ok
```


ts

```typescript
  const syncBody = (resolve: any, reject: any) => {
    console.log("sync body start")
    resolve("ok")
    console.log("sync body end")
  }
  const asyncBody = (resolve: any, reject: any) => {
    console.log("async body start")
    setTimeout(() => {
      console.log("timeout start")
      resolve("ok")
      console.log("timeout end")
    }, 1000)
    console.log("async body end")
  }

  console.log("create promise start")
  let p = new Promise((resolve, reject) => {
    console.log("promise body start")
    syncBody(resolve, reject)
    console.log("promise body end")
  })
  console.log("create promise end")

  console.log("specify promise.then start")
  p.then((x) => {
    console.log("resolved", x)
  })
  console.log("specify promise.then end")
```




---
This page is auto-translated from [/nishio/Promise](https://scrapbox.io/nishio/Promise) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.