---
title: "Polis"
---

> Polis is a real-time system that uses advanced statistics and machine learning to collect, analyze, and understand what large numbers of people are thinking in their own words. (DeepL)
- [Polis | The Computational Democracy Project](https://compdemocracy.org/Polis/)
- Pol.is] is also often written as [[Pol.is]], but I did so because the original owner calls himself Polis.
- [[Visualization of opinion distribution]]

<img src='https://scrapbox.io/api/pages/nishio-en/nihia/icon' alt='nihia.icon' height="19.5"/>Polis is a system that collects and analyzes the opinions and sentiments of large numbers of people in real time. The system uses advanced statistics and machine learning to make the collected opinions easier to understand.
- Main Features
    - Real-time collection and analysis: Collect and analyze the opinions of large numbers of people in real time to understand current opinion trends.
    - Efficient opinion gathering: designed to be more organic than surveys and less labor intensive than focus groups.
    - Cluster Analysis: The collected opinions are analyzed in clusters to identify common and conflicting opinions. This provides a holistic view of the diversity of opinions.
- Main applications
    - Policy Making: Governments and businesses can gather citizen and customer feedback to help improve policies and services.
    - Community consensus building: Used to facilitate coordination and consensus building within the community.
- technical background
    - Polis primarily uses the following technologies
        - Dimensionality Reduction: Use PCA (Principal Component Analysis), UMAP, etc. to reduce high-dimensional data to lower dimensions for easier visual understanding.
        - Cluster analysis: clusters opinions using the K-Means method or the Leiden algorithm to extract common groups of opinions.

This is very helpful.
- [https://github.com/compdemocracy/analysis-python/blob/main/notebooks/american-assembly-specific/american-assembly-representative-groups-and-comments.ipynb](https://github.com/compdemocracy/analysis-python/blob/main/notebooks/american-assembly-specific/american-assembly-representative-groups-and-comments.ipynb)
- <img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>This code shows a series of procedures for visualizing and clustering the opinion space using data in which participants "agree (+1)", "disagree (-1)", or "do not vote (0)" for a comment (statement).
    - The main processes are as follows
        - Data preprocessing:
            - Participant filtering based on data reading, missing value processing, and vote thresholds
            - Extraction of appropriate comments (those that remain after moderation)
        - Dimensional Reduction (PCA):
            - The voting matrix was compressed to a lower dimension (two dimensions) using Principal Component Analysis (PCA) and the participants were plotted on a two-dimensional space.
        - Clustering (K-means):
            - First, the PCA results were used to finely classify the participants into 100 clusters, and then the centers of those 100 clusters were further grouped into 2 to 5 clusters, with the optimal number of clusters selected by silhouette score.
        - Extraction of representative comments:
            - Comments that are particularly characteristic of each group are extracted using [[Fisher's exact test]] and the ratio R_v(g,c) to identify comments that show opinion trends specific to each group.
    - In summary, the code presents a series of analytical procedures for voting data consisting of a large number of participants and comments, from dimensionality reduction and clustering to deriving opinion groups and quantitatively identifying comments that are representative of the characteristics of those groups.


[[Polis: Scaling Deliberation by Mapping High Dimensional Opinion Spaces]]
- [[Polis Study Group]]


[https://github.com/compdemocracy/polis](https://github.com/compdemocracy/polis)
[https://github.com/pol-is](https://github.com/pol-is)

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What we tried
    - [[Polis Experience Report: Should we investigate the causes of terrorism?]]
    - [[Polis Experience Report: Should Same-Sex Marriage Be Legalized?]]



<img src='https://scrapbox.io/api/pages/nishio-en/gpt-4/icon' alt='gpt-4.icon' height="19.5"/>
- The Polis project is an AI-powered [[sentiment collection platform]] designed to be more organic than surveys and less labor intensive than focus groups. It aims to satisfy the basic human need to be understood at scale.
    - > Polis is an AI powered [[sentiment gathering]] platform.
        - [[sentiment gathering platform]] という表現をしている<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - [[desire to be understood]].
        - > the basic human need to be understood



- [[Nishio Experience on Plurality Tokyo]]

# [Algorithms](https://compdemocracy.org/algorithms/)
- Dimensionality reduction
    - [[PCA]]
    - [[UMAP]]
- Clustering
    - [[K-Means]]
    - [[Leiden graph based community detection]]
    - [[Hierarchical clustering]]




> [@nishio](https://twitter.com/nishio/status/1645979580623355904): maybe the good thing about Polis is that [[short piece of writing (e.g. passage, article, composition)]] I think the best thing about Polis is that it is [[short piece of writing (e.g. passage, article, composition)]]. If a human tries to reach a consensus with 100 people without the assistance of a machine, he/she has to read 100 times as much as he/she wrote, and most of us can't stand that. Opinions that are close to their own are easier to understand, and opinions that are far away are harder to understand, so they perceive more opinions that are close to their own.

- [[I want to do more Polis.]]

---
This page is auto-translated from [/nishio/Polis](https://scrapbox.io/nishio/Polis) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.