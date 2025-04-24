---
title: "Transparent handling of multiple projects"
---

from [/villagepump/multiple projects transparently](https://scrapbox.io/villagepump/multiple projects transparently).
A mechanism to solve [I can't connect scrapbox projects to each other.

What you can do.
- You can refer to it from your project whether you write it in [/hub](https://scrapbox.io/hub) or [/villagepump](https://scrapbox.io/villagepump).
    - Of course, the reverse is also possible
- What you write in a private project can be referenced from a public project.
    - Even if you divide what you write out into public or private, you can still connect the pages as if it was all your idea.
    - This is probably the most attractive feature.
What you can't do.
- Connect all projects that exist in scrapbox.io
    - It's no wonder you can't.
    - Connect all [External Project Links
        - Difficult to get a list of [[External Project Links]] on each page in [[Scrapbox API]].

method
- link to
    - Using [[ScrapBubble]]@0.2.0 or later
    - The linking method has been changed from the conventional method using Indexed DB, so that external projects can be immediately treated as if they were the same project.
- Connect input completion
    - [[external-completion]]
    - The latest beta version is buggy and left out.
        - I'm going to fix it soon.<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
- combine the following three.
    - (WIP)[[scrapbox-text-bubble]]
        - Allow text preview only in a pre-defined [[External Project]].
        - Note that if you make all the contents of [[External Project]] visible, you will get the [I'll be happy to just post the link.
            - cf. [/daiiz/[[daiizScript]] Forgoing the cross-project text preview function].
            - > It is important for [[Growing a Wiki]] to create a page for your own project and organize it in your own way using [[Scrapbox citation notation]], etc.
                - <img src='https://scrapbox.io/api/pages/villagepump//icons/なるほど/icon' alt='/villagepump//icons/なるほど.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/villagepump/yosider/icon' alt='/villagepump/yosider.icon' height="19.5"/>
                - If the page is interesting, I think I would want to do this kind of work even if I could preview the contents.
                    - I feel that it is very time-consuming to copy the page of an external project that I have previewed into my own project, change it to citation notation, and add comments.<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
                    - It's a hassle, so it's doubtful they'll actually do the work.
                - With quotation notation, I feel like I can't tamper with the content.<img src='https://scrapbox.io/api/pages/villagepump/yosider/icon' alt='/villagepump/yosider.icon' height="19.5"/>
                        - I'm not allowed to tamper with it to make it a [[Citation under the Copyright Act]].
                        - I want to use the words in the [[My project]] link.
                - It would be interesting to create an icon of that person in your project, and then add the icon to the person's statements, so that you are virtually writing in Scrapbox in collaboration with that person.<img src='https://scrapbox.io/api/pages/villagepump/yosider/icon' alt='/villagepump/yosider.icon' height="19.5"/>
                        - [[sock-puppeting (i.e. pretending to be more than one person)]]
                    - [[public project]], that could be a problem.
            - Is it performance-wise ok to be able to preview all external project links...?
                - It's not a big deal, just hit [/scrapboxlab//api/pages/$projectname/$pagetitle](https://scrapbox.io/scrapboxlab//api/pages/$projectname/$pagetitle) once!
                - And the notation parse is instantaneous.
                - <img src='https://scrapbox.io/api/pages/villagepump//icons2/へえ〜/icon' alt='/villagepump//icons2/へえ〜.icon' height="19.5"/>
            - I feel like I need to know the `$projectname` of every external project to be able to [["display the contents of all external projects in the dark"]], but is it possible to get it?
                - It's easy to do, just PREVIEW the linked page!
                    - Because the link itself contains `$projectname`, the
                    - Oh, I see. I was mistaken with external-completion...<img src='https://scrapbox.io/api/pages/villagepump/yosider/icon' alt='/villagepump/yosider.icon' height="19.5"/>
                    - if it is possible<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
    - [[scrapbox-card-bubble]]
    - [[external-completion]]
- The first is not yet implemented, so it is still incomplete, but it can be handled quite transparently even in its current state.
    - You can suggest links written in another project.
        - [/takker/external-completion-2](https://scrapbox.io/takker/external-completion-2)
    - You can suggest another page with the same link.
        - [[scrapbox-card-bubble]]

<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>Reference
- transparently handle [/takker/external-project](https://scrapbox.io/takker/external-project).
---
This page is auto-translated from [/nishio/複数プロジェクトを透過的に扱う](https://scrapbox.io/nishio/複数プロジェクトを透過的に扱う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.