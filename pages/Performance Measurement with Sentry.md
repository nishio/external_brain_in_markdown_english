---
title: "Performance Measurement with Sentry"
---

from [[Sentry Memo]]
Performance Measurement with Sentry
- [Included Instrumentation for React | Sentry Documentation](https://docs.sentry.io/platforms/javascript/guides/react/performance/included-instrumentation/)
    - Performance measurement is now available.
ts

```typescript
export const getNewTalkID = () => {
  const transaction = Sentry.startTransaction({ name: "getNewTalkID" });
  const span = transaction.startChild({ op: "getNewTalkID" });

  fetch(...)...
    .then((text) => {
    	  ...
          span.finish();
          transaction.finish();
        });
    })
    .catch(() => {
      Sentry.captureMessage("ERROR_ON_SERVER: getNewTalkID");
      ...
    });
};
```


![image](https://gyazo.com/9a4ebf11d8c86978e0194989da897c9c/thumb/1000)

If the filter is set to p100, outliers are included in the order of slowest to fastest.
In this example, there's one outlier that took 16 seconds.
Actually, this is what I wanted to know (the time it takes for the server to sleep and wake up after receiving a request).
![image](https://gyazo.com/a3fbe8c76d001c7c4e489a9503dd75e3/thumb/1000)

---
This page is auto-translated from [/nishio/Sentryでパフォーマンス計測](https://scrapbox.io/nishio/Sentryでパフォーマンス計測) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.