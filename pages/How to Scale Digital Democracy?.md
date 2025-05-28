---
title: "How to Scale Digital Democracy?"
---

How to Scale Digital Democracy?
- 2025-02-25 [[Plurality Tokyo Namerakaigi]] 20 min.
- 2025-02-28 [[Cybozu Labs Study Session]] 60 min.
- ![image](https://gyazo.com/e0cbca9528fb418c1248e823bbcfbba9/thumb/1000)
    - For Thumbnail
- Plurality Tokyo Namerakaigi Video
    - [https://www.youtube.com/watch?v=07BQsWtF5KA&list=PLHsuZp6_Tsv9RZnyar7J7F8dpbHDwX5Uf&index=5](https://www.youtube.com/watch?v=07BQsWtF5KA&list=PLHsuZp6_Tsv9RZnyar7J7F8dpbHDwX5Uf&index=5)
- Cybozu Labs Study Session Video
    - [https://youtu.be/9US9vrS18Yg](https://youtu.be/9US9vrS18Yg)
- [Scaling Digital Democracy examines the evolution and challenges of democracy from Classical Athens to the present day, and introduces new methods of voting, domain voting, Quadratic Voting (QV), Quadratic Funding (QF), and more. | Fractal Reader](https://www.fractal-reader.com/view/0697461e-f8e7-4601-82fe-edaffcc6db94)

impetus
- > <img src='https://scrapbox.io/api/pages/nishio-en/tkgshn/icon' alt='tkgshn.icon' height="19.5"/> I need you to speak for about 20 minutes on the topic of "Scaling Digital Democracy through Community" (how to achieve large-scale collaboration using [[Pol.is]] and [[Community Notes]] examples).
    - We've talked about various related topics in [[Cybozu Labs Study Session]] so far.
        - 2021-05-28  [[Mechanism Design Study Group]]
        - 2021-07-09  [[Majority Judgement Study Group]]
        - 2023-05-12  [[Plurality and Polis Study Group]]
        - 2023-06-23  [[Polis Study Group]]
        - 2024-03-15  [[Quadratic Voting and Plural Management Study Group]]
        - 2024-06-14  [[Talk to the City Study Group]]
        - 2024-10-18  [[Public Opinion Map Study Group]]
        - 2024-11-22  [[High-dimensional data analysis study group]]
    - I usually talk for an hour, so this time it's 1/3 of an hour, so it's compact.
        - I share my thoughts from the perspective of understanding what's in the implementation.
        - No amount of time would be enough to explain the implementation details.
        - More details will be written in a Note in the [[Digital Democracy Research Unit]].

I don't think of democracy as something vaguely good.
- To improve democracy means that there are bad things about "democracy in 2024."
- We need to think about "democracy" not in a vague way, but break it down into details, where it is good and where it is bad we need to dig deeper.
    - [[pivot]] = axis foot
    - Use the better leg of the current location as the axis leg, without moving the better part, and move the other leg toward the ideal.

- [[Scale of Democracy in Classical Athens]]
- 5th century B.C.
- Discussed at the meeting and decided on policy by majority vote
- It's nice to discuss and decide together."
- Who is this 'everyone'?"
- Adult males who are citizens by birth. Excludes women, slaves, and aliens.
- Approximately 10-20% of the total population, or about 30,000-60,000 people
    - By the way, Tokyo Dome holds 55,000 people.
    - Ishigaki Island, Miyako Island, Sado Island, and Amami Oshima have around 40,000-60,000 people.

- [[The people are the only legitimate authority.]]
    - After the [[French Revolution]] (1789), discussions on drafting a constitution
- Robespierre, "[[The people are the only legitimate authority.]]" (1793).
- I like the idea of giving every citizen the right to vote."
- Who is this 'everyone'?"
- Adult Men.
        - [[Women's suffrage in France]] did not exist until 1944. Women were not "citizens."
    - Women's suffrage in Japan, 1945, not much different.

- The [[one vote per person]] principle?
- They talk about the "one man, one vote" principle, but that hasn't been accomplished even at this point in time.
    - [[Minors do not have the right to vote]].
- Isn't it against the principle of one person, one vote to limit it to adults?"
- "Minors do not have the capacity to make rational political decisions because they do not have the judgmental capacity to make rational political decisions."
- What about seniors with dementia who have the right to vote?
    - Even though "adult wards who are judged to have insufficient capacity to make decisions due to dementia or intellectual or mental disabilities" have the right to vote since the 2013 amendment to the Public Offices Election Law? (see [[Voting rights of adult wards]])
    - You claim that 17 year olds are less capable of making decisions than those people?
- Why not give equal voting rights to all human beings, including 0-year-olds, and delegate to their parents or guardians those children who cannot express themselves?
    - This idea is named "[[domain voting system]]".
    - The domain is derived from the personal name Paul Demeny and is also called [[Demeny Vote]] or [[Demeny Vote]].

[[Quadratic Voting]]
- Maybe we should change the one-person, one-vote principle, because it's not really that important."
- and radical reforms proposed by [[Glen Weyl]] Quadratic Voting ([[QV]])
- Many of you have read about it in the book "[[Radical Markets]].
- Three slightly different things came out of this inspiration, so let's sort them out here
    - QV of [Audrey Tang
    - QV of [Glen Weyl
    - [[Quadratic Funding]](QF) by [[Vitalik Buterin]] et al.

[[Audrey Tang's QV]]
- A social implementation of [[Glen Weyl's QV]] described below, stripped down to fit reality
- For example, in voting for the Hackathon Excellence Award, one person is given 99 votes.
- Voting strength is the square root of the number of votes cast.
    - If you cast 64 votes, you have 8 voting power
    - If you cast 16 votes, you have a 4-vote power.
    - You can make better use of your vote by voting for a variety of candidates in small increments.
- The interesting thing is that they have "99 votes" instead of "100 votes".
    - I can't vote for one candidate for all of them because it's too close to the end.
    - If a friend said to me, "I'm in this contest, vote for me," if it were a conventional method, I would only vote for that friend.
    - This way, you get 81+16+1+1 or something like that, and your friends get 9 voting power, but you also get 6 voting power for other projects.
- Audrey says (from [[Quadratic Voting is useful for finding synergies]])
    - > The incentive is to look at multiple projects with high synergy and naturally try to find the "optimal combination.
    - > "Combined, they are worth more than the sum of their individual parts" = synergistic combinations emerge through voting behavior.
    - Used in [[Taiwan President's Cup Hackathon]], etc.

[[Glen Weyl's QV]]
- Proposal for QV in the first place
    - 'You can cast more than one vote if you want, but the cost will be the square of the number of votes cast.'
    - Where did that "plurality vote" come from?
    - The proposal depicted in [[Radical Markets]] is "the continuing value of the right to vote."
- Don't you all take it for granted that if you don't vote, your vote is worthless?
    - Current voting rights have no "continuing value".
- In every election, the question is, "Does it make sense to cast a white vote?" There is a controversy that
    - What to do when there is no candidate you want to vote for?
        - For example, there is a favored incumbent and no decent opponents.
    - Glen's QV offers a simple solution
        - We can save those votes and use them next time."
            - [[QV is a meaningful mechanism for not voting]]
        - [["Not voting is a bad thing" is an unfounded assumption]].
    - The current voting system ignores incumbents because votes not cast or white votes have no value.
        - However, with QV, "votes stocked without being voted" are voted for "opponents who might be able to defeat the incumbent who appears in the future," so the incumbent will do his best to increase his vote share.
- In terms of social implementation...
    - (Aside from the fact that no incumbent may want to include this.)
    - Technically, it's not easy to keep secret ballots and keep the unused votes belonging to the individual and surviving.
    - Audrey's QV facilitates social implementation by discarding continuity value.

[[Quadratic Funding by Vitalik Buterin et al.]]
- [[A Flexible Design for Funding Public Goods]](Vitalik Buterin, Zoe Hitzig, E. Glen Weyl)
- 'Tokens of continuing value? We already have that, don't we? It's gold!"
- I get an allergic reaction when I describe it as "buying votes with money."
- Let's look at it as crowdfunding and a guessing game for idols.
    - Functioning as a social implementation
    - AKB48 General Election 2009]
        - Fans earn votes by purchasing CDs.
        - At this time, "number of tickets purchased = number of ballots = voting power".
        - If the voting power is the square root of the number of ballots, it becomes QF.
    - [[Gitcoin]]
        - Established in 2017
        - Start redistributing funds to open source public goods through [[Gitcoin Grants]] around 2019.
        - Approximately $700,000 in the first year, followed by rapid growth and redistribution of approximately $21.4 million in 2022 ([link](https://www.gitcoin.co/blog/announcing-gg20)).
- What's wrong with buying votes with money in the first place?
    - Intention of the title "for Funding Public Goods
    - ![image](https://gyazo.com/7de5f0eae25deb83ad3ae020628a2fd5/thumb/1000)
        - In QF, 1 million yen (=1000 voting power) from 1 person and 100 yen (=10 voting power) from 100 people have the same power.
    - ![image](https://gyazo.com/b7b59fcc5cc066b7adaf26378206f3f6/thumb/1000)
        - 1,000,000 yen goes to the treasury and will be redistributed in the future, 10,000 yen per person if divided among 100 people.
        - People who think plan A is good are paying 10,000 yen each to people who think plan B is good (they can pay up to 100 yen).
        - Even those who think Plan B is better are paying 10,000 yen for one person who prefers Plan A, divided among 100 people.
        - For irreconcilable decision options, "pay more for everyone who makes you drink" is chosen.
        - Isn't this a very good characteristic from the point of view of [[redistribution of resources]] or investment in [[public goods (i.e. goods or services such as parks or highways)]]?

Voting and Crowdfunding
- Reflection on the past
- Many people associate the word "democracy" with the "voting" "ritual" in "Democracy in 2024" of "writing the names of politicians on paper and putting them in a box.
- But from the perspective of designing social mechanisms, we talked about how voting and crowdfunding have a common structure.
- Both are "mechanisms for gathering information from the many and consolidating opinions."
    - [[mechanism design]] of [[social decision making]].
    - We need to take a closer look and break down the concept of "voting" from this perspective.
    - The "ritual of writing a politician's name on a piece of paper and putting it in a box" is just one of the major implementations currently in place.


What was the vote?
- In the past, there were no computers, so aggregation algorithms were undeveloped.
- An easy-to-implement and widely used tally method is the [[majority rule]] algorithm: "write down the choices, vote, count the number, and choose the one with the most choices".
    - The other easy way was [[lottery]] ([[lottery system]]/[[lot drawing system]])
        - The Athenian arcon (regent) was decided by lot.
- They think there's a lot wrong with majority rule.
        - [[Plato]] "The judgment of the ignorant masses disturbs the state. The ideal is to be governed by those with expertise."
        - [[Aristotle.]] "Popular rule disregards minority opinion and is easily swayed by emotion."
    - [[James Madison]] "We need separation of powers and federalism to prevent tyranny of the majority."
        - [[John Stuart Mill.]] "Simple majority rule could undermine individual liberty and minority rights."
        - [[Alexis de Tocqueville.]] "Modern democracy runs the risk of populism and information bias."
    - I also wrote about the mathematical aspects on 2021-07-09 [[Majority Judgement Study Group]], if you are interested.
- There are many problems, so let's focus on one of them this time.
    - [[Elections are slow communications, sending 5 bits every four years.]] (Audrey Tang)
    - Pointing out that "Voting is too little information to be sent in the first place."
    - I want to send more
    - But conventionally not accepted.
    - Starting around 2023, the development of LLMs (large-scale language models) is enabling better aggregation algorithms
            - [[broad listening]]
        - Experiments are being conducted on a variety of applications, and various results are being achieved.
        - ![image](https://gyazo.com/8aed1a6ee239c672d1e504cdb48d0e9e/thumb/1000)

[[Polis]] / [[Community Notes]]
- These two are ballot-based methods that do not use LLMs
- Polis became famous when Audrey used it in vTaiwan.
    - [Pol.is (service)](https://www.pol.is/home) / [GitHub](https://github.com/compdemocracy/polis) / [[Uber discussion in Pol.is]]
    - People vote "for, neutral, or against" an opinion.
    - Opinions themselves can also be voted on (depending on the setting).
- Community Notes is used by X/Twitter. [GitHub](https://github.com/twitter/communitynotes)
    - In addition, it [[Meta eliminates fact-checking]] seems to change the system to a Community Notes-like system.
        - > Meta Platforms announced on January 7 (U.S. time) that it will discontinue its third-party fact-checking program on Facebook, Instagram, and Threads. --- [Meta to abolish fact-checking - a major shift before the Trump administration's resurgence | WIRED.jp [https://wired.jp/article/meta-ditches-fact-checkers-in-favor-of-x-style-community-notes](https://wired.jp/article/meta-ditches-fact-checkers-in-favor-of-x-style-community-notes) /]
    - People vote "useful/useless" for the notes.
    - You can even post the note itself (after accumulating some trust points).
- Processing Mechanism
    - Polis
        - Missing values are filled with the mean
        - PCA (Principal Component Analysis) to be 2-dimensional = people are placed in 2 dimensions.
        - Then clustering by k-means
    - CN has a problem with very many missing values.
        - Learning a "very simple neural net" using the given data as the teacher data (abridged explanation).
        - As a result people are placed in one dimension(= roughly in line with the political left and right)
        - Make the weight of people's political bias and unrelated note support the note score.
        - (For more information: [[Confidence Scoring Using Matrix Decomposition in Community Notes]])
- [[a mechanism for evaluating support from diverse entities]].

[[Talk to the City]]
- Talk to the City (TTTC) is an LLM-based methodology
    - Appeared in early 2023, then released as open source in October 2023
        - [Talk to the City: an open-source AI tool for scaling deliberation — AI • Objectives • Institute](https://ai.objectives.institute/blog/talk-to-the-city-an-open-source-ai-tool-to-scale-deliberation)
    - [GitHub](https://github.com/AIObjectives/talk-to-the-city-reports)
    - In Japan, Mr. Anno used it in his campaign for Governor of Tokyo, Nittele used it in the Lower House election, and the Tokyo Metropolitan Government used it to formulate a long-term strategy, and it is gaining recognition.
            - [[Nittele NEWS x 2024 House of Representatives Election x Broad Listening]]
            - [[Shin Tokyo 2050 Broad Listening]]
- Processing Mechanism
    - LLM converts people's opinion text into a higher dimensional vector
    - Make it 2-dimensional for visualization purposes (using [[UMAP]])
    - The two dimensioned items are clustered into groups, and the LLM generates a description of the groups.

- [[public opinion map]]
- Japanese NPO [[Mielka]] released [service](https://japanchoice.jp/polis) as a new feature of [[JAPAN CHOICE]] at the time of the [[2024 lower house election]].
- ![image](https://gyazo.com/1e1a56060aab7c997e9d0999fab108a8/thumb/1000)
- Polis and Talk to the City fusion line
- The first half is voted on like Polis, and the LLM generates commentary on the groups created, like TTTC.
- Overlaying "opinion vectors" extracted from political party manifestos is a feature not found in conventional Polis or Talk to the City.
- Data collected and visualized for 4,400 people in the 2024 House election: [GitHub](https://github.com/mielka/yoronchizu2024-data)

TTTC, Public Opinion Map and Beyond
- What features were in Polis, not in TTTC, and what features did the poll map cut from Polis?
    - It's "the ability to post comments after viewing the visualization"
- Currently TTTC and public opinion map "stops at visualization"
    - [[Meta-polis conception]]
    - ![image](https://gyazo.com/21beb7358d7da00e2bf24eccec79fbe9/thumb/1000) by [[mashbean]]
    - (I'm not sure I agree with the diagram itself from an engineering standpoint because of the functional overlap due to Polis and TTTC being black box components.)
    - I agree with you when you say "There needs to be an interface where users who see the visualization can be triggered by it to write their opinions and vote..."
    - The loop should keep spinning all the way around as an ongoing mechanism.
        - On the other hand, as a realistic project, it is easier to make it a lively event with a clear end.
        - How to fill the gap here is a challenge.

- [[Trade-off between depth and breadth of cooperation]]
- ![image](https://gyazo.com/2023cb08538c06434d3ac53d4991d24d/thumb/1000) from  [[Plurality Books]]
- Cooperation has depth and breadth, these are tradeoffs, and technological advances push the range of what is possible.
- Originally titled "How to Scale Digital Democracy?"
- ![image](https://gyazo.com/a7e741fc4fcebd8ba02b51f997ce24f5/thumb/1000)
    - The "voting" that is often associated with the word "democracy" has already been scaled considerably.
        - Wide but shallow
        - There's also the line, "Let's broaden it a bit more, maybe minors, foreigners, etc."(1)
    - Audrey's "Voting is too little information sent in the first place, isn't it?""More information" is a deeper approach(2)
        - From "Choose from the candidates" to "Vote directly for or against the agenda" or "Submit your opinion in writing".
            - (The fact that JOIN allows high school students to send out messages also contributes in the direction of expanding it.)
        - This direction stands out.
            - Because we are starting from a "wide" place.
- There are other approaches.
    - ![image](https://gyazo.com/1d9ebb5769c6c0e31e2d04831b3cc998/thumb/1000)
    - Productivity of discussions when you are talking to two like-minded people.
    - Productivity when discussing in small groups
    - How can we "deepen" (3) and "broaden" (4) this further?

- [[AI]] VTubers have freed [[town meetings]] from space and time limitations.
- Operated 24 hours a day for 5 days with no location restrictions and answered 6,000 questions.
    - Unlike humans, AI ans have no physical limitations.
    - [[desynchronization]]([[freeing from the limitations of space and time]]) broadened the range of people who could participate.
    - Work and child rearing.
    - [[Differences between ChatGPT and AI An's form of communication]]
    - ![image](https://gyazo.com/4e453420bbbc08b3a9671fa498ef022d/thumb/1000)
    - Information sharing by being able to see people around you instead of having a one-on-one conversation with the AI
        - Allows the general public to see "what questions other participants are asking and what responses they are getting".
    - [[Three levels of AI politicians]]
    - ![image](https://gyazo.com/de2c94f79f955838d374e0cc904e2eb5/thumb/1000)
    - Unlike (1), where AI only talks and does not listen to people, or (2), where AI listens to people but does not feed back its data, AI An has been structured as (3) from the beginning.
    - [[AI intervenes and asynchronizes]] so that "massive two-way communication" is occurring.

[[Open Space Technology]]
- This is one of the group discussion methods, and is conducted at Cybozu with more than 100 people.
- Participants propose a theme of their choice in front of everyone.
    - It's "[[Open up agenda-setting authority to people]]" (by Audrey).
- Everyone goes to the booths on topics of interest to each of you.
    - No one is forced to participate in a discussion in which they have no interest.
    - However, if you set an unpopular theme, fewer people will talk to you ([[Vitalik]]'s [[subjectivism]]).
- (Depending on the number of people and time constraints, in the case of Cybozu)4 sessions of 30 minutes per session, there were 13 booths.
- ![image](https://gyazo.com/98e35e5fc7521a65e82b853695717b25/thumb/1000) from  [[Plurality Books]]
- ![image](https://gyazo.com/9907d2b196a02dbb72d9f266e9f7880f/thumb/1000)
        - from  [[There are two opposing axes between the three ideologies.]]
    - A society is made up of a number of overlapping groups, not a single mass of society, nor individual people in isolation.
    - I think Open Space Technology fits very well with this idea of the Plurality book.
    - Dividing 100 people into 13 groups averages 7-8.
    - Close discussions in small, face-to-face groups.
    - Doing it four different times with four different groups would put you in four different groups.

Group Discussion Information Sharing
- There are many situations to discuss in groups, not only in Open Space Technology.
- There is a strong need to "know what other groups are discussing."
- But information sharing there is not smooth.
- How can I get a good summary of the conversation in a group discussion to be shared?
    - ![image](https://gyazo.com/b396aeb578a17b1fcfb5309bb84680dd/thumb/1000)
    - For example, one participant in each group will record the event with his/her smartphone and upload it to YouTube unlisted after the event is over.
    - YouTube will do the transcription for you.
        - So far, at this point, we already have the tools and can make it happen operationally.
    - Transcriptions are collected programmatically and summarized by AI
        - If you create a code to collect, you can create a summary report with Talk to the City.
        - It would be good to summarize with a link to the timestamp of the video so we can quickly check the original discussion.
    - Discovering that different groups are talking about related content and teaching the participants in each group
        - This is technically possible, no implementation yet.
- AI feedback in a few hours is possible at this point, and the time it takes will become shorter in the future.

[[AI-mediated communication]]
- ![image](https://gyazo.com/3aeba9eb57caa45165af87dccbc57406/thumb/1000)
    - New forms of communication being researched by Mr. Aoyama ([[Bluemo]])
    - from [/blu3mo-public/Intersubjective Model of AI-mediated Communication: Augmenting Human-Human Text Chat through LLM-based Adaptive Agent Pair](https://scrapbox.io/blu3mo-public/Intersubjective Model of AI-mediated Communication: Augmenting Human-Human Text Chat through LLM-based Adaptive Agent Pair) [https://arxiv.org/abs/2502.18201](https://arxiv.org/abs/2502.18201)
    - [[Intersubjective Model of AI-mediated Communication: Augmenting Human-Human Text Chat through LLM-based Adaptive Agent Pair]]
    - [https://arxiv.org/abs/2502.18201](https://arxiv.org/abs/2502.18201)
- Continued from "Sharing Information in Group Discussions."
    - The smallest form of "human group discussion" is "a conversation between two humans."
        - Productive discussions between two like-minded people are "very narrow but deep cooperation."
    - When AI is able to adequately replace humans, it will be able to have equally deep conversations on its own.
        - Time Constraints" are no longer a factor = Free from Time Constraints.
- "Group Discussion + AI" and "Human-AI one-on-one" both have advantages and disadvantages.
    - Group discussions provide an opportunity for "participation" even for those who do not proactively speak up.
        - Even if you don't have "something to talk about" from the beginning, you will find what you want to say as you listen to other people's discussions.
    - One-on-one between a human and an AI" doesn't require consideration of the other party's feelings.
        - No social risk that "the statement might worsen the relationship" [[psychological safety]].
- ![image](https://gyazo.com/e0cbca9528fb418c1248e823bbcfbba9/thumb/1000)
    - There are diverse forms of communication, not limited to "one-on-one human-AI".
        - AI An's town meetings are one of them.
    - AI participates in a variety of communication and loosely bridges the gap.

What is "scaling?"
- Making a small group bigger?
- Is it to increase the average level of activity in a society by creating many small, active groups?
- To [[loosely connect]] small groups of people with "information and communication channels that are neither 100% disconnected nor 100% shared"?

summary
- How to extend digital democracy "deeper and wider" for better social decision-making?
- It is necessary to divide democracy into elements rather than a single black box
    - Voting = writing one's name on a piece of paper," "one person, one vote," and "majority rules" are assumptions.
    - A history of questioning "conventional wisdom" from Classical Athens to the present day
- New voting and decision-making methods
    - Quadratic Voting/Quadratic Funding: Ideas to change the principle of one person, one vote.
    - Polis / Community Notes / Public Opinion Map: [[A mechanism for evaluating support from diverse entities]].
    - Talk to the City: AI visualizes and summarizes huge amounts of text
    - [[Trade-off between depth and breadth of cooperation]]
    - Open Space Technology: Networking through intense dialogue in small groups
    - AI Anno: Town meetings free from time and place constraints
- AI-based "hybrid dialogue"
    - Recording and transcription of group discussions → AI summary → Discovery of related discussions
    - New forms of discussion and psychological safety through "human x AI" communication
- Consider what "scaling" means.
    - It should not simply be about increasing participation.
    - Isn't the goal to improve the quality of "cooperation" by achieving deeper discussions and wider collaboration?
    - Enriching society as a whole by connecting many of the intense dialogues that occur in small groups
- Small Steps Starting at the Grassroots
    - Try Polis, TTTC, and [[Digital Democracy 2030]] internally and in the community.
    - Using transcription x AI summary at events and meetings [[Provide opportunities for those who cannot share the same time and place]].
    - We don't wait for someone else to make it for us, but introduce it ourselves, little by little, to suit "our place".





--- memo
# Making
### ver.2
I had exactly 20 minutes to practice my presentation, but I somehow got 15 minutes for my presentation. w

### cut from ver.2
Concept of [MetaPolis

Visualization is not the end of the story.
Hopefully after seeing the visualization, people will be inspired to speak up by it.
- Discussions "build up".
- A system where a common ground for discussion is created and improved.


### ver.1
Democracy [[scalability]].
- [[digital democracy]]
- [[Community]]
[[Polis]]
[[Community Notes]]
How to achieve [large-scale collaboration

- [[XY problem]]
- [[Four Steps for Deliberative Discussion]]

- [[There are two opposing axes between the three ideologies.]]

[https://chatgpt.com/c/67852ca0-16c0-8011-b292-250d1237518b](https://chatgpt.com/c/67852ca0-16c0-8011-b292-250d1237518b)

About Polis and Community Notes, technologies for scaling democracy

Replies do not scale.
- 1000 replies to one person's post
    - There's no way you can read.
    - And there's a high percentage of verbal abuse.
        - Mute all together
    - This mechanism is not enough for useful opinions to be exchanged and discussions to deepen.
TTTC
- Advances in LLM have made it possible to filter out rhetoric and group similar opinions
- You could say it's just visualization.
    - What are the next steps?
    - It's hard to function if you just pass it on the web.
    - +Broadcast
        - Nittele Case Study
            - Human commentary included.
            - Can be used as a springboard or topic for discussion with an expert (in this case, a politician)
    - +Internal deliberations
        - Tokyo Case Study
            - As a major public comment
            - More information will be available on 1/31 and I'll write that.



Polis
- Some kind of novel UI
    - I won't let you reply.
    - Order is shuffled (information-maximizing algorithm, must be checked)
- Not yet rooted in Japan.
    - The "Public Opinion Map" is a mobile-first UI redesigned for the Japanese environment.
        - The introduction should have been done by Mr. Tonfi first, so I won't do it here.
    - The internal tally server and other functions of Polis are used as they are, while AI-based cluster commentary and party icons are displayed.
    - Between Boat Match and Polis, which are relatively well rooted.
        - Public Opinion Map 2024

[[Your Priorities]]
- UI that is a little easier to understand
- Submissions divided in favor and against.
- No direct replies.
    - [[Cotonoha]]
- The good ones get upvoted.

Community Notes
- matrix decomposition
    - What's the difference from majority rule?
    - Drawing and Explanation
- Meta, Fact Check
    - > On April 7, U.S. Meta announced that it will discontinue the use of independent fact checkers to examine the accuracy of posted content on its Facebook and Instagram sites. It will be replaced with a "community note" system that leaves comments on accuracy to users, similar to that used in the U.S. social media X.
    - [https://www.bbc.com/japanese/articles/cgkxky4vvg3o.amp](https://www.bbc.com/japanese/articles/cgkxky4vvg3o.amp)
    - Some people just cut out the "abolish fact-checking" part and say something like, "That's outrageous! but the way they cut it out itself is biased.
    - Fact-checking by a small number of people to determine what is correct does not work very well, is not trusted by today's social media users, is not efficient, etc., so it is better to "connect a large number of people with an algorithm to check correctness".
    - The following English-language papers on expert evaluations of COVID-19-related notes in community notes are available
            - "Do Community Notes work? A case study of COVID-19 related notes": in this study, COVID-19 related community notes posted between 2022 and 2023 were medical experts evaluated the COVID-19-related community notes submitted between 2022 and 2023 and found them to be 97% accurate.
            - This paper demonstrates that community notes are highly reliable in providing information on COVID-19.


A decent rebuttal.
- Emotional rebellion, outbursts


---
This page is auto-translated from [/nishio/デジタル民主主義をスケールさせるには？](https://scrapbox.io/nishio/デジタル民主主義をスケールさせるには？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.