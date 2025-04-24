---
title: "What does react-dom/test-utils act do?"
---

Briefly, "flush until the update queue is empty after calling the callback."

If the callback is sync, repeat flushPassiveEffects until the while statement is empty.
ts

```typescript
const flushWork =
  Scheduler.unstable_flushAllWithoutAsserting ||
  function() {
    let didFlushWork = false;
    while (flushPassiveEffects()) {
      didFlushWork = true;
    }

    return didFlushWork;
  };
```


In the case of async, it flushes and re-stacks itself on the queue until the queue is empty.
ts

```typescript
function flushWorkAndMicroTasks(onDone: (err: ?Error) => void) {
  try {
    flushWork();
    enqueueTask(() => {
      if (flushWork()) {
        flushWorkAndMicroTasks(onDone);
      } else {
        onDone();
      }
    });
  } catch (err) {
    onDone(err);
  }
}
```


In addition to this, there are codes for checking "whether the act is double", "whether you await something that is not async", "whether you forget to await even though it is async", and so on.
---
This page is auto-translated from [/nishio/react-dom/test-utilsのactは何をする？](https://scrapbox.io/nishio/react-dom/test-utilsのactは何をする？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.