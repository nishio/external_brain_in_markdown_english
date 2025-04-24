---
title: "Improved physics"
---

- Instead of using the Raicast's RaicastHit.point as the source of force, it is better to use the center of gravity as the source
[https://www.youtube.com/watch?v=Qwp-ZSLIMn4&feature=youtu.be](https://www.youtube.com/watch?v=Qwp-ZSLIMn4&feature=youtu.be)
- Behavior is more natural compared to the version (below) where the ray cast is the source of the force.
    - [https://youtu.be/rkuv1eEkwC0](https://youtu.be/rkuv1eEkwC0)
    - This also includes [Physics keeps slides from getting too close.

- The earlier version looks natural at first glance, but strange behavior is occurring in the lower left corner and other areas. see [[Automatic slide movement]]
    - This is because the action-reaction is not included.
    - The subtle difference in front-back position causes the ray cast to hit or not hit, and only the side that is emitting the ray moves, which is counterintuitive to human intuition.
---
This page is auto-translated from [/nishio/物理演算の改善](https://scrapbox.io/nishio/物理演算の改善) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.