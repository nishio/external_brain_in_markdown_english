---
title: "Experiment 2023-04-06"
---

[[Vector searches do not always hit other languages with the same meaning.]]
- There are 54 Japanese articles and their 54 machine translations into English.
- Vector search this.
- Out of 108 cases, 58 cases are searches for article X, where the nearest article other than X is a "translation of X", and 50 cases are other "articles in the same language as X".
- If you collapse the vector space in the direction of the bilingual vector, you can improve the probability of a match from 50% to 80% regardless of language.

31806 :Yasukazu Nishio2023/4/3(Mon.) 14:50
I don't have enough time at all, but a note on what I'd like to try when I have more time.
The fact that the English and Japanese embedding vectors are far apart.
There is a possibility that there is a 1-3 dimensional component that expresses language differences, and if we can destroy it, we can determine similarity regardless of language.
Then you can answer a question in Japanese based on Wikipedia in English.
If this "similar content determination regardless of language" can be done, the cost of multilingual deployment of help should be drastically reduced in the Cybozu context.

31828 :Yasukazu Nishio2023/4/6(Thu) 0:10
All English translations of my Scrapbox and differential updates in Github Actions are finally working.
This would make a 31806 experiment.
We have created embed vectors for all the Japanese articles.
1: Create an embed vector of all English articles
2: Produce the percentage of each article's nearest article that is a "translated article" and the percentage that is an "article in the same language".
3: Try to get the difference between the bilingual vectors and average them (is it also useful to see how much they vary? Is the median better than the mean? Is it better to get the top 3 dimensions of the contribution ratio?)
4: Do 2 after crushing the dimension of 3
Something like this?
To be continued tomorrow

For the 3 bilingual vectors, I'd need to multiply the PCA to get the vectors in order of contribution rate, and also to check how many dimensions there are.

31836 :Yasukazu Nishio2023/4/6(Thu) 21:09
1: I thought I could just use the same Japanese vectors I used before, but that would have complicated the mapping to English, so I decided to redo them all together.
- It would take a long time to redo the whole thing, so while we wait, we'll try it with smaller data.
2: Out of 108 small data, 58 cases in which the nearest article other than my own is my translation, and 50 other cases in which the article is in the same language as my own.
3: Find the difference vector between Japanese and English translations and squash its axial components
4: Of the 108 articles, 85 were my translations and 23 were in other articles in the same language.

Therefore, if you crush the translation in the direction of the bilingual vector, you can improve the probability of a match from 50% to 80% regardless of the language.
This is useful for asking questions in Japanese when only English documents are available.
---
This page is auto-translated from [/nishio/実験2023-04-06](https://scrapbox.io/nishio/実験2023-04-06) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.