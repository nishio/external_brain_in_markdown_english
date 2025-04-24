---
title: "ReactN setGlobal returns a Promise, but can be updated synchronously."
---

Since ReactN's setGlobal returns `Promise<G>`, I had thought that it would be updated asynchronously at some unknown time and then Promise's then would be called.
So I thought I had to async/await to guarantee that they would be called in order.

This is a mistake.
Returns a resolved Promise after synchronously updating it unless the argument newGlobalState is a Promise.

ts

```typescript
export default function _setGlobal<...>(
  globalStateManager: GlobalStateManager<G, R>,
  newGlobalState: NewGlobalState<G>,
  callback: Callback<G, R> = null,
): Promise<G> { ... }
```

[https://github.com/CharlesStover/reactn/blob/master/src/set-global.ts](https://github.com/CharlesStover/reactn/blob/master/src/set-global.ts)
The default GlobalStateManager is bind as the first argument.
- `setGlobal: setGlobal.bind(null, defaultGlobalStateManager),` [index.ts](https://github.com/CharlesStover/reactn/blob/master/src/index.ts)

If the argument is not a Promise, it will eventually come here
ts

```typescript
  public setObject<O extends Partial<G> = Partial<G>>(
    obj: O, ...
  ): Promise<Partial<G>> {
    ...
    const stateChange: Partial<G> = this.flush(reducerName, reducerArgs);
    return Promise.resolve(stateChange);
  } 
```

[https://github.com/CharlesStover/reactn/blob/master/src/global-state-manager.ts#L350](https://github.com/CharlesStover/reactn/blob/master/src/global-state-manager.ts#L350)

If the argument is a Promise, it leads to then of the given Promise
ts

```typescript
  public setPromise(
    promise: Promise<NewGlobalState<G>>, ...
  ): Promise<Partial<G>> {
    return promise
      .then((result: NewGlobalState<G>): Promise<Partial<G>> =>
        this.set(result, reducerName, reducerArgs),
      );
  }
```


---
This page is auto-translated from [/nishio/ReactNのsetGlobalはPromiseを返すけど同期的更新できる](https://scrapbox.io/nishio/ReactNのsetGlobalはPromiseを返すけど同期的更新できる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.