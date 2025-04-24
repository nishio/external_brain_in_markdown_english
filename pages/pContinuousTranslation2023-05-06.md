---
title: "pContinuousTranslation2023-05-06"
---

context [[Continuous Translation]]
prev [[pContinuousTranslation2023-04-27]]

2023-05-06
- More and more content that is originally in English and wondering how to handle it.
- Context from [/villagepump/2023/05/04](https://scrapbox.io/villagepump/2023/05/04).
    - I've set up a system to translate Scrapbox Japanese into English, but I feel like I'm digging a hole and filling it in, even though I originally put the English text at DeepL
- Context from [[Let AI ask questions]].
    - > By the way, I have created an automatic translation system from Japanese to English, but recently I have been writing more and more in English. There must be a better way to integrate thoughts in English with thoughts in Japanese. Currently, I am using a machine translation from English to Japanese, but it is ridiculous.
    - This itself is a machine translation of something written in English

I haven't put it all together yet, but I'm recording bits and pieces.
- [[en]] / [[ja]] / [[jaen]]
- Indicator for the entire page
    - I'm writing directly in English, en
        - Even if you write it in Japanese and then translate it, if I'm the one ultimately writing it, then this is what you're going to get.
    - I'm writing directly in Japanese, ja, but this is the default value, so it's omitted.
    - What I wrote in Japanese is just a machine translation of what jaen
- Just looking at this description, it seems like I should just put on en
- What's the difference?
- This icon was introduced when I was doing the human translation of [[The Intellectual Production of Engineers]] in the first place.
    - The Japanese version cannot be placed in this Scrapbox due to an agreement with the publisher.
    - Recent content is written in English and machine translated to create Japanese content, which is then placed in Scrapbox.
    - The top half of the page is usually in English and the bottom half in Japanese.
        - Because for those who have seen the English version, if there is "machine-translated English" and "original English," it is natural for the original to come out on top.
        - digression
            - This is where the implicit judgment is occurring. Linguistically, it is like this:.
                - Japanese who see the English at the top of the page and leave without going to the bottom should not be considered as the intended audience.
        - It is strange to translate the lower half of the Japanese into English in a case like this.
- Proposal A: Introduce a "don't machine translate" indicator icon
    - Do not translate the line with that icon and its child
    - Put this icon on the parent of the machine translation zone
        - Machine-translated Japanese will appear in the English version.
        - That's a little crazy.
    - Necessary if you want to put English text mixed with Japanese as is.
- Proposal B: Introduce a "do not reprint in English" indicator icon
    - Same structure as above, not only not translated but also not reprinted.
- Case C: "Do not reprint from here on down" indicator
    - Uh, as for the "Japanese translation is below" situation, this might be a good one.
    - The for loop for a line is just broken when it sees that notation.

I made [[enjabelow]].
- Started using it.
- No, I thought it was a great idea, but subtle.
    - The implementation of parsing the tree structure was too cumbersome and I thought why not break it, but it was not designed from the user's point of view.
    - From the user's point of view, there is an English version, a Japanese translation is placed, and then the user sees the Japanese version and wants to add related links.
    - In this case, related links should be translated to connect pages


detection of a problem
- ![image](https://gyazo.com/79a7e4abaf7af4687c09aa80739a428c/thumb/1000)
- ![image](https://gyazo.com/e269d411b65914e5079248e2436c5f6e/thumb/1000)
- When the import to Scrapbox fails, the action ends before the cache commit runs, so the same amount of retranslation is applied the next day.
- You're throwing away about $12,000. Too bad.
- I've tried to commit first, but that's a bit tricky because if the difference is too big, the import will fail and the next time it will be the difference between the English version and the English version, so "pages not reflected in the English version" will be created.

No, no, not this one.
- What we did last time on 4/27
    - Extensive re-translation
    - Parallelization for higher speed
- When I do this, the "flag if updated" is no longer working.
- So "save translation cache to file if updated" is no longer working.
- As a result, it was supposed to cost me 3,000 yen one time, but it cost me every day after that.
- When I did extensive re-translation, it was my expectation that the difference uploads would not work because the differences were too large.
    - So I thought I could just upload it manually only then.
    - In fact, the translation cache was not working, which caused extensive re-translation each time afterwards, and the differential upload failed.

2023-05-07
![image](https://gyazo.com/b79a76e3f68931adbdd22f3a1677ae4a/thumb/1000)
- [https://github.com/nishio/etude-github-actions/actions](https://github.com/nishio/etude-github-actions/actions)
![image](https://gyazo.com/c33e0ce2f79ffe6b47c60191befb50c6/thumb/1000)
- [https://www.deepl.com/account/usage](https://www.deepl.com/account/usage)

---
This page is auto-translated from [/nishio/pContinuousTranslation2023-05-06](https://scrapbox.io/nishio/pContinuousTranslation2023-05-06) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.