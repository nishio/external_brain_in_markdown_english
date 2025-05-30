---
title: "Record of the birth of ai_museum"
---

from [[ai_museum]]
Record of the birth of ai_museum

2022-09-07 (private: [/mitoujr/Stable Diffusion#6317738aaff09e00000841ba](https://scrapbox.io/mitoujr/Stable Diffusion#6317738aaff09e00000841ba))
I'm running it on a WSL on a gaming PC (Windows) and I've added Dropbox to the host OS so that the generated images go into Dropbox.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- The prompts are also read from a file in Dropbox.
- It automatically reloads when the seed is incremented, so if you write a prompt appropriately and leave it alone, a picture will grow, farming style.
- I'm not sure if I should write an application to tile the growths to make them easier to select.
    - I'm not sure whether to write it in Python or Node, to be precise.

2022-09-08 (private [/mitoujr/workroom2022-09-08](https://scrapbox.io/mitoujr/workroom2022-09-08))
### 1:00
- I want to display a list of AI-generated images.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - I decided to do it with Next.js.
        - We decided that writing server-side code in TypeScript and writing client-side code in Python (which is not possible, so we will use it with JS) would benefit from the former's know-how in the future.
        - I named it [[ai_museum]].
    - I'm trying to figure out how to see the filesystem from Node.
        - `fs.readdirSync`
        - [File system | Node.js v18.8.0 Documentation](https://nodejs.org/api/fs.html#fsreaddirsyncpath-options)
        - The file list was taken.
    - Find out how to static serve images
        - It's local only, so you can either symlink to Dropbox in public
        - It's done.
    - Now, let's look at the image list as a result of hitting the API...
        - Oh, fetch is asynchronous, so it would be Promise.
        - Or you can hit it with useEffect and update it.

### 3:00
- succession
    - The list of images in one folder now appears.
        - Why do they line up vertically...
        - It was the flex-direction: column.
        - I wonder how they were supposed to be lined up so tightly...
            - flex-wrap or
    - I can now click to zoom in and out.
    - Next is the expansion display when there is a "folder within a folder".
        - Passing parameters to the API is...
ts

```typescript
    fetch("/api/get_images", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ folder }),
    })
```

        - then it will be in `req.body.folder`, which is convenient!
            - [/nishio/Unexpected token o in JSON](https://scrapbox.io/nishio/Unexpected token o in JSON)
        - Oh, I'll have to repeat this, I'll have to hit the API asynchronously, I don't know what to do.
        - Promise.all solves the problem.

### 23:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Clicked images are now enlarged in a modal dialog.
    - I want to display prompt info here, etc.
        - I've changed the way I store data several times, so what to do...
        - There's fs.exists, let's see if we can determine that.
            - deprecated
            - There is a fs.existsSync(path)
            - It's done.
    - Add the ability to move reviewed images.
        - fs.rename
        - I wrote it onClick on the client side and it didn't work, that's right.
        - So you just put an API on it.
        - It's done.
- The images in the subfolder are tiled like this
    - ![image](https://scrapbox.io/files/633e55151b49e40022b16ccc.png)
- Clicking on the button displays detailed information in a modal, and pressing "excellent!" here moves the file to a folder with good images.
    - ![image](https://scrapbox.io/files/633e551c36081a00237100f0.png)
- The test user (my wife) has gone to bed, so I'll continue tomorrow.

### chit-chat
- Today I learned<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - I wondered if I should write a tool that runs locally to help sort images in Python, which I'm used to for file processing and such, and use HTML+JS for the UI, or do Next.js in TypeScript, but the conclusion Next.js was super useful.
    - UI part can be easily created with React's JSX.
    - The API part is also just copying and increasing the sample files in the API folder.
        - It works without having to write routing or anything.
    - File manipulation systems, the ones in Python are usually in Node, too, and are called Sync.

---
This page is auto-translated from [/nishio/ai_museum誕生の記録](https://scrapbox.io/nishio/ai_museum誕生の記録) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.