---
title: "concentration (of one's attention)"
---

Adaptation in English
- [Empirical estimates of adaptation: the chance of two noriegas is closer to p/2 than p^2](https://dl.acm.org/doi/10.3115/990820.990847)
- The title noriega is the name of a politician. Kind of like "Kennedy."
- When the probability of a word appearing is p, we tend to think that the probability of it appearing twice is p^2
- But in reality, once a word appears, it appears with high frequency.
- How high a frequency is this?
- Surprisingly, the conditional probability $Pr(k\ge2|k\ge1)$ of appearing k+1 times with k occurrences is,
    - Not depending on the probability of one occurrence $Pr(k\ge1)$.
    - $Pr(k\ge1) = DF_1/D$
    - $Pr(k\ge2|k\ge1) = (DF_2/D)/Pr(k\ge1) = DF_2/DF_1$
![image](https://gyazo.com/b7dc9d57f2789bf54c540242d6543f29/thumb/1000)
- Comparing words with the same probability of occurrence, Kennedy, for example, shows a higher concentration of occurrence than except.
    - ![image](https://gyazo.com/d42ac8acd36b57adc7319d3aa6f03992/thumb/1000)
        - In [[Development of a system for extracting keywords in unexplored text information]], we compare the distribution of substrings in the paper with the distribution of strings chosen by humans as keywords, and show that the keyword distribution is the same as the story here, with probability independent distribution as in the story here.
    - Based on what we're talking about here, it seems like that kind of distribution for word distribution alone, and for keywords, it's on the upper end of the scale. I would like to compare the distribution of words with the distribution of keywords.
    - Conversely, for any given string, DF2/ DF is an indicator of "keywordiness" independent of its frequency of occurrence

---
This page is auto-translated from [/nishio/出現集中](https://scrapbox.io/nishio/出現集中) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.