---
title: "Wrong square root sum"
---

![image](https://gyazo.com/2f7560a27e525db33ecd671a8a186b27/thumb/1000)
[https://twitter.com/potetoichiro/status/1386262060028239878](https://twitter.com/potetoichiro/status/1386262060028239878)

explanation
$\sqrt{ka^2} + \sqrt{kb^2} - \sqrt{kc^2} - \sqrt{kd^2}$
$= a\sqrt{k} + b\sqrt{k} - c\sqrt{k} - d\sqrt{k}$
$= (a + b - c - d)\sqrt{k}$
$= \sqrt{k(a + b - c - d)^2}$

So we can find a number such that [$ (\pm a \pm b \pm c \pm d)^2 = \pm a^2 \pm b^2 \pm c^2 \pm d^2
K is for decoration

:

```
+sqrt(1) + sqrt(4) - sqrt(16) + sqrt(36) = sqrt(+1 + 4 - 16 + 36)
+sqrt(1) + sqrt(4) - sqrt(25) + sqrt(36) = sqrt(+1 + 4 - 25 + 36)
+sqrt(1) + sqrt(9) - sqrt(25) + sqrt(64) = sqrt(+1 + 9 - 25 + 64)
+sqrt(1) + sqrt(9) - sqrt(49) + sqrt(64) = sqrt(+1 + 9 - 49 + 64)
+sqrt(1) + sqrt(16) - sqrt(49) + sqrt(81) = sqrt(+1 + 16 - 49 + 81)
-sqrt(1) - sqrt(4) + sqrt(16) + sqrt(25) = sqrt(-1 - 4 + 16 + 25)
-sqrt(1) - sqrt(9) + sqrt(25) + sqrt(49) = sqrt(-1 - 9 + 25 + 49)
-sqrt(1) + sqrt(16) + sqrt(25) - sqrt(36) = sqrt(-1 + 16 + 25 - 36)
-sqrt(1) - sqrt(16) + sqrt(36) + sqrt(81) = sqrt(-1 - 16 + 36 + 81)
-sqrt(1) + sqrt(25) + sqrt(49) - sqrt(64) = sqrt(-1 + 25 + 49 - 64)
-sqrt(4) - sqrt(9) + sqrt(49) + sqrt(64) = sqrt(-4 - 9 + 49 + 64)
-sqrt(4) + sqrt(16) + sqrt(25) - sqrt(36) = sqrt(-4 + 16 + 25 - 36)
-sqrt(4) + sqrt(25) + sqrt(64) - sqrt(81) = sqrt(-4 + 25 + 64 - 81)
-sqrt(9) + sqrt(25) + sqrt(49) - sqrt(64) = sqrt(-9 + 25 + 49 - 64)
```


8-fold for loop
python

```
N = 10
for a in range(1, N):
    for sa in [1, -1]:
        for b in range(a + 1, N):
            for sb in [1, -1]:
                for c in range(b + 1, N):
                    for sc in [1, -1]:
                        for d in range(c + 1, N):
                            for sd in [1, -1]:
                                x = sa * a + sb * b + sc * c + sd * d
                                if x <= 0:
                                    continue
                                a2 = a ** 2
                                b2 = b ** 2
                                c2 = c ** 2
                                d2 = d ** 2
                                x2 = sa * a2 + sb * b2 + sc * c2 + sd * d2

                                def pm(x):
                                    return "+" if x > 0 else "-"
                                if x * x == x2:
                                    print(
                                        f"{pm(sa)}sqrt({a2}) {pm(sb)} sqrt({b2}) {pm(sc)} sqrt({c2}) {pm(sd)} sqrt({d2})"
                                        f" = sqrt({pm(sa)}{a2} {pm(sb)} {b2} {pm(sc)} {c2} {pm(sd)} {d2})"
                                    )
```


- [[Programmatic search]]

---
This page is auto-translated from [/nishio/間違った平方根の和](https://scrapbox.io/nishio/間違った平方根の和) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.