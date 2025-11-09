---
title: "Public Opinion Map Study Group"
---

2024-10-18  [[Cybozu Labs Study Session]]
- Previous: [[Broad Listening "That Figure" Study Group]]
    - This was a story about [[Talk to the City]] utilization in [[Governor's Race 2024]] as part of [[broad listening]].
    - This led to [[Nittele NEWS x 2024 House of Representatives Election x Broad Listening]] just recently (10/15).
        - [NTV News - NTV's first special election program during the election period, "Vote for Who" (October 16, 2024)　Nittele's first ... election special program during the election period, "Vote for whom conference" (Published on October 16, 2024)｜Nittele News NNN [https://news.ntv.co.jp/category/politics/1f1a83953f594a5e9fb295636](https://news.ntv.co.jp/category/politics/1f1a83953f594a5e9fb295636) ecea6e1]
        - We'll do it with the LDP on the 15th and with the Communists today, the 18th.
- This story [[public opinion map]].
    - Like a third arrow for the spread of [[broad listening]] in Japan.
        - By the way, the first arrow is intended to be [Plurality Japanese translation
        - There is a sense of a surface being created at the three points.
    - Since the release is scheduled for today, we will update the document after the release.
        - I did

What is a public opinion map?
- New features released in the 2024 major update of [JAPAN CHOICE
    - ![image](https://gyazo.com/f03c209f057ac5377e88093c24be9f8e/thumb/1000)
    - > 3. [[New Feature]] Public Opinion Map
    - > Our opinions are diverse by nature, to the extent that we can't get all of them across just by casting a single vote every four years. What does society really think? Where do I fit in? If you make a map, you may find that there are already points of agreement, or you may find that the real axis of conflict exists elsewhere. Let's visualize each person's thoughts and ideas on the "Public Opinion Map," a testing ground for democracy in the new era.
    - [[Published on Oct. 15]] JAPAN CHOICE, a website with all the information you need to vote, has undergone a major update! House of Representatives Election 2024] | NPO Mielka Press Release []](https://prtimes.jp/main/html/rd/p/000000013.000029162.html)
    - Implemented in collaboration with JAPAN CHOICE's engineering team
- What is [[JAPAN CHOICE]]?
    - JAPAN CHOICE is a political information provision platform operated by NPO Mielka. In order to make it easier for voters to find political parties and policies that match their views, the platform organizes the pledges and past performance of each political party in a way that is easy to compare and presents them in an easy-to-understand visual format. It also provides a variety of election-related tools to support decision-making, such as [[Congressman pedia]] and [[Voting Navigator]], which cover information on members of the National Diet.
        - [JAPAN CHOICE](https://japanchoice.jp/)
- What is Mielka?
    - >  Mielka is a non-profit organization founded in 2016 with a focus on politics x technology x education.
    - >  To improve voter turnout among young people and to increase their desire for [[political participation]] and [[social participation]], we are providing information from a politically neutral and impartial standpoint in order to make people think about society and politics as if it were [[their own]] business.
    - >  In order to bring young people and politics closer together, we communicate politics and elections in an easy-to-understand way by [[visualizing (data, results, etc.)]] (making visible) politics as a basis for decision-making in society.
        - [NPO Mielka | NPO Mielka](https://mielka.org/)
- [[[House of Representatives Election 2021]] JAPAN CHOICE, a website with all the information you need to vote, is now available! | NPO Mielka Press Release []](https://prtimes.jp/main/html/rd/p/000000007.000029162.html)
    - ![image](https://gyazo.com/be4a9194caf60315b5f3264e2746b776/thumb/1000)
        - [senatorpedia | senatorpedia](https://giinpedia.japanchoice.jp/)
    - ![image](https://gyazo.com/f62b0155084d5900962d513849078397/thumb/1000)
        - [Voting Navigator - JAPAN CHOICE](https://japanchoice.jp/vote-navi)(2024 Edition)
- Opinion cluster analysis of 110,000 people] on this VoteNavi data for the 2022 House of Councillors election ([[Polis]] algorithm + [[AI cluster explanation]]).
    - At this time, the data was not collected specifically for this analysis, but it could be visualized.
    - I've found that it's realistically possible to visualize public opinion with data on the scale of 110,000 people.
- This analysis was done on 2024-05-14, which means they were actually working together before Anno's election as governor.
    - We were talking about doing [[Polis]] at the time of the next lower house election.
    - On 2024-02-08, [[Yuki Toki]], President of [[Mielka]], and [[mashbean]] of [[Ministry of Digital Development, Taiwan]] discussed Polis applications.
- When [[Glen Weyl]] was in Japan for [[Funding the Commons Tokyo 2024]], we had dinner and a long discussion with people from JAPAN CHOICE (2024-07-27 [[Glen+JAPANCHOICE]]).
    - So this is part of [[Plurality's]] [[The Big Story]].

public opinion map
- ![image](https://gyazo.com/1ca8fe7ec530a9dd48dc114ac9f6b0db/thumb/1000)
- The back end is [[Polis]].
    - Original Polis look and feel
    - ![image](https://gyazo.com/cd1644cee2b1fc42b56518d6e65d55ec/thumb/1000)
        - from  [[Polis Experience Report: Should Same-Sex Marriage Be Legalized?]]
    - How it works (also explained in detail in [[Polis Study Group]] in 2023-06)
        - ![image](https://gyazo.com/1272e02943155b514268445d784e94ee/thumb/1000)
            - from [[Polis: Scaling Deliberation by Mapping High Dimensional Opinion Spaces]]
        - Polis part
            - Visualize the vector of people's opinions for and against the N types of opinions by reducing them to 2 dimensions using PCA ([[principal component analysis]]).
            - In contrast, clustering by k-means method
                - How much k should be set is determined by [[silhouette coefficient]].
                - Identify opinions that characterize each cluster using [Fisher's exact probability test
        - Public Opinion Map Side
            - LLM creates cluster descriptions based on "opinions that characterize each cluster" data.
            - View political party data
            - Visualize each cluster with [Convex Hull
- Front-end is developed by full scratch
    - TypeScipt + Next.js + [[D3.js]]
    - Developed with [mobile first
        - 85% of JAPAN CHOICE's 3 million unique users are on mobile devices
        - Determination that UX is important in a mobile environment
- Stop giving out personal social networking icons and instead give out political party icons.
    - This logic is implemented on the front end.
    - Calculate projected locations from political party opinion data to 2D with PCA
    - Similarly, user voting data can be used to calculate the projection points on the front end.
        - →User feedback can be provided at a faster rate than the original because there is no longer a need to go through the server!
- detailed display
    - The problem of too bad UX in this part of the original Polis.
        - ![image](https://gyazo.com/ac39d30d14844ddc93d06f0c26abd577/thumb/1000)
        - Pressing "Major Opinion," "A," or "B" changes the number of "Opinion" on the right.
            - This number is opinion ID
    - Some say the report screen is easier to read.
        - ![image](https://gyazo.com/8fc9bbf3a004b476674e42e9fc1b9ecd/thumb/1000)
        - While using this as a base, we have created a design that is easy to view on a smartphone screen.
            - It's hard in narrow environments to arrange them left to right in a tabular format.
    - ![image](https://gyazo.com/a9c966bf767aa3a2a84eb648c73b597f/thumb/1000)![image](https://gyazo.com/c1900075305d6d873a92710c81ef52d9/thumb/1000)
    - ![image](https://gyazo.com/acfa2ca54fae8f8f3f49e434fde85a96/thumb/1000)
    - A Little Attention to Detail
        - I have them in order of approval/neutrality/agreement, not approval/neutrality/agreement order.
        - Unvoted users are not represented in the graph.
        - This allows you to see the median opinion by looking at the center of the graph.
            - This is the idea of [Majority Judgement
            - <img src='https://scrapbox.io/api/pages/nishio-en/Majority Judgememt View/icon' alt='Majority Judgememt View.icon' height="19.5"/> 2023-06-15
- There is no explanation of what is meant by visualization and consensus display in the original document, but since it is often misunderstood, I decided to write it down properly.
    - Cluster size is not the number of people, but the scatter
        - > This graph groups people who are close in opinion according to their answers to the questions. The distance between groups indicates the degree of difference in opinion. Therefore, group size does not indicate the number of people in a group, but rather the variability of their opinions. The summary of opinions shown is the result of AI analysis of the current opinion group data, and will be updated as more users answer the questions.
    - Consensus is not a majority vote, but rather a multiplication of the pros and cons for each cluster
        - > "Everyone's Consensus" is selected not by a simple majority vote by adding up everyone's votes, but by a score obtained by multiplying the percentage of agreement and disagreement in each opinion group. In other words, even if a majority votes in favor of a proposal, it will not be selected if there is a group that strongly opposes it. Depending on the distribution of everyone's opinions, nothing may be selected here.
- The number of people in the cluster and the overall vote tallies are not shown.
    - By not displaying the number of people, it is difficult to tell which is the majority when the cluster is split in two.
    - By not giving the results of the overall vote, it makes it impossible to know "whether there is a majority in favor or a majority against this opinion.
    - I think that if you put these out there, you'll end up ignoring the unfamiliar ones and just looking at the "normal [[majority rule]]" results.
- AI Explanation of Clusters
    - ![image](https://gyazo.com/7546bedf1190c3c8e4d7f7dc2891ab51/thumb/1000)
    - It's [[Talk to the City]]-ish.
        - I too was under the mistaken impression that you got the idea by doing TTTC, but but I see you already have a prototype running on 5/8 that uses Polis data to create AI commentary...
        - We talked about [[mashbean]] and [[Polis 2.0]], so I guess it came from that.
            - This is a system that allows you to chat with AI based on cluster data
            - If you can do that, I'd like you to first explain what kind of cluster you're talking about.
    - Q: How many people can withstand naming in LLM?
        - A: The LLM part is not too burdensome, since the first stage, Polis, does all the work of dividing the data into clusters and producing the feature values of those clusters. Even if there are 100 million users, the LLM part will not become a bottleneck.

The Invisible Side of the Story
- Unknown how much access Polis can withstand
    - 110,000 people in the past with the actual number of voting navigators; the commonly used scale of Polis is a few hundred, so 2~3 orders of magnitude larger.
        - We can increase resources since we are a self-funded operation, but we don't know how large and how many resources we need in the first place.
        - Need to assume that the server may die
    - BTW, the Polis visualization is updated by polling asynchronously with user votes.
        - Line A
            - Users vote
            - DB is rewritten
            - PCA will be done
            - ![image](https://gyazo.com/a4dc704196509d22dcbb2b2dfb4bb563/thumb/1000)
        - Line B
            - Polling for PCA results.
            - No change
            - There is a change.
            - Redraw (also update user position here)
            - ![image](https://gyazo.com/595212b90edfe6f692861439bccb5148/thumb/1000)
    - However, as a result of research to produce political party icons during this development process, it is now possible to calculate the position of your icon on the front end as well.
    - What does that mean?
        - It's not essential that Line B is working.
        - If the PCA results are cached on the front end, the server will be fine even if the server dies!
        - ![image](https://gyazo.com/b84da6bf2cb372fc3050c185caf6a362/thumb/1000)
        - In detail, the Polis server has a DB server and a compute server.
            - This compute server is the bottleneck
                - So we designed it not to assume that the compute server is alive.
                - No real harm at all if the compute server is dead.
                    - User votes are recorded on the DB server so they can be recalculated later.
        - If the DB server also dies, user votes will no longer be recorded.
            - I don't think it's going to fall that far since it's just a small record INSERT into PostgreSQL.
            - but the spike when introduced on TV is a concern
            - made to fail silently without compromising the user experience.
    - How [[AI Cluster Description]] works
    - The front end formats the data Polis spits out.
:

```
# Team Red
## In order to ensure fairness of "benefit and burden" between the elderly and the working-age population, review the medical cost burden of the elderly (bring it closer to the burden of the working-age population, such as 20% or 30% burden).
 - **Overall** Yea: 18, Nay: 5, Neutral: 5, Total: 28
 - **This team** Yea: 0, Nay: 5, Neutral: 5, Total: 10

# Team Blue
## In order to ensure fairness of "benefit and burden" between the elderly and the working-age population, review the medical cost burden of the elderly (bring it closer to the burden of the working-age population, such as 20% or 30% burden).
 - **Overall** Yea: 18, Nay: 5, Neutral: 5, Total: 28
 - **this team** Yea: 11, Nay: 0, Neutral: 0, Total: 11

## Establish a system to add a certain amount to the pensions of low-income seniors
 - **Overall** Yea: 7, Nay: 9, Neutral: 14, Total: 30
 - **This team** Yea: 0, Nay: 8, Neutral: 3, Total: 11

## Reduce the flat 10% window charge for medical expenses for those 70 years and older and promote reduction and free of charge
 - **Overall** Yea: 4, Nay: 18, Neutral: 5, Total: 27
 - **this team** Yea: 0, Nay: 11, Neutral: 0, Total: 11

# Team Yellow
## Establish a comprehensive combined system that caps the total out-of-pocket expenses for social security services related to medical care, long-term care, welfare for the disabled, etc., according to income.
 - **Overall** Yea: 14, Nay: 5, Neutral: 11, Total: 30
 - **This team** Yea: 9, Nay: 0, Neutral: 0, Total: 9

## Fundamentally reform the pension system to a funded or tax-based system, as the social insurance system places an undue and disproportionate burden on the working-age population.
 - **Overall** Yea: 13, Nay: 4, Neutral: 11, Total: 28
 - **this team** Yea: 7, Nay: 0, Neutral: 0, Total: 7

## Public spending to lower the burden of social insurance premiums on the working-age population
 - **Overall** Yea: 13, Nay: 3, Neutral: 11, Total: 27
 - **this team** Yea: 6, Nay: 0, Neutral: 0, Total: 6

## Revise the maximum amount of social insurance contributions and require the wealthy to pay their fair share.
 - **Overall** Yea: 14, Nay: 2, Neutral: 11, Total: 27
 - **this team** Yea: 6, Nay: 0, Neutral: 0, Total: 6

## In order to ensure fairness of "benefit and burden" between the elderly and the working-age population, review the medical cost burden of the elderly (bring it closer to the burden of the working-age population, such as 20% or 30% burden).
 - **Overall** Yea: 18, Nay: 5, Neutral: 5, Total: 28
 - **this team** Yea: 7, Nay: 0, Neutral: 0, Total: 7
```

    - I have made custom GPTs that read this and create commentary.
        - ![image](https://gyazo.com/bd18952ff27ed261d2c53546805a7caf/thumb/1000)
    - I'm pasting the data manually, and the results come out in JSON, and I'm pasting it into the source code.
        - ![image](https://gyazo.com/3a8d46bf27260203dcd3769c1918f276/thumb/1000)
    - This is where the human review phase is required and cannot be automated.
        - Case 1: The
            - In a situation where "both A and B have a high tendency to agree with the opinion X, but B is relatively more opposed, which characterizes the cluster," you get something like "B is in favor of X."
            - It's not a lie, but A agrees with me more, so it's misleading when it's written that way in the cluster description.
            - That's not what I want you to focus on...
        - Case 2: The
            - AI abbreviates it as "policy expense" but I want it to be "policy activity expense".

Interesting findings
- The distribution is too homogeneous when the initial data is based on party manifestos.
    - There was some interesting behavior because of it.
        - ![image](https://gyazo.com/6453699e8638d4c4b1ebd7c90bc2436b/thumb/1000)
        - I'm thinking humans are (1).
        - The actual data is (2).
        - The data looks equally correct to the machine in both of the two ways of dividing the data (3).
    - This results in unnatural clustering from a human perspective.
    - After about 10-20 people voted, it turned into a convincing cluster.
    - I think this is due to the fact that the method of "selecting opinions from a party's manifesto, making them eligible for voting, and then considering them as the party's voting results" results in "one person for each position" type data.
        - As a result, the weights on each axis are too equal
        - Voting by unrelated people distributes the weights of the axes, resulting in a more stable clustering.
- The case of party opinion at all.
    - → Icons are also displayed in the exact same spot.
    - > I see only 7 party icons? I thought there were only seven, but the JCP, Kiriwa New Election Party, and Social Democratic Party have the exact same views, so they are overlapped in the same place, and the Social Democratic Party is last, so it's at the top of the list.
    - I'm struggling with how to resolve this, do you rebound with a spring model, etc?
    - > I've thought of several ways to solve this problem and how to implement it, but I feel that "create an icon with 3 parties in a row and treat it like a single party" is a good solution. I have already implemented the ability to specify the image and size of the icons individually.
    - ![image](https://gyazo.com/a5bb82f78386acf682a39f9ab15234e9/thumb/1000)
    - When it's three, well, okay.
    - 'The LDP and Komeito overlap!' What to do when there are two..."

Q&A
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q: If answering the question brings you closer to a party you don't like, will that create behavior to change your answer to avoid it?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I think that would be quite difficult.
    - Suppose that as a result of your answer, you "unexpectedly" moved closer to Party B instead of your favorite Party A.
    - To move away from B and closer to A, you have to give the same answer as A to a question where A and B have different opinions.
        - That means you have to know the opinion vectors of A and B.
        - However, the fact that he "unexpectedly" approached Party B means that he is not aware of Party B's opinion vectors.
            - You don't like party B, so you haven't heard party B's arguments properly, and you haven't read their manifesto carefully.
            - If I read it correctly, the party B, which I hated emotionally, was actually the closest to my opinion, and I didn't realize it, and I provided the opportunity to realize it.
            - I think it's a learning opportunity.
    - Even with a service like VoteNavi, the person thinks he or she supports Party A, but "the closest one is shown as Party B!" even though he/she intends to support Party A.
        - It may be more effective in promoting understanding at a finer granularity, since after answering a number of questions, the batch is told "close here" and each question moves on its own.
        - There's a map for each of the big categories, like the Constitution and the tax system, so you can see things like, "Party A on the Constitution, but Party B on the tax system.

- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>A political party is described as if it were a single person? In the mistake of treating an organization analogous to "[[There is no Mr. Company.]]" as a person?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I don't think we have a choice because of the system of selecting "parties" through proportional representation.
    - For a Polis-like analysis of individual politicians, see [[Polis-like visualization of the 2022 House of Councillors election]] (done on 5/27).
    - ![image](https://gyazo.com/77f9fc60c241159a0062e4842a7435cf/thumb/1000)
    - 668 people, each point is an individual, with real names and data tied to political parties.
        - Politicians are so full of it.
        - There is a problem that is difficult to see on a smart phone screen.
    - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Where did this data come from?
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> [[Joint research by Taniguchi Laboratory, University of Tokyo and Asahi Shimbun]]
            - > The University of Tokyo Taniguchi Laboratory and the Asahi Shimbun joint survey (the University of Tokyo Taniguchi Survey; before 2005, the University of Tokyo Kabashima-Taniguchi Survey) is a globally rare data set consisting of two surveys of voters and politicians conducted since 2003 during the House of Representatives and House of Councillors elections. This website has been established for the purpose of making this survey data available to the public for use in academic research.
            - Survey of all politicians
        - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Sounds like a lot of work.
    - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Can't we extract it with LLM?
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It can be done, but of course mistakes will be made, so the process needs to be designed to accept feedback from politicians and correct them.
            - Otherwise, even with a 90% success rate, you'll get angry calls from 67 people who are wrong.
            - Personally, I'd like to publish a CSV on GitHub and "pull request if wrong".
                    - [[fairness]]

2024-10-19
- Overall, more than 100 data were collected, so the display was updated.
- ![image](https://gyazo.com/86cd4282d56e4767045a4e0ab803c2f5/thumb/1000)
- ![image](https://gyazo.com/04783a16dc121a95fad1367240b9f62f/thumb/1000)
- ![image](https://gyazo.com/84d7bca9e6c498e9e61f5f3fe35bf336/thumb/1000)
- ![image](https://gyazo.com/a0b10444e9e24510a61acfa3c9d38cd9/thumb/1000)
- ![image](https://gyazo.com/3e03262662ef7ceb73eef83a65e1128a/thumb/1000)
- ![image](https://gyazo.com/7d6813f9746f8af171a3ec01d3b7997b/thumb/1000)

---
This page is auto-translated from [/nishio/世論地図勉強会](https://scrapbox.io/nishio/世論地図勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.