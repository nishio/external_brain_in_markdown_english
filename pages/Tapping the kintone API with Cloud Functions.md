---
title: "Tapping the kintone API with Cloud Functions"
---

[@kintone/rest-api-client - npm](https://www.npmjs.com/package/@kintone/rest-api-client)
in Cloud Function, but I wanted to try it in my local Emulator.
`$ npm run build`
I got the following error when I was in the process of

Because tsconfig.json looks like this
tsconfig.json

```json
{
  "compilerOptions": {
    "module": "commonjs",
    ...
```


`import { KintoneRestAPIClient } from "@kintone/rest-api-client";`
instead of
`const { KintoneRestAPIClient } = require("@kintone/rest-api-client");`
is correct.

error

```
node_modules/@kintone/rest-api-client/lib/http/AxiosClient.d.ts:2:8 - error TS1259: Module '".../kozaneba/functions/node_modules/@kintone/rest-api-client/node_modules/form-data/index"' can only be default-imported using the 'esModuleInterop' flag

2 import FormData from "form-data";
         ~~~~~~~~

  node_modules/@kintone/rest-api-client/node_modules/form-data/index.d.ts:10:1
    10 export = FormData;
       ~~~~~~~~~~~~~~~~~~
    This module is declared with using 'export =', and can only be used with a default import when using the 'esModuleInterop' flag.
```



---
This page is auto-translated from [/nishio/Cloud FunctionsでkintoneのAPIを叩く](https://scrapbox.io/nishio/Cloud FunctionsでkintoneのAPIを叩く) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.