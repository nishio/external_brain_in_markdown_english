---
title: "Regression and Classification"
---

This is fundamental to solving problems in machine learning, so let me reiterate it so there are no misunderstandings.

- What is the difference between a regression problem and a classification problem?
    - For the general public: regression problems for "predicting values" and classification problems for "grouping".
    - For those who want it expressed in mathematics: regression problems where the objective variable is continuous, classification problems where the objective variable is discrete

- Examples of regression and classification problems
    - I'd like to predict the sales of our products."
        - →Regression problem because we want to predict the value of sales.
    - I'd like to categorize news articles as 'politics' or 'sports.'"
        - → Classification problem because we want to classify them into groups
    - I want to estimate who the idol is from his or her facial image."
        - → Classification problem because face images are classified into "idol A's picture" and "idol B's picture".
    - I want to estimate the sugar content of a tomato from its photograph."
        - → regression problem since the value of sugar content is estimated.

Developmental Content
- Regression and classification problems can be mutually transformed
- Even if the requirements described by the customer seem to be regression problems, it may be appropriate to solve them as classification problems after listening to the details.
    - Example
        - If the customer explains the requirement, "I want to estimate the age of these people (regression)," but when we interviewed the customer about the use of the estimated results, he said, "I want to make sure that minors do not enter," then that should be solved with a classification problem of "whether they are minors or not."
        - Why "should" rather than "may" be solved? Regression is solved to minimize the discrepancy from the correct answer, so "mistaking a 50-year-old for a 60-year-old" and "mistaking a 15-year-old for a 25-year-old" would be treated as being equally wrong. However, considering the customer's actual application, "mistaking a 50-year-old person for a 60-year-old" is not a problem; "mistaking a 15-year-old person for a 25-year-old" is a major problem.
        - Therefore, solving by regression is not appropriate.

- Even if the requirements described by the customer are apparently regression problems, they may be solved as classification problems for clarification of other requirements.
    - Regression questions cannot give a "percentage of correct answers". The communication is, "There is this much margin of error."
    - If you tell a customer who says, "I want to forecast sales," that you have created a sales estimator and the average squared error is 100 yen, the only response you are likely to get is, "Reduce the error even more," because it is difficult to interpret.
    - It is better to solve the problem with a classification question and show "90% correct, here are the examples that fail". The advantage is that you can say, "Here are all the examples that fail," especially if there are only a few examples that fail.
    - Regression problems can also be shown as "the one with the largest error is here," but unlike classification problems, there is no clear boundary.


- Misleading point: "logistic regression" is overwhelmingly used for classification problems, not regression problems
    - Logistic regression is a method of solving the classification problem of "which group one belongs to" by finding the real value of "probability of belonging to a group" through regression. In other words, it is equivalent to converting a classification problem into a regression problem and then solving it.


Developmental Content
- Classify by what the learned model outputs
    - classification problem
        - Binary classification problem: output 0 or 1
        - Multivalued classification problem: output a single integer
            - For example, the problem of identifying an idol from its face image can be expressed in the form of "outputting an integer" if the idol is assigned a sequential ID number.
            - An integer is just an identification ID, and assumes a subject such that there is no meaningful relationship of size or addition/subtraction. adding the number 1 idol and the number 2 idol does not result in the number 3 idol.
            - If you answer 101 when the idol with number 100 is correct, you are totally incorrect.

    - regression problem
        - Output a single real number
            - For example, forecasting product sales.
            - Real numbers assume an object that has a meaningful relationship between a large and a small, or between addition and subtraction. 100 yen plus 200 yen equals 300 yen.
            - Sales can be expressed as integers rather than real numbers, but predicting a $1,000 sale as $1,001 is not "totally incorrect" and therefore a regression problem

Developmental Content
- I explained that regression has a continuous objective variable and classification has a discrete objective variable, but there are others.
- For example, ranking learning to learn rankings.
- In regression, the objective variable is an interval scale; in ranking learning, the objective variable is an ordinal scale; and in classification, the objective variable is a nominal scale.
    - see [scale level](https://ja.wikipedia.org/wiki/%E5%B0%BA%E5%BA%A6%E6%B0%B4%E6%BA%96)
---
This page is auto-translated from [/nishio/回帰と分類](https://scrapbox.io/nishio/回帰と分類) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.