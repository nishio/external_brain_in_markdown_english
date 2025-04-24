---
title: "A few thoughts on thin literary programming."
---

from [/villagepump/thin-literary-programming-thought-a-bit](https://scrapbox.io/villagepump/thin-literary-programming-thought-a-bit).
- [[Thin Literary Programming]] を少し考えてた<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- I'm writing a program in VSCode right now,
- Scrapbox does indeed have some nice features that are not in the current programming environment.
    - Like a line link.
- But the program environment has a lot of features in the browser that are not available in the Scrapbox environment.
    - type check
    - supplementation
    - GitHub Copilot
    - Jump to definition
    - symbol jump
        - Jump to symbols in the same file
        - In markdown, you can use `# headings` and so on.
    - Automatic reload of development server
    - Automated Testing
    - Version Control with Git
    - Automatic deployment after push to repository
    - The only decent implementations are formatter and[[LSP]]なし補完くらいだろうなあ<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
- Therefore, it is more straightforward to bring Scrapbox functionality to the VSCode side than to move the development environment to the Scrapbox side.
    - +1<img src='https://scrapbox.io/api/pages/villagepump/sta/icon' alt='/villagepump/sta.icon' height="19.5"/>
- That's the whole point.
    - As an extension of the editor called VSCode [[Wiki running on local file system]].
- So, that's why
    - Wiki that runs on the local file system as an extension to the editor called Emacs
    - Isn't it a revival of [[howm]] that is which became
    - In Vim, <img src='https://scrapbox.io/api/pages/villagepump/kuuote/icon' alt='/villagepump/kuuote.icon' height="19.5"/> made it.
- What I wrote here is a feeling I may or may not make during Golden Week.
    - Most programming languages have the ability for multi-line comments.
    - so that you can write a Scrapbox-like link there.
    - [I want to use Scrapbox offline.
    - Edit offline without internet and git push when you are online
- How to make VSCode extensions, I don't know anything about it.
    - I'll look into the possibility that "there's already a howm for VSCode."
        - [VS Code used by writers - Extensions｜Tadanori Kurashita｜note](https://note.com/rashita/n/n6bd4705c060c)
            - [I created an extension for Visual Studio Code called ActionLock | WriteIfElse](https://blog.bulkus.net/post/vscode-actionlock/)
                - >  [[ActionLock in Howm]] would have been useful.
                - Only some of the features are there.
            - [https://github.com/satokaz/vscode-memo-life-for-you](https://github.com/satokaz/vscode-memo-life-for-you)
                - Open "Today's date and time page" with shortcut keys like howm
    - [Your First Extension | Visual Studio Code Extension API](https://code.visualstudio.com/api/get-started/your-first-extension)
    - [[vscode-wiki]]なるものはある<img src='https://scrapbox.io/api/pages/villagepump/kuuote/icon' alt='/villagepump/kuuote.icon' height="19.5"/>
- A docstring becomes a wiki kind of thing.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
    - In emacs, it looks like a minor mode, so it could be implemented by combining existing modes (I'm not sure).<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
    - [[Ongoing Documentation]] の概念もヒントになるかも<img src='https://scrapbox.io/api/pages/villagepump/sta/icon' alt='/villagepump/sta.icon' height="19.5"/>

- I think it's a good idea to extend VSCode as something we can do now,[[Thin Literary Programming]] の理想形がどんな形なのかは気になる<img src='https://scrapbox.io/api/pages/villagepump/yosider/icon' alt='/villagepump/yosider.icon' height="19.5"/>

---
from [/villagepump/first half of Golden Week Chronicles 2022](https://scrapbox.io/villagepump/first half of Golden Week Chronicles 2022).
    - [[A few thoughts on thin literary programming.]] の件、とりあえずHello world的拡張を作って「VSCodeの拡張を作ったことがある」実績解除をやろうと思った<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - Hello world is ready.
    - Can reload with Cmd+R. Feels like developing a web app.

---
from [/villagepump/first half of Golden Week Chronicles 2022](https://scrapbox.io/villagepump/first half of Golden Week Chronicles 2022).

[[ActionLock]]<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- [[ActionLock in /villagepump/Howm]].
- reading comprehension
    - Once every 100 seconds, it updates text decorations, such as underlining, and determines if the cursor is in the RANGE at that time.
        - [/villagepump/ActionLock#626e5273aff09e00009a8e83](https://scrapbox.io/villagepump/ActionLock#626e5273aff09e00009a8e83)
    - The range is defined by a regular expression.
        - [/villagepump/ActionLock#626e5294aff09e00009a8f1c](https://scrapbox.io/villagepump/ActionLock#626e5294aff09e00009a8f1c)
    - Pressing Enter when in range executes the command.
        - [/villagepump/ActionLock#626e52c2aff09e00009a9065](https://scrapbox.io/villagepump/ActionLock#626e52c2aff09e00009a9065)
- I wish I could write a story like "I wish I could write a story like "I wish I could write a story like "I wish I could write a story like "I wish I could write a story like "I wish I could write a story like
        - [[Thin Literary Programming]].
- VSCode can't do it now, so we'll have to do it in Scrapbox.
- I tried it and got a page with only the source code posted...
    - This is only about 3 files now, but if there are more, would it be better to have separate pages for each source file...
- Would it be easy enough to jump to the corresponding page in Scrapbox if you enter on a string like `[/foo/bar]`?
- What should happen when you Enter on `[foo]`?
    - Scrapbox has an implicit jump target at the beginning of the page.
    - Clicking on the foo link results in a jump to the jump target at the beginning of the foo page
    - Each source code in VSCode has a file name, but not a title for humans in the Scrapbox sense.
        - Need a notation to create jump targets?
            - Create a jump target at an arbitrary position in the page, like [[come-from link]].
        - For example, if you write `[< determine if the cursor is in the range]` at [[ActionLock#626e5273aff09e00009a8e85]] in the source code, it will jump to that position when you enter with `[determine if the cursor is in the range]`. And so on.
        - I wonder if this can be done.
            - [https://code.visualstudio.com/api/references/vscode-api#WorkspaceSymbolProvider%3CT%3E](https://code.visualstudio.com/api/references/vscode-api#WorkspaceSymbolProvider%3CT%3E)
        - Even if you can't jump directly, you can do a "symbol search on that string" and get there in two hops.
            - That should work with file names, etc. in the bracket.

[[yahow]]

---
This page is auto-translated from [/nishio/シン・文芸的プログラミングを少し考えた](https://scrapbox.io/nishio/シン・文芸的プログラミングを少し考えた) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.