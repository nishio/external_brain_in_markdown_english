---
title: "IndexedDB"
---

> IndexedDB API is powerful, but may seem too complicated for simple cases. If you'd prefer a simple API, try libraries such as localForage, dexie.js, ... that make IndexedDB more programmer-friendly.
- [IndexedDB API - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)

- [[Dexie.js]]
    - A Minimalistic Wrapper for IndexedDB
    - [https://dexie.org/](https://dexie.org/)
- `$ npm install dexie`
- Read [Typescript](https://dexie.org/docs/Typescript)
    - Need to define classes for type convenience.
    - The name specified in `// (1)` is exposed in the browser scope, so include a human-readable application name or something similar for clarity.
localDB.ts

```typescript
import Dexie from "dexie";

export interface ITalks {
  id?: number; // Primary key. Optional (autoincremented)
  TalkID: string;
}
class MyAppDatabase extends Dexie {
  talks: Dexie.Table<ITalks, number>; // number = type of the primkey

  constructor() {
    super("MyAppDatabase");  // (1)
    this.version(1).stores({
      talks: "++id",
    });
    this.talks = this.table("talks");
  }
}

export const localDB = new MyAppDatabase();
```

use.ts

```typescript
localDB.talks
  .orderBy("id")
  .reverse()
  .limit(1)
  .toArray()
  .then((x) => {
    setGlobal({ TalkID: newID, previousTalkID: x[0].TalkID });
    localDB.talks.add({ TalkID: newID });
  });
```


- You can see the contents in Chrome Dev Tool > Application
    - ![image](https://gyazo.com/1b6ecf332579b1e48810e84fe64bff38/thumb/1000)


---
This page is auto-translated from [/nishio/IndexedDB](https://scrapbox.io/nishio/IndexedDB) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.