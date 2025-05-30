---
title: "Experiment with importing wiki into Scrapbox"
---

Related [[Mechanical Additions in Scrapbox]].

from [/villagepump/content-importing-surprisingly-maybe](https://scrapbox.io/villagepump/content-importing-surprisingly-maybe).
<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- Experiment with importing content
    - I've been experimenting with that for a while now because I thought the English Dominion wiki was CC-BY-NC-SA and could be imported with impunity in a public project.
    - [/dominion](https://scrapbox.io/dominion)
- Since the original content was a wiki, I imported it in a way that made use of its links, but there were quite a few links that said "link to X but display Y", so I couldn't import it perfectly.
- But, it doesn't feel subjectively bad in terms of working within that project.

- I had a feeling that importing content mechanically would be iffy, but maybe there isn't much of a problem with that link being somewhat broken when importing something with links.
    - When you have a link called FooBar and a link called FooBar|Baz, it is easy in Scrapbox to merge them after the fact.
    - You can also notice that there are links with similar notations in the suggestion when entering a link.
    - I mean, "no link at all" is a problem, but if you have some, it doesn't matter too much if it breaks a little.

- In light of this, it would be surprisingly comfortable to automatically generate fewer links when importing text without links.
    - If there are too many pages (like 100 pages with a certain keyword as a link), it's a problem, but as long as it doesn't happen, it may be surprisingly comfortable.
    - If you make a link to "a repeated string of text, but it appears less than 7 times in 100 pages of text" or something like that, an automatic link could work surprisingly well.

When [[Kozaneba+Scrapbox]] is finished, let's write a script!
---
This page is auto-translated from [/nishio/WikiをScrapboxにインポートする実験](https://scrapbox.io/nishio/WikiをScrapboxにインポートする実験) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.