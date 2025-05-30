---
title: "Zoom and translate with two-finger gesture"
---

I thought of using the two-finger gesture on the iPad to zoom in and out and move parallel to the screen.

At first, I implemented "the amount of shift of the center of gravity of two fingers as parallel shift and the ratio of increase or decrease of the distance between fingers as scaling," but this is not correct.

How is it incorrect? Let o1 and o2 be the touch start positions and p1 and p2 be the current touch positions.
For example, suppose you shrink your finger by 1/2 while keeping the center of gravity at the edge of the screen. `(4, 0), (4, 4) → (4, 1), (4, 3)`
In this case, the above formula would shrink by 1/2 without parallel shift. It is wrong whether it is to the origin or to the center of the screen.
It needs to contract against the center of gravity of the two fingers.
![image](https://gyazo.com/dc7f454780c7554eb9cb8e63a42495f6/thumb/1000)

Now, if we describe the deformation f in general as "x, y parallel shift after s times with respect to the origin", what happens to this s, x, y, respectively?

$f(o_1) = p_1, f(o_2) = p_2$ would be ideal, but is not feasible for some touch movements because the deformation does not include rotation.
So we minimize $E = (f(o_1) - p_1) ^2 + (f(o_2) - p_2)^2$. ( [[least-squares method]] )

Differentiate E by s, x, and y, respectively, and set it to 0. Organize Eq.
$x = ((p_1 + p_2)_x - s (o_1 + o_2)_x)/2$
$y = ((p_1 + p_2)_y - s (o_1 + o_2)_y)/2$
Substituting this for the derivative in s and never organizing x and y gives the formula for s.
$a = 2 (o_1 \cdot p_1 + o_2 \cdot p_2)$
$b = |o_1 - o_2|^2$
$c = (o_1 + o_2) \cdot (p_1 + p_2)$
$s = (a - c) / b$

Reference: Differentiation in s
- ![image](https://gyazo.com/0d62efd2cb9596c8c22172b4e50dcfce/thumb/1000)

It is easy to show that this is different from "the shift of the center of gravity of two fingers as a parallel shift and the ratio of increase or decrease of the distance between the fingers as a scaling.
![image](https://gyazo.com/d9d24e63d041fc296ffeb2c51c811447/thumb/1000)
For example, a move like this would be about 0.7x in the type that uses the increase or decrease in finger spacing as the magnification factor.
But if we try to minimize the error under the condition of "no rotation", it is correct to multiply by 0.5.
The above formula can be properly answered as "multiply by 0.5 and move (2, 1)".
![image](https://gyazo.com/60bce24dfc5d6b8634156fa21dbeba3e/thumb/1000)


---
This page is auto-translated from [/nishio/二本指ジェスチャでズームと平行移動](https://scrapbox.io/nishio/二本指ジェスチャでズームと平行移動) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.