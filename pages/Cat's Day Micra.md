---
title: "Cat's Day Micra"
---

[https://youtu.be/2da5QX3-Eb8](https://youtu.be/2da5QX3-Eb8)

![image](https://gyazo.com/0428ee55b3fdcc0efe70a156cdf135df/thumb/1000)

![image](https://gyazo.com/c9bd7c4c9e32b116e7ee737a1ccd0072/thumb/1000)
[https://twitter.com/nishio/status/1495990229500833792](https://twitter.com/nishio/status/1495990229500833792)

I'm updating this at [[mcpi]].
MIT License.
python

```
from random import random
from datetime import datetime
from mcpi import minecraft
from time import sleep

PORT = 4711
WOOL = 35
GLASS = 20
FURNACE_ACTIVE = 62
AIR = 0
SANDSTONE = 24

WHITE = 0
BLACK = 15

OX = 6033
OY = 80
OZ = 21


def new_buffer():
    return [[] for i in range(7)]


cmap = {"*": BLACK, ".": WHITE}


def make_data(s):
    s = s.strip().splitlines()
    assert len(s) == 5
    WIDTH = len(s[0])
    assert all(WIDTH == len(s[i]) for i in range(5))
    HR = [[WHITE] * WIDTH]
    return HR + [[cmap[c] for c in line] for line in s] + HR


s0 = """
***
*.*
*.*
*.*
***
"""

s1 = """
.**
..*
..*
..*
..*
"""

s2 = """
***
..*
***
*..
***
"""
s3 = """
***
..*
***
..*
***
"""
s4 = """
*.*
*.*
***
..*
..*
"""
s5 = """
***
*..
***
..*
***
"""
s6 = """
***
*..
***
*.*
***
"""
s7 = """
***
..*
..*
.*.
.*.
"""
s8 = """
***
*.*
***
*.*
***
"""
s9 = """
***
*.*
***
..*
***
"""

data_digits = [make_data(s) for s in [s0, s1, s2, s3, s4, s5, s6, s7, s8, s9]]
nyan = data_digits[2]

data_colon = make_data("""
.
*
.
*
.
""")

data_hyphen = make_data("""
..
..
**
..
..
""")

data_period = make_data("""
.
.
.
.
*
""")


def vline(buf, color=WHITE):
    for line in buf:
        line.append(color)


def add(buffer, new_item):
    for i, line in enumerate(new_item):
        buffer[i].extend(line)


def items_to_buf(items):
    buf = new_buffer()
    vline(buf)
    for item in items:
        add(buf, item)
        vline(buf)
    return buf


# --- build blocks
m = minecraft.Minecraft.create(HOST, PORT)


def pset(x, y, z, color):
    # m.setBlock([OX - x, OY - y, OZ - z, WOOL, color])
    if color == WHITE:
        m.setBlock([OX - x, OY - y, OZ - z, AIR])
    else:
        m.setBlock([OX - x, OY - y, OZ - z, SANDSTONE, 2])


def build_date():  # run once
    wan = data_digits[2]

    date_buf = items_to_buf([
        nyan, wan, nyan, nyan,
        data_hyphen,
        wan, nyan,
        data_hyphen,
        nyan, nyan,
    ])

    for y, line in enumerate(date_buf):
        for x, c in enumerate(line):
            pset(x, y - 6, 0, c)

# ---


def build_time():
    now = datetime.now()

    time_buf = items_to_buf([
        data_digits[now.hour // 10],
        data_digits[now.hour % 10],
        data_colon,
        data_digits[now.minute // 10],
        data_digits[now.minute % 10],
        data_colon,
        data_digits[now.second // 10],
        data_digits[now.second % 10],
        data_period,
        data_digits[now.microsecond // 100000],
        data_digits[(now.microsecond // 10000) % 10],
    ])

    for y, line in enumerate(time_buf):
        for x, c in enumerate(line):
            pset(x, y, 0, c)


def finish():
    time_buf = items_to_buf([
        nyan, nyan,
        data_colon,
        nyan, nyan,
        data_colon,
        nyan, nyan,
        data_period,
        nyan, nyan
    ])

    for y, line in enumerate(time_buf):
        for x, c in enumerate(line):
            pset(x, y, 0, c)


while True:
    if datetime.now() > datetime(2022, 2, 22, 22, 22, 22):
        break
    else:
        build_time()
        sleep(1 - random() * 0.1)

finish()
```



---
This page is auto-translated from [/nishio/猫の日マイクラ](https://scrapbox.io/nishio/猫の日マイクラ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.