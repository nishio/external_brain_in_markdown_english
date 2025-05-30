---
title: "Deep learning without mathematical prerequisites"
---

I wrote this as a test to see what would happen if I explained the shortest distance to deep learning without assuming knowledge of matrices.
This article uses numpy and scikit-learn. scikit-learn installs both.
[Installing scikit-learn — scikit-learn 0.21.2 documentation](https://scikit-learn.org/stable/install.html)

### matrix
.
Numpy will be used to explain.
python

```
>>> import numpy as np
>>> np.array([[1, 2, 3], [4, 5, 6]])
array([[1, 2, 3],
       [4, 5, 6]])
>>> _.shape
(2, 3)
```

The `_` in the code means the previous value.
A matrix is a rectangular array of numbers. The above code creates a matrix with two rows and three columns. Since it is absolutely confusing as to which is the row and which is the column, in this explanation we will use the expression "(2, 3) matrix" from now on.

### vector
.
A "vector" is a sequence of numbers; a sequence of N numbers is called an "N-dimensional vector. Vectors have several programmatic forms of expression.
python

```
>>> np.array([1, 2, 3])
array([1, 2, 3])
>>> _.shape
(3,)

>>> np.array([[1, 2, 3]])
array([[1, 2, 3]])
>>> _.shape
(1, 3)

>>> np.array([[1], [2], [3]])
array([[1],
       [2],
       [3]])
>>> _.shape
(3, 1) 
```

The second and third are (1, 3) and (3, 1) matrices, but in many cases they are called vectors without much distinction.

### matrix multiplication
.
The (A, B) and (B, C) matrices can be multiplied, resulting in the (A, C) matrix. Below.
- Example of multiplying (1, 3) and (3, 1) to get (1, 1)
- Example of multiplying (3, 1) and (1, 3) to get (3, 3)
the company's website.
Matrix multiplication, unlike integer multiplication, produces different results when the order is changed.
python

```
>>> v1 = np.array([[1, 2, 3]])
>>> v2 = np.array([[1], [2], [3]])
>>> v1.dot(v2)
array([[14]])
>>> v2.dot(v1)
array([[1, 2, 3],
       [2, 4, 6],
       [3, 6, 9]])
```


When multiplying matrices, the lengths of the B parts must be the same. If they are out of alignment, the following error will occur
Below, the user tries to multiply (1, 3) by (1, 3) and 3 ! = 1, it is pointed out.
python

```
>>> v1.dot(v1)
Traceback (most recent call last):
  File "<ipython-input-...>", line 1, in <module>
    v1.dot(v1)
ValueError: shapes (1,3) and (1,3) not aligned: 3 (dim 1) != 1 (dim 0)
```


### inner product
.
python

```
>>> v1.dot(v2)
array([[14]])
```

This is 1 * 1 + 2 * 2 * 3 * 3.
There is a sequence of numbers of the same length, each multiplied by the corresponding one and all added together.
This is called the "dot product. The method name "dot" comes from there.

If we write this "multiply each of the three corresponding things and add them together" in the mathematical way, we get
- $x_1 y_1 + x_2 y_2 + x_3 y_3$
becomes We can use this with sigma (Σ) to get
- $\sum_{i=1}^3 x_i y_i$
Written as. for short
- $\sum_i x_i y_i$
in Tokyo
- $\sum x_i y_i$
Also write.

### Formal neuron
: [Formal neuron - Wikipedia](https://ja.wikipedia.org/wiki/%E5%BD%A2%E5%BC%8F%E3%83%8B%E3%83%A5%E3%83%BC%E3%83%AD%E3%83%B3)
An idea created in 1943 that later became the basis for neural nets
![image](https://gyazo.com/94dd939f71749fa9a2b5070b242ba11a/thumb/1000)

- Multiply the input $x_i$ by the weights $w_i$ and add them together
- Output 1 if it exceeds the threshold $h$, 0 otherwise.

The inputs are multiplied by their weights and added together."
- This is the "inner product" I mentioned earlier!
- That is, $\sum_i x_i w_i > h$.

If you want to express it in code, you can use
python

```
>>> if x.dot(w) > h:
...     y = 1
... else:
...     y = 0
```


### logistic regression
.
A method to find appropriate weights $w$ by giving several combinations of input $x$ and output $y$.
One of the basic machine learning methods. In the code below, for example, scikit-learn is used to learn from 8 cases of data where the input is (1, 1, 1, 0) and the output is 0. The difference between square brackets and round brackets has no meaning other than for visibility.
python

```
>>> from sklearn.linear_model import LogisticRegression
>>> X = np.array([
...   (1, 1, 1, 0),
...   (1, 0, 1, 0),
...   (1, 1, 0, 0),
...   (0, 1, 1, 0),
...   (0, 0, 1, 1),
...   (0, 0, 0, 1),
...   (0, 1, 0, 1),
...   (1, 0, 0, 1)])
>>> Y = np.array([0, 0, 0, 0, 1, 1, 1, 1])
>>> m = LogisticRegression()
>>> m.fit(X, Y)
LogisticRegression(C=1.0, class_weight=None, dual=False, fit_intercept=True,
          intercept_scaling=1, max_iter=100, multi_class='ovr', n_jobs=1,
          penalty='l2', random_state=None, solver='liblinear', tol=0.0001,
          verbose=0, warm_start=False)
```


What is the case of (1, 1, 1, 0)?" I ask, "The probability of being 0 is 0.79, and the probability of being 1 is 0.21.
python

```
>>> m.predict_proba([(1, 1, 1, 0)])
array([[0.79460161, 0.20539839]])
```


When asked what happens if (1, 1, 1, 1, 1) was not included in the training data, the answer is 0 with a probability of 0.55.
The probability is close to 0.5, which means I'm not very confident.
python

```
>>> m.predict_proba([(1, 1, 1, 1)])
array([[0.54564474, 0.45435526]])
```


Values corresponding to w and h can be seen like this: w
python

```
>>> m.coef_
array([[-0.47815958, -0.47815958, -0.47815958,  1.16980067]])
>>> m.intercept_
array([0.08158937])
```


Let's do some arithmetic.
I didn't explain, but the activation function is a bit different from formal neurons. [activation function - Wikipedia](https://ja.wikipedia.org/wiki/%E6%B4%BB%E6%80%A7%E5%8C%96%E9%96%A2%E6%95%B0)
Formal neurons use a staircase step function that says "1 if $\sum_i x_i w_i$ exceeds $h$, 0 if it does not." Logistic regression uses a smooth S-shaped sigmoid function.
![image](https://gyazo.com/e984c3bc1bedafd04c8e9bf23b8f4410/thumb/1000)
The sigmoid function can be written in mathematical form like this
$f(x) = \frac{1}{1 + e^{-x}}$

python

```
>>> m.coef_.dot((1, 1, 1, 1)) + m.intercept_
array([-0.18308872])
>>> 1 / (1 + np.exp(- _[0])) # sigmoid function
0.454355256283273
```

The 0.45 that appears here is the following 0.45.
python

```
>>> m.predict_proba([(1, 1, 1, 1)])
array([[0.54564474, 0.45435526]])
```


### Multilayer Perceptron
.
Logistic regression does not solve surprising problems. The fact that you answered "0.5" in the code below means that you are not confident at all.
python

```
>>>  X = np.array([
...   (1, 1),
...   (1, 0),
...   (0, 1),
...   (0, 0)])
...  Y = np.array([0, 1, 1, 0])
...  m = LogisticRegression()
...  m.fit(X, Y)
LogisticRegression(C=1.0, class_weight=None, dual=False, fit_intercept=True,
          intercept_scaling=1, max_iter=100, multi_class='ovr', n_jobs=1,
          penalty='l2', random_state=None, solver='liblinear', tol=0.0001,
          verbose=0, warm_start=False)
>>> m.predict_proba([(1, 1)])
array([[0.5, 0.5]]) 
```


So, we try to accumulate a number of logistic regressions.
![image](https://gyazo.com/dbe9479365fa1cf7c3f7b65f3e5c0e9c/thumb/1000)

python

```
>>> from sklearn.neural_network import MLPClassifier
>>> m = MLPClassifier(hidden_layer_sizes=[3], max_iter=100000)
>>> m.fit(X, Y)
MLPClassifier(activation='relu', alpha=0.0001, batch_size='auto', beta_1=0.9,
       beta_2=0.999, early_stopping=False, epsilon=1e-08,
       hidden_layer_sizes=[3], learning_rate='constant',
       learning_rate_init=0.001, max_iter=100000, momentum=0.9,
       nesterovs_momentum=True, power_t=0.5, random_state=None,
       shuffle=True, solver='adam', tol=0.0001, validation_fraction=0.1,
       verbose=False, warm_start=False)
>>> m.predict_proba([(1, 1)])
array([[0.92259642, 0.07740358]])
```


The correct answer on (1, 1) is 0 with probability 0.92!" I can now answer, "The correct answer for (1, 1) is 0 with probability 0.92. I am happy and satisfied.
Note that this time, since the data is very small (4 cases), `max_iter=100000` (maximum of 100,000 iterations) is used for repeated training. In this case, `hidden_layer_sizes=[3]` is used to make the network small and thin, but you can make it wider or deeper by increasing the parameter here.

Let's look at the weights of this learned network.
python

```
>>> m.coefs_[0]
array([[ 1.39650888, -2.16802863, -0.96996648],
       [-1.39634665,  2.16818065,  1.11704021]])
>>> _.shape
(2, 3)
>>> m.coefs_[1]
array([[ 2.11163102],
       [ 3.05600029],
       [-1.74200157]])
>>> _.shape
(3, 1)
```


In this multilayer perceptron, the weights are in the (2, 3) and (3, 1) matrices.
Figure again. So we have (2, 3) where we first take a two-dimensional input to three neurons, and then (3, 1) where we take the next three neurons to one neuron.
![image](https://gyazo.com/dbe9479365fa1cf7c3f7b65f3e5c0e9c/thumb/1000)

next schedule
- RNN
- LSTM
- Attention

- [https://docs.chainer.org/en/stable/examples/rnn.html](https://docs.chainer.org/en/stable/examples/rnn.html)
    - He's suddenly using LSTM at the part of the RNN explanation.

---
This page is auto-translated from [/nishio/数学前提知識なしの深層学習](https://scrapbox.io/nishio/数学前提知識なしの深層学習) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.