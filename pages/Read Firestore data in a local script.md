---
title: "Read Firestore data in a local script"
---

2023-07-09
1:
- `$ npm init -y`
2:
- `$ npm install firebase-admin --save`
3:
js

```javascript
const admin = require('firebase-admin');
let serviceAccount = require('path/to/serviceAccountKey.json');

admin.initializeApp({
  credential: admin.credential.cert(serviceAccount)
});

let db = admin.firestore();
```

4:
- `$ node yourScript.js`

I got a dependency error when I tried to add it to the project's node_modules because I went through one.
- I'm not moving any other sources in the project, so just do 1 in a subfolder.

`let serviceAccount = require('path/to/serviceAccountKey.json');`
- The path for this will be something like `'. /foobar-fffff-firebase-adminsdk-xxxxxxx-xxxxxxxxxx.json'`.
    - `. /`.


---
This page is auto-translated from [/nishio/ローカルスクリプトでFirestoreのデータを読む](https://scrapbox.io/nishio/ローカルスクリプトでFirestoreのデータを読む) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.