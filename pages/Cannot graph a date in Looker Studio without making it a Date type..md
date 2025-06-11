---
title: "Cannot graph a date in Looker Studio without making it a Date type."
---

Cannot graph a date in [[Looker Studio]] unless it is set to [[Date type]].

I get an error "Dimension invalid
- It doesn't seem to understand the date as a string like "2025-01-01".
- It looks like just a line graph.

o3 is "[[ISO 8601 date]] 2025-05-15 year 4 digits - month 2 digits - day 2 digits (hyphen delimited), most reliably determined by Looker Studio." but it doesn't recognize it.
- After all, `PARSE_DATE('%Y-%m-%d', date)` in a calculated field is the quickest way.

relevance
    - [[Map aggregation not possible with LookerStudio string type]]

---
This page is auto-translated from [/nishio/Looker Studioで日付をDate型にしないとグラフにできない](https://scrapbox.io/nishio/Looker Studioで日付をDate型にしないとグラフにできない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.