---
title: "Kozaneba Development Diary 2022-05-26"
---

- [[Kozaneba Development Diary 2021-12-10]]
- [[Kozaneba Development Diary 2022-03-18]]
- [[Kozaneba Development Diary 2022-03-24]]

from [/villagepump/workroom 2022/05/26](https://scrapbox.io/villagepump/workroom 2022/05/26).

<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- Miscellaneous Task List
    - A: Isn't it possible to import Kozaneba's UserScript like Scrapbox? That too from Scrapbox. I'll give it a try.
    - B: I heard somewhere (Nota Tech Conf?) that "functionally usable but not good looking" should not be neglected. Kozaneba is in exactly that situation, so I'm going to improve the appearance.
    - C: You can already use Kozaneba in its current state to move a Scrapbox card to any position and share it with others by attaching a permalink to the card's placement.

### 13:00
- 13:25 Pomodoro begins🍅.
    - > A: Isn't it possible to import Kozaneba's UserScript like Scrapbox? That too from Scrapbox. I'll give it a try.
    - It is not enough to just write import in UserScript.
        - `import "https://scrapbox.io/api/code/nishio/Kozaneba%E3%81%AEUserScript/script.js";`
        - `Cannot use import statement outside a module`
        - Hmmm... I'm currently realizing UserScript by reading from LocalStorage and eval'ing, but that doesn't mean I can't import.
        - Oops, if you put in UserScript that causes serious errors, it dies on startup so you can't reach the edit screen (terrible).
            - I deleted it in the developer tools, but that's not good.
    - dynamic import is not allowed due to CORS restrictions
        - ![image](https://gyazo.com/fdb08ed037f662633fa1c572dba6bde9/thumb/1000)
        - Even if you replace the header on the server only for URLs you import directly, if you import code from another page from the code placed in Scrapbox, it will die there, so you won't be very happy anyway.
        - If you want to do it, you need a mechanism to collect all the files with dependencies in the form of a [[scrapbox-bundler]] or something like that.

            - [[ServiceWorker]]で解決できそう<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
                - ServiceWorker: A service that can intercept all HTTP requests, including `fetch` and `<img>`, and do whatever it wants.
                - Now, if you replace `https://scrapbox.io/api/code/` to fetch on the server, you can play around with all the `imports` or whatever.
                - Real world example: [Swdev: true no bundle frontend](https://zenn.dev/mizchi/articles/true-no-bundle-swdev)
                    - Import is intercepted and bundled locally and returned.
            - I see.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
            - hijack<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>

    - When you save the UserScript, it says Saved on the console, but it should be on the screen.
    - Breakdown on improving appearance with 4 minutes remaining
        - The button enclosure line is gone.
        - Help is available from the hatena icon on the status bar in the lower left corner, but ordinary users do not notice it, so a help button is placed in the upper right corner.
        - Only the arrow heads are 100% opaque.
            - Needs a major refactor, no real harm in use, so we left it alone, but it looks bad, so we'll improve it.
        - Arrowheads for nested groups may be misaligned.
            - Reproduction conditions are not clear

- 13:58 🍅<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - > Help is available from the hatena icon on the status bar in the lower left corner, but ordinary users don't notice it, so a help button is placed in the upper right corner.
    - 10min I added a help button.
        - ![image](https://gyazo.com/77bd12bcbb4f5a6efe7f02eec0f3528f/thumb/1000)
    - > The button enclosure line is gone.
    - 21min
        - ![image](https://gyazo.com/ccbe22abcddd817345735c1502a91756/thumb/1000)
        - CSS Specificity issue, DevMenu is an ID, but buttons added by user scripts are classes, so they did not have enough priority
    - Two minutes left, commit, close tab and prepare for next
    - I pushed it.
    - Notes of Concern
:

```
WARNING in ./node_modules/@progfay/scrapbox-parser/esm/parse.js
Module Warning (from ./node_modules/source-map-loader/dist/cjs.js):
Failed to parse source map from '/Users/nishio/kozaneba/node_modules/@progfay/scrapbox-parser/src/parse.ts' file: Error: ENOENT: no such file or directory, open '/Users/nishio/kozaneba/node_modules/@progfay/scrapbox-parser/src/parse.ts'
```



### 14:00
- 14:32 🍅<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - > Only the arrow heads are 100% opaque.
    - before
        - ![image](https://gyazo.com/b409d614e2e158f361ba980172136b11/thumb/1000)
        - I see, to begin with, the current code has two steps: "draw a line" and "add an arrow head if necessary".
        - It's bracketed out because the drawing of the arrow heads is common regardless of the type of line, but it's wrong that they're separated on the time axis.
        - Initially, it was loosely coupled, which was fine, but it was ruined when the specification to match transparency was added.
        - It should have been separated lexically and integrated with drawing a line on the time axis with a function call.
        - 8 minutes remaining
        - ![image](https://gyazo.com/a9d0ec92f97faddd12037bb017f1e70e/thumb/1000)
        - One step further ✅
### 15:00
- break<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - The head of the translucent arrow overlaps and darkens because of the overlapping translucent lines.
    - To solve this problem, it is necessary to change the current structure that treats the object as a unit of "line" and create a layer that treats it as a unit of "object composed of several lines".
    - I wonder if we can do it in one pomodoro, we should commit at the moment anyway.
- 15:07 🍅<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - ![image](https://gyazo.com/655e4e98331b7ad24a3a7f5bd0e5401d/thumb/1000)
    - Fix bugs and commit
    - I introduced the SVG g element.
        - ![image](https://gyazo.com/fe5385f19ce49d8100aa8d74f1582100/thumb/1000)
        - I think we can do this.
    - ![image](https://gyazo.com/aefff89cb4c2e46fe9371d888d77cca7/thumb/1000)![image](https://gyazo.com/f35ed0d225422eaab62365a1b85cafeb/thumb/1000)
        - Perfect!
    - I'd like to tweak the relationship between distance and density a bit more.
        - Let's commit so far for now ✅.
    - Modified to make the change in intensity continuous ✅.

- <img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - fixed `Failed to parse source map`
        - `.env`: `GENERATE_SOURCEMAP=false`
        - [javascript - Failed to parse source map - Stack Overflow](https://stackoverflow.com/questions/70599784/failed-to-parse-source-map)
    - I've confirmed that the Netlify deployment is successful, I'll have to write release notes.
- 17:20 🍅<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - [/kozaneba-forum-jp/release-note](https://scrapbox.io/kozaneba-forum-jp/release-note)Updated both in Japanese and English
    - We sought ways to reproduce the problem for the next fix.
        - ![image](https://gyazo.com/eb11d1a9b3882d331c37e2fac21f569e/thumb/1000)
        - Condition to reproduce the problem, nesting is not required, but it seems to write arrows for groups.
        - I guess I better make a test case for Cypress first.

- 18:35 I'll continue development tomorrow.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - [[How to organize Scrapbox cards in Kozaneba]] I only made the title, I'll write the contents later.
    - I saw "Anki" above and suddenly came up with the idea of turning [[oblique strategy]] into Anki.
    - By declaring what I'm going to do today at the beginning of the page, I've prevented myself from getting sidetracked and starting to do Anki.
### 19:00
- 7:25 p.m. I feel sleepy after dinner.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>

### 22:00
- 23:00 I woke up.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- 23:18 🍅<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - [[How to organize Scrapbox cards in Kozaneba]] wrote 1 pomodoro ✅.

---
This page is auto-translated from [/nishio/Kozaneba開発日記2022-05-26](https://scrapbox.io/nishio/Kozaneba開発日記2022-05-26) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.