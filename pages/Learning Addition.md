---
title: "Learning Addition"
---

By representing numbers as a combination of exponentially periodic rotating unit vectors in a [[Positional Encoding]]-like fashion, the [[addition]] can be learned in a surprisingly small network. If N-digit integers are embedded in 2N dimensions, the intermediate layer can answer all 3-digit addition questions correctly with only 32 units.

:

```
Percentage of correct 2-digit addition, when the embedding is 2-dimensional
16: 2291/5050 = 45.4%
32: 3586/5050 = 71.0%
64: 4276/5050 = 84.7%
128: 4719/5050 = 93.4%
256: 4909/5050 = 97.2%

In 4 dimensions
16: 4899/5050 = 97.0%
32: 5050/5050 = 100.0%
64: 5050/5050 = 100.0%
128: 5050/5050 = 100.0%
256: 5050/5050 = 100.0%

3-digit addition (embedded in 6 dimensions)
16: 423463/500500 = 84.6%
32: 500500/500500 = 100.0%
```


A neural net [[Visualizing Neural Networks in the Traveling Salesman Problem]] that correctly answers all 5050 addition problems with results between two-digit numbers that fall within two digits, as small as 8→32→4, shows that the middle layer is divided into two halves and It turns out that only half of the input is of interest.
![image](https://gyazo.com/34f4742106426e7ad3fdaf0684bfb5d7/thumb/1000)
And if we visualize the projection to the output layer according to this reordering of the intermediate layer, it looks like this.
![image](https://gyazo.com/25c805015f61b5df1a5cc5dff19d5861/thumb/1000)
As you might expect from the fact that two-digit integers are embedded in 2*2 dimensions, in essence, the rotators with period 100 and period 10 represent the tens and ones, respectively. However, since this is positional encoding, the 10's do not rise in a staircase-like fashion, but only oscillate 10 times slower.

NN that can add 3 digits.
![image](https://gyazo.com/75de58e055aa536519bc93541e817722/thumb/1000)
Two questions are still wrong: 32: 500498/500500 = 100.0%.
12→32→6

I tried to find a mathematical explanation for why 8→12→4 is more than 90% successful, but I don't know if there is one. In the case of simple multiplication, 4 times the input is required, but in this case, the fact that the input is restricted to the unit circumference is probably of some use.
:

```
20: 5043/5050 = 99.9%
19: 5041/5050 = 99.8%
18: 4975/5050 = 98.5%
17: 5002/5050 = 99.0%
16: 4957/5050 = 98.2%
15: 4765/5050 = 94.4%
14: 5003/5050 = 99.1%
13: 4921/5050 = 97.4%
12: 4592/5050 = 90.9%
11: 4489/5050 = 88.9%
10: 3632/5050 = 71.9%
9: 2866/5050 = 56.8%
8: 2477/5050 = 49.0%
7: 1919/5050 = 38.0%
6: 1887/5050 = 37.4%
5: 815/5050 = 16.1%
4: 368/5050 = 7.3%
3: 250/5050 = 5.0%
```


---
This page is auto-translated from [/nishio/足し算の学習](https://scrapbox.io/nishio/足し算の学習) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.