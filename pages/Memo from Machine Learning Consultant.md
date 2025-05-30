---
title: "Memo from Machine Learning Consultant"
---

A place to keep notes on various consultations.

- simple
    - The model should be as small as possible.
        - Larger models take longer experiments and reduce the number of experiments that can be done in unit time.
        - The larger the model, the more data required for decent training results.
    - Operational costs after being put into practice
    - Anxiety that a large black box will reveal something unexpected.

- How to determine various hyperparameters, such as the size of the middle layer of a neural net
    - Repeat experiments to determine
    - Especially in the case of image processing using deep learning, there are publicly available datasets on which many people have tried various methods, and information on the level of accuracy has been accumulated.
        - For example, [MNIST](http://yann.lecun.com/exdb/mnist/) provides a list of accuracies, including KNNs and others that are not neural nets.
    - On the other hand, in most cases in practice, datasets are not publicly available (only they have them)
        - There is a difference in the situational setting.

- publication bias


    - [[machine learning]] Consultant's note

---
This page is auto-translated from [/nishio/機械学習コンサルタントのメモ](https://scrapbox.io/nishio/機械学習コンサルタントのメモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.