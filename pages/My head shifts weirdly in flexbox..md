---
title: "My head shifts weirdly in flexbox."
---

![image](https://gyazo.com/8b4090e732de5400efd7e902063fa21a/thumb/1000)
I was consulted about this phenomenon and was troubled for a while, but now that I've solved the mystery, I'd like to summarize.

reproduction code
- [https://codepen.io/nishiohirokazu/pen/OJXVBby](https://codepen.io/nishiohirokazu/pen/OJXVBby)
    - ![image](https://gyazo.com/3b12d5d3c011a28e4b22efda00576550/thumb/1000)
- Conclusion.
    - Parent div does not have display: flex
    - The child div has display: inline-flex.
    - Baseline alignment is happening because the div is now an inline element.
- consideration
    - For left-to-right alignment purposes, the parent div only needs to have display: flex, so the child divs don't need it.
        - But in reality, the code is the result of combining parts that have been formatted in flex and were originally attached to the code.
    - If the parent div does not have display: flex, the div is a block element by default, so it is aligned vertically.
    - If the child div is set to display: inline-flex, it will become an inline element, so it will line up left and right.
        - If there is no content in a div, the layout will appear to be correct at first glance.
        - ![image](https://gyazo.com/8535a9689e88fc53afe874c8fbdf5654/thumb/1000)

Baseline alignment of inline elements
- ![image](https://gyazo.com/de07862ebf5706f4860cd1454ad705f9/thumb/1000)
- [https://www.google.co.jp/amp/s/html5experts.jp/takazudo/13339/amp/](https://www.google.co.jp/amp/s/html5experts.jp/takazudo/13339/amp/)

[[flexbox]]

---
This page is auto-translated from [/nishio/flexboxで頭が変にズレる](https://scrapbox.io/nishio/flexboxで頭が変にズレる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.