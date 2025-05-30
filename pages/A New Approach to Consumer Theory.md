---
title: "A New Approach to Consumer Theory"
---

[[Lancaster1966]]
[[Lancaster]]
A New Approach to Consumer Theory
Author(s): Kelvin J. Lancaster
Source: The Journal of Political Economy, Vol. 74, No. 2 (Apr., 1966), pp. 132-157 Published by: The University of Chicago Press
Stable URL: [http://www.jstor.org/stable/1828835](http://www.jstor.org/stable/1828835)
Accessed: 22/09/2008 02:58


In the traditional consumer model, the relationship between goods (GOODS) was two choices: same goods or different goods
- The relationship between butter and margarine is the same as the relationship between shoes and boats
- Are red Chevrolet and gray Chevrolet the same goods or different goods?

So we built a model in which utility is defined for features rather than goods.

- Create a new model with the following three elements (p. 134)
    - 1: Utility is a function of characteristic (previously it was a function of goods).
    - 2: A good has one or more characteristics, and a characteristic is shared by several goods.
    - 3: The characteristics of the combination of goods are different from those of the individual goods.
![image](https://gyazo.com/d02de0d3d274b728849fd3502ecdf4db/thumb/1000)
This would allow, for example, a red Chevrolet and a gray Chevrolet to be described as "goods that share most characteristics and differ only in color characteristics.

### Representation of the model in the formulas
.
In the Simplified model, which will be explained later, there is a one-to-one correspondence between Activity (purchase and other actions) and Good, but this is not the case in the general model, so Good is represented by x and Activity by y.
$x_j = \sum_k a_{jk} y_k$
$x = Ay$
When Activity and Good are in one-to-one correspondence, A is a unit matrix and $x = y$.
A, which expresses this relationship between Activity and Good, is assumed to be linear and objective.

The relationship between Activity y and Characteristic z is assumed to be linear and objective as well.
$z_i = \sum_k b_{ik} y_k$
$z = By$

Utility U is a function of z. In contrast to the conventional model where it is a function of x.
- Utility U is not necessarily linear ([[law of diminishing marginal utility]])

The linear budget constraint is expressed as $px \leq k$ using the price vector p.
- (Lancaster intended to use k for later discussion as the level of activity for the purposes of later discussion.)

To sum up.
$\text{Maximize} U(z)$
$\text{subject to} px \leq k$
$\text{with} z=By,\quad x=Ay,\quad x,y,z \geq 0$
become

In the Simplified Model, where Activity and Good have a one-to-one correspondence, x and y are considered identical.
$\text{Maximize} U(z)$
$\text{subject to} px \leq k$
$\text{with} z=Bx,\quad x,z \geq 0$
become

In the previous model, utility was defined in Good-space ([[G-space]], the space of goods), so the relationship with the budget constraint could be expressed by Indifference-curve ([[indifference curve]]), but in this model, utility is defined in Characteristic -space([[C-space]], space of features), so a mapping is necessary.
- p137
    - a) Since convex set on G-space is also convex on C-space, the budget constraint line is also convex on C-space.
    - b) Since there is not necessarily an inverse in B, any z on the C-space does not necessarily have x on the corresponding G-space
    - c) If there is an inverse matrix, this is also a mapping of a convex hull onto a convex hull, so the convexity of U is preserved

### the structure of consumption technology
In the Simplified model, A disappears, so B is important. This B is called consumption technology ([[consumer technology]]). The discussion is divided into three patterns depending on the shape of this B.
- 1: If the number of features is the same as the number of goods
    - Some conditions lead back to the conventional model.
- 2: If the number of features is greater than the number of goods
    - Bx=z, viewed as a simultaneous equation, has no solution in general because "there are more equalities than the number of variables".
    - So think in slices (ignoring some of too many features).
    - Lancaster emphasizes that convexity is maintained at this time
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>to "what does it mean in the real world that there is no exact solution for x corresponding to given z?" I feel that this is not the case. In the real world, if a consumer is not satisfied with a product on the market that satisfies his/her "desired feature z," he/she will buy a similar product if it is satisfactory, and thus the consumer will be absorbed into the framework of utility maximization. There is no need for an exact solution.
- 3: If the number of goods is greater than the number of features
    - At this time, there exists more than one x satisfying Bx=z
    - The customer then makes a choice among those multiple x's.
        - The EFFICIENCY of that choice is MINIMUM COST ("efficient" in the sense of the efficient market hypothesis is used).
    - The optimization for efficient x* for given z* is
        - $\text{Minimize} px$
        - $\text{subject to} Bx=z^*, x\geq 0$
    - The set of z for which px=k is satisfied when z* is moved is called the characteristic frontier
        - This indicates the boundary of the set of features that can be maximally obtained within a given budget constraint

This is the end of the explanation of the model, and now we will apply this model to various problems.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Impressions of
- The space of goods is finite, which is unavoidable given the computational resources available in 1966.
    - In dealing with contexts such as new product development, there are a myriad of goods because the natural behavior is to "choose the one that seems to have the highest customer utility out of the myriad of products that could be created.
    - (This is not an outlandish idea; recent natural language processing considers the word space to be of infinite dimension, and includes a prior distribution using the [[Dirichlet process]], etc.)
    - Or approximate in a sufficiently large dimensional space.
- We are dealing with this as a linear problem.
    - I suppose it is inevitable because it would be analytically unsolvable, but since the quantity of goods is a continuous value, it would be possible to act "buy 1/3 3.5" HDD and 2/5 5" HDD" with a limited budget.
    - Realistically, it's impossible to buy half a camera, and can only be approximated by cloth, water, grain, etc. sold by weight.
    - This is due to the fact that we are treating the choice of goods x as a vector in the first place.
    - If we insert the one-hot constraint "customers buy only one good", then one point on the C-space will correspond to one point on the G-space.
        - Instead, it will not be able to handle the COMBINATION of goods, but it is better to be clear about what you are good at and what you are not good at.
    - The shattering of G-space makes it difficult to discuss budget constraint lines, but we can add the inverse of price as one of the features, as [[Adner 2002]] does
        - Instead, the discussion of technology constraint lines on C-space carries more weight.

---
This page is auto-translated from [/nishio/A New Approach to Consumer Theory](https://scrapbox.io/nishio/A New Approach to Consumer Theory) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.