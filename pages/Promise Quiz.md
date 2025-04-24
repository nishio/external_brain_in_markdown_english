---
title: "Promise Quiz"
---

Answer in which order the console.logs are executed
js

```javascript
const f = async () => {
  let resolve;
  const p = new Promise((r) => {
    resolve = r;
  });
  const p1 = p
    .then(() => {
      console.log("p1-1");
    })
    .then(() => {
      console.log("p1-2");
    });
  const p2 = p.then(() => {
    console.log("p2");
  });

  console.log("a");
  resolve();

  const p3 = p.then(() => {
    console.log("p3");
  });
  const p4 = p2
    .then(() => {
      console.log("p4-1");
    })
    .then(() => {
      console.log("p4-2");
    });
  console.log("b");
  await p;
  console.log("c");
  await p1;
  console.log("d");

  return Promise.all([p1, p2, p3, p4]);
};
f();
```


answer
answer

```
"a"
"b"
"p1-1"
"p2"
"p3"
"c"
"p1-2"
"p4-1"
"d"
"p4-2"
```

[https://jsfiddle.net/1bepvt28/](https://jsfiddle.net/1bepvt28/)
![image](https://gyazo.com/3d9124304768b8654495ca52e6015e13/thumb/1000)

explanation
- ![image](https://gyazo.com/a76ac996f30b29fb5f758032178f0e24/thumb/1000)

- It is not executed because it is just chained to a promise that has not yet been resolved at the "a" stage.
- The three direct children of p enter the execution queue at the stage of resolve, they only enter the queue, so they are not yet executed.
- b is output
- With await p, the synchronous execution of this async function is completed. The continuation is queued.
- Empty the queue, run the three that were in earlier, and you'll see c.
- Two are queued at the time of this execution, so they will appear at the time of the next await.

---
This page is auto-translated from [/nishio/Promise Quiz](https://scrapbox.io/nishio/Promise Quiz) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.