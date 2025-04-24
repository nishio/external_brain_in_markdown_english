---
title: "store's subscribe and useEffect"
---

from [[pRegroup-done-2019]]
store's subscribe and useEffect
There is semantic overlap between store subscribe and useEffect, but I'm not sure which one to use.
Is this how it should be or should I make it a LISTENER?
ts

```typescript
 useEffect(() => {
   ...
 }, [store.getState().items]);
```


Read subscribe description
[https://redux-docs.netlify.com/api/store#a-id-subscribe-class-anchor-a-subscribelistener-subscribe](https://redux-docs.netlify.com/api/store#a-id-subscribe-class-anchor-a-subscribelistener-subscribe)
> It is a low-level API. Most likely, instead of using it directly, you'll use React (or other) bindings. If you commonly use the callback as a hook to react to state changes, you might want to write a custom observeStore utility. The Store is also an Observable, so you can subscribe to changes with libraries like RxJS.

---
This page is auto-translated from [/nishio/storeのsubscribeとuseEffect](https://scrapbox.io/nishio/storeのsubscribeとuseEffect) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.