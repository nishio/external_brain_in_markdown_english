---
title: "Cloud Firestore"
---

Backend of [Regroup
- The old KJ method tool used [[Google Realtime API]], but will end in January 2019
- I was thinking about using [[Firebase]], but when I investigated, Cloud [[Firestore]] had a beta release.
    - I decided to go this way because it seemed to fit better in terms of the data model.
- I've dropped the idea of using Scrapbox as a backend.
    - Scrapbox is still an interface to humans, not a place to put mechanical data.
        - [[Import from Scrapbox]] will be made available.

- How "Documents" are in "Collections
    - Think of the document as JSON (+ some additional data types).
    - Documents up to 1 MB
    - I can put the collection back in the document.

- [supported data types | Firebase](https://firebase.google.com/docs/firestore/manage-data/data-types?hl=ja)
    - Maps, arrays, and references can be included in the document.
    - text
        - > Only the first 1,500 bytes of the UTF-8 representation are considered by the query.
        - Indexes on single fields are automatically generated, but long texts should be explicitly excluded (in terms of billing) because indexes are meaningless

- doc("...") .set(...) Overwrite with (or create if not present)
    - merge: merge if true is specified [ref](https://firebase.google.com/docs/firestore/manage-data/add-data?hl=ja)
    - collectionsRef.doc("hoge").set(...) can be created by specifying an ID with
    - collectionRef.add(...) can be added with automatic ID generation
        - ref = collections.doc() and then ref.set(data) would be better
        - {timestamp: firebase.firestore.FieldValue.serverTimestamp()} would be good to include
            - I may write offline, so I'd better put the timestamp at hand in the CREATED field.
    - Write instruction returns Promise and then is called on completion
        - If you write offline, then when you come back online and can write to the server, then is called.
        - So it seems like a good idea to watch this and show the "written" mark
        - Apart from that, snapshot.metadata.hasPendingWrites will tell you if there are any outstanding writes.
            - [Get real-time updates with Cloud Firestore | Firebase](https://firebase.google.com/docs/firestore/query-data/listen)
    - There's also docRef.update, what's the difference between that and merge:true?
- Getting a document that does not exist does not result in an error.
    - Empty objects return.
    - doc.exists() => false
- `.onSnapshot(function(querySnapshot) {`
    - Listen for updates
- Batch Write [src](https://firebase.google.com/docs/firestore/manage-data/transactions)
    - 500 at a time
    - batch = operation against db.batch() then batch.commit()

- [full text search | Firebase](https://firebase.google.com/docs/firestore/solutions/search?hl=ja)

- Offline persistence
    - [Enable Offline Data | Firebase](https://firebase.google.com/docs/firestore/manage-data/enable-offline)
    - > If a user has multiple browser tabs open that reference the same Cloud Firestore database and offline persistence is enabled, Cloud Firestore will only work correctly on the first tab.
    - I'm afraid that would be an inadvertent mistake, opening multiple tabs and skimming the data.
    - The sample code seems to be able to detect it at least, so we should warn users.
    - I've confirmed that what I write off wifi is saved on the server after reconnecting wifi.
        - Whether there is a connection or not, snapshot.metadata is fromCache: false
        - On the other hand, when the browser is reloaded, fromCache: true

- Python API
    - [Try using Cloud Firestore | Firebase](https://firebase.google.com/docs/firestore/quickstart) in Python.
    - For `cred = credentials.ApplicationDefault()` to succeed [Start Authentication | Authentication | Google Cloud](https://cloud.google.com/docs/authentication/getting-started) to download JSON and set environment variables.
    - In Python, `collection.document()` instead of `collection.doc()`.
    - DocRef#get returns `document.DocumentSnapshot
        - .to_dict() to become a dictionary
    - It says that `db.collection("...") .get()` says "returns all documents" and I thought it was serious, but it creates a generator, so no worries!
        - `DeprecationWarning: 'Collection.get' is deprecated:  please use 'Collection.stream' instead.`
        - `xs.__next__() # => document.DocumentSnapshot`
    - Use where for conditions
python

```
In [25]: [d.to_dict()["text"] for d in db.collection("pieces").where("text", "<", "t").stream()]
Out[25]: []

In [26]: [d.to_dict()["text"] for d in db.collection("pieces").where("text", ">", "t").stream()]
Out[26]: ['test']
```

    - [https://googleapis.github.io/google-cloud-python/latest/firestore/client.html](https://googleapis.github.io/google-cloud-python/latest/firestore/client.html)
- Web JS API
    - [Add Firebase to your JavaScript project | Firebase](https://firebase.google.com/docs/web/setup)
        - First read some JS in the script tag, then configure
        - They have a JS that won't work if you open it from the local file system.
            - Serve with firebase-tools
            - I'm sure a Python http.server would be fine, but first I decided to do as you said.
            - > Error: Cannot understand what targets to deploy. Check that you specified valid targets if you used the --only or --except flag. Otherwise, check your firebase.json to ensure that your project is initialized for the desired features.
            - hmm
            - `$ python3 -m http.server`
                - It doesn't seem particularly problematic in
            - It seems easier to use [Firebase Hosting | Firebase](https://firebase.google.com/docs/hosting/index) at release time
    - [Using Cloud Firestore | Firebase](https://firebase.google.com/docs/firestore/quickstart)
        - In JS, set and get return Promise
js

```javascript
db.collection("pieces").get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
        console.log(`${doc.id} => ${doc.data()["text"]}`);
    });
});
```


- REST API
    - [https://firebase.google.com/docs/firestore/reference/rest/v1beta1/projects.databases.documents/createDocument](https://firebase.google.com/docs/firestore/reference/rest/v1beta1/projects.databases.documents/createDocument)

---
This page is auto-translated from [/nishio/Cloud Firestore](https://scrapbox.io/nishio/Cloud Firestore) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.