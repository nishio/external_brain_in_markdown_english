---
title: "Use model evaluation for model selection"
---

Pages for organizing thoughts

After training a model in machine learning, it is widely practiced to obtain a value of "model goodness" (e.g., accuracy) by "evaluating the model" in some way. In addition, "model selection," in which a model with a good value is chosen, is also often performed.

Criticism of this: "Model selection that maximizes model evaluation results causes overlearning to the data used for evaluation."

Model Evaluation Methodology (Percentage is an example)
- A: Separate 20% of the data and evaluate the performance of the model trained on the remaining 80% with 20% of the data (holdout method).
- B: Divide the data into five parts of 20% each (D1, D2, D3, D4, D5). The model trained on D1+D2+D3+D4 is evaluated on D5, the model trained on D2+D3+D4+D5 is evaluated on D1, and so on. 5 evaluations are performed and the results are averaged (cross-validation method)
- C: Divide the data into 60%, 20%, and 20% (D1, D2, D3). evaluate the model trained in D1 with D2. Then the model learned in D1+D2 is evaluated in D3.
    - Generally, the parameter with the maximum R2 is obtained by repeating "learning D1 with different parameters and evaluating with D2", and then the parameter learned with D1+D2 is evaluated with D3.
        - I'm not sure how to use the results evaluated by D2 (R2) and the results evaluated by D3 (R3).
            - If I'm going to make a model selection based on R2, what is the value of R3 used for? Just look at them and be satisfied?
        - If you look at the value of R3 and say, "It's lower than I thought," and do another trial, then this is part of the model selection process, and there is not much point in separating R2 and R3.
        - If the value of R3 is not used for model selection, then it makes sense to claim that "we divided the data D2 for trial and error and D3 for final evaluation only". But in reality, isn't it often used for model selection?
        - For example, if it's in the form of "train on D1+D3, evaluate on D2, train on D1+D2, evaluate on D3, and take the average", it makes sense in the form of "I wanted to do a 5fold cross-validation, but the computational cost was too high, so I only did it twice".
        - It is not clear how bad R3 must be compared to R2 to be considered a failure. It is unclear what the purpose of the experiment is and what condition is defined as success. Isn't it necessary to decide that before the experiment?

Model Selection
- Choosing whether SVM or LR is better
- Choosing how much to parameterize SVM
- Selection of the number of epochs to stop in a NN system (how much the parameter "number of learning epochs" should be) (early stopping)

- A (holdout) is usually used in early stopping
- If the calculation cost is low, just do B (cross-validation)
- C may be useful, for example, in situations where it is computationally difficult to do B, but if A is done, it is expected to be challenged, "Isn't that overfit to the validation data in the parameter search stage? It is not due to the parameter search.
---
This page is auto-translated from [/nishio/モデルの評価をモデルの選択に使う](https://scrapbox.io/nishio/モデルの評価をモデルの選択に使う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.