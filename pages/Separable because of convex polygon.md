---
title: "Separable because of convex polygon"
---

- [[Learning the identity map]] asked how I came up with "separable because it's a convex polygon"
I noticed it right after I saw it, so I guess there is a clue in the "not knowing and struggling stage" a little before that.

![image](https://gyazo.com/bd4c11b8cf72d95c26065ac6285e40a8/thumb/1000)

- At first, I thought "a one-hot representation in 2^N dimensions can be represented in N dimensions if the number it represents is represented in binary notation".
- I was still thinking this way when I saw the results of an experiment where 100 dimensional inputs could be represented by 7 intermediate layers.
- However, even six intermediate layers could be represented.
    - 2^6 is 64, okay? Not enough, huh?
- I couldn't wrap my head around how it was accomplished.
    - I was also trying to visualize and observe the weights of the neural net, not mentioned in the article.
- I figured I'd do it in two dimensions to observe.
- Observations show that they are arranged in a ring pattern.
    - ![image](https://gyazo.com/6c69f70790025de635ab2d5fa532c44f/thumb/1000)
- This is something that finally worked after many attempts with different initial values, so the placement of this point has a strong significance
- If it is a meaningful arrangement, what is its meaning?
- I thought, "Well, they're lined up like this so I can just cut one out on a flat surface."
- Putting it into words, "any convex polygon is separable from any other vertex at any one vertex."

---
This page is auto-translated from [/nishio/凸多角形だから分離可能](https://scrapbox.io/nishio/凸多角形だから分離可能) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.