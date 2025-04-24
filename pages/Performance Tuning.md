---
title: "Performance Tuning"
---

> As with Gear VR applications, there are a few basic settings that should be enforced for all Oculus Go applications:

- > Always render with Multi-View (what Unity calls “[[Single-Pass Stereo]]” rendering). In Unreal, ensure that you are using “Mobile Multi-View” and “Mobile Multi-View Direct.”
- > In Unity, using [[OVRManager]], disable [[Enable Adaptive Resolution]].
- > In Unity, ensure [[Dynamic Batching]] and [[Static Batching]] are both enabled in the Player Settings. [[Graphics Jobs]] should not be used.
[https://developer.oculus.com/blog/everything-you-need-to-know-to-develop-for-oculus-go/](https://developer.oculus.com/blog/everything-you-need-to-know-to-develop-for-oculus-go/)

---
This page is auto-translated from [/nishio/Performance Tuning](https://scrapbox.io/nishio/Performance Tuning) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.