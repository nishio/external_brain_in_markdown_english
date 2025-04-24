---
title: "jsonpatch didn't work."
---

Regarding the approach of passing a large JSON to [[o1 Pro]] and having [[jsonpatch]] output the modified parts.
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
> The following JSON Patch is an example of RFC 6902 format. When actually applying, please rewrite the index (line number) of /tasks/◯◯ to match the actual array position.
:

```
[
  {
    // Change T0103 to Done
    "op": "replace",
    "path": "/tasks/<<<INDEX_OF_T0103>>>/status",
    "value": "Done"
  },
  ...
```


LLM doesn't seem to know how many items a particular element in a large JSON list is

Well, I passed it to [[Roo Code]] and it finally applied it correctly, but in the process, this one was `[...] `[...} `, and I started a trial-and-error process to fix the syntax error of the whole JSON, which is also not suitable for LLM.

I have already prepared a script to change the task to done, so I could have made Roo read the script's guide and given it the instruction "Change T0103 to Done". I should have had Roo output a higher-level "list of operations that Roo can understand".
- You're talking about the Tool definition.


- [[AI Task Management]]
[[ai task management 2025-02-01]]

---
This page is auto-translated from [/nishio/jsonpatchではダメだった](https://scrapbox.io/nishio/jsonpatchではダメだった) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.