---
title: "Nodal Point of Thought 2025-06-06"
---

    - [[Wide hearing AI and dense cluster extraction]]
    - [[Talk to the City clustering]]

[dd2030 slack](https://dd2030.slack.com/archives/C08F7JZPD63/p1749041733485549) 2025-06-04
Shinta Nakayama (tokoroten)
- After chatting with Mr. Nishio, I feel like we need to have a meeting to dig up tttc operational expertise (and current Team Mirai operational expertise) from the Governor's campaign.
- Lack of people with experience in handling large data sets of tttc and broadband AI who can speak in the language of data science and engineers about awareness of issues and operational know-how.

NISHIO Hirokazu
- By the way, that's about 70% nasuka and 30% me.
    - [[Shin Tokyo 2050 Broad Listening]] was done not by Yasuno's team, but by GovTechTokyo, and Yasuno's team only provided support and advice, not actual data analysis.
- Oh, no, you're not talking about the gubernatorial race.

Shinta Nakayama (tokoroten)
- Yes, I want to siphon off the know-how from the Tokyo gubernatorial campaign.
- [How to use Talk to the City in the Tokyo Gubernatorial Election 2024｜NISHIO Hirokazu](https://note.com/nishiohirokazu/n/n0661204bda5b)
- I want a story three levels deeper than this one.

NISHIO Hirokazu
- I wonder if there was anything else,
- It's hard to share with non-engineers if you don't have a preview server attached, and I've solved that with a broadband AI,
- Japanese people will leave if the UI is in default English.
- I initially tried YouTube comments and Twitter, but YouTube comments are not very good for this kind of analysis (too much noise) because of the limited time and people post poorly worded posts.
- Twitter is better, but it costs a lot more money, and in the end, "people who don't normally make political statements evade writing on Twitter".
- I hear they ended up annexing Google Form for "no one gets left behind."

Shinta Nakayama (tokoroten)
- Like how to use it to try to gain insight.
- I'm only feeding them dummy data or data that looks like that of other people, so I'm not taking the data or the results of the analysis seriously.
- How do you look at the data and analysis results when you take them seriously, what do you want to see and what do you want to get out of them?

NISHIO Hirokazu
- Insight!
- There's obviously a difference between a setting that's suitable for showing to the general public, which doesn't have data analysis literacy, and a setting when you want to analyze data and gain insight.
- Well, the principle of "roughly first, then in detail" is fine.
- I think the general public already has a lot at about 7 clusters, and they tend to judge the 7 clusters by their labels without reading the descriptions of the clusters.
- If you're trying to pull off an insight, well, you're going to have to break it into 30 clusters or something.
- Even 30 clusters are not enough to grasp the structure, and there is a need to dig deeper into the clusters.
- There is a way to separate data into clusters and then do further TTTC by cluster, but it is very tedious, so we introduced hierarchies in the broadband AI.


2025-06-06
- Shingo OHKI
    - I happened to hit upon a memo from Mr. Nishio that seems important as to the history of the development of the Wide Hearing AI!
        - [[Wide hearing AI and dense cluster extraction]]
- NISHIO Hirokazu
    - Thanks, I forgot all about what I wrote and couldn't get it out right away myself.
    - A story I was explaining separately to @SintaNakayama the other day.
- Shinta Nakayama (tokoroten)
    - Ah, the dense cluster was a pseudo-implementation of HDBSCAN, I finally understand what you mean.

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Digest Commentary for Data Scientists
- Selection logic for clustering methods
    - The BERTopic used by Talk to the City runs UMAP→HDBSCAN internally, but Talk to the City also splits it further with Spectral Clustering, which can break consistency. (see [[Talk to the City clustering]])
    - The remedy is either (1) to use the output of HDBSCAN as it is and fine-tune it with threshold values, or (2) to split BERTopic into a keyphrase extractor and integrate clustering externally.
    - Wide hearing AI is integrated into hierarchical clustering

- Comparison of clustering before and after UMAP
    - Clustering in high-dimensional space preserves distance, but is computationally heavy and difficult to visualize
    - While the process is faster and looks better in the GUI if the image is projected to 2D in UMAP and then split, the local distance is distorted, which may result in "clusters that look close but are far away/far away but are the same cluster.

- Spectral Clustering's "broken cluster" problem used by Talk to the City
    - In order to cut in Laplacian eigenspace, priority is given to the connectivity of the k-nearest neighbor graph rather than the 2D coordinates themselves.
    - Therefore, even if the point sequence is geographically divided, it can be the same label - it needs to be explained with annotations and auxiliary lines when visualized
    - This phenomenon is often asked about and has a high explanation cost, so we have adopted an algorithm that does not cause this phenomenon in the wideband AI (we stopped using Spectral Clustering and changed to Hierarchical Clustering).

- Changes in "dense cluster extraction" algorithms (see [[Wide hearing AI and dense cluster extraction]])
    - Originally, the high-dimensional HDBSCAN was used to detect dense areas.
    - In actual operation, UMAP → subdivision k-Means → density filter for cost reduction.
    - The original HDBSCAN takes an additional 10 minutes for 10,000 data.
    - Nishio envisions that "in the future, after high-speed analysis, it would be good to have a mechanism that allows additional analysis to be performed as a plug-in, where the high-dimensional HDBSCAN can be reverted.
    - Additional analysis plug-in concept
        - Separate from the core visualization pipeline, allowing disruptive new methods to be injected as "additional analysis."

---
This page is auto-translated from [/nishio/思考の結節点2025-06-06](https://scrapbox.io/nishio/思考の結節点2025-06-06) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.