---
title: "getter with React Hooks"
---

What if we made something like this? (It's just an idea, so I haven't verified it properly yet.)
typescript

```typescript
function useGetter<T>(init_value : T){
  let [state, update] = useState<T>(init_value);
  let ref = useRef(state);
  const getter = () => {
    return ref.current;
  }
  const setter = (f : Function) => {
    let newState = f(ref.current);
    newState = Object.assign({}, newState);  // force update
    ref.current = newState;
    update(newState);
  }
  return [getter, setter];
}
```

[[React Hooks]]
[[React]]

---
This page is auto-translated from [/nishio/React Hooksでgetter](https://scrapbox.io/nishio/React Hooksでgetter) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.