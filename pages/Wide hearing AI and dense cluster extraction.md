---
title: "Wide hearing AI and dense cluster extraction"
---

Note what I wrote in Slack.
- I will share the documents from when "dense cluster extraction" was first created and proposed to GovTech Tokyo.
        - [[Deep Cluster Extraction]]
- The current "subdivision k-means and then filtering by density" is an approximate method created after trying HDBSCAN.
- On the other hand, if HDBSCAN is done separately from the current "hierarchical clustering after k-means subdivision," it would take about 10 minutes for an additional 10,000 entries, and whether this is acceptable or not was discussed when [[public information AI]] was created. This was discussed when [[public information AI]] was created.
- We decided to start with this policy because we believed that the approximate method would allow us to standardize most of the processes and achieve "dense cluster extraction" without additional cost.
- Behind this decision was the fact that at the time there was (and still is) no way to quantitatively compare the "goodness of results" and it was difficult to determine whether the "dense clusters" created by HDBSCAN were "better" than those created by k-means.
- It's like, we can't pay an additional processing cost of 10 minutes for something we can't determine if it's good or not.

memo
- I think the broadband AI changed its name from "[[Deep Cluster Extraction]]" to "Deep Cluster Extraction.

---
This page is auto-translated from [/nishio/広聴AIと濃いクラスタ抽出](https://scrapbox.io/nishio/広聴AIと濃いクラスタ抽出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.