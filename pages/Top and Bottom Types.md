---
title: "Top and Bottom Types"
---


[A Little Theory with your TypeScript: Top and Bottom Types | by Kevin B. Greene | Medium](https://medium.com/@KevinBGreene/a-little-theory-with-your-typescript-top-and-bottom-types-61b380f227d)

ts

```typescript
const s: string = "string";
const n: number = s;  // Type 'string' is not assignable to type 'number'.
```


ts

```typescript
const n: number = 123;
const s: string = n;  // Type 'number' is not assignable to type 'string'.
```


---
### unknown

ts

```typescript
const n: number = 123;
const x: unknown = n;  // OK
```


ts

```typescript
const x: unknown;
const n: number = x;  // Type 'unknown' is not assignable to type 'number'.
```


---
### cast

ts

```typescript
const s = "string";
const n: number = s as number;  // Conversion of type 'string' to type 'number' may be a mistake because neither type sufficiently overlaps with the other. If this was intentional, convert the expression to 'unknown' first.
```


ts

```typescript
const s = "string";
const n: number = (s as unknown) as number;  // OK
```


---

ts

```typescript
const x: never;
const n: number = x;  // OK, no type error 
```



---

ts

```typescript
const supplyNever = (): never => {
  throw new Error();
};

const x: never = supplyNever();
const n: number = x;
```



---
This page is auto-translated from [/nishio/Top and Bottom Types](https://scrapbox.io/nishio/Top and Bottom Types) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.