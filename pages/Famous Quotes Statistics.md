---
title: "Famous Quotes Statistics"
---

- [[wise saying]]

N=54019, max=224, min=3

length
:

```
plt.hist([len(x) for x in meigens], range=(0, 230), bins=23)
```

![image](https://gyazo.com/2caf5288b7042ee01272331276c8534e/thumb/1000)
:

```
array([5.5000e+02, 6.3190e+03, 1.0824e+04, 9.8560e+03, 7.3950e+03,
        5.5090e+03, 3.8870e+03, 2.8790e+03, 2.2460e+03, 1.5070e+03,
        1.0490e+03, 6.9100e+02, 4.5500e+02, 3.3500e+02, 2.0800e+02,
        1.2200e+02, 6.1000e+01, 5.1000e+01, 3.2000e+01, 2.4000e+01,
        6.0000e+00, 7.0000e+00, 6.0000e+00]),
 array([  0.,  10.,  20.,  30.,  40.,  50.,  60.,  70.,  80.,  90., 100.,
        110., 120., 130., 140., 150., 160., 170., 180., 190., 200., 210.,
        220., 230.]),
```


word count
![image](https://gyazo.com/b37490f6eaddb9a9879708d99b75796a/thumb/1000)
:

```
plt.hist([len(x) for x in meigens], range=(0, 160), bins=32)
Out[74]: 
(array([2.120e+02, 1.299e+03, 6.021e+03, 8.835e+03, 8.675e+03, 6.817e+03,
        5.358e+03, 4.067e+03, 3.209e+03, 2.444e+03, 1.925e+03, 1.528e+03,
        1.026e+03, 7.560e+02, 5.180e+02, 4.000e+02, 2.940e+02, 2.190e+02,
        1.430e+02, 8.100e+01, 6.100e+01, 3.800e+01, 3.900e+01, 1.600e+01,
        1.400e+01, 6.000e+00, 8.000e+00, 4.000e+00, 3.000e+00, 2.000e+00,
        1.000e+00, 0.000e+00]),
 array([  0.,   5.,  10.,  15.,  20.,  25.,  30.,  35.,  40.,  45.,  50.,
         55.,  60.,  65.,  70.,  75.,  80.,  85.,  90.,  95., 100., 105.,
        110., 115., 120., 125., 130., 135., 140., 145., 150., 155., 160.]),
 <a list of 32 Patch objects>)

```


:

```
In [89]: for i in range(20):
    ...:     print(", ".join(vocab[i * 15 : i * 15 + 15]))
    ...:     
    ...:     
The,. , is, is, BOS, EOS, to, not, in, and, that, also, thing
Is, Na, DID, did, do, person, being, thing, if, myself, is, because, that, is, that
N, ",", human, it, will, be, that, like, then, (, ), no, without
What, life, is, is, mind, is, only, than, better, than, you, ya, for, good, I, me, )

become, in, want, want to, ne, think, words, others, live, should, all, this, be, necessary, as, much
Success, partner, so, think, power, by, be, until, this, happiness, Follow, Follow, some, as
I, sneak, into, no, woman, be, taken, by, a, woman! He should, have, love, love, go, go, to, be, like, a, woman.
thing, man, only, who, and, think, how, do, do, fail, comes, does, one, we, what
Time, ? Just, see, let, world, now, well, way, effort, etc., live, way, do, also
Way, Happy, But, For, Most, Good, That, That, Problem, We, Say, Important, Many, Eyes, Hands
Can, What, Not, Think, Most, Must, Exist, Action, Dream, Kind, Like, There, You, God, Yourself
Thinking, Having, People, Big, Before, Getting, Saying, Giving, -, Always, Other, Never, One, Meaning, Meaning, Cherish
You, Child, Know, If, Day, Do, First, Always, World, 0, Say, Our, Feelings, Unhappy, Up
Value, only, so, ability, new, life, born, know, nature, death, if, believe, alone, bad, may
Freedom, Today, Year, Be, And, Good, Love, While, While, Against, Every, Said, Know, Body, Die
Experience, World, Too, Too Much, Because, Even, Spirit, Already, Courage, Understanding, Truly, Way, Aro, Past, Seeing
Because, result, Hence, self, more, in, joy, society, oneself, forget, money, true, everyone, such, feeling
Such, many, show, out, book, truth, own, give, knowledge, right, future, love, only, goal, ten
Marriage, Hope, Me, Shirre, Important, Talent, Of, Money, One, Purpose, Get, Growth, We, Should, True
```


---
This page is auto-translated from [/nishio/名言の統計量](https://scrapbox.io/nishio/名言の統計量) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.