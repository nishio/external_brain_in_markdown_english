---
title: "Minimal examples of weird EXCESSIVELY DEEP"
---

Minimal examples of Type instantiation is excessively deep and possibly infinite
The head of the list is cut off sequentially, so it is sure to end in finite times, but TypeScript can't figure it out.
- F alone is not considered EXCESSIVELY deep by TypeScript either.
- I'm doing the same thing with G and then handing it over to F.
    - Here it is determined to be EXCESSIVELY DEEP
    - Actually, it's not that deep because it becomes `[0, []]` before passing to F.

ts

```typescript
type LIST = [0, []] | [0, LIST]
type F<N extends LIST> = (
  {
    0: F<N[1] extends LIST ? N[1] : never>,
    1: [0, []]
  }[N[1] extends LIST ? 0 : 1]
)

type G<N extends LIST> = (
  F<
    {
      0: G<N[1] extends LIST ? N[1] : never>,
      1: [0, []]
    }[N[1] extends LIST ? 0 : 1]
  >
)
```



:

```
Type instantiation is excessively deep and possibly infinite.

Type '{ 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: ...[((((((((((({ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[...[(((((((((((N[1] extends LIST ? N[1] : never)[1] extends LIST ? (N[1] extends LIST ? N[1] : never)[1] : never)[1] extends LIST ? ((N[1] extends LIST ...' does not satisfy the constraint 'LIST'.
 Type '{ 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: { 0: ...[((((((((((({ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[{ 0: ...[...[(((((((((((N[1] extends LIST ? N[1] : never)[1] extends LIST ? (N[1] extends LIST ? N[1] : never)[1] : never)[1] extends LIST ? ((N[1] extends LIST ...' is not assignable to type '[0, LIST]'.
```


---
This page is auto-translated from [/nishio/変なexcessively deepの最小限の例](https://scrapbox.io/nishio/変なexcessively deepの最小限の例) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.