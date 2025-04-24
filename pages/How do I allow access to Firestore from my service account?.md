---
title: "How do I allow access to Firestore from my service account?"
---

2023-07-09
from  [[I want to aggregate Firestore data.]]

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I would like to update the following rule to allow script access to [[Firestore]]. How can I do this? ...
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- The current Firestore rule `allow read, write: if request.auth ! = null && request.auth.uid == userId;` restricts access to authenticated users and checks if the authenticated user ID (request.auth.uid) matches the user ID (userId) in the document path.
    - This allows users to access only their own data.
- However, if you are using the Firebase Admin SDK, the request.auth object will be null.
    - The Admin SDK uses a "service account" for authentication, not a user account.
    - Therefore, server-side scripts cannot access the data with the current rules.
- To check if the request is from a service account, check request.auth.token.firebase.sign_in_provider. If this field is "null", it means that the request was authenticated by a service account:
    - `|| request.auth.token.firebase.sign_in_provider == "null"`

- [[I want to aggregate Firestore data.]]
---
This page is auto-translated from [/nishio/Firestoreへのサービスアカウントからのアクセスを許可するには？](https://scrapbox.io/nishio/Firestoreへのサービスアカウントからのアクセスを許可するには？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.