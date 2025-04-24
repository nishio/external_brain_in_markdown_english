---
title: "The white square adjacent to the black square is turned to black"
---

Title needs improvement
For all black squares, if there is a white square adjacent to the black square, it is black" is the same as "For all black squares, if there is a white square adjacent to the black square, it is black

python

```
for x in all_white_cell:
    if any(is_black(y) for y in neighbor(x)):
        toBlack(x)
```


python

```
for x in all_black_cell:
    for y in neighbor(x):
        if is_white(y):
            toBlack(y)
```


In the latter case, once a black square is processed, it does not have to be processed again, thus reducing the amount of calculation.

- [[problem transformation]]

---
This page is auto-translated from [/nishio/黒マスに隣接している白マスを黒にする](https://scrapbox.io/nishio/黒マスに隣接している白マスを黒にする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.