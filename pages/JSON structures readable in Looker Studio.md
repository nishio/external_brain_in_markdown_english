---
title: "JSON structures readable in Looker Studio"
---

[[Looker Studio]] can read JSON, so [[Gist as GET API]] would be easy! but it turns out that it can't read plain JSON.
NG.json

```json
{
  "total_contribution_prs": 72,
  "daily_counts": {
    "2025-06-09": 11,
    "2025-05-22": 9,
    ...
  },
  "generated_at": "2025-06-10T05:32:26.282510Z"
}
```

OK.json

```json
{
  "total_contribution_prs": 72,
  "daily_counts": [
    {"date": "2025-05-15", "count": 5},
    {"date": "2025-05-16", "count": 3},
    {"date": "2025-05-18", "count": 6},
    ...
  ],
  "generated_at": "2025-06-10T13:47:41.871113Z"
}
```

By using the latter style and specifying the root element as daily_counts, it can be handled as a table-type data source.

next:  [[Cannot graph a date in Looker Studio without making it a Date type.]]

---
This page is auto-translated from [/nishio/Looker Studioで読めるJSON構造](https://scrapbox.io/nishio/Looker Studioで読めるJSON構造) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.