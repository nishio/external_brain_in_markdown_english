---
title: "hub-like tag"
---

[/blu3mo-public/Scrapbox should not use hub-like tags](https://scrapbox.io/blu3mo-public/Scrapbox should not use hub-like tags).

After all, there are benefits provided by "hub-like tags" in addition to the benefits provided by "links" in Scrapbox, and Scrapbox has made both "links" and designed the UI with "links" as the primary usage, so using hub-like tags will cause inconvenience.

So is it better to clearly separate links and hub-like tags?
- Allow hashtag notation to function differently than links
    - For example, "connection" by hashtag does not expand 2-hop, and so on.
I think this is a "possible design" for an information system design theory, but I personally think it's a streak of evil.
- Reason: It started out as a link, but after the fact it can become a "link connecting many pages" similar to a hub tag as a result of a great deal of excitement on the subject.
    - Related [[The Problem of Too Large Links]].
    - Example "KJ method."

So personally, I think we need a refactoring feature to break up "too big a link".
- Cannot know the appropriate tag in advance.
- It is necessary to be able to easily break down what is "too big" as a result of various writings into more detailed and narrower concepts after the fact.

However, it is possible that there are very few users who need that functionality in the operation of the service.
- Difficult to understand.
- Only those who create huge projects encounter inconveniences.

Then, I wonder if it would be in the form of a tool to analyze and refactor the JSON export.

PS
> If you use Scrapbox properly(?) If you use Scrapbox to,
>  When a link that's too big is created, it will have a finer tag than that, too, because it will be properly tagged.
>  I think I can deal with it just by making links that are too big .icon or something.
- Problems with confidence in "am I using it properly?"
- If it's a hashtag at the end of a page, you can replace it with an icon, but I don't think it's the same as replacing a keyword in the text with an icon.
- To begin with, "icons are one-way links" is a tricky solution using Scrapbox's less-than-obvious behavior, so it's delicate.
    - I think it's a realistic place to start if you're asking "how to do it with Scrapbox today," but as an "ideal externalization brain," I mean it's a bit more subtle.
- The idea of "making hashtags and links different behavioral connections" was suggested above, but in that sense, there's already a "different behavioral connection" of icons, I guess.
    - Then maybe we could have more variety.
        - [[come-from link]].
    - Refactoring assistance is good, even if it is difficult to use it appropriately in advance

---
This page is auto-translated from [/nishio/ハブ的タグ](https://scrapbox.io/nishio/ハブ的タグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.