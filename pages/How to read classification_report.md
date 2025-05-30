---
title: "How to read classification_report"
---

[sklearn.metrics.classification_report](http://scikit-learn.org/stable/modules/generated/sklearn.metrics.classification_report.html) A brief explanation of how to read the results of

python

```
>>> from sklearn.metrics import classification_report
>>> print(classification_report([0, 0, 0, 1, 1, 1], [0, 0, 1, 1, 1, 1]))
             precision    recall  f1-score   support

          0       1.00      0.67      0.80         3
          1       0.75      1.00      0.86         3

avg / total       0.88      0.83      0.83         6
```


If the first argument y_true (correct answer) is `[0, 0, 0, 1, 1, 1]` and the second argument y_pred (predicted value) is `[0, 0, 1, 1, 1, 1]`.
- The two predictions of 0 are all correct: the precision of 0 is 1.00
- 4 predicted to be 1, 3 of which are correct: 1 has a PRECISION of 0.75
- Of the 3 correct answers that were 0, 2 were correctly predicted to be 0: 0 recall (recall) of 0 is 0.67
- Of the three that were correct, all were correctly expected to be 1: 1 recall of 1.00
- f1-score is the harmonic mean of precision and recall see [[F value]]

imbalance data
python

```
>>> print(classification_report([0, 0, 0, 0, 0, 0, 0, 0, 1, 1], [0, 0, 0, 0, 0, 0, 0, 1, 1, 1]))
            precision    recall  f1-score   support

         0       1.00      0.88      0.93         8
         1       0.67      1.00      0.80         2

avg / total      0.93      0.90      0.91        10

>>> print(classification_report([0, 0, 0, 0, 0, 0, 0, 0, 1, 1], [0, 0, 0, 0, 0, 0, 0, 0, 0, 1]))
            precision    recall  f1-score   support

         0       0.89      1.00      0.94         8
         1       1.00      0.50      0.67         2

avg / total      0.91      0.90      0.89        10
```


- In fact, only 2 out of 10 are actually 1
- first half
    - I expected three one, two of which are correct.
    - This is a good method if the customer "really doesn't want to take 1 thing off the table".
        - It can be expressed as "because the recall of 1 is 1.00
    - On the other hand, if you're thinking, "I want everything I predict to be 1 to be 1," this is a bad way to go.
        - It can be expressed as "because the PRECISION of 1 is only 0.67
- second half
    - I expected only one to be 1.
    - This is a bad way to go if the customer "really doesn't want to take 1 thing off the table".
        - It can be expressed as "because the recall of 1 is only 0.50".
    - On the other hand, if you want everything you predict to be 1 to be 1, this is a good way to go.
        - It can be expressed as "because the PRECISION of 1 is only 1.00".

- I really don't want to take away from the one."
    - When you break one stone, a gemstone comes out, and you can sell it for 100,000. It costs 10,000 to purchase."
        - If you make a slight mistake and break one stone, you'll make a fortune.
        - So please keep me informed of anything that looks like one.
    - I guessed 3 1 and got 2 correct -> paid 30,000, got 200,000...made 170,000.
    - Guess 1 for 1, get 1 correct -> pay 10,000, get 100,000...make 90,000...get 100,000...make 90,000...get 100,000...make 90,000.
- I want everything I predicted to be a one to be a one."
    - When you break one stone, a gemstone comes out and you can sell it for 100,000. It costs 90,000 to purchase."
        - It's a business on the edge, and if you make a bad move, you'll lose money.
        - So I want you to tell me only the one thing you're sure about.
    - I guessed 3 1 and got 2 correct -> I pay 270,000 and get 200,000. 70,000 loss.
    - Guessing 1 for 1 and getting 1 correct -> pay 90,000, get 100,000. 10,000 profit.
    - [[breakeven point]]
    - With logistic regression, accuracy and recall can be adjusted by moving the default threshold of 0.5 up or down. Precision and recall move in opposite directions. When the threshold is adjusted to match the precision and recall values, the precision is called the precision-recall breakeven point. (Terminology in the field of information retrieval)
        - When we simply refer to the break-even point, we are often referring to [[the break-even point]] in management. [break-even point - Wikipedia](https://ja.wikipedia.org/wiki/%E6%90%8D%E7%9B%8A%E5%88%86%E5%B2%90%E7%82%B9)

#Machine Learning
#TODO Write about break even points [http://ibisforest.org/index.php?F%E5%80%A4](http://ibisforest.org/index.php?F%E5%80%A4)
---
This page is auto-translated from [/nishio/classification_reportの読み方](https://scrapbox.io/nishio/classification_reportの読み方) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.