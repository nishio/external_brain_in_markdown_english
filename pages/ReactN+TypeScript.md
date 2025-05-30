---
title: "ReactN+TypeScript"
---

When using [[ReactN]] with [[TypeScript]], I got an error message "Argument of type '"a"' is not assignable to parameter of type 'never'. I fixed it by feeling without reading the manual, but it was not actually fixed, so I wrote down the correct way to fix it.
- [[TypeScript types]]
ts

```typescript
import { useGlobal, setGlobal } from 'reactn';
const INITIAL_STATE = {
  a: 1,
  b: "foo",
}
type TState = typeof INITIAL_STATE;
//type TState = {a: number; b: string;}
setGlobal(INITIAL_STATE);

const App: React.FC = () => {
  const a = useGlobal("a");
  // ERROR: Argument of type '"a"' is not assignable to parameter of type 'never'.
...
```


When I added a type specification to useGlobal, the compile error disappeared and I thought that was all right, but the type was wrong and the problem occurred later.
ts

```typescript
  const [a] = useGlobal<TState>("a");
  // no compile error, it seems OK but...
  // const a: string | number
  // So,
  console.log(a + 1);
  // Operator '+' cannot be applied to types 'ReactText' and 'number'.
```


How to fix it right [https://github.com/CharlesStover/reactn/blob/master/README.md#typescript-support](https://github.com/CharlesStover/reactn/blob/master/README.md#typescript-support)
ts

```typescript
declare module 'reactn/default' {
  export interface State extends TState { }
}

const App: React.FC = () => {
  const [a] = useGlobal("a");  // OK, no generics needed
  console.log(a + 1);  // OK
```


the reason why `a: string | number`
ts

```typescript
useGlobal<TState>("a");
// return value: StateTuple<{
//   a: number;
//   b: string;
// }, "a" | "b">
```


ts

```typescript
useGlobal<G extends {} = State, Property extends keyof G = keyof G>(property: Property): StateTuple<G, Property>;

export type StateTuple<G extends {}, P extends keyof G> = [
  G[P],
  Setter<G, P>,
];
```


This is caused by the fact that when one type is specified for generics, which takes two type arguments, the other type is changed.
If no type argument is specified, the type Key is inferred from the argument, which is a literal type of string.
On the other hand, if the type is passed to Dict, Key becomes the keyof Dict. In this case, it becomes the union type of all keys.
ts

```typescript
interface DefaultDict {
  a: number,
  b: string,
}
const dict: DefaultDict = {
  a: 1,
  b: "foo"
}
const bar: <
  Dict extends {} = DefaultDict,
  Key extends keyof Dict = keyof Dict
  >(key: Key) => Key
  = (key) => key;

const a1 = bar("a");
// const a1: "a"

const a2 = bar<typeof dict>("a");
// const a2: "a" | "b"

const a3 = bar<DefaultDict>("a");
// const a3: "a" | "b"
```


`G[P]` of `StateTuple[0]`, since P is the union type of all keys
ts 

```
 export type StateTuple<G extends {}, P extends keyof G> = [
   G[P],
   Setter<G, P>,
 ];
```


---
This page is auto-translated from [/nishio/ReactN+TypeScript](https://scrapbox.io/nishio/ReactN+TypeScript) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.