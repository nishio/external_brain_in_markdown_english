---
title: "2021-07-29Movidea Development Diary"
---

prev  [[2021-07-28Movidea Development Diary]]

`Namespace '".../node_modules/firebase/index"' has no exported member 'firestore'.`

index.d.ts

```typescript
declare namespace firebase.firestore { ... }
```


:

```
firebase.default.initializeApp(config);  // OK
firebase.initializeApp(config);  // Property 'initializeApp' does not exist on type ...
```


> simply instead of import * as firebase from 'firebase/app', do import firebase from 'firebase/app'
- [Typescript error on firebase.initializeApp(config) · Issue #4302 · firebase/firebase-js-sdk](https://github.com/firebase/firebase-js-sdk/issues/4302)
ts

```typescript
// import * as firebase from 'firebase/app'; // NG
import firebase from 'firebase/app'; // OK
```


In Regroup, it was "firebase":"^7.14.4". This time it's 8.8, so I guess that means the proper import method has changed with the upgrade.
I thought "that's a weird way to import" before, so I guess that means it's been fixed in a decent way.

---
In this case, if it is a sequential number, the cloud format is version 3, but version 2 contains information on handwritten paths, so "reading and saving over version 2 data" is not allowed.

Well, reading and saving past data as another name is not a feature we need right now.

Objects coming from firestores have no type information, so "defense at the water's edge" is necessary to validate them and then type them appropriately.

![image](https://gyazo.com/6482e4980895c043be0538121ce2d65c/thumb/1000)

If we make it possible to rewrite the mapname of the write destination, the read-only function will be meaningless.

![image](https://gyazo.com/8378e636437df078c33a967b7cb36d23/thumb/1000)
![image](https://gyazo.com/7de35162d80a08483b62f1a91e74b453/thumb/1000)
I got a status bar like I've seen somewhere else. w

Policy of not hiding the canvas by making it transparent
![image](https://gyazo.com/483a9ed21166434fda05fc57ee88ba81/thumb/1000)

By the way, the one under Scrapbox seems to be FontAwesome that is spinning, and the check for completed display is self-explanatory.
- [Font Awesome Examples](https://fontawesome.com/v4.7/examples/)
- [Kamon icons](https://nota.github.io/kamon/example/)
I don't have any particular preference to use differently, so I guess I'll just use FA.

2021-07-30
- [Animating Icons | Font Awesome](https://fontawesome.com/v5.15/how-to-use/on-the-web/styling/animating-icons)
    - `<i class="fas fa-spinner fa-spin"></i>`
- [React | Font Awesome](https://fontawesome.com/v5.15/how-to-use/on-the-web/using-with/react)
ts

```typescript
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome'
import { faCoffee } from '@fortawesome/free-solid-svg-icons'

const element = <FontAwesomeIcon icon={faCoffee} />
```

- final answer
    - `<FontAwesomeIcon icon={faSpinner} spin={true} />`
- Just check `FontAwesomeIconProps` to see what arguments it takes.

I didn't get much done today because of all the conference stuff (well, I knew that, so I did the display of icons, which I could do with less concentration).


This week's summary
- URL routing change
    - Assign a new URL to the page for testing
    - After accessing the route, I can now start the tutorial (the tutorial itself is not yet available).

- Drag in and out of groups.
- nested group

- Adding Sticky Notes
- Group/Ungroup a selection
- Delete: delete group, delete stickies, delete selected items at once

- Cloud storage function (on the way)

---
2021-07-31
- In retrospect, I think the Regroup phase used the metaphor of "connecting to a server."
    - He had a way of organizing them as "read-only connections" and "connections with reads and writes."
    - This is not an appropriate metaphor.
- Concrete reality
    - Local Changes
    - Overwrite and save to server
    - Single shot retrieval from server
    - Server Update Watch
- Combine these to create a "latest data is local/cloud" situation
    - local put mode
        - Update local state without worrying about the cloud
        - Indicate that it is in a mode where it is not saved in the cloud (= disappears when the browser is closed)
        - Should be able to "save this as new cloud data" after the fact
    - Put it in the cloud mode
        - Save local updates to the cloud as soon as possible.
            - I used to check for updates every three seconds.
            - That's because of "not fatal when it's buggy and in an infinite loop" or "I updated the state by dragging and the save ran for every event" or something.
        - Cloud updates are reflected locally as soon as possible.
        - While there is a discrepancy between cloud and local, show it
            - So-called "saving in progress" spinners
        - Last time I checked there was a "ReadOnly" in addition to this.
            - At first it was designed to be editable if you knew the URL.
                - As stationery for one's own use, "if you can access it, you can write on it" is natural.
                - But when you give it to someone, they get rewritten too.
            - So a read-only mode was created where "even if you know the URL, you can only look at it and not rewrite it.
                - This was something that when the cloud side was updated, the local side was updated as well.
                - This is a metaphor for "what you are working with at hand, others can see".
                - The theory that screen sharing is fine.
            - Even later, a case came up where we wanted to show a snapshot of a certain point in time of something that we would be updating.
                - Save as and share it's ReadOnly link
                - This is a "copy the document and give it to me" kind of thing.

- If you want to prevent others from rewriting it, do you log in and lock it down?
    - The current design is based on the "I want to make it easy to start without logging in.
    - While you're editing a quick start, you're the only one who knows the URL in the first place, so there's no need to protect it with a login.
    - Set access rights when it's time to share it with others, which is a natural process.
        - Same as Google Docs or something.

2021-08-01
- I didn't put a login feature on Handoff to focus on being able to pass URLs and collaboratively edit them, but it's time to consider including logging in and using it as an option.
    - If you want to create a cloud storage function from scratch.
    - Last time, we were making it up as we went along, so we should think properly about how it should be natural this time.
- Definite no-no's.
    - Require login before starting tutorial
    - The ability to obtain editing privileges from a URL passed in a view-only manner.
- something (which) one does not like
    - That when you use it alone and pass it on Handoff, you need to log in at the destination you pass it to.
        - Is it acceptable if you only have to log in once and the session lasts a long time?
- [Firebase Authentication](https://firebase.google.com/docs/auth?hl=ja)
    - > Anonymous Authentication
    - >  Use the ability to create temporary anonymous accounts to allow users to authenticate without requiring them to log in. If the user decides to register later, the anonymous account can be upgraded to a regular account, allowing the user to continue operations from where they left off last time.

next  [[2021-08-02Movidea/Kozaneba Development Diary]]

---
This page is auto-translated from [/nishio/2021-07-29Movidea開発日記](https://scrapbox.io/nishio/2021-07-29Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.