---
title: "Learning the identity map"
---

One-line summary: The identity map of a one-hot vector can be constructed in any number of dimensions if there are two neurons in the middle layer of a three-layer perceptron.

In other words, a one-hot vector of any dimension can be embedded in 2-dimensional space in a form that can be undone by the perceptron.

---

The identity map that takes as input a one-hot of dimension 100 and outputs the same one-hot of dimension 100.
A 3-layer perceptron with an intermediate layer size of 6 can be trained.
Learning is usually successful at size=7 and sometimes successful at size=6.
Is 6 the lower limit or not?

We experimented to see how many dimensions of one-hot identity maps can be learned by increasing the size of the intermediate layer to 2.
The students were able to learn 12-dimensional identity maps.
It is two-dimensional, so you can visualize the value of the middle layer for each input: the
![image](https://gyazo.com/6c69f70790025de635ab2d5fa532c44f/thumb/1000)
I see, so it is a [[convex polygon]].
If the point cloud is a convex polygon, you can always create a [[separated hyperplane]] that separates only one of its points.
![image](https://gyazo.com/44fb288e9a5fd6384ee6775e9ccf63db/thumb/1000)
So, theoretically, any one-hot vector of any number of dimensions can be made into an identity map if there are two intermediate layers.
Learning may or may not work, but humans can also construct appropriate weights.
In that case, the precision of the floating point numbers would limit the dimensions that can be expressed.

PS: Embedding in [[Poincaré disc]] may be easier to learn because the same 2 dimensions have exponentially wider perimeters.

---
This page is auto-translated from [/nishio/恒等写像を学習する](https://scrapbox.io/nishio/恒等写像を学習する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.