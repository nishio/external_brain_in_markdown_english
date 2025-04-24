---
title: "Save to Firestore with Cloud Functions"
---

There's an official sample that you can look at.
[functions-samples/quickstarts/uppercase-firestore at main · firebase/functions-samples · GitHub](https://github.com/firebase/functions-samples/tree/main/quickstarts/uppercase-firestore)

What I thought when I saw [code](https://github.com/firebase/functions-samples/blob/main/quickstarts/uppercase-firestore/functions/index.js)
- I see what you mean about doing `admin.initializeApp();` outside of exports.
- `functions.https.onRequest(async (req, res) => { ... })` and async function, so you can await the result with `const writeResult = await ... I see.

Save to [[Firestore]] in [Cloud Functions
---
This page is auto-translated from [/nishio/Cloud FunctionsでFirestoreに保存する](https://scrapbox.io/nishio/Cloud FunctionsでFirestoreに保存する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.