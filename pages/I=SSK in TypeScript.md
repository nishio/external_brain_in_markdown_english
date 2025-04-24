---
title: "I=SSK in TypeScript"
---

- [[TypeScript types]]
ts

```typescript
let I: <T>(x: T) => T;
let K: <T1, T2>(x: T1) => ((y: T2) => T1) = (x) => {
  return (y) => x;
};
let S: <Tz, Tyz, Ts>(x: (z: Tz) => ((yz: Tyz) => Ts)) => ((y: (z: Tz) => Tyz) => ((z: Tz) => Ts)
) = (x) => {
  return (y) => {
    return (z) => {
      return x(z)(y(z));
    }
  }
}
let SKK = S(K)(K);
I = SKK;
let x: 0 = SKK(0);
```


I've been trying to work a little on VSCode's auto-indenting to make it look relatively decent.
ts

```typescript
let S: <Tz, Tyz, Ts>
  (x: ((z: Tz) => ((yz: Tyz) => Ts)))
  =>
  (y: (z: Tz) => Tyz)
    =>
    (z: Tz)
      => Ts
  =
  (x) => (
    (y) => (
      (z) => (
        x(z)(y(z))
      )
    )
  )
```


ts

```typescript
{
  type Tx<Txx> = (x: Tx<Txx>) => Txx
  let M: <Txx>(x: Tx<Txx>) => Txx = (x) => (x(x));
}
```


The next puzzle is to eliminate any from now on!
ts

```typescript
let iota: (x: any) => any = (x) => x(S)(K);
let I = iota(iota);
```


Hmmm, I did it naively and got a mysterious mold.
ts

```typescript
  type Ts = typeof S;
  type Tk = typeof K;
  let xs: <Tr>(x: (s: Ts) => Tr) => Tr = (x) => x(S);
  let yk: <Tr>(y: (k: Tk) => Tr) => Tr = (y) => y(K);

  let iota: <Txsk>(x: (s: Ts) => (k: Tk) => Txsk) => Txsk = (x) => x(S)(K);
  //let I = iota(iota); // error message is below

  let a = S(S);
  let b = S(S)(K);  // let b: (z: (z: {}) => (yz: {}) => {}) => (z: {}) => {}
  let c = S(S)(K)(K)
```



- Argument of type
    - '<Txsk>(x: (s: <Tz, Tyz, Ts>(x: (z: Tz) => (yz: Tyz) => Ts) => (y: (z: Tz) => Tyz) => (z: Tz) => Ts) => (k: <T1, T2>(x: T1) => (y: T2) => T1) => Txsk) => Txsk'
- is not assignable to parameter of type
    - '(s: <Tz, Tyz, Ts>(x: (z: Tz) => (yz: Tyz) => Ts) => (y: (z: Tz) => Tyz) => (z: Tz) => Ts) => (k: <T1, T2>(x: T1) => (y: T2) => T1) => {}'.

    - Types of parameters 'x' and 's' are incompatible.
        - Type
            - '(y: (z: (z: {}) => (yz: {}) => {}) => (z: {}) => {}) => (z: (z: {}) => (yz: {}) => {}) => (z: {}) => {}'
        - is not assignable to type
            - '(k: <T1, T2>(x: T1) => (y: T2) => T1) => (z: {}) => {}'.

[[TypeScript]]

---
This page is auto-translated from [/nishio/TypeScriptでI=SSK](https://scrapbox.io/nishio/TypeScriptでI=SSK) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.