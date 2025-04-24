---
title: "Kozaneba Development Diary 2021-08-03"
---

prev  [[2021-08-02Movidea/Kozaneba Development Diary]]

Today's Picture of the Day
![image](https://gyazo.com/c2db45f96be0e3dbd64f864e8dd49f58/thumb/1000)


---
![image](https://gyazo.com/a9bf026f6d8fedf4194fad70e273b5c0/thumb/1000)
![image](https://gyazo.com/c2db45f96be0e3dbd64f864e8dd49f58/thumb/1000)
I found that Google is telling me "This browser is not secure and will not let you log in" in a Cypress environment, this is... what should I do...

This is what happens when you can log in
![image](https://gyazo.com/f1daec02929883a67f49b843261ec29c/thumb/1000)


![image](https://gyazo.com/0f7adba500d9b354f594cf93fc6d71da/thumb/1000)
- [Firebase Local Emulator Suite Overview](https://firebase.google.com/docs/emulator-suite?hl=ja)
- [[Firebase Local Emulator]]


![image](https://gyazo.com/b5a724ec32a5170c33982ff23d323d9e/thumb/1000)

[https://github.com/prescottprue/cypress-firebase](https://github.com/prescottprue/cypress-firebase)
> Error
>  Your API key is invalid, please check you have copied it correctly.
I thought it would be easy to do, but I ran into an error with little information.

Maybe it would be better to configure Local Emulator Suite and do the authentication on a local server
[https://firebase.google.com/docs/emulator-suite/install_and_configure?hl=ja](https://firebase.google.com/docs/emulator-suite/install_and_configure?hl=ja)

2021-08-04
`$ firebase init emulators`
:

```
=== Project Setup

First, let's associate this project directory with a Firebase project.
You can create multiple project aliases by running firebase use --add, 
but for now we'll just set up a default project.

? Please select an option: Use an existing project

Error: Failed to list Firebase projects. See firebase-debug.log for more info.
```


They say the old version of the login information fails, so you should log in again.
`$ firebase logout`
`$ firebase login`
OK, done.

`$ firebase emulators:start`
- ![image](https://gyazo.com/c4dba360588a600e820155a5a0f04b73/thumb/1000)
- ![image](https://gyazo.com/030750d60fbb7f81db39db7e3ee3566e/thumb/1000)
- ![image](https://gyazo.com/581925abfc1da86af130f48d1863ba9a/thumb/1000)
It's not an anonymous login, but it's showing up as anonymous because there's no displayName.

Users can be configured on the emulator side
![image](https://gyazo.com/66b20dfa8e4aff84601c4de6941b2c88/thumb/1000)
![image](https://gyazo.com/14e588098aa587c00dd2e57e94cd5803/thumb/1000)
![image](https://gyazo.com/64989f1edefacf1f3f1d8e37c17d2960/thumb/1000)
The user name is displayed properly.

---
`$ firebase emulators:start`
:

```
⚠  firestore: Did not find a Cloud Firestore rules file specified in a firebase.json config file.
⚠  firestore: The emulator will default to allowing all reads and writes. Learn more about this option: https://firebase.google.com/docs/emulator-suite/install_and_configure#security_rules_configuration.
```


[https://firebase.google.com/docs/emulator-suite/install_and_configure#security_rules_configuration](https://firebase.google.com/docs/emulator-suite/install_and_configure#security_rules_configuration)

There is a syntax error in the official sample, though.
I wrote a configuration file and installed Java and it worked.

![image](https://gyazo.com/390da980e7dfa8c5b3c2b7bd1e9e179d/thumb/1000)

Firestore is running locally, so I can always delete the whole thing without regret, and I'll try to save it in a mess.
- I mean, if you can't delete everything from the test code, the test will behave differently, as it should.
- There was there, there was there
    - >  The Firestore production environment does not provide a platform SDK method for flushing the database, but the Firestore emulator provides a REST endpoint for this purpose.
        - [Connect your app to the Cloud Firestore emulator | Firebase](https://firebase.google.com/docs/emulator-suite/connect_firestore?hl=ja#web-v8)

[[Cypress+Firestore=invalid data]]

Cypress+Firestore+experimentalForceLongPolling=CORB

`firebase.firestore().settings({ experimentalForceLongPolling: true })`
- [firebase - can't use cypress to test app using using firestore local emulator - Stack Overflow](https://stackoverflow.com/questions/59336720/cant-use-cypress-to-test-app-using-using-firestore-local-emulator)
- `Cross-Origin Read Blocking (CORB) blocked cross-origin response https://firestore.googleapis.com/google.firestore.v1.Firestore/Write/channel?... with MIME type text/plain. See https://www.chromestatus.com/feature/5629709824032768 for more details.`
- same: [Firestore emulator does not work in Cypress · Issue #1975 · firebase/firebase-tools · GitHub](https://github.com/firebase/firebase-tools/issues/1975)

[https://githubmemory.com/repo/firebase/firebase-js-sdk/issues/4917](https://githubmemory.com/repo/firebase/firebase-js-sdk/issues/4917)
> you should be using the useEmulator() after the firestore.settings({ experimentalAutoDetectLongPolling: true }).

ts

```typescript
const db = firebase.firestore();
// NG
db.useEmulator("localhost", 8080); 
db.settings({ experimentalForceLongPolling: true });
// OK
db.settings({ experimentalForceLongPolling: true });
db.useEmulator("localhost", 8080);
```


it works!
![image](https://gyazo.com/6a561071ab7f9abd76a19a9ba9f12d45/thumb/1000)

- ExperimentalForceLongPolling must be set to true
- You need to do this before you useEmulator.

next  [[Kozaneba Development Diary 2021-08-05]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-03](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-03) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.