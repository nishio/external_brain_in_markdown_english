---
title: "Using ReactN with Next.js"
---

In three lines.
- I want to initialize the global state only once before mounting the component.
- But [[Next.js]] doesn't have a place to write that easily.
- Therefore, initialization is performed using a higher-order component ([[HOC]]) that performs initialization only once.
> In some cases (such as when using [[Next.js]]), you may be unable to run a setup script prior to your ReactN components mounting. In order to instantiate your global state and reducers prior to mounting, you may use the withInit Higher Order Component. This HOC will await the setting of your global state before mounting the provided Lower Order Component (e.g. <App />).
[https://github.com/CharlesStover/reactn#withinit](https://github.com/CharlesStover/reactn#withinit)

Here is the code `_app.tsx` created by Next.js code generator
_app.tsx

```
import '../styles/globals.css'
import type { AppProps } from 'next/app'

function MyApp({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />
}

export default MyApp
```


Add a higher-order component withInit to it.
Although the README sample is as follows
- No type information
- Component takes no arguments
It cannot be applied to `_app.tsx` as is in terms of `_app.tsx`.
ts

```typescript
import React, { useDispatch, useGlobal, withInit } from 'reactn';

const INITIAL_REDUCERS = {
  addOne: ({ count }) => ({
    count: count + 1,
  }),
};

const INITIAL_STATE = {
  count: 0,
};

export default withInit(
  INITIAL_STATE,
  INITIAL_REDUCERS
)(function App() {
  const addOne = useDispatch('addOne');
  const [count] = useGlobal('count');
  return <button onClick={addOne}>Count: {count}</button>;
});
```


I checked the source and found that the third type argument takes the type of the component argument. So we can pass it there appropriately.
Also declare for use with TypeScript.
- [https://github.com/CharlesStover/reactn#typescript-support](https://github.com/CharlesStover/reactn#typescript-support)

_app.tsx

```
import "../styles/globals.css";
import type { AppProps } from "next/app";
import React, { withInit } from "reactn";

const INITIAL_STATE = {
  count: 0,
};

type TYPE_STATE = typeof INITIAL_STATE;

const INITIAL_REDUCERS = {
  addOne: ({ count }: TYPE_STATE) => ({
    count: count + 1,
  }),
};

type TYPE_REDUCERS = typeof INITIAL_REDUCERS;

declare module "reactn/default" {
  export interface State extends TYPE_STATE {}
  export interface Reducers extends TYPE_REDUCERS {}
}

const MyApp = withInit<TYPE_STATE, TYPE_REDUCERS, AppProps>(
  INITIAL_STATE,
  INITIAL_REDUCERS
)(({ Component, pageProps }: AppProps) => {
  return <Component {...pageProps} />;
});

export default MyApp;
```



---
This page is auto-translated from [/nishio/Next.jsでReactNを使う](https://scrapbox.io/nishio/Next.jsでReactNを使う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.