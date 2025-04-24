---
title: "To be able to change the highlight color."
---

Changed GameObject highligher that MakeSlide object had to public static
- Not very good manners.
- This instance will remain a singleton in the future, so if so, the class object may have a value
- I mean, the member variable to_highlight is already public static.
- Should I use [[message passing]] in Unity's manner?

- No, if it is known that an instance of a particular class is a singleton.
- > var slides = GameObject.FindObjectOfType<MakeSlides>().slides;
- Is this what you want?

- But if there are multiple instances, they will be compiled without any problem, so wouldn't it be safer to have them in a class object, which in principle can only be one?

---
This page is auto-translated from [/nishio/ハイライトの色を変えられるように](https://scrapbox.io/nishio/ハイライトの色を変えられるように) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.