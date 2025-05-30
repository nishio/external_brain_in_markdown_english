---
title: "Angle distribution"
---

[Talk about spikes standing out when displaying the frequency of angles from the origin of integer grid points](https://twitter.com/abee2/status/1347785348315713536) (Twitter @abee2)
I'll try it in Python.

N=100
- ![image](https://gyazo.com/f434c0c2b420c9802567d133b7743e3b/thumb/1000)
    - You can see the spikes standing on multiples of 45 degrees as well.
        - Not only that, but there appears to be a small spike in 15 degree increments as well.

N=1000
- ![image](https://gyazo.com/390c0b7d7e2b181496b06e0ec0719d1c/thumb/1000)
    - When I made the ticks finer, the 45 degree and other spikes were less noticeable, but the 0 degree and 180 degree spikes were more noticeable.
    - Interesting that it makes a large dent at 180 degrees.
        - atan2(1,1000) == 0.0009999996666668666, atan(1, -1000) == 3.1405926539231266
        - Is it influenced by the fact that the number around 0 degrees is a "good number" and the number around 180 degrees is a "bad number"?
- Ah, I'm starting to get it.
    - The value range of atan2 is -pi ~ pi
    - int(-0.1) == 0 i.e. rounding to zero
    - That's why they congregate at zero.
    - When changed to rounding (floor) in the -inf direction
        - ![image](https://gyazo.com/db4e66f6830bfbfd1f864212fcb439da/thumb/1000)
        - Now we only have "spikes in multiples of 45 degrees" of equal length.
            - Spikes anywhere in multiples of 90 degrees and of the same height
            - Otherwise, a slightly longer (perhaps twice the root) spike in multiples of 45 degrees.
                - Maybe this one just looks longer because it's pointed to begin with?
            - Spikes in multiples of 90 degrees decrease "one degree less" by the same amount.
:

```
87 8751
88 8737
89 8243
90 9243
91 8737
92 8751
```

            - The same phenomenon may be occurring at other multiples of 45 degrees, but it's hard to tell because it overlaps with the original peak.
- Limited to the lattice points inside the circle.
    - `if x ** 2 + y ** 2 > N ** 2: continue`
    - ![image](https://gyazo.com/c329b081cbe655fcb1721588b33c773c/thumb/1000)
x,y and angle relationship

```
(1000, -1): -1
(1000, 0): 0
(1000, 1): 0
---
(1000, 1001): 45
(1000, 1000): 45
(1001, 1000): 44
```

    - There are a non-negligible number of points that are just on the boundary of an integer bin.
        - If you add the slightest bit of noise, it could be sorted into two bins, say 44 and 45.
        - Because it all goes into 45, there are fewer 44s and more 45s.
    - Is there anything other than a multiple of 45 degrees where the tangent is a rational number?
        - And it's not just a rational number, it's 1/8, which is a nice binary number.

python

```
from math import atan2, pi
from matplotlib import pyplot as plt

N = 1000
count = [0] * 360
for x in range(-N, N + 1):
    for y in range(-N, N + 1):
        if x == y == 0:
            continue
        theta = int(atan2(x, y) / 2 / pi * 360)
        count[theta] += 1

for i in range(360):
    print(i, count[i])

plt.bar(range(360), count)
plt.show()
```


---
This page is auto-translated from [/nishio/角度の分布](https://scrapbox.io/nishio/角度の分布) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.