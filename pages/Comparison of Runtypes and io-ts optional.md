---
title: "Comparison of Runtypes and io-ts optional"
---

First, how a normal TypeScript type looks on the code and on the VSCode hints.
- It's easier to write and look as close to this as possible
ts

```typescript
// typescript
{
  type OptionalY = { x: number; y?: number };
  const value1: OptionalY = { x: 1 };
  const value2: OptionalY = { x: 1, y: 2 };
}
```

![image](https://gyazo.com/0dbfd6c60848295b0e3e48c569716ac8/thumb/1000)

For Runtypes
- Type object is like "well, can I read it in verbatim translation?
- Generated static types are exactly the same as in TypeScript
ts

```typescript
// runtypes
{
  const RT_OpeionalY = Record({ x: Number, y: Optional(Number) });
  type OptionalY = Static<typeof RT_OpeionalY>;
  const value1: OptionalY = { x: 1 };
  const value2: OptionalY = { x: 1, y: 2 };
}
```

![image](https://gyazo.com/6d3f4f112bef34630d8d35e7213abce4/thumb/1000)
![image](https://gyazo.com/8887af7557d6b24987f8aac41fe6cd02/thumb/1000)

For io-ts
- First of all, how to write to create an intersection with PARTIAL as explained in the official documentation.
- As for the static types, well, if you are a programmer at the level where you are not confused by the interpretation of the middle `} & {`, there is not much harm in it.
- As for the type object... reading "y is optional" from here seems like a high cognitive cost.
ts

```typescript
// io-ts, official solution
{
  const IO_OpeionalY = t.intersection([
    t.type({
      x: t.number,
    }),
    t.partial({
      y: t.number,
    }),
  ]);
  type OptionalY = t.TypeOf<typeof IO_OpeionalY>;
  const value1: OptionalY = { x: 1 };
  const value2: OptionalY = { x: 1, y: 2 };
  // const value3: OptionalY = { x: 1, y: "foo" };
  // expected ERROR: Type 'string' is not assignable to type 'number | undefined'.
}
```

![image](https://gyazo.com/96aaa9ff55003b6b06b14b08331665d4/thumb/1000)
![image](https://gyazo.com/ba29ab9ae416674b103b7f6f03f8f99c/thumb/1000)

io-ts' approach to creating utility functions that seem to work (in fact, they don't work at all).
- In the value3 example, the mistake of putting a string in an optional number is not detected, so it's not good at all.
    - I have set [No Implicit Any](https://www.typescriptlang.org/tsconfig#noImplicitAny) in tsconfig to true in Recommended, so this code is an error in the first place.
    - The default of false is also pointed out: `Parameter 'tp' implicitly has an 'any' type, but a better type may be inferred from usage.`
        - In other words, tp is any
        - So it propagates and y is also any, which is the cause of the value3 problem.
- Also, the pattern "y does not exist" as in value1 should not be a type error, but it is.
ts

```typescript
// io-ts
{
  const optional = (tp) => t.union([tp, t.undefined]);
  const IO_OpeionalY = t.type({
    x: t.number,
    y: optional(t.number),
  });
  type OptionalY = t.TypeOf<typeof IO_OpeionalY>;
  // const value1: OptionalY = { x: 1 };
  // ERROR: Property 'y' is missing in type '{ x: number; }' but required in type '{ x: number; y: any; }'
  const value2: OptionalY = { x: 1, y: 2 };
  const value3: OptionalY = { x: 1, y: "foo" }; // unexpected OK
}
```

![image](https://gyazo.com/7f01f7afef7ae573ee855b64d4e355d4/thumb/1000)
- There is a way to use generics to solve the value3 any problem.
    - However, this method does not solve the problem of the absence of value1 members
ts

```typescript
{
  const optional = <T extends t.Mixed>(tp: T) => t.union([tp, t.undefined]);
  const IO_OpeionalY = t.type({
    x: t.number,
    y: optional<typeof t.number>(t.number),
  });
  type OptionalY = t.TypeOf<typeof IO_OpeionalY>;
  // const value1: OptionalY = { x: 1 };
  // ERROR: Property 'y' is missing in type '{ x: number; }' but required in type '{ x: number; y: any; }'
  const value2: OptionalY = { x: 1, y: 2 };
  // const value3: OptionalY = { x: 1, y: "foo" };
  // expected ERROR: Type 'string' is not assignable to type 'number | undefined'
}
```


PS
- As above, assigning an object with no members to a variable of a generated static type results in a type error, but when assigning from a decode result, it enters without error.
- The decode result looks identical to the original object in both Jest's toEqual comparison and in the JSON.stringify result, but it is actually different in the ENTRY
    - In short, at the decode stage, y does not exist, but is changed to an object with undefined in y.
- Hmmm, this is going to be a problem when using "libraries that behave differently when a member is undefined than when it does not exist"...
    - Firebase Cloud Firestore throws an exception if `undefined` is included in serialization.
    - This is not the main topic of this page, but I noticed that Firestore has more options to ignore undefined in the May 2020 update. I'll add it.
        - > Whether to skip nested properties that are set to undefined during object serialization.  If set to `true`, these properties are skipped and not written to Firestore. If set to `false` or omitted, the SDK throws an exception when it encounters properties of type `undefined`. [doc](https://firebase.google.com/docs/reference/js/v8/firebase.firestore.Settings?hl=ja#optional-ignoreundefinedproperties)

ts

```typescript
const input_object = { x: 1 };
const tmp = IO_OpeionalY.decode(input_object);
let value4: OptionalY;
if (isRight(tmp)) {
  value4 = tmp.right;
} else {
  throw new Error();
}
expect(JSON.stringify(value4)).toBe(`{"x":1}`);
expect(value4).toEqual(input_object);
// expect(Object.entries(value4)).toEqual(Object.entries(input_object));  // fail
```



---
This page is auto-translated from [/nishio/Runtypes と io-ts のoptionalの比較](https://scrapbox.io/nishio/Runtypes と io-ts のoptionalの比較) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.