---
title: "I want to aggregate Firestore data."
---

2023-07-09
- I would like to aggregate Firestore data for [[ChatGPT for middle and high school students]].

- [[Read Firestore data in a local script]]

I tried to read the data, but couldn't.
- I did `db.collection('users').get()` but snapshot.size is zero
- I asked what caused it.
    - Several causes were mentioned, check from above.
    - I thought the rules were wrong." I was told, so I put up the rules and asked him to check them.
        - [[How do I allow access to Firestore from my service account?]]

I couldn't read the rules after I changed them.
- I created the code to get one specific message, and it was done.
- But `db.collection('users').get()` but snapshot.size is zero

Thinking again, I realized, "Even if I grant service accounts the same access rights as normal users, I can't get a list of users.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>snapshot.size is zero. I just noticed that the rule deny traversal. Fix it
- <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>`allow list: if request.auth.token.firebase.sign_in_provider == "null";`

Still no luck, I asked why the phenomenon of being able to get the terminal object but not being able to traverse the parent occurs.
- <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>No user document: When you fetch a nested sub-collection document directly (as in code A), Firestore doesn't need the parent document to exist. In other words, even if there's no document at users/{userId}, you can still fetch a document at users/{userId}/rooms/{roomId}/messages/{messageId}.
- [HF8NVT*MTY4ODgyODA1My4xNi4xLjE2ODg4MzM2NDguMC4wLjA.#non-existent_ancestor_documents Managing Cloud Firestore in Firebase console](https://firebase.google.com/docs/firestore/using-console?hl=ja&authuser=0&_gl=1*1y83w4p*_ga*MTQ5MDA3NDc1MS4xNjg2MDI5OTU3*_ga_CW55)
- > A document can exist even if the ancestor does not exist.
- This...

How do I enumerate descendant documents when no ancestor document exists?
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> How to get all `/users/<user_id>/rooms/<room_id>` when `/users/<user_id>` is not exists.
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt-4/icon' alt='gpt-4.icon' height="19.5"/> There is a way to fetch all rooms from all users using a Firestore feature called Collection Group Queries.
    - `db.collectionGroup('rooms').get()`
    - It's done.

How do you know which user the room belongs to?
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Given doc, how can I see its parent <user_id>
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt-4/icon' alt='gpt-4.icon' height="19.5"/> `doc.ref.parent.parent.id`

All that's left is to tally the totals! And then it's over!

---
This page is auto-translated from [/nishio/Firestoreのデータを集計したい](https://scrapbox.io/nishio/Firestoreのデータを集計したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.