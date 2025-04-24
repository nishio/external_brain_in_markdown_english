---
title: "pVectorSearch2023-06-06"
---

prev [[pVectorSearch2023-06-05]]

Store search results in Firebase and create permalinks to share them
- `$ npm install firebase`
- ![image](https://gyazo.com/82af3a39197d8eb14dd5749d40371f6f/thumb/1000)
    - Hoh, a new way of writing is being born.
    - Would you understand if I told ChatGPT to use the new way of writing?
        - I've rewritten myself into a new writing style.
- Get ID from URL in NextJS and display it? I said, and he wrote it down.
    - `pages/result/[id].js`
    - Forgot to specify TypeScript and written in JS
    - I asked him why I got a 404 even though it passed compile. I asked him and he gave me a checklist.
    - I was asked to check if I had the right path. I checked and found that I had put it in `app/pages/result/[id].tsx`.
        - I know about the typical mistakes people tend to make w

Released: [[Vector Search in Nishio]].

Page title image
- `/api/pages/:projectName/:pageTitle/icon`
- I was able to display ✅.

- Screen for administrator
    - Search queries are stored and made available for the administrator to see.
        - ✅Create a page with an explanation to that effect.
        - ✅When you search, you can either put the results into Firebase and give out permalinks.
    - ✅Publish
    - Add ❎[URL Fragment Text Directives
        - This is tricky.
            - For example, if there's Scrapbox notation in the mix, there's no notation in the browser text, so there's no hit.
            - If we're going to be serious about this, it needs to be plain text.
        - No, when you open a new page, Scrapbox assumes it's a line ID and takes it, so it doesn't trigger the behavior it should.
        - Commented out.
            - Scrapbox is not working? It's just that it's not working, so it might work with other services.
- Change the UI depending on whether you are an administrator (or specially authorized person) or not.
    - [GitHub - firebase/firebaseui-web: FirebaseUI is an open-source JavaScript library for Web that provides simple, customizable UI bindings on top of Firebase SDKs to eliminate boilerplate code and promote best practices.](https://github.com/firebase/firebaseui-web)
    - `$ npm install firebase firebaseui --save`
- ![image](https://gyazo.com/4f694f09f47ddd2ee50ae33b078e56c9/thumb/1000)
    - Looks aside, the admin page is up.
ts

```typescript
 let list = null;
 if (user.email === "nishio.hirokazu@gmail.com") {
   list = QueryList();
 }
 return (
   <>
     <div>Welcome, {user.displayName}!</div>
     {list}
   </>
 );
```

- It's like this, so you can only allow certain functions to certain people you know.
- I just had a chance to talk to him and I told him that I made this and got permission from hal_sk and yuiseki to make it a search target.
- Next action is to suck the data from the public project and index it without going through export
    - Should be able to do it with the well backup project code.

[GPT](https://chat.openai.com/share/50048950-c6f4-414b-b941-d26c2b1e235a)
next [[pVectorSearch2023-06-07]]

---
This page is auto-translated from [/nishio/pVectorSearch2023-06-06](https://scrapbox.io/nishio/pVectorSearch2023-06-06) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.