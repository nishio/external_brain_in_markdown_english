---
title: "Tapping the Scrapbox API with Cloud Functions"
---

from  [[Kozaneba Development Diary 2021-08-29]]
Hit [[ScrapboxAPI]] in [Cloud Functions

Introduction:.
- Added Scrapbox Kozane to Kozaneba.
- It is troublesome for humans to set various parameters
- I thought about giving them the URL of the page and they would hit Scrapbox's API to get the necessary data.
- However, due to CORS restrictions on Scrapbox's API, Scrapbox's API cannot be directly hit from the browser that opened Kozaneba.
- So we hit it with Cloud Functions.

Explanation with pictures
- ![image](https://gyazo.com/2dba023d5006b6d506f526d52bd3b7d2/thumb/1000)


Notes on what we did
- Upgrade Rate Plans
- I'm used to Python for the server side, but I don't want to just use Python all the time, and this one shouldn't be too hard, so I'll do it in Node.js.
    - I want to use [[scrabox-parser]] in the near future and
- [Writing Cloud Functions | Cloud Functions Documentation | Google Cloud](https://cloud.google.com/functions/docs/writing)
- How do you add Functions to the emulator?
:

```
$ firebase init emulators

You're about to initialize a Firebase project in this directory:

  /Users/nishio/kozaneba

Before we get started, keep in mind:

  * You are initializing within an existing Firebase project directory
```

![image](https://gyazo.com/78375db9636c8d0659bee712c2839151/thumb/1000)
It's done.
- Funny how the way to change the settings is "init"...

You're not doing it.
`$ firebase emulators:start --import firebase_emulator_data`
![image](https://gyazo.com/e1be11881d578cfc80150730880d92ce/thumb/1000)
> ⚠  functions: The functions emulator is configured but there is no functions source directory. Have you run firebase init functions?

`$ firebase init functions`
:

```
? What language would you like to use to write Cloud Functions? TypeScript
? Do you want to use ESLint to catch probable bugs and enforce style? Yes
? Do you want to install dependencies with npm now? Yes
```


Is this done?
`$ firebase emulators:start --import firebase_emulator_data`
:

```
⚠  Error: Cannot find module '/Users/nishio/kozaneba/functions/lib/index.js'. Please verify that the package.json has a valid "main" entry ...
⚠  We were unable to load your functions code. (see above)
   - It appears your code is written in Typescript, which must be compiled before emulation.
   - You may be able to run "npm run build" in your functions directory to resolve this.
```

Uh, they want me to build it first because I selected TypeScript.

I've got some sample code, so I'm going to uncomment it out and build it.
ts

```typescript
import * as functions from "firebase-functions";

// // Start writing Firebase Functions
// // https://firebase.google.com/docs/functions/typescript
//
export const helloWorld = functions.https.onRequest((request, response) => {
  functions.logger.info("Hello logs!", { structuredData: true });
  response.send("Hello from Firebase!");
});
```


This time it's done.
![image](https://gyazo.com/3c15fc1641e8e7a27ec20d7ec43212de/thumb/1000)
Access `http://localhost:5001/regroup-d4932/us-central1/helloWorld` with a browser and view the response

` functions.logger.info("Hello logs!", { structuredData: true });` As for ` functions.logger.info("Hello logs!", { structuredData: true });` I got this in the terminal where the emulator is running
:

```
i  functions: Beginning execution of "us-central1-helloWorld"
>  {"structuredData":true,"severity":"INFO","message":"Hello logs!"}
i  functions: Finished "us-central1-helloWorld" in ~1s
```


Now, create a ScrapboxAPI
Where can I find the specification of the request object?
![image](https://gyazo.com/7f105c12581a995e808e2796a65301fd/thumb/1000)
I see... same as Express.
[https://expressjs.com/en/4x/api.html#req](https://expressjs.com/en/4x/api.html#req)

ts

```typescript
export const get_scrapbox_page = functions.https.onRequest(
  (request, response) => {
    console.log(request.body);
    response.json(request.body);
    // functions.logger.info("Hello logs!", { structuredData: true });
    // response.send("Hello from Firebase!");
  }
);
```

js

```javascript
fetch("http://localhost:5001/regroup-d4932/us-central1/get_scrapbox_page", {
  method: "post",
  body: JSON.stringify({ foo: "bar" }),
})
  .then((x) => x.json())
  .then((x) => console.log(x));
```

output

```
{"foo":"bar"}
```

Okay, the interaction part is done.
Now let's hit Scrapbox's API.

ts

```typescript
import fetch from "node-fetch";

export const get_scrapbox_page = functions.https.onRequest(
  (request, response) => {
    const body = JSON.parse(request.body);
    const url = body.url;
    const api_url = url.replace("scrapbox.io/", "scrapbox.io/api/pages/");
    fetch(api_url).then((req) => {
      console.log(req);
      req.text().then((text) => {
        console.log(text);
        response.send(text);
      });
    });
  }
);
```

js

```javascript
fetch("http://localhost:5001/regroup-d4932/us-central1/get_scrapbox_page", {
  method: "post",
  body: JSON.stringify({
    url: "https://scrapbox.io/nishio/2021-08-28Kozaneba%E9%96%8B%E7%99%BA%E6%97%A5%E8%A8%98",
  }),
})
  .then((x) => x.json())
  .then((x) => console.log(x));
```

output
![image](https://gyazo.com/8703a9fcaa4f8fec4b0c26b8443f1a3d/thumb/1000)
It's done.

Then let's hit this API from the app -> CORS
[https://cloud.google.com/functions/docs/writing/http#handling_cors_requests](https://cloud.google.com/functions/docs/writing/http#handling_cors_requests)
- ![image](https://gyazo.com/c22f02704c9ea44de89383deddd5643c/thumb/1000)
I see.
ts

```typescript
export const get_scrapbox_page = functions.https.onRequest((req, res) => {
  res.set("Access-Control-Allow-Origin", "*");

  if (req.method === "OPTIONS") {
    // Send response to OPTIONS requests
    res.set("Access-Control-Allow-Methods", "GET");
    res.set("Access-Control-Allow-Headers", "Content-Type");
    res.set("Access-Control-Max-Age", "3600");
    res.status(204).send("");
    return;
  }

  const body = JSON.parse(req.body);
  const url = body.url;
  const api_url = url.replace("scrapbox.io/", "scrapbox.io/api/pages/");
  fetch(api_url).then((req) => {
    req.text().then((text) => {
      res.send(text);
    });
  });
});
```

I can now hit it from the app with no problem.

ready, able
![image](https://gyazo.com/9c5646f9b6aae0c45c0cbc4351f97867/thumb/1000)
Then you can firebase deploy...
`$ firebase deploy`
![image](https://gyazo.com/702e52e97041dee67073fc8713680227/thumb/1000)
ESLint complains and is noisy, so I disable it.

`$ firebase init functions`
:

```
? Do you want to use ESLint to catch probable bugs and enforce style? No
```


Deploy again
`$ firebase deploy`
:

```
i  functions: creating Node.js 14 function get_scrapbox_page(us-central1)...
✔  functions[get_scrapbox_page(us-central1)]: Successful create operation. 
i  functions: cleaning up build files...
Function URL (get_scrapbox_page(us-central1)): https://us-central1-regroup-d4932.cloudfunctions.net/get_scrapbox_page
```

![image](https://gyazo.com/74cc324e13b6c473331b5535e3f4b57d/thumb/1000)
It's done.

replace `localhost:5001` to `https://us-central1-regroup-d4932.cloudfunctions.net/get_scrapbox_page` to hit

ts

```typescript
fetch("https://us-central1-regroup-d4932.cloudfunctions.net/get_scrapbox_page", {
  method: "post",
  body: JSON.stringify({
    url: "https://scrapbox.io/nishio/2021-08-28Kozaneba%E9%96%8B%E7%99%BA%E6%97%A5%E8%A8%98",
  }),
})
  .then((x) => x.json())
  .then((x) => console.log(x));
```


It's done.
![image](https://gyazo.com/56af245ad9d26f348640d586b1258b98/thumb/1000)

---
This page is auto-translated from [/nishio/Cloud FunctionsでScrapboxのAPIを叩く](https://scrapbox.io/nishio/Cloud FunctionsでScrapboxのAPIを叩く) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.