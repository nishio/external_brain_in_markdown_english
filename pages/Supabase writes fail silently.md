---
title: "Supabase writes fail silently"
---

ts

```typescript
await supabase.from("foo_table").insert({...})...
```


The Supabase API is designed to return a [[Result Type]] instead of throwing an [[Exception]] on failure.
Therefore, if you use the design with the intention of throwing an exception on failure, it will fail silently.

If you want to throw an exception, do this
ts

```typescript
const {data, error} = await supabase.from("foo_table").insert({...})...
if (error) {
    throw new Error(`Failed to insert data: ${error.message}`);
}
```


<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Why error handling with exceptions is not always optimal when using cloud databases in TypeScript
- Error Recovery: When an error occurs in a database operation, it may be more appropriate to attempt to recover from the error condition and retry rather than throwing an exception and aborting the process. For example, logic may be implemented to retry for timeouts or temporary connection problems.
- API Design: It is common for libraries and APIs that manipulate cloud databases to return detailed error responses so that users can implement error handling for their own use. This allows for more flexible error handling, using error codes and error messages instead of throwing exceptions.
---
This page is auto-translated from [/nishio/Supabaseの書き込みがサイレントに失敗する](https://scrapbox.io/nishio/Supabaseの書き込みがサイレントに失敗する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.