---
title: "Analyze Polis data"
---

Analyze Polis data with your own Python scripts
- [[Export from Polis]]

2023-06-21
We collected data by [[Polis in EC2]] on our own.
- [https://polis.nhiro.org/3bbdm2tsss](https://polis.nhiro.org/3bbdm2tsss)
- ![image](https://gyazo.com/41dbf7cf1ac885827d28dc9bbbae9d20/thumb/1000)
- 59 people data were obtained.

- [[Export data from Polis DB]] I did.
- Data: [https://gist.github.com/nishio/897cdad38e9a797917f7b8e5a27c7524](https://gist.github.com/nishio/897cdad38e9a797917f7b8e5a27c7524)

py

```
import pandas as pd
df = pd.read_csv("/Users/nishio/Downloads/polis.csv")
matrix = df.pivot_table(index="pid", columns="tid", values="vote")
print(matrix)
```


![image](https://gyazo.com/e08623d52b83779b1db863dfb491d2c9/thumb/1000)
75 rows

[https://github.com/compdemocracy/analysis/blob/master/notebooks/jupyter/american-assembly-representative-groups-and-comments.ipynb](https://github.com/compdemocracy/analysis/blob/master/notebooks/jupyter/american-assembly-representative-groups-and-comments.ipynb)

py

```
matrix = matrix.dropna(thresh=3)
print(matrix.shape)
# => (59, 8)
```

The paper said 7 was the threshold, but it actually looks like 3.

K-3
![image](https://gyazo.com/02458b971fbad2068ab060ce0575a508/thumb/1000)

[[Polis: Scaling Deliberation by Mapping High Dimensional Opinion Spaces]]

![image](https://gyazo.com/024b99a6ea894895dc345ffb441bff82/thumb/1000)

![image](https://gyazo.com/39b7589b772d69ec0f047da7daa3a5e0/thumb/1000)

![image](https://gyazo.com/26de6308bf8b358fad9a85c240c925c2/thumb/1000)

![image](https://gyazo.com/2828ca1c6ea1d4eab64c78677cd05ac0/thumb/1000)![image](https://gyazo.com/41dbf7cf1ac885827d28dc9bbbae9d20/thumb/1000)
0 12
1 36
2 11
Hmmm, I got a picture that looks like that, but the results don't match.

[[2023-06-22CodeReading]]

It's done.
- ![image](https://gyazo.com/8a746a484dff28c8c0971b0b0207b3cb/thumb/1000)
:

```
comment 7
Count of +1 votes in group:  0.0
Count of 0 votes in group:  2.0
Count of -1 votes in group:  12.0
 
Count of +1 votes outside group:  19.0
Count of 0 votes outside group:  19.0
Count of -1 votes outside group:  7.0
 
pvalue:  5.840739168435112e-05
```

Polis clustering and calculation of "characteristic responses" per cluster from CSV of polling data without Polis backend implementation.

2023-06-22
![image](https://gyazo.com/f3fec605e6fa35612f21ad1a1c3cd461/thumb/1000)![image](https://gyazo.com/41dbf7cf1ac885827d28dc9bbbae9d20/thumb/1000)

![image](https://gyazo.com/f6e42bdef2612da442f54e526178edba/thumb/1000)

Related next [[Polis2024-05-13]].

---
This page is auto-translated from [/nishio/Polisのデータを解析](https://scrapbox.io/nishio/Polisのデータを解析) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.