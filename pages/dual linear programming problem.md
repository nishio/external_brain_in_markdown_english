---
title: "dual linear programming problem"
---

![image](https://gyazo.com/448ff0eede42a3e7683c517b42b504bf/thumb/1000)

For a given linear programming problem (LP1)
- minimize
    - $c_1^Tx_1 + c_2^Tx_2$
- subject to
    - $A_{11} x_1 + A_{12} x_2 \ge b_1$
    - $A_{21} x_1 + A_{22} x_2 = b_2$
    - $x_1 \ge 0$
The following linear programming problem (LP2) is called a dual problem
- maximize
    - $b_1^T y_1 + b_2^T y_2$
- subject to
    - $A_{11}^Ty_1 + A_{21}^Ty_2 \le c_1$
    - $A_{12}^Ty_1 + A_{22}^Ty_2 = c_2$
    - $y_1 \ge 0$
Since the maximize is changed and the direction of inequality is changed, we have to invert the sign and align it with LP1, like this
- minimize
    - $-b_1^T y_1 - b_2^T y_2$
- subject to
    - $-A_{11}^Ty_1 - A_{21}^Ty_2 \ge -c_1$
    - $-A_{12}^Ty_1 - A_{22}^Ty_2 = -c_2$
    - $y_1 \ge 0$

The correspondence between the variables LP1 and LP2 is as follows, so we can see that this transformation can be done twice to get back to the original
Variable support
| LP1 | x1 | x2 |  |  c1 | c2 | b1 | b2 | A11 | A12 | A21 | A22 |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| LP2 | y1 | y2 |  | -b1 | -b2 | -c1 | -c2 | -A11^T | -A21^T | -A12^T | -A22^T |


For simpler problems
- minimize
    - $c^Tx$
- subject to
    - $A x = b$
    - $x \ge 0$
The dual problem of the following
- minimize
    - $-b^Ty$
- subject to
    - $-A^T y \ge -c$
Variable support
|  | x |  |  |  c |  |  | b |  |  | A |  |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| LP1 | x1 | x2 |  |  c1 | c2 | b1 | b2 | A11 | A12 | A21 | A22 |
way of thinking
- Since x is positively constrained, this corresponds to x1.
- The coefficient of x1 in the objective function is c1
- The constraints are equations, and if we focus on x1, A21 and b2
- All other values are zero.
- Substituting for a dual problem
- A21 hangs on y2, which we will call y
- Note that y2 is not positively constrained.


- minimize
    - $c_1x_1 + c_2x_2$
- subject to
    - $a_{11} x_1 + a_{12} x_2 \ge b_1 \cdots (eq1)$
    - $a_{21} x_1 + a_{22} x_2 \ge b_2 \cdots (eq2)$
    - $x_1 \ge 0, x_2 \ge 0$
- Consider $y_1 \times eq1 + y_2 \times eq2$$(y_1 \ge 0, y_2 \ge 0)$
    - $(a_{11}y_1 + a_{21}y_2) x_1 + (a_{12} y_1 + a_{22} y_2) x_2 \ge b_1 y_1 + b_2 y_2$
- If the left-hand side is less than the objective function, then the objective function is greater than the right-hand side
    - $c_1x_1 + c_2x_2 \ge (a_{11}y_1 + a_{21}y_2) x_1 + (a_{12} y_1 + a_{22} y_2) x_2 \ge b_1 y_1 + b_2 y_2$
- So, if we choose y so that the right-hand side is as large as possible, we get the following linear programming problem
- maximize
    - $b_1y_1 + b_2y_2$
- subject to
    - $c_1 \ge a_{11}y_1 + a_{21}y_2$
    - $c_2 \ge a_{12} y_1 + a_{22} y_2$
    - $y_1 \ge 0, y_2 \ge 0$



- [[LP twins]]   [[dual LP]]
- [[linear programming]]   [[linear programming problem]]
ref:
- [study text Linear Programming (2) Dual Problem and Dual Theorem](http://www.me.titech.ac.jp/~mizu_lab/text/PDF-LP/LP2-dual.pdf)

- [[Frame Covers]]   [[integer programming]]   [[relaxed linear programming]]   [[Application of Primal Dual Method]]
[http://www.akita-pu.ac.jp/system/elect/ins/kusakari/japanese/teaching/InfoMath/2008/note/14.pdf](http://www.akita-pu.ac.jp/system/elect/ins/kusakari/japanese/teaching/InfoMath/2008/note/14.pdf)

---
This page is auto-translated from [/nishio/双対線形計画問題](https://scrapbox.io/nishio/双対線形計画問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.