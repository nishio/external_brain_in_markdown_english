---
title: "ppoi"
---

## ppoi(ish)

This is a library that supports machine learning to easily make similar judgments in situations where it is not possible to clearly describe the conditional expression of an if statement, but good and bad examples can be provided.
[Github](https://github.com/nishio/ppoi)

Since the main script is `__init__.py`, the checked out directory can be imported directly as a Python module. You can rename it to an appropriate, easy-to-understand name. For example, if you want to make it judge whether it looks like a keyword or not, you can use `mv ppoi keyword` or something like that as follows.

python

```
if keyword.ppoi(something):
    print("{} is keyword-ppoi".format(something))
```


(I thought of `import keyword` as a bad name, so I added `to_bool`. I think `keyword_ppoi.to_bool(something)` is better.)

`__init__.py` can be executed directly. You can run it with `--initialize`.
Unjudged input must be placed in unknowns.txt before execution.
- (I've thought about this a lot and it's not required, so I'll change it in a future version.)
- (I felt it would be better to prepare a separate script for execution instead of executing __init__.py in the first place.)

The sample data to determine if it is a keyword or not is included in the samples. The contents of this sample is one line and one item, and contains examples of the data to determine if it is a keyword or not. This is a sample of the data in Scrapbox, which is mostly keywords, but some of the keywords are not keywords because they are misplaced in the square brackets in the source code.
:

```
Elimination of Genus
self-introduction
0
voice input
\r\n
${currentPageTitle}
[ 0.67869952,  0.35340645, -0.37436676,  0.50602025,  0.13514392
```


`cp samples/unknown.txt . ` Then do `python3 __init__.py --initialize`. You will then be asked to enter at least one "keyword-like" example and at least one "non-keyword-like" example. (We assume that Python3, NumPy and Scikit-Learn are already installed.)

:

```
Enter at least one positive examples (empty to exit)
> 
```


Enter as appropriate
:

```
Enter at least one positive examples (empty to exit)
> Elimination of Attributes
> Self Introduction
>                    
Enter at least one positive examples (empty to exit)
> ${currentPageTitle}
> [ 0.67869952,  0.35340645, -0.37436676,  0.50602025,  0.13514392
> 
```


Then, based on the examples you gave, it will display "This looks like a keyword, best 5", "This doesn't look like a keyword, worst 5", and "I'm not sure which one it is".
:

```
BEST 5
Good ideas inspire those around you to start growing on their own: 0.7077
Nature of freedom: 0.7077
Responsible for their own productivity: 0.7077
The less confident people are, the more they speak ill of others: 0.7077
There are two types of genus elimination: 0.7077

WORST 5
https://speakerdeck.com/kazuph/builderscon-tokyo-2018-day1-chan-ye-degatili-yong-sareruraspberry-pifalsehua: 0.2073
http://d.hatena.ne.jp/nishiohirokazu/20111020/1319117086: 0.2073
Elemwise{minimum,no_inplace}.0, Subtensor{:int64:}.0, Subtensor{:int64:}.0, Subtensor{:int64:}.0, Subtensor{:int64:}.0, [* IncSubtensor{Set;:int64:}.0: 0.2230
http://wedge.ismedia.jp/articles/-/12062?layout=b: 0.2230
https://www.okudahiromi.com/blog/20180310/1923: 0.2230

LESS CONFIDENT
kintone migration tips for people used to Facebook: 0.4967
03 1 Structuring Fragmentary Information_Frontal and Actual KJ Method Flow: 0.5056
03 2 Structuring Fragmentary Information_KJ Method Practice: 0.5056
Real numbers between 0 and 1 to {0, 1}: 0.5056
Supplement to DB Press article: 0.5056
```


If you are satisfied with the results, you can use them as soon as possible.
:

```
In [1]: import ppoi

In [2]: ppoi.ppoi("Hello")
Out[2]: False

In [3]: ppoi.ppoi("keyword extraction")
Out[3]: True
```


If you are not satisfied, you will have to add more training data. You don't have to edit the files manually if you use "interactive active learning," which I will explain later, but this time we will paste all five of the LESS CONFIDENT into positive.txt.

If you change the data, it will be relearned with `python3 __init__.py --learn`. This option only relearns without displaying anything, and this explanation is not interesting, so let's display the analysis results again with `python3 __init__.py --describe`.

Here are the results
:

```
BEST 5
"Biologically evolved software will sometimes get sick like a cold, and if you leave it alone, it will go away. Now it's just a matter of being able to properly tie requirement specifications to death. : 0.9511
The good thing about a corporation is that the necessary condition of profit exists. In other words, the ability to go bankrupt is inherent. The function of bankruptcy is the best aspect of the free enterprise system. : 0.9231
Aggregation of organizations connected by people belonging to multiple organizations: 0.9125
"Even with equal rules (with seemingly high equality of results), there will be disparities, surprise," the argument is implicit in the parentheses, so isn't the tweak "If the WTA has low equality of results, there will be disparities" misplaced? The story is that. : 0.9081
(2) A private document shall be presumed to be duly executed when it is signed or sealed by the principal or his/her agent. : 0.9025

WORST 5
 0.45792096,  0.20519401,  0.77490418, -0.08403411, -0.37505412: 0.2266
 0.50602025, -0.08403411,  0.68316922, -0.34559589,  0.38823327: 0.2266
-0.20123254,  0.07652205,  0.50049221,  0.38823327,  0.74325791: 0.2266
-0.26671759,  0.89310368, -0.08178549, -0.34559589,  0.07142937: 0.2266
-0.37436676,  0.77490418,  0.04681577, -0.08178549,  0.50049221: 0.2266

LESS CONFIDENT
Feeling of Knowing in Memory and Problem Solving: 0.5010
2018-03: 0.5013
harajune: 0.4984
the structure of consumption technology: 0.4984
Scrapbox Drinkup 20180810: 0.5019

```


The sentences that begin with `" `, which are in the BEST 5 this time, are inline quotation syntax, and these guys can be played with a clear rule that "if it begins with `" `, it is not a keyword", so it is better to do it outside of ppoi. If something can be written in logic, it is better to write it in logic.

In cases where you can't play by those clear rules and can't separate the data well by adding more data, you need to add more features. Since `_make_features` is a function that takes a single line of text and returns an np.array, we would have to modify it.

Right now it assumes that the input is a string that does not contain newlines, but I will create other cases when I handle the other cases. Until then, I'll just use JSON for now.

# interactive active learning
.
When activated with `--interactive`, you can learn interactively. The data will be displayed in the order of the LESS CONFIDENT, and if you interactively answer positive or negative, the answer will be added to the data file. This is so-called active learning.

In addition to positive and negative, there is also neutral. If you cannot tell whether it is positive or negative at a glance, put everything in neutral.

:

```
$ python3 __init__.py --interactive
Feeling of Knowing in Memory and Problem Solving: 0.5010
negative(z), neutral(x), positive(c), quit(q)>c
Peter F. Drucker: 0.5023
negative(z), neutral(x), positive(c), quit(q)>c
virtual: 0.5014
negative(z), neutral(x), positive(c), quit(q)>x
https://www.okudahiromi.com/blog/20180310/1923: 0.5016
negative(z), neutral(x), positive(c), quit(q)>z
2015: 0.4997
negative(z), neutral(x), positive(c), quit(q)>c
Lancaster1966: 0.4972
negative(z), neutral(x), positive(c), quit(q)>c
https://scrapbox.io/cybozu-make-club/: 0.4986
negative(z), neutral(x), positive(c), quit(q)>z
Regret  Analysis  of  Stochastic  and  Nonstochastic  Multi-armed  Bandit  Problems: 0.4994
negative(z), neutral(x), positive(c), quit(q)>c
2018-03: 0.4981
negative(z), neutral(x), positive(c), quit(q)>c
data.Name=="1299c1b7a9e0c2bf41af69c449464a49": 0.5034
negative(z), neutral(x), positive(c), quit(q)>z
Habitica: 0.5075
negative(z), neutral(x), positive(c), quit(q)>c
Miller1956: 0.5078
negative(z), neutral(x), positive(c), quit(q)>c
72, 101, 108, 108, 111, 44, 32, 119, 111, 114, 108, 100, 33: 0.5032
negative(z), neutral(x), positive(c), quit(q)>z
```


In the current implementation, every time one answer is given, the data file is updated and then reread and relearned. This eliminates "asking similar things over and over" when we teach one and can also determine similar cases, but it gets slower and slower as more data is added.

what to do
- Cache of trained models (since we created --learn for that purpose)
    - Now, if you simply import the library, you're still learning and creating a model the first time you make a decision.
    - It's OK to relearn every time in the early data creation phase, but it's useless to relearn every time when the data grows or when we are in the phase of mere use, so it's better to relearn explicitly with --learn.
    - On the other hand, in the early stages, it's a burden for humans to think about whether they need to relearn, so it's better to do it on their own.
- Create a commentary on how to improve the features

- --initialize first asks "Enter at least one positive example (empty to exit)", but I would like a version that asks me to choose one from unknowns.txt.


---
This page is auto-translated from [/nishio/ppoi](https://scrapbox.io/nishio/ppoi) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.