---
title: "Either the performance improvement will be a headache, or the performance will improve endlessly."
---

When "the totality of knowledge that mankind has accumulated in the form of language and other information" is fully learned, will the performance improvement reach a ceiling, or will the performance improve without limit?

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758056342880256) The AI community is boiling over with GPT. No one, including the developers, understands the reason for the rapid performance improvement. Normally I try not to mutter too much about current events that will be old in six months or a year, but the recent developments have been so fast that there is growing uncertainty about the future, so I would like to organize the scenario at the moment a little. (1/15)

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758122210230278) First, let me summarize the current state of the art. Most of the recent achievements are due to the encoder-decoder model called the transformer. It is noteworthy that this has abolished mechanisms that prevent parallel computation, such as convolution and recursion, and thus enables the aggregation of computational power, making it possible to learn on dramatically larger data sets. (2/15)
- [[Transformer]]

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758202300473344) What happened there was [[Discover the scaling rule]] (2020).  ([https://arxiv.org/abs/2001.08361)](https://arxiv.org/abs/2001.08361)) In other words, by simultaneously increasing the computational complexity, data size, and scale of the model, the performance of the model appears to increase without any upper limit. (3/15)arxiv.org
>  Scaling Laws for Neural Language Models
>  We study empirical scaling laws for language model performance on the cross-entropy loss. The loss scales as a power-law with model size, dataset size, and the amount of compute used for training,...

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758313478881280) Furthermore, in 2022, a phenomenon was identified in which the performance improves rapidly after the 23rd to 24th power of 10 times per computation >[ktakahashi74 It is difficult to see what will happen in the future, as we appear to have moved from a somewhat predictable scaling law to a discontinuous takeoff ([https://ai.googleblog.com/2022/11/characterizing-emergent-phenomena](https://ai.googleblog.com/2022/11/characterizing-emergent-phenomena) -in.html...).　(4/15)
> ![image](https://gyazo.com/16a678b84c88c121d2ce0407a9011111/thumb/1000)


> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758476930940928) So back to basics. What machine learning models can do is induction from the data used for training (they can only predict what they have already seen). However, GPT3/4 appears to perform deductive tasks such as flexible response and multi-stage argumentation that seemingly cannot be derived directly from the training data set. There are two possible explanations. (5/15)
- Many people try to classify this as induction or deduction, but it is possible that [[false dichotomy]] is to think of the two as opposites.

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758545738493953) The first is the possibility that most of what we thought was deduction was induction. For example, when we hear the word "zebra" and think of a zebra with stripes, the same type of pattern, in which a certain feature is combined with a certain object to derive another object, was included somewhere in the data set. (6/15)

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758636218028032) Perhaps 24th power FLOPS of 10 is the amount of computation required to extract [[semantic network (AI)]] from the total knowledge accumulated by humans in the form of linguistic information. The threshold has been exceeded and the semantic network has rapidly connected and performance has improved. In this case, it is likely to continue in a sigmoidal manner (a rapid increase followed by a period of stagnation). (7/15

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758697056403456) The second possibility is that, as Kitagawa-san (@takuyakitagawa) and google blogs, the network The second possibility is that emergent (phase-transition-like) phenomena are occurring in the model. In other words, it is possible that the application of computational power is generating new linkages and semantic networks that are not explicitly included in the data set. (8/15)

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758837032906752) Just as various theorems and propositions are created from axiomatic systems in mathematics, new information is created from the information contained in linguistic data. If the human brain has explored only a part of it, this is a scenario where AI may take on a deeper and broader intellectual search in the future. It could be said that the language system itself has the potential to be deductive. (9/15)

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758908919091202) Either of these may become clear in a few more months or a year or two. (10/15)

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637758974140497922) If the first possibility is correct, the amount of training data will eventually be unable to keep up with the growth in computational power and model size, and the performance improvement will reach its ceiling when "the total amount of knowledge that mankind has accumulated in the form of languages and other information" has been learned. If the first possibility is correct, the amount of training data will eventually fail to keep pace with the growth in computational power and model size, and performance improvement will reach its ceiling when the "total body of knowledge that humans have accumulated in the form of language and other information" has been learned. (11/15)

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637759088783409152) If the second possibility is correct, the performance would appear to improve without limit for the time being. In that case, the physical constraints on computational power will be critical, as I have organized the scenario in my 2018 paper, which I have presented several times ( [https://jstage.jst.go.jp/article/jjsai/33/6/33_867/_article/-char/](https://jstage.jst.go.jp/article/jjsai/33/6/33_867/_article/-char/) en/...). (12/15)jstage.jst.go.jp
>  Lecture Series: "Singularity and AI" [[Part 7]] Scenarios and Junctures for Future Machine Intelligence
>  Artificial Intelligence, 2018 vol. 33, no. 6 p. 867-872

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637759157146365952) Current language model-based AI is limited in that it lacks active and physical features, but there are various research efforts to develop a mechanism to allow machine learning models to use tools and sensors. However, research on mechanisms to make machine learning models master tools and sensors (cognitive architecture) is being undertaken in various places. (13/15)
    - [[active (bio-medical contexts)]]

> [ktakahashi74](https://twitter.com/ktakahashi74/status/1637759270791049216) Since there is no fundamental technological barrier to the development of AI that uses robots, net tools, etc. to perform active learning, then, theoretically, " totality of mankind's knowledge to date" would no longer be a reason to set an upper limit, and only the time constant of physical phenomena would remain as a limitation (see the above paper). This would be related to a scenario bifurcation looking further ahead. (14/15)



---
This page is auto-translated from [/nishio/性能向上が頭打ちになるか、際限なく性能が向上するか](https://scrapbox.io/nishio/性能向上が頭打ちになるか、際限なく性能が向上するか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.