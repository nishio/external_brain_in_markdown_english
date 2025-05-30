---
title: "palm rejection"
---

- I want to eliminate the harmful effects of my hand touching the tablet surface while using a handwritten notebook.
- Use only stylus events for pen drawing
    - Turn on mode to consider mouse or direct tap as stylus on devices without pen
- Look at the touch radius and ignore anything too large
    - [[Touch.radiusX]]
- What to do next
    - Identify and correct the causes of fast movement, unnatural behavior, and
    - Maybe around multi-touch, if you observe the number of touches, it starts with one and goes to two, and when it goes from two, it goes to one.
    - There may be a bug that is not taken into account
    - When the palm touches, touchstart happens and then touchcancel happens.
        - Now both are equated with mouseup.
    - What happens over 3 touches?
    - It's only 1 to 2, not 1 to 2, either when you do a 1-touch operation and then inadvertently touch it, or when you try to do a 2-touch operation and it's delayed for a second and then it goes to 1.
        - Whether drag events occur in between?




:

```
83 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
84 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
85 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
86 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
87 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
88 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
89 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
90 "{\"type\":\"touchend\",\"touchLen\":0,\"chTouchLen\":1,\"radius\":null,\"touchType\":null}"
91 "{\"type\":\"touchend\",\"touchLen\":0,\"chTouchLen\":1,\"radius\":null,\"touchType\":null}"
92 "{\"type\":\"touchstart\",\"touchLen\":2,\"chTouchLen\":2,\"radius\":72.97311401367188,\"touchType\":\"direct\"}"
93 "{\"type\":\"touchstart\",\"touchLen\":2,\"chTouchLen\":2,\"radius\":72.97311401367188,\"touchType\":\"direct\"}"
94 "{\"type\":\"touchcancel\",\"touchLen\":0,\"chTouchLen\":2,\"radius\":null,\"touchType\":null}"
95 "{\"type\":\"touchcancel\",\"touchLen\":0,\"chTouchLen\":2,\"radius\":null,\"touchType\":null}"
96 "{\"type\":\"touchstart\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
97 "{\"type\":\"touchstart\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
98 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
99 "{\"type\":\"touchmove\",\"touchLen\":1,\"chTouchLen\":1,\"radius\":0,\"touchType\":\"stylus\"}"
```


[https://gist.github.com/nishio/212e03210e7cefd01198f7c8e72faf8a](https://gist.github.com/nishio/212e03210e7cefd01198f7c8e72faf8a)

[https://gist.github.com/nishio/4aa9db73f795bf65f5c19400cd28bbfd](https://gist.github.com/nishio/4aa9db73f795bf65f5c19400cd28bbfd)

>  app.paper.project.view.zoom
< 5.1416015625
>  app.paper.project.view.center
< Point {_x: -131.3868127723678, _y: 407.52494081589373, _owner: Rectangle, _setter: "setCenter", initialize: [], …}

I was surprised when the screen suddenly turned white, but somehow it was magnified 5 times.
I'd also like to include zoom and center in the log.

---
This page is auto-translated from [/nishio/パームリジェクション](https://scrapbox.io/nishio/パームリジェクション) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.