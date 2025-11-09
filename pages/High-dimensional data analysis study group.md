---
title: "High-dimensional data analysis study group"
---

2024-11-22  [[Cybozu Labs Study Session]]
- Previously: 2024-10-18 [[Public Opinion Map Study Group]].
    - It was the day that "[[public opinion map]]", a service that collects and visualizes people's opinion vectors in the [[2024 lower house election]], was released.
- This ended up with 4403 rows x 84 columns of data
    - (We are in the process of converting it to open data and will write about it here when it is ready)
- In this article, I will explain "analysis of high-dimensional data," including the analysis of this data.
- Rough Table of Contents
    - History of dimensionality reduction (from PCA to UMAP)
    - UMAP visualization experiment for the 2022 Upper House election
        - pleasant feeling
        - [[UMAP of public opinion map]] Experiment
        - Struggle with high-dimensional mud dumplings
        - Distressed -> Aware
    - New projects (to be announced 11/22)
    - [[Extraction of dense masses]]
    - Relation to the KJ method


History of dimensionality reduction (from PCA to UMAP)
- PCA (Principal Component Analysis) is a linear dimensionality reduction method
    - The classic method proposed by [[Karl Pearson]] ([[Karl Pearson]]) in 1901
- Mid-20th century: Limitations of PCA (reliance on linearity) begin to be pointed out and the need for methods to handle nonlinear structures increases.
- 1960s: [[Multidimensional Scaling]] (MDS)
    - Mapping high-dimensional data to low-dimensional space based on a distance matrix.
    - > Classical MDS is also called Principal Coordinate Analysis (PCoA), and is equivalent to Principal Component Analysis when Euclidean distance is used in Principal Coordinate Analysis. --- [Multidimensional scaling - Wikipedia](https://ja.wikipedia.org/wiki/%E5%A4%9A%E6%AC%A1%E5%85%83%E5%B0%BA%E5%BA%A6%E6%A7%8B%E6%88%90%E6%B3%95)
    - There are linear and nonlinear versions, and nonlinear MDS can handle non-Euclidean distances.
- 1982: [[Self-organizing map]] ([[SOM]], [[Self-Organizing Maps]])
    - Actually, my PhD research 20 years ago was one of the extensions of SOM, so when I told ChatGPT to write a history of nonlinear dimensionality reduction and this came up, I was like, "Whoa, a familiar face!
        - ChatGPT explains that it's "based on a neuroscientific approach, mapping data onto a low-dimensional grid," and well, in general, that's not wrong, but it's a "model inspired by the neural connections in the brain," which is common at this time, and it's so close that it no longer has much to do with the behavior in the brain. It doesn't have much to do with the behavior in the brain.
            - Well, now neural nets are much less neural.
        - k-means method with adjacencies/distances between representative points
            - Pioneering role as an analysis method that takes into account the topological characteristics of data
        - As of 20 years ago, extensions to non-Euclidean distances were being made.
- 1998: Kernel PCA (Kernel PCA)
    - [[kernel method]] to deal with nonlinear structures.
        - [[regenerative nuclear hillbelt space]] (RKHS) to apply PCA.
    - One of the derivations from the prosperity of [[Support Vector Machine]](1992)
    - Kernel concepts are getting renewed attention in relation to the mathematics of deep learning.
- Development of "analytical methods that take into account the topological properties of the data.
    - 2000: [[Isomap]] ([[Isometric Mapping]])
        - Distance structure is approximated based on graphs, and dimensionality reduction preserving the manifold structure.
    - 2000: [[LLE]] ([[Locally Linear Embedding]])
        - Dimensionality reduction is achieved by exploiting the local linearity of the data.
- 2008: t-SNE (t-Distributed Stochastic Neighbor Embedding)
    - Probabilistic representation of local similarity in higher dimensional spaces and mapping to lower dimensions.
    - Widely used as a specialized method for visualization.
- 2018: UMAP (Uniform Manifold Approximation and Projection)
    - Improvements to the shortcomings of t-SNE (computational load and collapse of local structure).
    - Mainstream modern visualization and dimensionality reduction methods.
- I was going to explain the detailed algorithm of UMAP, but that alone would have taken up an hour, so I decided to save it for another time.
    - Summary of this section
        - PCA is a classical dimensionality reduction method from 1901
        - Nonlinear dimensionality reduction methods have been studied for many years because of the disadvantages of being linear
        - Right now it's considered a good idea to use the 2018 UMAP.
- Cases where PCA is not a good choice
    - ![image](https://gyazo.com/188215f1b3ee60ca4f81903b19984082/thumb/1000)
        - [[antagonistic dimension]]
        - 1: A and B are in conflict
        - 2: (A+B) and C are in conflict
        - 3: ((A+B)+C) and D are in conflict
            - Here the number of dimensions is not enough so that A and B become identical in the 2-dimensional [[PCA]].
            - Nonlinear dimensionality reduction (e.g., [[UMAP]]) divides



- [[UMAP visibility for the 2022 Upper House election]]
- My experience so far has been that Polis tends to become less and less divided into clusters as it progresses.
    - I didn't want all the clusters to be separated at the end of this poll map.
    - So I was considering a version that uses non-linear UMAP instead of dimensionality reduction using the original Polis PCA.
    - In the experiment of the public opinion map, the "tendency for the clusters to become less divided as they progress" was not observed.
        - This phenomenon may not be due to an increase in the number of voting users, but rather to the fact that the opinion space is becoming more highly dimensioned as users contribute new opinions
        - Detailed discussion: [[Problem with two Polis clusters]].
- As a preliminary experiment, I visualized the 2022 Upper House election data ([[Joint research by Taniguchi Laboratory, University of Tokyo and Asahi Shimbun]]) analyzed by PCA using [[UMAP]] before the public opinion map data were available ( 592 respondents, 42 questions)
    - Left: UMAP [[UMAP visibility for the 2022 Upper House election]] / Right: PCA [[Polis-like visualization of the 2022 House of Councillors election]].
    - ![image](https://gyazo.com/2d34ad06a7c1206fc84cc7292123700d/thumb/1000)![image](https://gyazo.com/77f9fc60c241159a0062e4842a7435cf/thumb/1000)
    - The PCA is almost just an ellipse if you look at the dots.
        - The party is surrounded by [[Convex Hull]] and painted in color because the meaning is not so clear as it is.
        - This is what "PCA will no longer separate clusters" means
        - However, it is not divided into separate sections, but it seems to be very interesting, and Mr. Yasuno introduced it at the Keynote of [[Code for Japan Summit 2024]] on 2024-11-16.
        - ![image](https://gyazo.com/b5cbb13a30bb7cc903d0cabae78a7040/thumb/1000)
        - ![image](https://gyazo.com/9efdf13860b4680989cac0361b5f0e97/thumb/1000)
        - Advantage is that it is PCA, so the axes make sense.
            - Non-linear methods make the current interpretation impossible because the axis bends all over the place.
- The UMAP analysis is very clearly divided into clusters compared to the PCA analysis, which is almost one cluster of ellipses.
    - ![image](https://gyazo.com/2d34ad06a7c1206fc84cc7292123700d/thumb/1000)
    - Red boxes are manually added for detailed explanation
        - For a detailed cluster-by-cluster explanation, see: [[UMAP visibility for the 2022 Upper House election]].
    - Some islands are dense, occupied by a particular political party, while others are a mixture of several parties
        - In other words, when there are parties A, B, and C, we tend to think that the division of opinion is between the parties, but in fact the division is between extremists and moderates within the parties.
        - ![image](https://gyazo.com/3916e82cf21628e1fd4e0e54177dda48/thumb/1000)
- I think this is a pretty interesting outcome.



- [[UMAP of public opinion map]]
![image](https://gyazo.com/30c9d0303e0de3e01269148c72184c1e/thumb/1000)
- I got the data for the poll map and immediately UMAP'd it.
    - [[Public Opinion Map 3970 UMAP]]
    - 3970 people x 84 dimensions (when data from all maps are combined)
- Unlike the 2022 Upper House election data, there is no party data, so I used [[DBSCAN]] to cluster the data.
    - DBSCAN has nothing to do with database scanning at all, but Density-Based Spatial Clustering of Applications with Noise
    - Density-based clustering methods (I'll talk more about them later, so that's enough for now)
- There are about 13 scattered clusters and a central [high-dimensional mud pie
- What is the data volume ratio?
    - 3970 in all, with 655 smaller clusters around the perimeter.
    - 84% of users are in a central cluster with no clear separation
- Perhaps in the case of politicians answering a questionnaire with a name, there is a "dynamics of opinion polarization" such as the relationship with the claims of the party they belong to, position talk of the opposition party to the ruling party, [[group polarization]], etc.
        - [[The opinion vectors of anonymous citizens are not so clearly separated.]]



Struggle with high-dimensional mud dumplings
- Can we analyze this part of the center a little better?
    - ![image](https://gyazo.com/ca78ba9feeb5beabee68258e4128cdc9/thumb/1000)
    - It looks like it has a meaningful internal structure, doesn't it?
- I was trying to analyze this part of the analysis ([[Should UMAP results be clustered?]], I started thinking that it might be better not to cluster them).
    - ![image](https://gyazo.com/2ede642899c3f91ba27476630daa82f7/thumb/1000)
    - Increasing parameter eps to reduce gray "outliers" causes clusters to be merged
    - ![image](https://gyazo.com/868a75c921455b846d041acd1ca2a45c/thumb/1000)![image](https://gyazo.com/8f47923a4850a422f8cd1d6b127b5db3/thumb/1000)
    - This is more of a problem with interpreting DBSCAN "outliers" as "data that is discarded because it is an outlier that is far away" and should be interpreted as "data that is between two clusters and hard to say which side it is on".
        - ![image](https://gyazo.com/a7b9acd91aa50cf79544b11fff78fde0/thumb/1000)
        - We want to separate A from B, so where do we draw the line?"
            - Isn't this question wrong in the first place? that this question is wrong in the first place, isn't it?
            - Drawing a boundary line is putting in the assumption that it is divisible by a line of no thickness.
            - In reality, many things in the world do not have clear boundaries, but are divided across a wide "neither-here-nor-there" zone
    - (I understood later that this was reinventing the design concept of the DBSCAN/HDBSCAN system.)
- I shared this story within the Yasuno team and they told me an interesting story: [[Careful clustering of tSNE results]].
- Attempted clustering directly on higher dimensional space rather than on post-UMAP data
    - ![image](https://gyazo.com/dcd3a244de09a631bc23d62aece80449/thumb/1000)
    - I was shocked to see these results.
    - ![image](https://gyazo.com/8648c886f5ef2c68dc9cb97c5db24fc4/thumb/1000)
    - What I mean is.
        - Cluster-like dense masses" (blue and purple) after 2D visualization in UMAP
        - ![image](https://gyazo.com/ca78ba9feeb5beabee68258e4128cdc9/thumb/1000)![image](https://gyazo.com/5eb99e21a33cd7a7e65d68bfb98457aa/thumb/1000)
        - That this is actually not dense at all in higher dimensional space.
- What is happening?



- [[UMAP of the data for and against]] issue
- ![image](https://gyazo.com/66f90b8311c1343c4720c730623b1ca1/thumb/1000)
    - The greater the amount of data that is neither for nor against, the more reddened it is.
    - The "cluster-like dense clusters" were collections of data with few missing values, and the surrounding complex and meaningful shapes were data with many missing values.
- Originally, this data was set to `matrix.dropna(thresh=3)` (only keep the data with 3 or more missing data), but when I changed this to `matrix.dropna(thresh=8)`, the UMAP result was as follows
    - ![image](https://gyazo.com/cfdedf73e89a82d60ef898acd424606f/thumb/1000)
    - Almost all of the complex shapes were artifacts caused by missing values.
    - Reprinted: [[The opinion vectors of anonymous citizens are not so clearly separated.]]
- Maybe it's like this:.
    - The process of filling in missing values with averages has created a very strong cluster of "people who hardly vote at all".
    - Those who voted properly a lot are scattered in the higher dimensional space, forming a "thin, clear, boundaryless mass".
    - UMAP estimates density using the distance to the k nearest neighbor points, which interferes with the characteristics of the opposite data where the data are discrete and overlap at the same coordinates, and is recognized as "clusters that are denser than they really are", and UMAP attempts to isolate and visualize the characteristic clusters.
- I have not been able to verify it thoroughly, but once I decided that the discrete value opposite vector is not suitable for UMAP, I put this line of thinking on hold.
    - I discarded all the people with missing values and UMAPed the data for only one map, not the 84 dimensions of the whole map, and I was able to get a better idea.
        - ![image](https://gyazo.com/757f3430e3b2aec806bc9a31117dc920/thumb/1000)

    - This also supports the hypothesis that "the lack of cluster separation is not a phenomenon caused by an increase in the number of voting users, but by the opinion space becoming more dimensional as users contribute new opinions" for the negative observation in [[Problem with two Polis clusters]]. Support.



New project (to be announced on 11/22 → [[Shin Tokyo 2050 Broad Listening]])
- This is an analysis for embedded vectors of natural language
- I found the characteristics of the data distribution to be important, so I examined them with similar data.
        - [[distribution of text-embedded vectors]]
        - Argument 7574 extracted by Talk to the City extruction from the 18129 retrieved from X
        - Embedded in [[text-embedding-3-large]], 3072 dimensions
        - A single mass of nearly uniform distance with some dark areas in places.
            - Conceptual drawing: [[One lump with small grains]].
                - ![image](https://gyazo.com/3f553409f14a1b3dd040101a7c102a6d/thumb/1000)
    - [[Clustering and Partitioning]]
    - The "where do we draw the line" question I mentioned earlier.
        - ![image](https://gyazo.com/80377b55bf03bd7d9ff2cae6ff49cc34/thumb/1000)
        - If you have a density distribution with nothing in between the density peaks like the one on the left, you don't have to worry about clustering.
        - Real world data has no clear boundary because the data is also between density peaks, as shown on the right.
    - Traditional "[[clustering]]" such as [[K-means]] attempts to "split" the data set
        - That "division" (partition) is called a cluster.
        - ![image](https://gyazo.com/a68806e0a41cf35ff092174d3580ce7f/thumb/1000)
        - Even data that are quite far from the peak of A, such as X, separated by a thin density zone, would be considered a "cluster of A".
        - The DBSCAN authors saw this as a problem.
        - What is a "cluster" anyway?
    - The concept of "clusters" redefined by the authors of DBSCAN
        - A cluster is an area where data points are densely distributed."
            - > a cluster is defined to be a set of density-connected points which is maximal wrt. density-reachability.
        - ![image](https://gyazo.com/e5281054f0acd540ae656eebb2362ad7/thumb/1000)
            - The idea that a cluster is just a region of data points above a certain density, and X is noise that does not belong to any cluster.
        - To distinguish between these two ways of thinking about clustering, they refer to the former as "partitioning"
- Clustering of opinion vectors using Talk to the City is "partitioning"
    - ![image](https://gyazo.com/c2c76475e5a518a3fe868e76c588a42d/thumb/1000)
            - [[Differences between SpectralClustering and HDBSCAN]]
        - Spectral Clustering is used by Talk to the City for visualization purposes.
        - HDBSCAN is "Hierarchical DBSCAN
        - While watching the discussion in [[Nittele NEWS x 2024 House of Representatives Election x Broad Listening]], I wondered, "Wouldn't it be better to cut out the high-density parts and discard them as "X is low-density data" so that downstream "generation of [[AI-based cluster commentary]]," etc. would work better." I was thinking.
    - Then I learned about DBSCAN and other issues and thought, well, it's the same thing!



[Deep Cluster Extraction
- Now that I understand DBSCAN/HDBSCAN a little better, I decided to use that policy to tweak the Talk to the City algorithm.
    - Experiment log: [[pTTTC2024-11-12]].
- Argument 7574 extracted by Talk to the City extruction from the 18129 retrieved from X
- Embedded in [[text-embedding-3-large]], 3072 dimensions
- From here, we extracted the densely populated areas with HDBSCAN(min_cluster_size=5, max_cluster_size=30, min_samples=2) and obtained 79
    - This setting is intended to pick up a lot of fine clusters
    - Visually, it became, "It's definitely dense content."
- 739 data used for the cluster, 9.8% coverage
    - Judgment that 90% is noise
    - Sometimes we call noise [[the outlier]], but when we say outlier, you'd think it's relatively small.
- This approach has advantages and disadvantages compared to the current TTTC
- The current TTTC, which shows the whole picture with scatter plots and forced clustering, is well suited to satisfy the desire [[Let's start with the broad strokes...]] [[I want to get the whole picture...]].
    - During the gubernatorial campaign, it was like they'd shut up and show it to the people across the net OR the policy team would read it and refer to it.
        - Some policy team members suggested that another method [[Talk to the City Turbo]] was more in-depth and helpful (N=1).
        - [[Nittele NEWS x 2024 House of Representatives Election x Broad Listening]] needed to provide "commentary" for viewers
        - The process clarified the need to not only present the big picture, but also to "dig deeper into deep opinions.
            - In this process, the current TTTC can only show N=1 by "mouse hovering over a point".
            - Also, there is a lack of support in that "finding an opinion to focus on" area.
                - You just look at a few at random and leave it up to luck.
                - You end up looking at all 7,000 cases.
        - The new method we have developed will improve this area.
            - Reduce the burden of "looking at 79 clusters with high concentration instead of looking at all 7,000 cases."
            - Increased persuasiveness by being able to present as "N=5~30 opinions instead of N=1".
- We applied this algorithm to the data in [[TTTC: Public Comments on AI and Copyright]], which can be made publicly available.
    - [https://github.com/nishio/ai_kj/blob/main/dense_cluster_extruction.ipynb](https://github.com/nishio/ai_kj/blob/main/dense_cluster_extruction.ipynb)
    - 5957 cases 1536 dimensions
    - 48 clusters were extracted
    - We had GPT-4o score the cluster interesting, but that in itself did not yield very interesting results!
        - Well, this may be partly because we haven't taught the AI what the purpose of research is and what kind of things are interesting.
    - It would be more interesting to include a prompt in the output list of clusters to "List clusters that introduce a unique perspective and what is original about them.
        - ![image](https://gyazo.com/6f6d83e0fb6c3fda4c88b197727d82f0/thumb/1000)
    - [ChatGPT log](https://chatgpt.com/share/6735c2e5-5bac-8011-bccc-d8ffd64fd1d9)



Relation to the KJ method
- In the June [[Talk to the City Study Group]], I also wrote about the connection with the [[KJ method]] in the appendix.
    - ![image](https://gyazo.com/973ea9617662cabdccfcf594eff6bb7c/thumb/1000)
        - [[way of thinking]]  p.77
    - > In his mind, he has a dogmatic principle of grouping, such as, "In my opinion, it is correct to divide this paper material into three major categories: market research, quality control, and labor management. They are simply applying this dogmatic classification scheme and sifting and fitting the paper materials into a ready-made framework. This is a mere sifting and fitting of paper materials into the ready-made wakku, which completely defeats the conceptual significance of the KJ method.
        - [[Jiro Kawakita]] criticized human beings for sieving, fitting into [* dogmatic classification wakugumi
    - As a way to deal with this problem, I proposed the KJ method, which is to look at each piece one by one and attach it to the related pieces.
    - This is [[Agglomerative Hierarchical Clustering]] in data science terms.
    - TTTC avoids "dogmatic human fitting" by having machines, rather than humans, perform the clustering.
- This time, the relationship with the KJ method has become even clearer.
- Clustering in the sense of "partitioning" has split the data set top-down.
- Extracting clusters with high concentration using a method like DBSCAN is almost equal to "collecting related things to form a group" in the KJ method
- Leaving things that don't fit well in a cluster without putting them in a cluster is the same as the KJ method "[[leave monkey]] away".
    - It is not KJ legal to say that 90% of the data will be away monkeys.
    - This phenomenon is caused by the fact that this method defines "proximity" as "distance in the embedded vector space.
    - When humans do the KJ method, they are asked to find connections between things that do not seem to be connected and group them together, and they "discover relationships" such as "This X and Y do not seem to be connected at first glance, but they are related on [[side]] A.
        - So this is finding another meaning of "nearness" by performing an additional operation on something that is "far" in the sense of "cosine distance in the embedded vector space".
        - I think the reason why the KJ method causes the promotion of ideas as a "way of thinking" or "intellectual production technique" is because it forces people to do this "search for relationships.
    - How can a machine search for relationships that are not expressed in the distance of the embedding vector?
        - In my book "[[Natural Language Processing with word2vec]], [Similarity of concepts is not distance.
        - In this case, it may be possible to deal with the problem by randomly collapsing axes, or by collapsing axes with low contribution rate by PCA, or by collapsing axes with the closest contribution rate by reversing the idea (future experiment).
        - If you'd rather get into the LLM context, you could let LLMs "discover relationships" just like humans.
            - I think it's good to chop it down to an amount that will fit into the LLM context.
            - Because there is a limit to the number of labels that can fit in the human field of vision.
- KJ legal never throws away one of the away monkeys.
    - In order to achieve this, we need to figure out how to merge the separate monkeys into a cluster.
    - Maybe on a mere distance basis it would "move, but not with good results".
    - Need to experiment to see if I can prompt the LLM to do it.
- The KJ method is a technique that requires a great deal of skill to begin with, and Jiro Kawakita, the world's most experienced KJ methodner, says "[[50 KJ method assumes 10 hours]]" and has done only 129 KJ sheets in 5 years because it takes too much time. I felt that the time was approaching when AI would make it an easy method.

---
This page is auto-translated from [/nishio/高次元データ分析勉強会](https://scrapbox.io/nishio/高次元データ分析勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.