---
title: "Example of forgetting to return in TypeScript causing NEVER problem"
---

I was translating a sample written in JS from [useHistory | useHooks](https://usehooks.com/useHistory/) to [[TypeScript]] and the `Type 'any' is not assignable to type 'never'`. .
The cause is ultimately a "non-exhaustive switch/case", resulting in a return type of T | undefined due to the "non-returned path", which is never in React's useReducer's type inference process.

The first way to see it is this
ts

```typescript
  const [state, dispatch] = useReducer(reducer, {
    ...initialState,
    present: initialPresent
  });
```

![image](https://gyazo.com/130dbfe2c6bdd3d09caa7c73e2ad78b6/thumb/1000)

You think "present" is "never. But it's no good if you use "any" for everything.
ts

```typescript
const initialState = {
  past: [] as any[],
  present: null as any,
  future: [] as any[]
}; 
```


When a mysterious phenomenon occurs, the problem is divided.
ts

```typescript
  let x = {
    ...initialState,
    present: initialPresent
  }
  const [state, dispatch] = useReducer(reducer, x);
```

At this time, an error is displayed for x in `useReducer(reducer, x);`.
- > Argument of type '{ present: any; past: any[]; future: any[]; }' is not assignable to parameter of type 'never'.

So the phenomenon is "the type of the second argument of useReducer is inferred to be never".
Examine the behavior of inference around useReducer.
- `useReducer(null, null)`
    - > Argument of type 'null' is not assignable to parameter of type 'Reducer<any, any>'
- `useReducer(()=>1, null)`
    - > Argument of type 'null' is not assignable to parameter of type 'number'.
    - So we can expect the return value of the first argument to be inferred to be the type of the second argument

So what is the type of reducer in this case?
:

```
const reducer: (state: {
    past: any[];
    present: any;
    future: any[];
}, action: any) => {
    past: any[];
    present: any;
    future: any[];
} | undefined
```

For some reason, it is undefined (you can guess around here).

The implementation of reducer uses switch/case to branch in four different ways and returns in each of them.
The type system does not know that only these four cases exist. Therefore, it is assumed that there is a pathway out of switch/case that does not match any of the cases. As a result, the return type is undefined, and the reducer's type inference process will turn it into never.
- (It might be interesting to delve deeper into the process of "reducer's type inference process transforms it into never," but I'll pass this time.)

So there are two solutions to this problem
- Cutting corners: return state; after switch/case to align the types.
- Serious: Declare by type that action.type takes only 4 types of values

I got lazy and did a lazy implementation.

---
The process of "reducer's type inference process that turns it into never."
 ts

```
    function useReducer<R extends Reducer<any, any>>(
        reducer: R,
        initialState: ReducerState<R>,
        initializer?: undefined
    ): [ReducerState<R>, Dispatch<ReducerAction<R>>];
    
    type Reducer<S, A> = (prevState: S, action: A) => S;
    type ReducerState<R extends Reducer<any, any>> = R extends Reducer<infer S, any> ? S : never;
```

If the type of reducer is (T, any) => (T | undefined)
- R = (T, any) => (T | undefined)
- R extends Reducer<any, any> succeeds
    - Reducer<any, any> = (any, any) => (any) because
    - (T | undefined) in the return value any
- R extends Reducer<infer S, any> ? S : never seems to succeed with S being any...
    - I wonder if "infer" will ever answer "any".
        - Well, if it were, the infer would always succeed, so the conditional expression would be meaningless.
        - It's hard to say without knowing how the infer works/specs.
    - I think infer S will fail and return NEVER.

---
This page is auto-translated from [/nishio/TypeScriptのreturn忘れがnever問題を起こす例](https://scrapbox.io/nishio/TypeScriptのreturn忘れがnever問題を起こす例) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.