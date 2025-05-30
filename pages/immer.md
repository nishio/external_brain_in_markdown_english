---
title: "immer"
---

![image](https://gyazo.com/f15c24829b9b7d6f349b9566daca3bdf/thumb/1000)
> Immer (German for: always) is a tiny package that allows you to work with immutable state in a more convenient way. It is based on the copy-on-write mechanism.
>  The basic idea is that you will apply all your changes to a temporary draftState, which is a proxy of the currentState. Once all your mutations are completed, Immer will produce the nextState based on the mutations to the draft state. This means that you can interact with your data by simply modifying it while keeping all the benefits of immutable data.
[https://immerjs.github.io/immer/docs/introduction](https://immerjs.github.io/immer/docs/introduction)

I've been making the same thing in parts and getting confused about the molds, so let's be honest and use this one.

[[updateGlobal.ts]]
updateGlobal.ts

```typescript
import { State } from "reactn/default";
import { setGlobal } from "reactn";
import { produce } from "immer";

export const updateGlobal = (update: (g: State) => void) => {
  // update global variable in destructive manner using immer
  setGlobal((g: State) => {
    return produce(g, update);
  });
};
```

usage.ts

```typescript
updateGlobal((g) => {
  g.foo.bar += g.baz.quux;
});
```





[Twitter immer mizchi](https://twitter.com/search?q=immer%20mizchi&src=typed_query&f=live)
- > immer is the best. All mankind should use it. I mean, I want this spec in tc39's proposal.
- > I used to write JS/TS code with the rule of never causing side-effects, but honestly I got tired of it and landed in a place where I just used immer a lot and ensured immutable at the scope level.
- > immer is a draft object, and I want to write it in a syntactically clean way, because it would be messy if the logic to rewrite the draft object would refer to the original data.
- > immer said
js

```javascript
const newObj = produce(obj, draft => {
  draft.x = 1;
});
```

- > but with some kind of scope and capture-like concept in it.
js

```javascript
const newObj = immutable do {
  obj.x = 1; // changes here are not propagated outside;.
  obj; // returned by do exppression rules
}
```

- > I want something like that for JS.
- > I'm starting to understand how to use immer, but this is a lose-lose situation if you do complex calculations inside immer callbacks, and I hope you limit it to only assignments of 2 nests or more.
- > I've been using immer for a while now, and it's probably the only utility I use.
- > The reason I can't remember the order of splice arguments is that I basically avoid in-place destructive functions, but the reason I mentioned this now is that when I use immer, I need to write destructive functions for pure object creation, which rarely requires me to write splice. I can't remember, so I have to google it.

---
This page is auto-translated from [/nishio/immer](https://scrapbox.io/nishio/immer) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.