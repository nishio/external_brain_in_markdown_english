---
title: "Polis Experience Report: Should we investigate the causes of terrorism?"
---

2023-04-26
In April 2023, a bomb attack on the prime minister occurred in Japan.
- [24-year-old man arrested over explosion at prime minister Kishida speech site | NHK WORLD-JAPAN News](https://www3.nhk.or.jp/nhkworld/en/news/20230415_15/)
- This sparked a Twitter storm of opinions, some saying that the cause of the attack should be investigated, and others disagreeing with that.
- The author has prepared a [[Polis]] on this issue
- Seed opinions were prepared in Japanese and spread through Twitter in Japanese.
- In the end, 460 people participated in the voting, casting a total of 16,779 votes.
- Polis' visualization algorithm divided the voters into two groups
    - ![image](https://gyazo.com/7853f222914978d8b8d35538386092d1/thumb/1000)![image](https://gyazo.com/f4d1be2e1f809a8af526250551a4eda0/thumb/1000)
    - Detailed report: [https://pol.is/report/r3p4ryckema3wfitndk6m](https://pol.is/report/r3p4ryckema3wfitndk6m)
- In the course of the experiment, there was an interesting discussion about the swing of meaning

# Commonly supported opinion
.
First, we will focus on opinions commonly supported by both groups.
- The discussion of why they did such a thing and whether such a thing is right or wrong are two completely different dimensions," was supported by 91% of respondents.
- Eighty-six percent disagree with the statement, "For example, exploring why violent teachers commit violence is tantamount to justifying violence."
- The 90% agreed that "If there were issues that were first recognized by the majority due to terrorism, we should consider whether such issues could not have been siphoned off through channels other than terrorism, and the mechanism should be considered," suggesting a Next Action.
- ![image](https://gyazo.com/76de07329115ab0842a8fdf00aa51d8f/thumb/1000)
    - Trying to determine the causes of terrorism is an affirmation of terrorism: No 85%.
    - If an unwanted social phenomenon is occurring, it is natural to explore its causes and set issues: Yes 85%.
    - Do not investigate the motives of terrorists: No 84%.
    - It was a mistake to address the issue of the second generation religious because former Prime Minister Abe is dead: No 75%.
    - If there is a problem, it should be fixed sooner rather than later: Yes 88%.
    - If there were issues that were first recognized by the majority due to terrorism, we should consider whether such issues could not have been absorbed through channels other than terrorism and the mechanism should be considered: Yes 90%.
    - Knowing why you did it is one thing, but knowing why you did it and debating whether it is right or wrong are two completely different dimensions: Yes 91%.
    - Sharing the collective experience of "why people commit crimes" is as necessary for community safety as properly punishing criminals. Yes: 89% Yes
    - For example, exploring why a violent teacher did violence is tantamount to justifying violence: No 86%.
    - Secret trials are unavoidable in terrorism cases: No 80%.

impressions<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Now that the voting is over, when you look at the nearly 90% support from all of these opinions, it feels as if it was the obvious opinion all along.
- But I think it's [[hindsight bias]].

# disagreement between opinion groups
.
Now let's see what the two opinion groups A/B disagree about
- Example: Determining causes and motivations and eliminating them is an effective way to reduce terrorism: A Yes 81% / B No 57
    - ![image](https://gyazo.com/613eea3f75757cc21a8eee0a01b53a59/thumb/1000)
- I'll list the details below, but it's hard to read meaning into it, so let's first look at the results of telling GPT-4 to "explain the difference between the opinions of A and B"
    - Brief summary:.
        - <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/> A supports an approach that addresses the root causes of terrorism and considers the circumstances of both perpetrators and victims. On the other hand, B supports an approach that addresses terrorism from the standpoint of protecting democracy, with an emphasis on strengthening state power and ignoring the claims of terrorists.
    - <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>The differences between the opinions of A and B have much to do with their approach to terrorism and their assessment of its consequences. The following is a summary of the differences in their respective opinions.
        - 1: The concept of investigating the causes and motives of terrorism:.
            - A believes that investigating and resolving the causes and motives is the way to effectively reduce terrorism. On the other hand, B disagrees and argues that it is better to strengthen state power without confronting the causes and motives.
        - 2: Concerns about how to deal with terrorism:.
            - A is concerned that not confronting the causes of terrorism may lead to a second or third incident. However, B believes that democracy will be defeated by violence if we affirm that terrorism is the catalyst to improve society.
        - 3: Assessment of the terrorist's claims and background:.
            - A argues that the circumstances of the perpetrator should also be considered. On the other hand, B argues that to ignore the claims and background of the person who committed the attack and to investigate the cause of the attack would be to affirm terrorism.
        - 4: Terrorism Risk Assessment:.
            - While A believes that there is a risk of future terrorism that can be lowered by the resolution of the former Unification Church issue, B argues that there is a greater risk of future terrorism that can be increased by a successful terrorist attack.
        - 5: Views on victim responsibility:.
            - A believes that the person who was terrorized may have been responsible for the attack, whereas B clearly denies it.
        - These differences indicate that A supports an approach that addresses the root causes of terrorism and considers the circumstances of both perpetrators and victims. On the other hand, it can be said that B supports an approach to dealing with terrorism from the standpoint of protecting democracy, with an emphasis on strengthening state power and ignoring the claims of terrorists.
- ![image](https://gyazo.com/2f65a7e9e32cfd2418906740b0940fc0/thumb/1000)
- Determining causes and motivations and eliminating them is an effective way to reduce terrorism: A Yes 81% / B No 57
- It is dangerous to strengthen state power to crack down on terrorism without confronting its causes and motivations: A Yes 83% / B No 52
- Not working to solve the problem because the trigger is terrorism may lead to a second or third incident: A Yes 91% / B No 43
- When a person commits a terrorist attack, there is not a single regard for that person's claims or background. There is no social approach that can be derived from this. A No 87% / B Yes 58%
- Attempting to determine the causes of terrorism is an affirmation of terrorism: A No 96% Yes 1% / B No 59% Yes 25
- The risk of future terrorism increased by successful terrorism is much greater than the risk of future terrorism decreased by solving the former Unification Church problem: A No 44% / B Yes 79
- If we affirm that we can improve society in the wake of terrorism, democracy will be defeated by violence: A No 51% / B Yes 80
- The perpetrator's situation should also be considered: A Yes 48% / B No 78
- The person who was attacked is also responsible: A Pass 39% / B No 93

impressions<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Summarizing disagreements is emotionally taxing for humans because any summary may be claimed to be "maliciously distorted"
- LLMs make it easy to get a summary of opinions.
    - But of course that's assuming the LLM doesn't distort their opinions.
    - LLM distorts opinions on some topics.
    - This is due to the fact that AI is being trained with good intentions not to say things that are unethical for humanity today, and Nishio fears that this could be an example of "[[The road to hell is paved with good intentions."]]" but I'm not sure that this is an example of Polis' story. Not really relevant, so let's stop talking about this.
- It was a bit of a pain to get the Polis output into a suitable form to give to the GPT-4. I think writing a program to convert it or making some modifications on the Polis side will help to make a better connection.
- In summarizing the "For, Against, Pass, Not Voting" values in the detailed report, we decided to include the largest value among the "For, Against, Pass, Not Voting" values.
    - Most of the time that's fine, but there were a few exceptional cases.
    - In some cases, "the majority of both groups were against it."
        - Example: Attempting to determine the cause of terrorism is an endorsement of terrorism: A No 96% Yes 1% / B No 59% Yes 25
        - ![image](https://gyazo.com/33d4c7df8639c922217308a91066b704/thumb/1000)
    - Majority pass on one side, 93% No on the other.
        - Example: the person who was terrorized has a cause.
            - A: Yes 25% No 34% Pass 39%
            - B: Yes 1% No 93% Pass 5%
        - ![image](https://gyazo.com/757a4830761317fa7b2b3b95b6ab9691/thumb/1000)
    - Hard to understand when expressed in text, but not so with a graphical representation.
        - A good graphical representation in a textual medium might be a good idea.
        - A: 🟩🟩🟩🟥🟥🟥⬜⬜⬜ v.s. B: 🟥🟥🟥🟥🟥🟥🟥🟥🟥🟥

# Discussion on semantic swing
.
In the course of this experiment, there was an interesting discussion about [[semantic swing]].

In the early stages, opinion groups were visualized in this way
- "Trying to determine the causes of terrorism is an affirmation of terrorism."
    - ![image](https://gyazo.com/baeffd885fb442a7a60af8ee48e1564e/thumb/1000)
- Most agreed with the statement, "Do not affirm terrorism." However, the opinion groups differed as to whether they considered "affirming terrorism" and "investigating the causes of terrorism" to be the same or different

Tweet from the author after observing this phenomenon
- > [@nishio](https://twitter.com/nishio/status/1647675305350537217?s=20): ... There's the issue of "ambiguity in the meaning of a word." In this case, the meaning of "affirmation" is clearly shaky.
- >  and until now, I wondered if the discrepancy in the meanings of the words would make it impossible to reach a consensus.
- > ... The meaning of a word is not a point, but a distribution, and as you repeatedly take actions for and against the same short sentence and visualize how it compares to the world's opinions, you will gradually come to align with the same distribution...
- Opinions on Polis are expressed in short sentences. This has the advantage of reducing the cost of reading. On the other hand, however, we were concerned that the lack of words might lead to a swing in interpretation.
- In fact, the shaking of the interpretation itself is visualized by Polis, and the less shaky ones crystallize after the fact. So I realized that there is no need to worry.
    - Opinions that are shaky in interpretation or don't make sense sink, and the list of majority opinions is what everyone agrees on, so you don't have to worry about it from the get-go.
    - It is a problem that such "poor quality opinions" are also presented to newcomers for voting: [[Problem of too many Polis questions]].
- The author feels that it is a natural observation from his experience with Clean Language, a coaching technique, that "the same word can mean different things to different people. For example, some people use the word "light" with the pleasant image of "the light of a warm and gentle spring day," while others use it with the unpleasant image of "the blinding and painful spotlight shining on the stage," and it is impossible to know in advance which one it is, so one should not treat the word with prejudice.
    - relevance
            - [[Four Steps for Deliberative Discussion]]
            - It is pointed out here that "the same fact causes different emotions in different people."

The following exchange took place after the author verbalized this realization (detail log: [[Log of Discussion on Interpretation Swings on Polis: Investigating the Causes of Terrorism]])
- H: I'm in the "I don't think I can understand the logic of a terrorist at all" faction, but I guess we all think we can stand with them.
- N: "I think we can all lean on each other" is an unfounded interpretation (no opinion poll with that content).
- H: If you look at this and see what's in it, A generally says it can be solved by pursuing the cause or motive, which means that "everyone" thinks it can be solved by "understanding = leaning on" the cause or motive.
    - ![image](https://gyazo.com/8e6eb90e6efcada9ad6d68406caeff3f/thumb/1000)
- N: "Understanding the cause or motive = leaning in" is the interpretation. Probably False.
- H: If "leaned on" was the wrong word, then my intention is to be able to understand causes and motives.
- N: That would be a swing in the meaning of "understand."
- H: Assuming there was a swing in the "understanding" of the crowd,
    - 1: I don't think polis expresses the swing in semantics because it synthesizes and maps the positives and negatives of the superficial string.
    - 2: I feel that if the interpretation of the surface layer is blurred due to the nature of classification by surface expression, then the mapping loses its meaning.
- N: It's simple, the assumption in (2) is True. That is, people's usage of the term is of course shaky, so there is no "certain meaning" in a "snapshot of the distribution at a certain point in time". It means that there is value in the "process of improvement" as the distribution is updated as the current swing becomes observable data.

The hypotheses that emerged during this discussion were also tested by data
- > "I think we can all cuddle up" is an unfounded interpretation.
    - ![image](https://gyazo.com/f2337307169fd9bdf06b19ad9e8ca6cb/thumb/1000)
    - We can be there for those who terrorize.
        - Not "everyone" thinks they can "lean in," only 34% agree.
- > "Understanding the cause and motive = leaning in" is the interpretation. Probably False.
    - ![image](https://gyazo.com/89e34925a7e85e25a13fe96efb84c67b/thumb/1000)
    - Understanding causes and motives" means "leaning in": No 78%.
- >  H: My intention is "to be able to understand causes and motives" / N: That would be a swing in the meaning of "understand".
    - I'm not sure a direct "what is understanding?" type of question would work very well on this.
        - You lumped them together as "cause or motive," but since the two words have different meanings, I thought lumping them together would blur the focus.
        - Not very clear-cut results, but let me get this straight.
    - result
        - ![image](https://gyazo.com/5ef4cade0cbdf823728b673971042e5f/thumb/1000)
        - I have no desire to understand the logic of a person who would commit a terrorist attack: No 62%.
        - I don't understand other people in the first place: Yes 53%.
        - ![image](https://gyazo.com/50d24d6f7d896779dfdeb23555fd69b1/thumb/1000)
        - We can understand the motives of those who commit terrorism: Yes 45%.
        - We can understand the causes of terrorism: Yes 56%.
    - In other words, "understandable" depends on the subject of understanding and the moderation
        - Terrorist logic: 62% capable of doing so
            - This one has "not at all" in the original opinion, so anyone who thought they could "do a little" is counted as "able."
        - Causes of terrorism: 56% possible
        - Motives of those who commit terrorism: able 45
        - Others: Can't 53%.
    - There is not enough data to make a definite statement, but the author's interpretation is as follows:.
        - The majority interpreted "understanding others" as "being able to understand the unobservable inner feelings of others" and considered it "impossible."
        - Since more people thought "the motives of those who commit terrorism" were "capable" than those who thought they were "incapable," many probably interpreted it to mean "observable triggers of terrorism," etc.
        - When it comes to the description "causes of terrorism," more people think it's more "understandable" because it's not limited to people.
        - When people see the statement, "Let's investigate the causes and motives of terrorism," what they imagine as the "causes and motives" differs from person to person, and depending on these differences, there is a difference in judgment as to whether it can be done or not.

# About getting participants
.
In the case of [[vTaiwan]], the government's commitment that the results would be reflected in policy created an incentive for participation. Not everyone can create this incentive.
The author was first exposed to Polis at [[Plurality Tokyo]], became interested in it, and wanted more opportunities to experience it. In this case, eliciting government commitment would go a long way. We needed another form of incentive that could be created by individuals.

This experiment began when the author's friend noticed that they were having a parallel discussion on a social networking site. Both sides were smart and engaged in discussions that were not emotionally abusive, but it did not seem to be a fruitful discussion. The author saw this as an opportunity. This discussion led him to trace a few discussions on social networking sites on this topic and chopped them up into Polis' seed opinion.

He then Tweeted the following, avoiding the word "Polis," which is unknown to many.
> [@nishio](https://twitter.com/nishio/status/1647669628406206464): You can now vote for and against each side of the debate on the investigation of the causes of terrorism. Voting will show you where your opinion lies in the distribution of everyone's opinion.
> Vote for all and you can post your new opinion.
So this shows two types of incentives.
- 1: You know where your opinion falls in the distribution of everyone's opinion.
- 2: You can post your opinion and be eligible for others to vote on it.

In addition, to those who used statements in Polis' opinion, I sent a "I used your opinion" mentions
- We didn't execute it very tightly, just sent it messily to some people.
- But this may be more beneficial than you think. Because people want to know whether people agree or disagree with their opinions, which would be a third incentive.
- It might be better to reply to each individual tweet saying "I used this tweet.

Such an approach would be useful for those who would like to gain experience in Polis management. It is not uncommon to see lively discussions on social networking sites about current issues.
I think that the experience of more people in Polis, and the experience of many people in Polis operations, will help spread the system of [[careful deliberation]] in the long run.

Related Articles
- [What is the logic behind "don't report the motive of the culprits"?　Some LDP lawmakers claim in the attack on the prime minister: Tokyo Shimbun TOKYO Web](https://www.tokyo-np.co.jp/article/245507)

---
This page is auto-translated from [/nishio/Polis体験レポート:テロの原因究明をするか](https://scrapbox.io/nishio/Polis体験レポート:テロの原因究明をするか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.