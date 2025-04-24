---
title: "Talk to the City Study Group"
---

2024-06-14 [[Cybozu Labs Study Session]] Lecture Presentation by Yasukazu Nishio
- I'd like to add my verbal questions, but I'm busy and behind.

Shift to the past
- After [[Plurality Tokyo]] on 2023-04-12, I became interested in [[Plurality]], especially [[broad listening]], and talked about its elemental technology, [[Polis]], in a study group.
        - [[Plurality and Polis Study Group]] (2023-05-12)
        - [[Polis Study Group]] (2023-06-23)
- I was interested in the system introduced by [[Audrey Tang]] in [[Plurality Seoul]] on 2023-12-02, and asked [[Gisele Chou]] about it, and he told me it was [[Talk to the City]].
    - I met [[Deger Turan]] of [[AI Objectives Institute]] who is developing this on 2024-05-15, talked a bit, and wanted to give it a try!
    - On 2024-05-31, 5957 opinions for 2013 people were extracted and tested using data from the Agency for Cultural Affairs' [[Public Comment on AI and Copyright]].
        - ![image](https://pbs.twimg.com/media/GO39erpaEAAGVXM?format=jpg&name=medium#.png)
    - The main story of this Talk to the City (TTTC)



current topics
- 2024-06-06  [[Takahiro Yasuno to run for Governor of Tokyo]]
    - > In the past, the election period has been a time to "broadcast the candidate's views," that is, to tell voters what the candidate thinks one way or the other. I believe that this time around we can use technology to make it a period where people's opinions are heard. In the world of digital democracy, we call this "[broad listening". Through this broad listening, I would like to make the election period a time for everyone to think about ideal policies.
    - [[My number card]] to verify your identity and achieve one-person, one-vote voting.
        - > [[Direct voting]] results to capture the will of the people with a high resolution.
    - and
        - > All programs used in these campaigns will be released as [[open source (software, etc.)]] after the election
            - [[digital public goods]]
    - [[Audrey Tang]] also commented
        - > "I like the way Mr. Anno combines broad listening, the my number system, and the open source spirit."
        - >  "Mr. Anno is not protesting. I like that very much. He is saying, 'We can change for the better'."
- impressions
    - > [golden_lucky](https://x.com/golden_lucky/status/1798982636616196255) Plurality, I didn't expect it to be a realistic option so soon in Japan.
    - > [nishio](https://x.com/nishio/status/1800054514420224503) Really that()
    - When I first learned about the concept of broad listening, I thought this was a technique that would allow me to "hear the multitude of opinions" at a level that was impossible for a live person.
    - So I thought it was a kind of [[human enhancement]] or [[increased intellectual productivity]].
    - With the future development of LLM, the cost of realization will come down and it will become an "easy-to-use technology" in a few years, and in 5 or 10 years, it will be a technology that cannot be ignored by groupware companies like Cybozu.
    - 〜I had been thinking that the time span of the world would be about 1.5 to 2 years, but to come this far in one year, the world is changing at a rapid pace! That's how I feel.
    - [[Talk to the City for Governor]]
    - > [takahiroanno](https://x.com/takahiroanno/status/1800374247984107736) Public tweets about #TOKYOAI will be crawled via API and visualized using LLM, [[Talk to the city]], etc. We will try to visualize them using LLM, [[Talk to the city]], etc.
    - I'm helping!



- Review of [broad listening
- ![image](https://gyazo.com/8aed1a6ee239c672d1e504cdb48d0e9e/thumb/1000)
    - Figure from "[Not subjective or objective, but from the subjectivity of one to the subjectivity of many.
- explanation
    - The development of technology to duplicate and distribute information has made it easier for one person to communicate ideas to a large number of people.
    - However, when a large number of people transmit information, the volume of information received by one person becomes enormous, and the person drowns in the flood of information.
    - In a society and company where people actively communicate, technology that supports listening to the opinions of many will be important.
- Technical
    - This is a kind of "summary" in the broadest sense
    - But in LLM training, the "summary task" is trained with training data, such as putting in the text of the paper and taking out the abstract portion.
    - This assumes "a well-formed sentence written by one person" as input.
    - Summarizing techniques are needed for "a set of sentences written by many people, each with his or her own writing style."
    - Trial and error on how to do that is taking place.
- digression
- Haruyuki Seki of Code for Japan gave a keynote presentation titled "[[Updating Society and Democracy through Civic Tech]]" at the Organized Session "AI and Democracy" of the 2024 National Conference on Artificial Intelligence on 2024-05-31. The presentation was titled "Updating Society and Democracy through Civic Tech".
    - ![image](https://gyazo.com/6ba0de3971710aa53717ccf0cee66be9/thumb/1000)
    - ![image](https://gyazo.com/48c12e0903a8841a6eb3b512bd451ce5/thumb/1000)
    - My [[Hand drawn diagram]] suddenly appears on a beautiful slide.
    - (I wonder if someone could make a cleaned up version of this in CC0 or something...)
    - (I have given permission to Mr. Seki to use the images in Scrapbox as he likes.)



Review of [Polis
- ![image](https://gyazo.com/c482df2fe3d92e75422add645a647d78/thumb/1000)
    - [[Polis: Scaling Deliberation by Mapping High Dimensional Opinion Spaces]]
    - [Polis | The Computational Democracy Project](https://compdemocracy.org/Polis/)
- Opinion vectors are "agree (+1)", "disagree (-1)", and "don't know/neutral (0)" to the text.
- This vector is clustered, and the sentences and other information that caused the clusters to separate are displayed.
- What we actually did
        - [[Polis Experience Report: Should Same-Sex Marriage Be Legalized?]]
    - ![image](https://gyazo.com/cd1644cee2b1fc42b56518d6e65d55ec/thumb/1000)
    - Found a higher percentage of sentences in favor of legalization (73%) than in favor of legalization (73%).
    - Example: Marriage as social proof and marriage as taxation/social security have their own issues to be considered in different layers. : 74% in favor, 11% opposed, 13% neutral
    - 86% in Cluster A, where most people are against same-sex marriage, and 69% in Cluster B, where all are in favor of same-sex marriage, both majorities.
    - In other words, in order to resolve this "pro-same-sex marriage" conflict, it would be better to first proceed along the lines of "let's separate social proof from financial social security," which both sides have agreed to do.
    - Incidentally, [[Same-sex marriages in Taiwan are not kinship.]]
        - It is clear that many opponents of same-sex marriage are not opposed to same-sex marriage per se, but rather feel, for example, that "if my son marries a man and my son is happy, that is acceptable," "but I am not sure about this 'male spouse of my son,' so I am not comfortable making him a member of my family. (p. 3)
- Visualization and analysis allow us to observe the conflict composition from a different angle.
- Polis is used in [[vTaiwan]] in 2015.
    - vTaiwan is an online platform established by the Taiwanese government to promote citizen participation
    - Primarily used as a forum for gathering public input and debate on public policy and legislation
    - Keywords: [[open government]] and [[digital democracy]], [[transparency]] and [[participatory democracy]]
- It's from 2015, so no LLM or other AI-like features.
    - The basic idea is to vote for or against the text.
    - The text itself can be set up to post as well.
        - Audrey Tang thinks this is good: [[Open up agenda-setting authority to people]].
    - But there will be problems such as too many sentences and the people voting will get tired, or the sentences will be full of similar content, or the meaning of the sentences will be unclear.
        - [[moderation]] issue
        - [Moderation | The Computational Democracy Project](https://compdemocracy.org/Moderation)
                - [[Polis Moderation]]


What is Talk to the City?
- > Audrey Tang (summary): In 2014 it was impossible to gather the opinions of so many people and retain all the nuances, but now, thanks to the "Talk to the City" tool, it is very easy and inexpensive to do so.
    - Original: [Talk to the City - AI - Objectives - Institute](https://ai.objectives.institute/talk-to-the-city)
    - Translation and summary: [[Audrey Tang's comments on AOI's TTTC page.]]
- Talk to the City is an open source analysis tool developed by the [[AI Objectives Institute]] (AOI)
    - Purpose of the tool: Improve [[collective discussion]]/[collective decision-making
        - Designed to facilitate dialogue with communities, especially cities
    - Collect and analyze Twitter tweets, Polis results, etc.
    - Visualize clusters of opinions and arguments and generate commentary for each cluster
    - This helps people get a fuller picture of the comment distribution and promotes constructive dialogue
- What is [[AI Objectives Institute]]?
    - A non-profit organization founded in 2021 by Peter Eckersley ([Peter Eckersley](https://en.wikipedia.org/wiki/Peter_Eckersley_(computer_scientist))), to guide the direction of AI development toward human flourishing The purpose of the organization is to guide the direction of AI development toward the prosperity of mankind.
    - [[Peter Eckersley]] is an Australian computer scientist and computer security researcher, who has worked for the [[Electronic Frontier Foundation]] (EFF) and launched projects such as "[[Let's Encrypt]]", "[[Certbot]]", and "[[Privacy Badger]]" and other projects.
        - [Let's Encrypt](https://letsencrypt.org/) is a high-profile project that aims to improve security and privacy across the Web
        - Cybozu has also donated to this project for 6 years: [Open Source Software | Cybozu Tech](https://tech.cybozu.io/oss/)
    - Peter Eckersley unfortunately passed away in 2022, and his colleagues [[Deger Turan]] and [[Brittney Gallagher]] are taking over AOI's activities, led by their colleagues.



How Talk to the City works technically
- Unlike Polis, input is text data
    - So if you have text data, you can use it for anything.
    - Utilize a variety of data sources, not only Polis, but also Twitter, Google Forms, comment sections of news articles, groupware, etc.
    - As an outlandish experiment, I included each paragraph of the book:.
            - [[Visualize the contents of the Plurality book with Talk to the City]]
        - Useful or not, technically possible.
- Use LLM to extract concise, readable messages for input text
    - Obtained in JSON list format, so multiple messages may be extracted for a single input.
    - The default is GPT-3.5-turbo with Few-shots as an example.
- Cluster this set of messages with [BERTopic
    - (2022) [[BERTopic: Neural topic modeling with a class-based TF-IDF]]
        - First, embed documents into high-dimensional vectors in the language model
        - [[UMAP]] (Uniform Manifold Approximation and Projection) projection to low-dimensional space
        - Hierarchical clustering with [[HDBSCAN]](Hierarchical Density-Based Spatial Clustering of Applications with Noise)
- Visualization by dropping into 2D space with UMAP
- TF-IDF, which considers a cluster as a document, and identifies keywords that characterize the cluster.
- LLM generates cluster commentary



Let's see it in action
- 2024-06-12 The first part of the report was published!
    - > [takahiroanno](https://x.com/takahiroanno/status/1800734598344925656) We extracted comments on the runoff announcement and created an AI-based analysis report.
    - >  I now have a more concrete picture of where your interests and concerns about me lie. We will also use data and AI to face the thoughts and feelings of the people of Tokyo!
        - [People's reactions and issues regarding Takahiro Yasuno's run for Governor](https://takahiroanno2024.github.io/yahoo-comment-analysis-20240610/)
    - > [takahiroanno](https://x.com/takahiroanno/status/1800734887290577198) Listening to people's opinions through the use of technology is called "broad listening" in the world of digital democracy. As a concrete example, we have created this analysis report. We will continue to update this report and listen to your opinions!
- ![image](https://gyazo.com/8d2af6ecf7cbfb9190301b04f4ef88b4/thumb/1000)



Polis 2.0
- Idea proposed by Audrey Tang
    - It's like a development code name that has never been officially announced.
    - (Confirmed by [[mashbean]], MODA, Ministry of Digital Development, Taiwan)
- Create clusters in TTTC from Polis data
- Allow chat with virtual opinion leaders generated from that cluster
- ![image](https://gyazo.com/f4340548f38ff6bc2c43958a01d63a39/thumb/1000)
    - from  [[Polis 2.0: forging ahead with a critical review]]  by [[mashbean]]
- This is what Audrey was talking about in [Plurality Seoul
    - ![image](https://gyazo.com/70ef859c94406820a5a8a4da5b6a3c5e/thumb/1000)
    - >  For many participants, this is the first time interacting with AI in the context of [[careful deliberation]].
    - >  In other words, instead of talking to the AI alone, we are discussing it as a group for the benefit of all.
    - >  With this augmented deliberation, everyone can contribute to and benefit from digital democracy.
    - >  Increased deliberation increases the [[resilience]] (ability to overcome difficulties) of a society.
    - >  Because it deepens understanding and empathy for different cultures and integrates information in a consistent manner.
    - >  This discussion platform is designed as an [[open source (software, etc.)]] tool.
- This "augmented deliberation" is very interesting from the perspective of my interest in increasing intellectual productivity!
    - but not very exciting.
    - The reason for this is probably
        - People are not used to a situation where the person they are talking to is a "cluster" with no characterization.
        - I'm unfamiliar with this form of communication, so I want to see what others are doing first.
        - Even if you can see other people's interactions, you can't meet other people unless you get a certain number of people together.
- It would be interesting to see Yasuno's measures from that perspective.
    - > AI Town Meeting on YouTube Live --- [Full text of press conference by engineer and author announcing his candidacy for Governor of Tokyo｜Takahiro Yasuno](https://note.com/takahiroanno/n/nead5c2e2454b)
    - Using the already existing communication format of "interaction between VTuber and viewer".
    - Viewers can start by watching others interact with each other, and the archive will remain as a YouTube feature.
    - Characterization as a candidate for Governor of Tokyo
- In terms of candidates for governor of Tokyo.
    - A flesh and blood person can only use a portion of the 24 hours in a day.
        - Communicate with voters who could physically come there by standing in front of the station or
        - The content of communication is clouded.
    - A digital person (virtual personality) can remain active 24 hours a day.
        - You can stay on a specific YouTube channel all the time and access and communicate from anywhere in the world.
        - The content of the communication is preserved.
            - This means that comments made on YouTube Live can be included in TTTC's analysis.
- I'm thinking it's a good idea.



[[interactive mass communication]].
- In one-on-one communication, I say things like, "Don't just talk one way, listen to what the other person is saying," and "Since we have one mouth and two ears, we should be willing to listen twice as much.
- However, in conventional mass communication via TV, newspapers, etc., a large number of viewers only receive what is transmitted one way.
- The reason why this happened is because the technology to duplicate and deliver information to a large number of people developed faster than the technology to summarize information.
- ![image](https://gyazo.com/8aed1a6ee239c672d1e504cdb48d0e9e/thumb/1000)

- It is difficult to generalize, since various technologies spread at different rates, but one example is Germany's [[national radio (esp. an NHK radio station)]], which reached 70% of the population in 1939.
- Over the last 100 years, viewers accustomed to [[one-way mass communication]] have become less confident that it's okay to speak up and that there are people who will listen.
- First, we launch "[[Attitude of listening]]" and collect comments, visualize them and show "this is what happened as a result of listening to your voices", and then people who see them update their perception and write better comments to ...... By repeating this cycle, better "interactive mass communication" will be realized.
- ![image](https://gyazo.com/c993101b5fb2bc34d642d7f880a9ad7a/thumb/1000)
    - from  [[Polis 2.0: forging ahead with a critical review]]  by [[mashbean]]
        - > <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Formation of a feedback loop allows automatic generation of seed opinions and expansion of the Polis database
    - There are various ways of expression, but the direction of "making mass communication bidirectional by repeating the cycle" is being sought in many parts of the world.
    - As Audrey Tang says, "[[Digital natives]] don't think that once-every-four-years upload bandwidth is enough."
        - It is important to increase upload bandwidth.
- The image of a [[snowball]] that rolls and gets bigger and bigger.



summary
- In this workshop, [[broad listening]], [[Polis]], [[Talk to the City]], and [[Polis 2.0]] were explained and the future direction of interactive mass communication was explained.
    - [[digital democracy]], Takahiro Yasuno's campaign for governor of Tokyo utilizes the concept of broad listening to listen to the voices of a large number of voters.
    - Interactive communication strategies utilizing YouTube have the potential to transform traditional one-way mass communication.
    - This campaign will raise the profile of broad listening in Japan, and if it is shown that many voters consider it important, other politicians will embrace broad listening.
- Polis and Talk to the City are both copylefted, open source (AGPL) tools that become more sophisticated the more people use them.
    - Technological developments make it possible to efficiently aggregate the opinions of large numbers of people and promote constructive dialogue.
    - Through these efforts, more people will be able to participate in the democratic process and contribute to social decision-making.
- The interactive nature of mass communication is gradually approaching realization through repeated feedback loops.
    - Just as a snowball grows as it rolls, we hope that these efforts will accumulate and lead to the realization of a better society.



Aside: I'll write when I have room.
- Analogy with KJ method
- ![image](https://gyazo.com/973ea9617662cabdccfcf594eff6bb7c/thumb/1000)
    - [[way of thinking]]  p.77
- > In his mind, he has a dogmatic principle of grouping, such as, "In my opinion, it is correct to divide this paper material into three major categories: market research, quality control, and labor management. They are simply applying this dogmatic classification scheme and sifting and fitting the paper materials into a ready-made framework. This is a mere sifting and fitting of paper materials into the ready-made wakku, which completely defeats the conceptual significance of the KJ method.
    - [[Jiro Kawakita]] criticized human beings for sieving, fitting into [* dogmatic classification wakugumi
- As a way to deal with this problem, I proposed the KJ method, which is to look at each piece one by one and attach it to the related pieces.
- This is [[Agglomerative Hierarchical Clustering]] in data science terms.
- TTTC avoids "dogmatic human fitting" by having machines, rather than humans, perform the clustering.
- I think it's an easy way to get some of the benefits of the KJ method.
- Replace the KJ method in its entirety?
    - Skin feeling that it is not.
    - For the moment, "proximity" is "cosine distance in the embedded vector space".
    - I suspect this is where the human KJ method differs from the human KJ method, but it's not really different, and humans may be processing it in a similar way.
    - I think it would be more linguistic to compare a human doing KJ method and TTTC for the same data, future research.
    - Analogy with [U-theory
    - ![image](https://gyazo.com/4af6ff261bf5d9399b1a3158120c28c6/thumb/1000)
        - 1: Stuck inside the frame
        - 2: Look outside the box
        - 3: The frame you originally had fades away with outside perspectives.
        - 4: Gathering perspectives from outside the company creates "understanding from a number of perspectives.
    - TTTC seems to be a system that encourages people to move to level 3~4

---
This page is auto-translated from [/nishio/Talk to the City勉強会](https://scrapbox.io/nishio/Talk to the City勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.