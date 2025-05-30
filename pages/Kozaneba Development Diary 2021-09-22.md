---
title: "Kozaneba Development Diary 2021-09-22"
---

Using Runtypes, a check mechanism is put in place to ensure that the JSON has the expected structure.
- [GitHub - pelotom/runtypes: Runtime validation for static types](https://github.com/pelotom/runtypes)

I don't like the idea of using the same name for Runtype and static types.
- Maybe prefix RT and T.
- before
ts

```typescript
export type ItemId = ItemIdBrand & string;
enum ItemIdBrand {
  _ = "",
}
```

- after
ts

```typescript
import { Static, String } from "runtypes";

export const RTItemId = String.withBrand("ItemId");
export type TItemId = Static<typeof RTItemId>;
```


Quick exception, I'll leave the short, positively meaningful type as it is.
- before
ts

```typescript
export type V2 = [number, number];
```

- after
ts

```typescript
import { Number, Static, Tuple } from "runtypes";

export const RT_V2 = Tuple(Number, Number);
export type V2 = Static<typeof RT_V2>;
```


Branded types are simpler to write in Runtypes
- before
ts

```typescript
enum WorldBrand {
  _ = "",
}
enum ScreenBrand {
  _ = "",
}

export type TScreenCoord = ScreenBrand & V2;
export type TWorldCoord = WorldBrand & V2;
```

- after
ts

```typescript
export const RTScreenCoord = RT_V2.withBrand("Screen");
export type TScreenCoord = Static<typeof RTScreenCoord>;
export const RTWorldCoord = RT_V2.withBrand("World");
export type TWorldCoord = Static<typeof RTWorldCoord>;
```


Now that we're all set up, we're going to take down the big guy.
- before
ts

```typescript
export type TKozaneItem = {
  type: "kozane";
  text: string;
  position: TWorldCoord;
  id: TItemId;
  scale: number;
  custom?: {
    style?: CSSProperties;
    url?: string;
  };
};
```

- after:
ts

```typescript
const RTKozaneItem = Record({
  type: Literal("kozane"),
  text: String,
  position: RTWorldCoord,
  id: RTItemId,
  scale: Number,
  custom: Optional(
    Record({
      style: Dictionary(String.Or(Number)).optional(),
      url: String.optional(),
    })
  ),
});

export type TKozaneItem = Static<typeof RTKozaneItem>;
```

- What to do with third-party types like CSSProperties is a vexing question
    - [runtyping: Generate runtypes from static types & JSON schema.](https://github.com/johngeorgewright/runtyping)
    - There is an approach to generate code from static type definitions, but I don't really want to do that.
    - Let's just make it a Dictionary for now and observe what problems arise in the future.

Code I was writing to check if the JSON is the expected structure.
- before
ts

```typescript
export function isTKozaneItem(x: any): x is TKozaneItem {
  return (
    x.type === "kozane" &&
    typeof x.text === "string" &&
    isV2(x.position) &&
    typeof x.id === "string" &&
    typeof x.scale === "number"
  );
}
```

- after: can simply be deleted, no need to implement on your own
- Fix where you're using it, too.
- before
ts

```typescript
export function isTItem(x: any): x is TItem {
  return (
    isTKozaneItem(x) || isTGroupItem(x) || isTScrapboxItem(x) || isTGyazoItem(x)
  );
}
```

- after
ts

```typescript
export function isTItem(x: any): x is TItem {
  return (
    RTKozaneItem.guard(x) ||
    isTGroupItem(x) ||
    isTScrapboxItem(x) ||
    isTGyazoItem(x)
  );
}
```

- The other guards will gradually wake up and change, and eventually this guard will disappear.

Let's do the other ones without hesitation.
- before
ts

```typescript
export type TGroupItem = {
  type: "group";
  text: string;
  position: TWorldCoord;
  items: TItemId[];
  id: TItemId;
  scale: number; // scale of Nameplate Kozane
  isOpen: boolean;
  custom?: { style?: CSSProperties };
};
```

- after
ts

```typescript
export const RTGroupItem = Record({
  type: Literal("group"),
  text: String,
  position: RTWorldCoord,
  items: Array(RTItemId),
  id: RTItemId,
  scale: Number,
  isOpen: Boolean,
  custom: Record({
    style: RT_CSSProperties.optional(),
  }).optional(),
});
export type TGroupItem = Static<typeof RTGroupItem>;
```

- CSSProperties is out there again, so I'll name it in case I need to replace it in the future.
    - `export const RT_CSSProperties = Dictionary(String.Or(Number));`

before
- `export type TItem = TKozaneItem | TGroupItem | TGyazoItem | TScrapboxItem;`
after
ts

```typescript
export const RTItem = Union(
  RTKozaneItem,
  RTGroupItem,
  RTScrapboxItem,
  RTGyazoItem
);
export type TItem = Static<typeof RTItem>;
```

isTItem was successfully removed.

Ah, I think I found the problem with CSSProperties.
I see, CSSProperties is an interface, so it can't be assigned.
ts

```typescript
const f = (x: CSSProperties) => {
  type T = Static<typeof RT_CSSProperties>;
  let y: T = x;
  // Type 'CSSProperties' is not assignable to type '{ [x: string]: string | number; [x: number]: string | number; [x: symbol]: string | number; }'.
 // Index signature for type 'string' is missing in type 'Properties<string | number, string & {}>'.
};
```


I looked up what to do and found a method called withGuard in the interface Runtype.
- Type guard can be specified
- If its type guard is T, then it will also be T when converted to a static type.
    - No need to change from one existing third party static type to another
- How much you check can be controlled by how seriously you write the type guard.
    - The messiest one.
        - `Unknown.withGuard((x): x is CSSProperties => true)`
        - I don't know what it is, but this should be CSSPropertiet!"
        - Well, it's messy, but it still doesn't make it worse because it's not checked w
    - I'll try to be a little more sane.
ts

```typescript
export const RT_CSSProperties = Unknown.withGuard(
  (x): x is CSSProperties => {
    return typeof x === "object";
  },
  { name: "RT_CSSProperties" }
);
```

test.ts

```typescript
type T = Static<typeof RT_CSSProperties>;
// T is CSSProperties
RT_CSSProperties.check(1);
// throws `ValidationError: Failed constraint check for RT_CSSProperties`
```


---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-22](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-22) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.