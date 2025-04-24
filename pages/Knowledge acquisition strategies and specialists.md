---
title: "Knowledge acquisition strategies and specialists"
---

![image](https://gyazo.com/c87874588e271a962ef3a9fd33e0a404/thumb/1000)

----
- [[Knowledge Acquisition Strategies]] and [[specialist]] and [[generalist]]
I decided to create a [[Knowledge Distribution Chart]], which I often use, in code so that I can experiment with it.

You are given a choice of three objects to study each step and learn one according to your own knowledge acquisition strategy.
When we learn, we gain a random amount of knowledge. Since we also add random noise to the domain of knowledge gained, we sometimes "gain knowledge in areas that are slightly out of line with what we were trying to learn.
We observed the difference between the strategy of choosing "the subject of which one has more knowledge" from among the three options (specialist strategy) and the strategy of choosing "the subject of which one has less knowledge" (generalist strategy), with the conditions other than the knowledge acquisition strategy being the same.
![image](https://gyazo.com/45da70185788ef347932cb3983a11a15/thumb/1000)
I was under the impression that there was only one peak for specialists, but multiple peaks occurred.

I had imagined a more "generalists win in most areas, but specialists are overwhelmingly strong only in their areas of expertise" phenomenon, but specialists win in 44% of the areas.

This behavior occurs because the situation lacks "freedom of the object of learning," which is to choose from three random options out of a total of 100 objects to be learned. This is what happens when the number of choices given is 10.
![image](https://gyazo.com/c87874588e271a962ef3a9fd33e0a404/thumb/1000)
This is what happens when you have 30 options, or 30% of all subjects, to choose from freely.
![image](https://gyazo.com/bb6f9c91f74d4cbb9931912a82923f2d/thumb/1000)
The "specialist strategy" of choosing what one does best leads to more freedom of choice and more concentration on a single peak.
On the other hand, the generalist strategy is less affected by freedom of choice.

3 specialists and 1 generalist
Although gathering three generalists is not a [[literal]] wisdom because none of them are alike,
When specialists come together and play to their strengths, they will demonstrate higher knowledge than a group of generalists in most areas.
![image](https://gyazo.com/2cae28889415e54e823d6c1caf5a83be/thumb/1000)


[Colab](https://colab.research.google.com/drive/15or2hCehfO-NfWFjX5WBeKCS0vOc55bI)
python

```
import numpy as np
from matplotlib import pyplot as plt
KNOWLEDGE_WIDTH = 100
TIMES = 10000

def get_knowledge(policy):
  knowledge = np.zeros(KNOWLEDGE_WIDTH)
  for t in range(TIMES):
    targets = np.random.randint(0, KNOWLEDGE_WIDTH, size=3)
    target = targets[policy(knowledge[targets])]
    target = int(np.random.normal(target))
    if target < 0 or target >= KNOWLEDGE_WIDTH: continue
    knowledge[target] += np.random.random()
  return knowledge

specialist = get_knowledge(policy=lambda xs: xs.argmax())
generalist = get_knowledge(policy=lambda xs: xs.argmin())
plt.plot(specialist, label="specialist")
plt.plot(generalist, label="generalist")
plt.legend()
```


---
This page is auto-translated from [/nishio/知識の獲得戦略とスペシャリスト](https://scrapbox.io/nishio/知識の獲得戦略とスペシャリスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.