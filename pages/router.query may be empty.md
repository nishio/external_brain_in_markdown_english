---
title: "router.query may be empty"
---

ts

```typescript
  const { id } = router.query;
  const topicId = Array.isArray(id) ? id[0]! : id!;
  useEffect(() => {
    get_topic(topicId).then(...);
  }, [topicId]);
```


<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The problem in the above code is when useEffect is executed: it gets the id from router.query and assigns it to topicId, an operation that is performed when the page is first loaded. At this time, router.isReady may still be false, and therefore router.query may still be empty. As a result, topicId will be undefined.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Why isn't the route fixed at the first rendering...
[[Next.js]]

---
This page is auto-translated from [/nishio/router.query は空である可能性がある](https://scrapbox.io/nishio/router.query は空である可能性がある) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.