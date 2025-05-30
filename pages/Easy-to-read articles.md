---
title: "Easy-to-read articles"
---

- Japanese laws can be viewed in article form on e-Gov e-Gov. Example: [Civil Code on e-Gov](http://elaws.e-gov.go.jp/search/elawsSearch/elaws_search/lsg0500/detail?lawId=129AC0000000089)
- But the letters are small and hard to read on a smartphone or iPad.
- I want something easy to view on my phone or iPad.

prototype
- Civil law [https://nishio.github.io/better_egov/minpo.html](https://nishio.github.io/better_egov/minpo.html)
- Copyright Law [https://nishio.github.io/better_egov/chosakukenhou.html](https://nishio.github.io/better_egov/chosakukenhou.html)
- Patent Law [https://nishio.github.io/better_egov/tokkyohou.html](https://nishio.github.io/better_egov/tokkyohou.html)

- Known Issues
    - Font size is still a bit small for viewing on iPad. I would like to have an adjustment function.
    - Copyright Law 81 is incorrectly labeled.
        - Since the hierarchy below No. 1 appears
    - The text of the furigana will be prefixed with the furigana: `A person who has defamed or damaged the reputation of another`.
    - When I put a link to Facebook, a strange part of the link is cut off and displayed.

=====
2020-02-19
    - I was doing [[Redirect for SPA in Netlify]] and realized it would be useful for this project as well.
    - It can solve the problem of "When I put a link to Facebook, a strange part of the link is cut off and displayed.
        - Change [[Twitter Card]] for each URL in [react-helmet
            - [[SSR at Netlify]]

- The previous prototype was XML to HTML in Python.
    - In the future, TS will parse XML and create screens with DOM manipulation.
- Previous repository renamed [Github](https://github.com/nishio/better_egov_html)
- I was able to verify that meta can be out by URL path and SSR by netlify [Github [https://github.com/nishio/better_egov/blob/7805b89203a29f9713b9e4ae0fedf8d82d017826](https://github.com/nishio/better_egov/blob/7805b89203a29f9713b9e4ae0fedf8d82d017826) /src/App.tsx]
- [Facebook](https://www.facebook.com/nishiohirokazu/posts/10220733262497969)

---
2019-05-14
The problem of "when I link to Facebook, strange parts are cut off and displayed", I realized that it would be better to create a "Share button" and the URL obtained by the button would be a link to the article itself.
- Create a static page for each article?
- Or is it better to use JS to narrow down the display?

---
2018-08-04
Prototype version 2.1
- [https://nishio.github.io/better_egov/minpo.html#555](https://nishio.github.io/better_egov/minpo.html#555)
    - You can link to section 555 with `#555`.
- [https://nishio.github.io/better_egov/minpo.html#13.1.4](https://nishio.github.io/better_egov/minpo.html#13.1.4)
    - You can link to Article 13.1.4 with `#13.1.4`.
- [https://nishio.github.io/better_egov/minpo.html#c3](https://nishio.github.io/better_egov/minpo.html#c3)
    - `#c3` can link to 3 editions.
    - Container c
    - We have decided to call all "structures for holding other things" such as knitting and chapters collectively as containers.
- [https://nishio.github.io/better_egov/minpo.html#c3.1.5.1.3](https://nishio.github.io/better_egov/minpo.html#c3.1.5.1.3)
    - Can be linked to `Part III: Claims, Chapter I: General Provisions, Section 5: Extinguishment of Claims, Subsection 1: Payment, Division 3: Subrogation by Payment` in `#c3.1.5.1.3`.
- Directly below each container are links to the container's parent, siblings, and child containers.
    - ![image](https://gyazo.com/a414a759346a99b0b88b24bf59a8f9af/thumb/1000)
- Copy function restored.
    - ![image](https://gyazo.com/8985a5f6762b7e4b1b2cd5e1274bc700/thumb/1000)
    - The copy button in the address section copies everything in the black frame.
    - The copy button to the right of "Article X" copies the portion excluding the address (in this case, "(Method of deposition)" and thereafter).
    - The copy button to the right of each section copies only that section.

-----
2018-07-13
Prototype version 2
- [https://nishio.github.io/better_egov/minpo.html#555](https://nishio.github.io/better_egov/minpo.html#555)
    - You can link to section 555 with `#555`.
- [https://nishio.github.io/better_egov/minpo.html#13.1.4](https://nishio.github.io/better_egov/minpo.html#13.1.4)
    - You can link to Article 13.1.4 with `#13.1.4`.
- [https://nishio.github.io/better_egov/minpo.html#c3](https://nishio.github.io/better_egov/minpo.html#c3)
    - `#c3` can link to 3 editions.
    - Container c
    - We have decided to call all "structures for holding other things" such as knitting and chapters collectively as containers.
- [https://nishio.github.io/better_egov/minpo.html#c3.1.5.1.3](https://nishio.github.io/better_egov/minpo.html#c3.1.5.1.3)
    - Can be linked to `Part III: Claims, Chapter I: General Provisions, Section 5: Extinguishment of Claims, Subsection 1: Payment, Division 3: Subrogation by Payment` in `#c3.1.5.1.3`.
- Directly below each container is a child container of that container and a link to its sibling containers.
    - I wanted it when I was using the previous version.
    - ![image](https://gyazo.com/8989f36e578837bcac3108fa2fd255aa/thumb/1000)
- Copy function once gone.
    - I'm undecided where to put the button and where to make it a copy target.
- Can now convert directly from e-Gov XML
    - So it should be possible to convert every possible law.
    - However, it was made with civil law in mind, so if you include other laws, there probably won't be any editions and you'll get an error.
    - I'll do that area another time. Personally, I want to do copyright law and patent law.
    - hooray (lit: I or we did it)
        - Copyright Law [https://nishio.github.io/better_egov/chosakukenhou.html](https://nishio.github.io/better_egov/chosakukenhou.html)
        - Patent Law [https://nishio.github.io/better_egov/tokkyohou.html](https://nishio.github.io/better_egov/tokkyohou.html)

- Known problems and what you wish you had
    - There is a ruby in the case and it is not handled correctly: `a person who has defamed another`.
    - If the article number is hung, it would be nice if it could be a link too.
        - Rather cumbersome as there are many different patterns.
            - `A trial for commencement of assistance shall be made together with a trial under Article 17, paragraph (1) or a trial under Article 876-9, paragraph (1). `
    - When zooming on iPad, I want the text to wrap at the width of the screen after zooming.
        - I've been doing a lot of research and trying, but I don't know the best way to do it.
    - I want the article to appear in the preview properly when I post it on Facebook, etc.
        - I was getting one in v1, but I don't know why not in v2.
        - From the behavior of [this](https://developers.facebook.com/tools/debug/sharing/?q=https%3A%2F%2Fnishio.github.io%2Fbetter_egov%2Fminpo_v1.html%23s3) Then it seems to be picking up the content of the first p-tag that appears first, such that there is more than a certain percentage of ground content that is not a link, etc.
        - It is now displayed by enclosing it with a p tag.
            - ![image](https://gyazo.com/377a55bcaf5b7f796d1093a716482f5e/thumb/1000)
            - But if you look closely, you can see that the link is to Article 556, but what is shown is Article 557.
            - Also, the notation "what article" doesn't show up.
            - I just noticed that even in v1, it shows Article 556.2, even though it links to Article 556.
                - ![image](https://gyazo.com/0608ae2c6d07a98608c6a96eac866d70/thumb/1000)
            - Hmmm...
            - [https://developers.facebook.com/tools/debug/sharing/?q=https%3A%2F%2Fnishio.github.io%2Fbetter_egov%2Fminpo_v1.html%23556](https://developers.facebook.com/tools/debug/sharing/?q=https%3A%2F%2Fnishio.github.io%2Fbetter_egov%2Fminpo_v1.html%23556)
            - [https://developers.facebook.com/tools/debug/sharing/?q=https%3A%2F%2Fnishio.github.io%2Fbetter_egov%2Fminpo.html%23556](https://developers.facebook.com/tools/debug/sharing/?q=https%3A%2F%2Fnishio.github.io%2Fbetter_egov%2Fminpo.html%23556)
        - I looked at [https://schema.org/](https://schema.org/) and it doesn't look like a solution


Prototype version 1
- [https://nishio.github.io/better_egov/minpo_v1.html#555](https://nishio.github.io/better_egov/minpo_v1.html#555)
    - You can link to section 555 with `#555`.
- [https://nishio.github.io/better_egov/minpo_v1.html#s3](https://nishio.github.io/better_egov/minpo_v1.html#s3)
    - `#s3` can link to 3 editions.
- Tap the area marked `[copy]` to copy the article to the clipboard.
- impressions
    - It would be useful if the structure directly below each heading appeared
    - They say the headline should be before the article.
        - address (e.g. of house)
        - headline
        - What is the article?
    - The #'s are just bullet points, but they want to put permalinks.
    - Wouldn't it be better to convert from e-Gov xml
        - In the future, it would be better to support e-Gov XML to increase the number of articles covered.
        - For now, the most recent layout is limited to civil law and can be done by trial and error, so it can be put off until later.
- Still small on iPad
    - Would it be nice to have the ability to zoom to 2x and limit the width?
---
This page is auto-translated from [/nishio/見やすい条文](https://scrapbox.io/nishio/見やすい条文) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.