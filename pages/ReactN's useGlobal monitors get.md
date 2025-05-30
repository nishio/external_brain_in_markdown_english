---
title: "ReactN's useGlobal monitors get"
---

In ReactN's useGlobal, if you call `useGlobal()` instead of specifying the property explicitly as `useGlobal("foo")`, ReactN will monitor get accesses to the returned global value and ` addPropertyListener`.

So there was no need to be concerned that ``useGlobal()`` would cause a redraw on every update. was unnecessary.

useGlobal
use-global.ts

```typescript
export default function _useGlobal<...>(...): UseGlobal<G, Property> {
  ...
  if (typeof property === "undefined") {
    ... 
    return [globalStateManager.spyState(forceUpdate), globalStateSetter];
  }
```


spyState
global-state-manager.ts

```typescript
  public spyState(propertyListener: PropertyListener): G {
    // When this._state is read, execute the listener.
    return objectGetListener(
      this._state,
      (property: keyof G) => {
        this.addPropertyListener(property, propertyListener);
      },
    );
  }
```


objectGetListener
object-get-listener.ts

```typescript
// Return an object that executes a read listener.

export default function objectGetListener<Shape>(
  obj: Shape,
  listener: Function,
): Shape {
  return (Object.keys(obj) as (keyof Shape)[]).reduce(
    (accumulator: Partial<Shape>, key: keyof Shape): Partial<Shape> => {
      Object.defineProperty(accumulator, key, {
        configurable: false,
        enumerable: true,
        get: (): Shape[keyof Shape] => {
          listener(key);
          return obj[key];
        }
      });
      return accumulator;
    },
    Object.create(null)
  );
};
```


[[reactn]] of [[ReactN]].

---
This page is auto-translated from [/nishio/ReactNのuseGlobalはgetを監視する](https://scrapbox.io/nishio/ReactNのuseGlobalはgetを監視する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.