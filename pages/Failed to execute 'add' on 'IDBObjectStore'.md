---
title: "Failed to execute 'add' on 'IDBObjectStore'"
---

Unhandled Rejection (DataError): Failed to execute 'add' on 'IDBObjectStore': Evaluating the object store's key path did not yield a value.

Error when trying to write data to [[IndexedDB]] via [[Dexie.js]],
I was baffled because I was able to write a similar code in another project without any problems.

The cause was that the sample code was using the name "MyAppDatabase" for the database and using localhost:3000 as the development server.
The database created in the "other project" is visible because both projects are identical, so the database for this project is not created, and an error occurs when trying to write to a database with a different schema.

If the schema happened to be the same, it could have been a more complicated bug, so let's give the database a proper name that identifies the project.


---
This page is auto-translated from [/nishio/Failed to execute 'add' on 'IDBObjectStore'](https://scrapbox.io/nishio/Failed to execute 'add' on 'IDBObjectStore') using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.