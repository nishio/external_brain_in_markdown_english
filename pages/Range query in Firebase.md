---
title: "Range query in Firebase"
---

In [[Firebase]], [[range query]].
- Posts in the last 24 hours
- Posting on a specific day
I want to get a

> First, use one of the sorting functions: orderByChild(), orderByKey(), or orderByValue()
> Next, these can be combined with the other five methods limitToFirst(), limitToLast(), startAt(), endAt(), and equalTo() to perform complex queries.
[https://firebase.google.com/docs/database/admin/retrieve-data#section-queries](https://firebase.google.com/docs/database/admin/retrieve-data#section-queries)

> No index is needed for development
>  Indexes are not required for development, except when using the REST API. Real-time client libraries can perform ad hoc queries without specifying indexes.
[Indexing Data | Firebase Realtime Database](https://firebase.google.com/docs/database/security/indexing-data)

[Get Data | Firebase Realtime Database](https://firebase.google.com/docs/database/admin/retrieve-data#section-ordered-data)

---
This page is auto-translated from [/nishio/Firebaseでレンジクエリ](https://scrapbox.io/nishio/Firebaseでレンジクエリ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.