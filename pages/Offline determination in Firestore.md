---
title: "Offline determination in Firestore"
---

It cannot be done on its own.
→Another idea: transactions always fail when they are offline, so maybe there is a way to use that.

see: [Building a Presence with Cloud Firestore | Firebase](https://firebase.google.com/docs/firestore/solutions/presence)

[[Realtime Database]] has a special path called '.info/connected'.
js

```javascript
firebase.database().ref('.info/connected').on('value', function(snapshot) {
   // If we're not currently connected, don't do anything.
   if (snapshot.val() == false) {
       return;
   };
   ...
```


What about [[Cloud Firestore]]?
> Connectivity - This implementation measures connectivity to Realtime Database, not Cloud Firestore.
Even the official documentation doesn't solve the problem with Cloud Firestore, but substitutes a connectivity check with Realtime Database.

---
This page is auto-translated from [/nishio/Firestoreでオフライン判定](https://scrapbox.io/nishio/Firestoreでオフライン判定) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.