---
title: "⿻Plurality and Plural Management Protocol"
---

2024-03-30 [[Namera Conference 4]] Lecture
- Cybozu Labs/Mitoh Incorporated Association Yasukazu Nishio

⿻Plurality Book
- "⿻ 數位 Plurality: The Future of Collaborative Technology and Democracy."
- [[Audrey Tang]] and [[Glen Weyl]] are writing a "[[book as OSS]]" on Github.
- The English version of the manuscript was completed on 2024-03-24. PDF is [here](https://github.com/pluralitybook/plurality/releases/tag/latest)!
- ![image](https://gyazo.com/849e79ba434c6ed6e748912659a1653d/thumb/1000)
    - It has been mentioned several times at the [[name-your-price conference]], but I'll take this opportunity to explain it for those who know nothing about it.

Audrey Tang
- Programmer, active in the open source community
- At 32 [[Sunflower Student Movement]] (2014)
    - > A social movement that began on March 18, 2014, when students and citizens of the Republic of China (Taiwan) occupied the Legislative Yuan (the Japanese equivalent of the National Assembly building). --- [Sunflower Student Movement - Wikipedia](https://ja.wikipedia.org/wiki/%E3%81%B2%E3%81%BE%E3%82%8F%E3%82%8A%E5%AD%A6%E7%94%9F%E9%81%8B%E5%8B%95)
    - Cable pulled, broadband connection, Live relay
        - Created a means of direct information dissemination sharing instead of existing media
        - > (Audrey) I supported the students' movement by [[live transmission]] online with members of [[g0v]] inside the Legislative Yuan, where the students were holed up. We connected the inside and outside of the Legislative Yuan with live cameras so that 20 private organizations could discuss human rights, labor, and environmental issues. Then we put together four demands in three weeks and proposed them to the Speaker of the Legislative Yuan. The Speaker of the Legislative Yuan at the time found the four demands to be reasonable and agreed to all of them. --- [Taiwanese IT genius who once occupied the Legislative Yuan talks about his roots | Gold Online](https://gentosha-go.com/articles/-/33224)
- Serve as [[Reverse Mentoring]] for the Minister
- Digital Minister at age 40 (2022~)

Glen Weyl
- At the age of 27, he proposed a [[voting mechanism]] called [[Quadratic Voting]](QV) (2012, preprint) (see below for details).
- At 33, proposed [[Quadratic Funding]](QF), a [[funding distribution mechanism]] for public goods (2018)(see below).
    - Co-authored with [[Vitalik Buterin]] of Ethereum
- Book [[Radical Markets]] (2018)
    - Many of you have probably read it since it was translated into Japanese.
- Establishment of [[RadicalxChange]] (2018)
    - Founded a non-profit organization for social change with Audrey and Vitalik
    - X" comes from [[Yukito Emaya]]'s [[interchange format]] (see below for details)
- Proposed [[an organizational governance mechanism]] called [[Plural Management]] this year.
    - January 2024 preprint release, freshly completed (the main theme of this issue).

- [[Miscellaneous Explanations of Exchange Styles]]
- [[Structure of World History]] (2010)~[[Yuuheng Theory]] (2014)~[[Study of D]] (2015-2016)~ [[power and modes of exchange]] (2022)
- 1:
    - They shared the food they took in a small group of blood relatives.
        - [[joint deposit]], [[reciprocal gift]], community, exchange style A
- 2:
    - The more people, the less successful it will be -> need a "governing" (RULE) mechanism
    - Protect if you obey, punish if you don't follow the rules, state, exchange style B
- 3:
    - Private "contracts" made possible by the power of the state to "punish you if you don't play by the rules".
        - If you break the contract, the state power retaliates against you, which creates a deterrent and protects the contract.
    - Currency, investment, markets, division of labor with faceless people, capitalism, mechanisms broader than the state, modes of exchange C
- Through the exchange style A -> B -> C, [[recovery at a higher level of exchange style A]] takes place, which is the X of Gyoto Karatani.
- RadicalxChange's superposition of meanings
    - Radical Markets→Radical Exchange
    - Radical x Change
    - Change to Radical X
- > (Audrey) Vitalik's "new mode of exchange" researched and developed on Ethereum allows an unspecified number of people to exchange for the public good. While this may at first glance appear to be for the benefit of the individual, it ultimately leads to a common understanding that it is for the benefit of the community as a whole. These are ways to utilize mechanism design, and I try to apply this to Taiwanese politics as much as possible... Why did you name this style of exchange RadicalxChange and not label it as Radical x Change in separate words? Because it was inspired by [[interchange format]] X, or "[[interchange format]]" as proposed by the Japanese literary scholar and philosopher [[Yukito Emaya]].
    - [Teachings and environment that nurtured "Tang Feng," Taiwan's Digital Minister: The words of his mentor and the education of his parents that made him a genius | Toyo Keizai education×ICT](https://toyokeizai.net/articles/-/363750)

Trade-off between depth and breadth of cooperation
- Key Concepts in the Plurality book
- ![image](https://scrapbox.io/files/657fc12e986d8d0025e6dce1.png)
- Vertical Axis: Depth of Cooperation / Horizontal Axis: Extent of Cooperation
    - Top left: familial intimacy: can't do it in large numbers
    - Bottom right: Broader relationships through the market: Shallow
- Depth vs. space is a trade-off.
    - Technology pushes this frontier (production possibility frontier metaphor)
- This is associated with [recovery at a higher level of exchange style A
    - The community / state / comodity in the figure corresponds to the exchange forms A/B/C.
    - > (Audrey) This trichotomy of [[interchange format]] into community, nation, and commodity was inspired by the work of [[Yukito Emaya]] in [[Structure of World History]] (2014). Emaya proposes a new mode of exchange, named "X," which seeks to transcend the limits of previous modes by fostering a global network of [[reciprocity]] and [[cooperation]]. --- [/plurality-japanese/gyojin emaritani and Plurality](https://scrapbox.io/plurality-japanese/gyojin emaritani and Plurality).
- The power of technology is creating a "new social system" that combines the strengths of "small communities based on reciprocal giving" and "large capitalist societies based on contracts.
    - This is the direction ⿻Plurality is heading.

Plural Management Protocol
- Various technologies are being explored to move in the direction of ⿻Plurality
- One of them is Glen's [[Plural Management Protocol]](PMP)
- Glen is not only proposing in the [[Plural Management]] paper, he is trying to validate it by actually operating it!
    - The Plurality book project itself is a PMP experiment.
    - Gov4Git (GitRules), which implements PMP, has been introduced to Github
    - Github Bot written in Golang
    - > A decentralized protocol for governing open-source communities based on git
        - [gov4git: Decentralized governance for git communities](https://gitrules.ai/)

Why PMP is needed
- Hierarchical organization problem: decision-making bottlenecks tend to occur
- Flat organization problem: difficult to act in a consistent direction
- It's a given, isn't it?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - "Let's work together on this project!" and a team is formed, but tasks that are important to the execution of the project are left unattended, while unimportant tasks are carried out.
    - In order to execute a project, you eventually need someone who sees the project as a [[personal affair]] and "picks up all the important tasks when they spill over", this is the leader
    - Leaders are essential for project start-up, but as the project is launched and grows in size, the leader becomes the decision-making bottleneck [[leader becomes the bottleneck]].
- Difficulty in evaluating and prioritizing contributions as the project grows, especially with OSS development
        - [[Tragedy of Common Land]] will be discussed. Source code is a resource that can be replicated at almost zero cost. What "limited resources" are being gobbled up?
    - When a bug report or pull request is sent in, the "assessment" of whether it is of importance to the project is high cost
    - If decision-making is not distributed, the load will be concentrated on the "leader," i.e., organization is necessary, but an engineer who is good at writing software alone is not necessarily good at organizing
- I propose a PMP to solve this.

PMP Mechanism
- Primarily a combination of Quadratic Voting (QV) and Quadratic Funding (QF)
- ![image](https://gyazo.com/470f14aa288673827449ebae4ac4130c/thumb/1000)
- Prioritization of issues (QF):.
    - Members use credits to prioritize assignments
    - If each member $i$ assigns $P_i$ credits, the priority of the assignment is
        - $\left(\sum_i \sqrt{P_i}\right)^2$.
    - The person who solves this task gets credit for it (QF principle, more on this later).
- Vote to approve contributions (QV):.
    - Members vote on whether or not to "adopt" the proposed problem-solving contribution with credit
    - At this time, $N^2$ credits are consumed to cast $N$ votes (QV principle)
    - (Forecast markets are also combined, but omitted.)
- Rewards for contributions:.
    - If the contribution is approved by a vote, the contributor is rewarded with "credits collected in priority setting.
    - Additional bonuses from matching funds.
    - Credits used to vote on approval of contributions are transferred to matching funds to incentivize new contributions

example
- PMP in Operation in the Plurality Book Project
- Priority setting of issues
    - ![image](https://gyazo.com/61aabde782f7a6b0f2c227499bb382df/thumb/1000)
        - QF against Github Issues in order of funds acquired.
    - ![image](https://gyazo.com/0cab73c154ff746854f67426bcc662e5/thumb/1000)
        - When you click "Vote" on an Issue, it looks like this and you can vote
    - Credits for voting
        - ![image](https://gyazo.com/5ba85fbc4c3794b078c091e872b36435/thumb/1000)
        - The degree of contribution to the project is quantified and information is shared
        - Like a game score board
        - It's also the in-game currency.
    - [e.g.](https://github.com/pluralitybook/plurality/commit/6e2695e4a9547c767bb2401590b07451fcd10874) of the proposed contribution.
        - ![image](https://gyazo.com/a278d132379139b4c839a15b0eb0ddf3/thumb/1000)
        - > `[^PICSY]`: An early implementation of such a value-propagating system is exemplified by PICSY, pioneered by Ken Suzuki in 2009.
        - I thought about whether I could insert the PICSY story somewhere and put a footnote at Liquid Democracy.
- Current status of the project
    - Now is still "the time for one leader to lead."
    - Glen is making contribution decisions and issuing new credits to contributors.
    - I haven't experienced the approval voting process yet.
    - Looking forward to seeing what happens in the future.

- [[Smoothing" of organizational management]]
- PMP creates a middle ground between hierarchical and flat organizations, decentralizing authority and decision-making in organizational operations
- Main differences from a hierarchical organization
    - If it were traditional OSS, it would be a binary of "a few trusted committers with commit privileges" and "ordinary people without commit privileges who can propose contributions without permissions".
    - Many hierarchical organizations also have "authorized" and "other" [[step functions]].
    - PMPs get credit based on their contributions and are given management privileges dynamically based on the amount of credit they receive.
        - For example, if you find a typo and make a pull request, you'll get about 1000 credits and be able to participate in the voting.
    - [[Smooth transfer of authority]]
- Main differences from a flat organization
    - In a flat organization, each individual tends to think about "what to do" and "what is the contribution" in a discrete way
        - In PMP, QFs collectively and intelligently prioritize issues and determine "what needs to be done.
        - In the PMP, the QV collectively and intellectually determines the acceptance or rejection of a proposed solution and "what is the contribution".
        - The act of pursuing personal gain to earn credits on PMP leads to the formation of collective knowledge in a cooperative game-like manner.
    - Meritocracy, where members' influence is linked to their contributions
        - It's not a [[one vote per person]] vote where the number of people determines your voice, and it's not a [[one dollar per vote]] vote where your voice is bought with money.
        - A greater voice is given to those "capable" of understanding the project's objectives and making a useful contribution.
    - Credit incentives to encourage participation and cooperation
        - As with traditional OSS, contribution proposals are accepted permissionless
        - I'm a total newcomer too, I didn't even know the repository existed until last October.
        - From there, a few months of activity
            - Look at Issues and think about how to get credit.
            - I found something that could be done, and I'll propose a contribution.
            - I was accepted and gradually got the hang of contributing, so I contributed more and more.
            - Their contributions are accumulated and visualized as credits.

Finally.
- I think this is a very interesting thing that is happening.
- The English version of the manuscript was completed on 2024-03-24 and we invite you to read it: [PDF](https://github.com/pluralitybook/plurality/releases/tag/latest)
- I'll publish a Japanese translation of the book from Cybozu Style Books, meeting with the translator scheduled for Monday.
- If you speak English, join the official Discord: [Invite link](https://discord.gg/db9spxpGJF)
- Support in Japanese here: [/plurality-japanese](https://scrapbox.io/plurality-japanese).


Below are unused fragments
- A mechanism that dynamically links contribution and influence is essential to both the active participation of members and the strategic direction of the organization.
- PMP is a method of governance that bridges the gap between hierarchical governance and market governance (a mechanism where everyone does as they please with individual incentives, resulting in a division of labor and cooperation)
    - Q: Why not market-based governance? A: If that were the case, there would be no need for organizations. The purpose of an organization's existence is to accumulate "resources that cannot be procured in the marketplace" within the organization, and to enable more efficient cooperation than the division of labor in the marketplace.

- It can be said that the PMP seeks to achieve flexibility and adaptability, strategic decision-making, and a cooperative organizational culture through dynamic allocation of authority based on contributions and the use of collective knowledge, while maintaining a balance between hierarchy and equality. As a new paradigm of [[organization theory]], the significance of PMP is significant.

- PMP's potential to bring about a paradigm shift in organizational management
    - PMP has the potential to bring about a paradigm shift in organizational theory through decentralization of authority and decision-making in organizational management
    - First, PMP challenges the assumptions of traditional hierarchical organizations by introducing a dynamic allocation of authority based on contribution and participation
        - Meritocratic system in which influence is determined by actual performance, not position.
        - Can be expected to increase members' motivation and commitment to the organization
        - It will also help eliminate decision-making bottlenecks and increase organizational agility and adaptability.
    - Second, PMPs have the potential to improve the quality of organizational decision-making by providing a mechanism to leverage the collective knowledge of members. By allowing members to anticipate organizational priorities and participate in the evaluation of their contributions, feedback from diverse perspectives can be obtained and more appropriate decisions can be made. In this regard, the PMP is noteworthy as a paradigm that facilitates organizational learning and evolution.
    - Third, PMP presents a new model of organizational management that encourages cooperation and the creation of public good through an incentive design called credit. This approach, which dynamically links individual gain with organizational benefit, sheds light on the issue of cooperation, which has often been overlooked in traditional organizational theory. what PMP suggests is the importance of mechanism design that links individual rationality and organizational rationality.

- Of course, PMPs have their challenges and limitations. Practical problems remain, such as friction with existing organizational cultures, new power relations among members, and the stability of credit economies. However, PMP's approach to challenging the dilemmas of hierarchy and decentralization, individuals and organizations, and competition and cooperation, can be evaluated as presenting new possibilities for a paradigm shift in organizational theory. It is hoped that a new paradigm for organizational management will open up through the continued development and implementation of PMP in the future.

---
This page is auto-translated from [/nishio/⿻PluralityとPlural Management Protocol](https://scrapbox.io/nishio/⿻PluralityとPlural Management Protocol) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.