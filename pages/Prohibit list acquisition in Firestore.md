---
title: "Prohibit list acquisition in Firestore"
---

The security rules for [[Firestore]] initially look like this
:

```
match /{document=**} {
  allow read, write;
}
```


This read permission can be divided into get and list. By restricting this list privilege, it is possible to prohibit the acquisition of a list.
:

```
match /{document=**} {
  allow get;
  allow list: if false;
  allow write;
}
```


The following code was successful before narrowing down the security, but after narrowing it down, the error occurs as expected
:

```
firebase.firestore().collection("collection_foo").get().then((qs) => {
  qs.forEach((d) => console.log(d.id));
});
// Uncaught (in promise) FirebaseError: Missing or insufficient permissions.
```


doc [https://firebase.google.com/docs/firestore/security/rules-structure](https://firebase.google.com/docs/firestore/security/rules-structure)

[[Capability URL]]

---
This page is auto-translated from [/nishio/Firestoreで一覧取得を禁止する](https://scrapbox.io/nishio/Firestoreで一覧取得を禁止する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.