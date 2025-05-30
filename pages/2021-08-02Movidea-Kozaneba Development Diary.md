---
title: "2021-08-02Movidea/Kozaneba Development Diary"
---

Windows users
- A type of touchpad that even recognizes four-finger gestures
- Can you operate it?
The more uncertain something is, the quicker it should be verified.
- Authentication and cloud storage should be put aside for now to verify if it can be operated.
- To do so, we need to
    - Deployment.
    - Either go with Movidea or change now to Kozaneba, which I was planning to change when I get settled.
        - [[2021-07-15Movidea Development Diary#60effb2baff09e00003b7dcd]]
        - I'm going to Kozaneba now because it's twice as hard to change the repository and Netlify settings again later.
        - Change the source, title bar, etc. later.
    - Make a small sample to test if it can be manipulated
        - [https://kozaneba.netlify.app/#tinysample](https://kozaneba.netlify.app/#tinysample)
    - I took a video of me operating with two finger gestures.
        - [https://youtu.be/FvZvZ1jVKrk](https://youtu.be/FvZvZ1jVKrk)
- Chrome on Windows has a behavior that locks you into moving in that direction when you first move vertically or horizontally
    - 980479 - two-finger trackpad movement locks in as horizontal or vertical - chromium
    - [https://bugs.chromium.org/p/chromium/issues/detail?id=980479](https://bugs.chromium.org/p/chromium/issues/detail?id=980479)


Certification
- anonymous authentication
    - ![image](https://gyazo.com/85e7eba0fd4c3bd40818c6694c063ec9/thumb/1000)

[Using JavaScript for Firebase Anonymous Authentication](https://firebase.google.com/docs/auth/web/anonymous-auth?hl=ja)
- > Convert an anonymous account to a permanent account
- >  After an anonymous user registers for the app, he/she may need to be able to continue working under the new account. For example, if a user added items to their shopping cart prior to registering for the app, they may want to add those items to the shopping cart of their new account as well. The procedure is as follows
- >  ...
- If the >link call succeeds, the user's new account will have access to the anonymous account's Firebase data.
- I wonder if the user.uid will be the same after linking.
    - [Linking multiple authentication providers to an account using JavaScript | Firebase](https://firebase.google.com/docs/auth/web/account-linking?hl=ja)
    - > User can be identified by the same Firebase user ID regardless of the authentication provider used for login.
    - I see. So it's a one-to-one correspondence between the user and the authentication provider.

[Authentication State Persistence | Firebase](https://firebase.google.com/docs/auth/web/auth-state-persistence?hl=ja)
- Seems to leave me logged in by default, which is fine.

At least I got as far as "current user: null".
- ✅ Log in anonymously, reload the browser and you are still logged in.
- I need to create a logout menu.
- ✅If you log out and log in anonymously again, you'll get a different uid.
- ✅Google OAuth
    - ![image](https://gyazo.com/c22edbc879ea0a5937af97351b2b59be/thumb/1000)
        - [Showing a custom domain during sign in](https://cloud.google.com/identity-platform/docs/show-custom-domain)
            - [Connect a custom domain | Firebase](https://firebase.google.com/docs/hosting/custom-domain)

(computer) console
- ![image](https://gyazo.com/582157f59c7c6dad53f159fa3b8e7d98/thumb/1000)
- Ha, I see, this is how it goes.

ts

```typescript
import "firebaseui";
var ui = new firebaseui.auth.AuthUI(firebase.auth());
// 'firebaseui' refers to a UMD global, but the current file is a module. Consider adding an import instead. ts(2686)
```

ts

```typescript
import firebaseui from "firebaseui";
// Attempted import error: 'firebaseui' does not contain a default export (imported as 'firebaseui').
```

ts

```typescript
import * as firebaseui from "firebaseui";
// Import may be converted to a default import. ts(80003)
```

![image](https://gyazo.com/f20f0b9ebab31b694a6f6233970dbcb5/thumb/1000)

html

```html
<link type="text/css" rel="stylesheet" href="https://www.gstatic.com/firebasejs/ui/4.8.1/firebase-ui-auth.css" />
```

![image](https://gyazo.com/4d92cd515b20dd245b8910bb42c81ccf/thumb/1000)

[https://www.npmjs.com/package/identicon](https://www.npmjs.com/package/identicon)

Thinking again now that the parts are much more complete.

reprint
- Definite no-no's.
    - Require login before starting tutorial
    - The ability to obtain editing privileges from a URL passed in a view-only manner.
- something (which) one does not like
    - That when you use it alone and pass it on Handoff, you need to log in at the destination you pass it to.
        - Is it acceptable if you only have to log in once and the session lasts a long time?

By default, if you know the URL, you can access it.
- Access rights can be narrowed down later.
    - You could limit WRITE to specific users.
    - You could create a lead-only link.
        - This is the same as limiting WRITE to one author.
    - Only the owner has this "right to change access rights".
        - Create anonymous users even if not logged in for owner identification here?
        - Or do you require a login to save to the cloud?
            - That's not a crazy design, it happens all the time.
            - On the other hand, does it seem iffy to start using it without an account?
                - Not so much of a concern because it's OAuth, not an email and password account?

It is necessary at the time of narrowing down access rights, but I wonder if it would be natural to be told to "log in" at the time of saving to the cloud before that.
- And at that stage, I haven't narrowed down the access rights, so I can write when I Handoff.
- Then, when I tried to create a read-only view and share it, the device that was able to write on it would not be able to write on it... I thought, why not just keep track of the WRITER and focus on the existing WRITER instead of focusing on the owner when creating a read-only view?
- The terminal passed by Handoff logs in anonymously and writes its own user ID to writer.
    - Now you can also "visualize how many people are connected in write mode right now.

---
This page is auto-translated from [/nishio/2021-08-02Movidea/Kozaneba開発日記](https://scrapbox.io/nishio/2021-08-02Movidea/Kozaneba開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.