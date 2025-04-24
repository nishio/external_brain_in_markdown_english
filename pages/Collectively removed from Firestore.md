---
title: "Collectively removed from Firestore"
---

I did it with Chrome devtool.
js

```javascript
let querySnapshot;
db.collection("kakidashi").get().then((qs) => { querySnapshot = qs})
querySnapshot.docs[0].data().items
querySnapshot.forEach((x) => {
	if(x.data().items.length == 0){
	  x.ref.delete()
	}
})
```


[[Firestore]]


---
This page is auto-translated from [/nishio/Firestoreからまとめて削除](https://scrapbox.io/nishio/Firestoreからまとめて削除) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.