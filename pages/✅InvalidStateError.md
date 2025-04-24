---
title: "✅InvalidStateError"
---

`Failed to execute 'transaction' on 'IDBDatabase': The database connection is closing.`

- > The reason could be ... or if there is a newer version of the db loaded in another tab or window, so the db has to close down to resume an upgrade.
    - [Error InvalidStateError: Failed to execute 'transaction' on 'IDBDatabase': The database connection is closing. · Issue #2710 · firebase/firebase-js-sdk](https://github.com/firebase/firebase-js-sdk/issues/2710)
- If this is the cause, now that the schema has been changed, it would only have occurred to those who left the tab open.
    - No schema changes planned at this time.
    - Might not happen in the foreseeable future.
- This is where the non-essential functionality of the past conversation list comes into play, so we want to watch for recurrence and allow the user to continue with the operation even if the error occurs.
    - → Report to Sentry behind the scenes without an error dialog.

---
This page is auto-translated from [/nishio/✅InvalidStateError](https://scrapbox.io/nishio/✅InvalidStateError) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.