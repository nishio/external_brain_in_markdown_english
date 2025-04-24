---
title: "React Hook useEffect has missing dependencies"
---

ts

```typescript
  const [state, setState] = useGlobal("state");
  const { key } = useParams();
  useEffect(() => {
    if (state === "NORMAL") {
      if (key === "new") {
        foobar().then((id) => {
          setState("CREATED_NEW")
        });
        setState("WAIT_NEW")
      }
    }  // (snip)
  }, [key]) 
```

I wrote this with the intention of updating the state by triggering a change in key, but it warns me that there are missing dependencies for the state.
What's wrong and what should we do about it?

---
This page is auto-translated from [/nishio/React Hook useEffect has missing dependencies](https://scrapbox.io/nishio/React Hook useEffect has missing dependencies) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.