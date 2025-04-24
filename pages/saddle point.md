---
title: "saddle point"
---

![image](https://gyazo.com/37623b5764bab2290f65a9f9f4d64d33/thumb/1000)
- [Optimization algorithm for gradient descent method](https://www.slideshare.net/nishio/ss-66840545)

- For higher dimensional functions, most of the points with zero gradient (stopping points) are saddle points.
    - 99.8% for 10 dimensions

    - If you look at it from the perspective of maximizing [[utility function]], the story goes like this
    - Select the product with the largest utility function among those that are not too far removed from the current product.
        - = Based on the gradient of the point represented by the current product, update in the direction with the greatest gradient
    - Repeat that and you'll reach the saddle point.
    - Utility decreases if you go in the direction you have been going by the time you come to the saddle point.
    - We need to go in a completely different direction.
    - #NecessaryExperiments

---
This page is auto-translated from [/nishio/鞍点](https://scrapbox.io/nishio/鞍点) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.