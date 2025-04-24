---
title: "Birdwatch"
---

Twitter's [[Community Notes]] algorithm

[[Birdwatch: Crowd Wisdom and Bridging Algorithms can Inform Understanding and Reduce the Spread of Misinformation]]
> We present an approach for selecting objectively informative and subjectively helpful annotations to social media posts. We draw on data from on an online environment where contributors annotate misinformation and simultaneously rate the contributions of others. Our algorithm uses a matrix-factorization (MF) based approach to identify annotations that appeal broadly across heterogeneous user groups - sometimes referred to as "bridging-based ranking." We pair these data with a survey experiment in which individuals are randomly assigned to see annotations to posts. We find that annotations selected by the algorithm improve key indicators compared with overall average and crowd-generated baselines. Further, when deployed on Twitter, people who saw annotations selected through this bridging-based approach were significantly less likely to reshare social media posts than those who did not see the annotations.
- [https://arxiv.org/abs/2210.15723](https://arxiv.org/abs/2210.15723)
- (DeepL)
    - We present an approach to selecting objectively useful and subjectively useful annotations for social media posts.
        - In Japanese, the word has been translated into the same "beneficial," but the word is divided into objective and subjective.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - objectively informative
            - subjectively helpful
    - We exploit data from online environments where posters annotate erroneous information and simultaneously rate other postings. Our algorithm uses a [[matrix decomposition]] (MF)-based approach to identify annotations that have broad appeal to heterogeneous user groups, also called "bridging-based ranking. also known as "bridging-based ranking". #bridging
    - We combine these data with a survey experiment in which individuals were randomly assigned to view annotations to posts. The results show that the annotations selected by the algorithm improve key indicators compared to the overall mean and crowd-generated baseline.
    - Furthermore, when deployed on Twitter, those who saw the annotations selected for this bridging-based approach were significantly less likely to re-share the social media posts than those who did not see the annotations.

The (GPT3) Birdwatch project addresses two primary goals. The first goal is to present high-quality user-generated notes that are objectively informative. For the purposes of this paper, "objectively informative" refers to summary notes that causally improve the reader's understanding of key claims in potentially misleading tweets. The second goal is to present notes that are perceived as useful to a wide range of Twitter users.
- Identifying notes that meet both of these goals is a challenge. For example, a source may be reliable but unhelpful because it is poorly written. They may also use language that is perceived as bias or argumentative. For example, if a note is perceived as offensive or simply difficult to read, one might take this as a signal to ignore the information, rather than consider the information contained in the note.
- Similarly, notes that are weakly sourced and not factual may resonate with people by provoking ideas and assumptions that are taken for granted. For example, a large number of people on Twitter might agree with a misleading or uninformative note and find it useful because it is consistent with their prior beliefs.
- The core challenge for Birdwatch, therefore, is not only to identify notes that are accurate and contain high-quality information, but also to identify notes that are written in a way that will resonate with a broad audience, not just those who are already likely to agree.
- We propose an algorithm that identifies notes that are considered informative and useful based on the user-generated notes themselves and the history of user-generated ratings for each note. Using these inputs, we attempt to overcome two obstacles to our goal. First, rating is a factor that depends not only on the potential characteristics of the notes (e.g., quality, tone, bias, etc.), but also on how the raters react to the notes given each rater's prior beliefs. Second, there is no a priori information about each rater's prior beliefs, the potential characteristics of each note, and how these attributes interact in the process of generating individual ratings. We developed a matrix factorization (MF) method from Birdwatch's rater-note matrix to capture the underlying tendency of raters to rate notes as "helpful" and their "perspective" based on previous ratings of similar notes.

(GPT3) One participatory democracy tool, [[Polis]], clusters the output of matrix factorization to divide users into clusters of opinions, giving priority to content with high common group agreement (consensus among clusters).
- The Birdwatch bridging-based ranking algorithm proposed in this paper uses matrix factorization as a non-taught learning method to construct a representation of the (polarized) opinion space. However, unlike previous approaches, Birdwatch's algorithm does not require clustering users or items into different groups, but rather bridges viewpoints over a continuous space. Another new contribution of our study is the effectiveness of bridging-based scoring as demonstrated by the survey data. It selects memos that are deemed useful for users who self-report different political affiliations over the baseline non-bridging algorithm.

![image](https://gyazo.com/18cee5201c045e55d0459921c964ee26/thumb/1000)

<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>This paper proposes a crowdsourced approach to addressing misinformation on Twitter called Birdwatch.
The main flow is as follows
- First, we built a system in Birdwatch that allows users to annotate (note) tweets containing misinformation and rate other users' annotations.
- Next, we developed an algorithm to evaluate annotation quality, using an approach called Matrix Factorization to identify annotations that are widely supported among users with different political positions.
- To evaluate the performance of the algorithm, the study was divided into two groups: a control group that was shown only the target tweets and an experimental group that was shown the tweets plus selected annotations.
- The results of the experiment showed that the annotations chosen by the algorithm helped users understand and were rated as useful by people from a wide range of political positions. The results were better than simple majority-based selection.
- In addition, showing annotations suppressed the spread of tweets containing misinformation by 25-34%.
- However, the algorithm has some challenges. Resistance to malicious users, performance when scaled up, and other issues require continuous improvement.
- Finally, ethical considerations in pursuing these efforts are discussed.
Overall, the paper presents a new approach to dealing with misinformation by combining the power of the cloud with algorithms.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Explain how to use [[Matrix Factorization]].

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>Matrix Factorization (MF) is a technique for extracting potential user and annotation characteristics from user and annotation evaluation data. In this paper, MF is used to evaluate the quality of Birdwatch's annotations as follows
- Create a user x annotation rating matrix. Each element represents whether or not a user rated a particular annotation as "useful".
- MF is applied to learn a vector representation of each user and annotation. These vectors are expected to capture users' evaluation tendencies and potential annotation characteristics.
- The learned vector is used to compute the "intercept term" for each annotation. This can be interpreted as a measure of the universal quality of the annotation, after excluding the influence of the user's political position and other factors.
- Annotations with an Intercept term above the threshold are considered "Currently Rated Helpful". These annotations are expected to be widely supported among users with different political positions.

The key point of MF is that it allows for more sophisticated annotation evaluation than simple majority voting by extracting potential characteristics of users and annotations. In particular, the use of INTERCEPT TERMS allows for the selection of politically unbiased, high quality annotations.
However, there are some issues in actual application, such as sparse data and countermeasures against malicious users. These points are expected to be improved in future research.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Matrix Factorization, [[matrix decomposition]], I know there are many different types, but what is the nature of the one you are using here?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>In this paper, we use a particular method of matrix decomposition for [[valuation forecasting]]. Specifically, we assume the following model
- $\hat{r}_{un} = \mu + i_u + i_n + f_u \cdot f_n$
where $\hat{r}_{un}$ is the predicted value of user $u$'s rating for annotation $n$, $\mu$ is the overall bias, $i_u$ is the bias representing the rating tendency of user $u$, $i_n$ is the bias representing the general quality of annotation $n$ (intercept term) and $f_u$ and $f_n$ are the latent vectors of user $u$ and annotation $n$, respectively.

This model has the following features
- Bias terms ($\mu, i_u, i_n$) can be introduced to express the individuality of users and annotations.
- By using the inner product of the latent vectors of users and annotations ($f_u \cdot f_n$), [[collaborative filtering]] is achieved. In other words, similar users and annotations can be automatically discovered.
- By focusing on the intercept term ($i_n$) of the annotation, we can evaluate the universal quality of the annotation, independent of the user's personal preferences.
Such models are often used in evaluation prediction tasks such as the Netflix Prize, and are one of the leading methods of collaborative filtering. However, $i_n$ is usually used as an item bias for recommendations, and using it as an indicator of annotation quality, as in this paper, is an unusual use.

As described above, this paper uses MF in the context of valuation forecasting, but applies it to a new problem setting, Birdwatch, by devising an interpretation of $i_n$.





The style of emphasizing information that is supported by people with different tendencies of opinion is also related to [Plural QV

Apps that collect subjectivity and extract useful information from it are also related to the [[sentiment gathering]] aspect of Polis
- Polis' Consensus coefficient calculates the product of the degree of agreement from each cluster of people clustered by opinion vector.
    - That is, a form of unanimity extended to real numbers, not binary.

Also related to Jiro Kawakita's "[[All data is a lie]]"
- Instead of discarding subjective data as "garbage because it's not objective," draw meaning from it by collecting a lot of it.
- In the past, we only used crappy features like "[[total]], [[average]], [[majority rule]]", so it was not useful to collect a lot of subjective data.
    - With the increase in computer performance and the development of [[matrix decomposition]] research, it has become easier to make sense out of higher-dimensional matrices.


Github
- [https://github.com/twitter/communitynotes](https://github.com/twitter/communitynotes)

relevance
- [Hot off the press about what I want you to know about Twitter Comm Note - Yuji Fujii::dot net](https://fujii-yuji.net/2023/twitter/community-notes)
- [How do you rate the new twitter feature "community notes" that annotates tweets? Does it help to prevent hoaxes or provoke sterile discussions? - Togetter](https://togetter.com/li/2182249)


---
This page is auto-translated from [/nishio/Birdwatch](https://scrapbox.io/nishio/Birdwatch) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.