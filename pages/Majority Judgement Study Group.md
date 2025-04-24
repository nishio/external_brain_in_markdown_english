---
title: "Majority Judgement Study Group"
---

2021-07-09  [[Cybozu Labs Study Session]]
- To summarize in three lines.
    - It is widely known among researchers that majority rule, "a mechanism for decision-making by multiple people," is seriously flawed.
    - Researchers consider "[[strategicity]]" a good trait. This is the idea that "lying is not beneficial. [Stupid is good, but lying is not.
    - In 2007, it was reported that "everyone rates the median on a 6-point scale and chooses the one with the best median" ([[Majority Judgement]]) is strategy-resistant. I present it to you today.
- I brought the knowledge to the front to get a rough idea this time, and the mathematical and academic talk came later.
- Previous: [[Mechanism Design Study Group]].

The [[vote split]] issue
- Introduce a situation in which "a majority of people do not like the decision" is reached by "choosing one of the candidates and voting by majority".
- In that situation, the Majorty Judgement shows that the majority's preferred decision can be made
- context setting
    - For a given agenda item P, 40% of people prefer option P1 and 60% prefer option P2
    - On the other hand, there is an agenda item Q, which is not as important as P. Both options Q1 and Q2 are supported by 50% each
    - There are three candidates A: (P1, Q1), B: (P2, Q1), C: (P2, Q2)
    - ![image](https://gyazo.com/d84911dd7a82029d0a57ea4dcc0fc5e0/thumb/1000)
- Take a majority vote.
    - Mechanism: Each voter selects one person whose opinion is closest to his or her own and votes for that person.
    - ![image](https://gyazo.com/2e2915f11f376e2627853128931cf0f5/thumb/1000)
    - Candidates B and C each get 30% of the vote
    - Voters (P1Q2) who did not find a candidate that matches their preferences vote for candidate A who is closer to their opinion
    - ![image](https://gyazo.com/3b05c765cabd59547f5b0097ab8715bf/thumb/1000)
    - As a result, A gets 40% of the votes and takes first place
        - 60% of people wanted P2 to be chosen, but P1 was chosen.
        - A majority vote can make a majority unhappy.
    - What's wrong.
        - Even if the person who chose B thought "I'd rather be C than A," there's no way to express that in a method that designates a single candidate.
        - A vote for B is equivalent to "if not B, then A or C".
    - Distortion on the candidate side
        - It's easier to get votes if you appeal to the options that the other candidates have not chosen, rather than the options that he or she truly believes are better.
        - It is a mechanism that encourages people to make untrue statements (to lie).
    - Distortion on the part of voters
        - A person from Faction B might say to a person from Faction C, "If we don't do this, the vote will be split and A will win, we have to vote for B, not C!" and solicit them to vote for B instead of C.
        - Behavior that encourages people to vote (lie) for someone who is not the candidate they truly believe is better.
    - strategicity
        - Majority rule can be strategically manipulated.
            - Strategic manipulation is to make the consequences more favorable to oneself by making statements that differ from the truth
            - I lie because it's more profitable to lie.
        - = Majority rule is not strategy resistant.
        - Is a strategy-resistant social choice mechanism (a mechanism that brings together everyone's opinions to choose one of several options) possible?
- Make a Majorty Judgement
    - How it works: Everyone rates on a scale of 6, with the median being the best.
        - The meaning of the number 6 is discussed below.
    - For example, "6: Very good, 5: Good, 4: Somewhat good, 3: Somewhat bad, 2: Bad, 1: Very bad".
    - Voters rate all candidates on a 6-point scale
        - ![image](https://gyazo.com/c16a8d2a92c8e4cb31b1588a3f1c39fe/thumb/1000)
    - aggregation
        - ![image](https://gyazo.com/eaaa33fe506c256e32a2565fba348613/thumb/1000)
        - A is "6: very good" (20%), "5: good" (20%), and "2: bad" (30%), so the median is "2: bad
        - B is 30% "6: very good" and 30% "5: good", so the median is "5: good" (C is exactly the same)
        - Thus, B and C are tied for first place.
    - Majorty Judgement cannot lie and move his social reputation in this direction (see below).

change-over phenomenon
- Related story.
    - For example, let's say you're talking about changing part of your company's office to be used for other purposes.
    - We had a discussion about how to change it and came up with a lot of ideas.
    - Each proposal was untenable, so we decided to put it to a vote of the employees.
    - I inadvertently put "no change" in that ballot item.
    - Composition: A: do not change, B: change, C: change
    - The vote to change it was split between B and C, and the vote resulted in a "no change" vote.
    - 'Oh, no? I thought the majority wanted to change it?"
- There are multiple ways to change it, but only one way not to change it, so when you take a poll like this, "don't change it" tends to be the choice
    - For example, unless you vote first on "change/no change" or have a "change is good" kind of corporate culture, you'll end up with a company that won't change.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q: Can it be "no change" if there are many people who say "I would like to change to proposal B, but I would not change it (proposal A) so that it becomes proposal C (and vice versa)" (and those who prefer C and prefer A over B)?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>be capable of becoming
    - Example
        - B6 A4 C2 40%
        - C6 A4 B2 40%
        - A6 B2 C2 20%
    - In aggregate, these are
        - Proposal A 6 20% 4 80
        - Proposal B 6 40% 2 60
    - A is selected as "4: Somewhat good

Consider real-world applications
- 6-level rating is not difficult to express in the WebUI and not difficult for users to operate
- Doesn't that take a lot more time than voting for one person?"
    - The authors tested MJ on 12 actual candidates by the side of a polling station during the French presidential election.
        - Most subjects voted in less than a minute.
            - Less than 5 seconds per candidate
            - It is a 6-point scale for each candidate, so you can make a decision for each candidate. No need to think, "Which is better than the other candidate?"
        - Voter satisfaction was high with the ability to state, "Not this candidate."
            - It has to do with this, which I explained at the majority vote.
                - > A vote for B is equivalent to "if not B, then A or C."
            - Voters often have the opinion "I don't care if it's B or C, just not A", but the "choose one of the candidates and vote by majority" system does not convey this
- Meaning of 6 in "six steps."
    - As a mathematical model, it can be any number of things.
    - It can be "scored on a scale of 0 to 100."
    - In an experiment for the French presidential election, 12 candidates were rated on a 6-point scale, but 86% of the respondents used only 5 types
        - So, the authors believe that most people will only use a portion of it, even if it is more detailed than this.
        - For example, if you ask people to give a score out of 100, they will use a coarse scale, like "this one gets a 60, this one gets an 80.
    - What it means to be even
        - The authors believe that the lack of a neutral rating like "neither" makes it easier for differences to be expressed as "dare I say good or bad?"
        - This is not experimentally verified as good or bad, but merely the authors' interpretation.
        - It could be interpreted that the lack of a neutral option distorts the message by forcing people who really have neutral feelings to twist it into something good or bad, instead of accurately expressing their feelings.
        - I guess it doesn't matter either way, since the distortion in this case is not much compared to the severity of the "choose one of the candidates and vote by majority" (Nishio's interpretation).
        - In the "determine the initial value of the vote" pattern described below, it is more convenient to have a neutral value.
    - If we use two steps, the structure will be the same as that of [[Approval voting]] proposed in the 1970s.
        - Increasing the number of steps can be interpreted as increasing expressiveness.

Functions as a lie-free questionnaire
- No point in analyzing a survey if it's mixed with lies [Tweet](https://twitter.com/absinthe9999999/status/1407881914317373443)
    - > A resigning employee said to me, "I always gave the highest score on the internal survey mechanically because I didn't want to be told anything by my supervisor. I've been doing it that way ever since I started thinking about quitting." The morning is about to end with an MTG where the survey supervisor who heard the message shuts down and no remedial action is taken.
    - > This is one answer to the "why is it a problem that people are leaving when engagement is not declining from the survey results?" but it seems to be difficult to accept from those in charge.
    - >  But I think it's [[a flesh-and-blood person]] who does this kind of thing.
    - > While the survey design is anonymous and supervisors cannot directly identify respondents by name, a small team, such as five or fewer people, will be asked, "Did you answer negatively? What was the reason?" However, in small teams of less than 5 people, it is not clear whether everyone will answer honestly because the survey is anonymous.
- Honest answers are damaging = gain by lying = not strategy resistant
- Analyzing data collected by non-strategic mechanisms is difficult to interpret because the distribution of values is misaligned from the true distribution to begin with.
- Majorty Judgement voting results can also be used as a 6-point rating questionnaire for each option
    - Good quality data with no lies
    - However, you can't hear everything you want to hear.
- Q: So this example was an incentive not to vote honestly by leaking information about the vote to the supervisor, but wouldn't it be the same in MJ if the information is leaked?
    - A: Of course. In addition, even if no information is revealed, if there is no benefit to be gained by answering the question, it is "a loss of effort to take it seriously," so I don't take it seriously.
        - The basic premise is that there is an incentive to respond seriously, for reasons such as the distribution of resources within the organization depending on the results of the answers, etc. In addition, if a strategy-resistant method is used, the data gathered there can also be the results of a survey without distortion.

(a) summary
- With respect to the mechanism for bringing together the opinions of several people to make a decision, the traditional majority rule tends to be used: "Vote for the candidate you think is the best and take the one with the most votes.
    - This has the problem of vote splitting.
    - It's also a mechanism that gives you an advantage when you lie.
- The mechanism of the Majorty Judgement was introduced: "Rate each option on a scale of 6 and choose the one with the highest median value.
    - This is not a vote-splitting issue.
    - Lying is not advantageous (see below).
- Data mixed with lies is useless.
    - MJ also functions as a questionnaire that does not contain lies.

strategicity
- Math gradually from here
- What does it mean that "lying is not advantageous" in MJ?
- When your reputation is higher than your social reputation as determined by MJ, you can't fish your social reputation out of the water by lying.
    - ![image](https://gyazo.com/71033fdd8b9ce54b2e6f8f1d5acbc34e/thumb/1000)
- The reverse is true as well, and you can't drag down your social reputation.
- You can "lie and lower your social reputation when you value yourself more highly than society values you."
    - But I won't do it because it's a loss for me.

    - ![image](https://gyazo.com/9710b18fe00f83ffdfc348f95c6f65b9/thumb/1000)
- This is a common feature of rank functions
- Only rank functions?
    - If we let the evaluation vocabulary be an interval of real numbers and assume continuity of aggregate functions, then the rank function is the only function that satisfies strategy resistance, anonymity, congruence, and monotonicity
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I guess mathematically it's valuable that the theorem was proved, but realistically it's hard to imagine that the evaluation vocabulary is an interval of real numbers, and if the evaluation vocabulary is a finite set, we can make examples other than rank functions, so I'm not too thrilled 🤔.
- Why use the median function when there are many different rank functions?
    - When the majority evaluation is unanimously r, there is a property that the social evaluation is also r.
    - Only the median function has this.
    - If voter dissatisfaction is defined as "discrepancy between one's evaluation and social evaluation" and minimized, it is still a median function
- If you want to follow this area of the story mathematically, "From One Person, One Vote to Majority Judgment" [PDF](http://www.orsj.or.jp/archive2/or57-06/or57_6_295.pdf) is a good explanation.

- Relation to [Boulder Rule
- In Boulder Rule, voters rank each candidate.
    - Then, the higher the ranking, the higher the score, and the winner is determined by the sum of the scores.
    - [https://ja.m.wikipedia.org/wiki/ボルダ得点](https://ja.m.wikipedia.org/wiki/ボルダ得点)
    - ![image](https://gyazo.com/6419b00fbf2a3d4fde0af56138be74f7/thumb/1000)
- Sometimes presented as an improvement over traditional voting, but weak in terms of strategy resistance
    - For example, let's say there are five candidates on the ballot, A through E, and only two of them are decent candidates, A and B, and the rest are bad guys who would massacre a certain ethnic group.
    - For simplicity's sake, let's assume there are three voters, two of whom are in the A camp and one of whom is in the B camp.
    - If you vote honestly, A wins.
        - ![image](https://gyazo.com/c52d6a383dce63a988a555f33cbac980/thumb/1000)
    - Here, if the B faction lies and says that A is even less preferable than the extremists, B wins.
        - B-ers lie because it's more advantageous to them.
        - ![image](https://gyazo.com/e5157d1f4bc7752bfcc027e9e5872cde/thumb/1000)
    - It is undesirable for group A to win by having only group B vote strategically.
        - So let's assume that group A did the same and strategically voted that "B is even worse than the extremists"...
        - ![image](https://gyazo.com/920c5f66b708aee0522f92f23b819ce4/thumb/1000)
        - What a bunch of decent candidates dragged their feet and an extremist that no one wanted won!
- Comparing Boulder Rule to Majorty Judgement
    - N candidates rated in N steps with the same value prohibition corresponds to the Borda score
    - In Boulder Rule, take the sum of these, in MJ, take the median.
    - In short, a kind of [phenomenon where the mean is affected by outliers
    - If the aggregation method is the median, then the attack you just made [["B-ers lie and say that A is even less desirable than the extremists"]] would no longer be valid.
        - The median of 5,5,1 is also 5.
        - ![image](https://gyazo.com/98b8b8fdeece4402f4b2335ed43c0c43/thumb/1000)

Try to make it with kintone
- ![image](https://gyazo.com/76d0cbf4f097adfef0a617c56917b5c7/thumb/1000)
- ![image](https://gyazo.com/a8dd4a46c198bd46de65b223f1e224f7/thumb/1000)
- ![image](https://gyazo.com/b1f60667d7b764255a3afd26c57a5124/thumb/1000)
- Aggregate by number of records and sort in ascending or descending order rather than by "aggregate value".
    - Then the 6 o'clock position on the pie chart would be the median.
    - I thought the trick was to put the number at the beginning of the radio button choices, but I was wrong.
        - Sorting is by order of choice, so 6 comes first in ascending order.
        - It doesn't matter that I put the number at the beginning.
- I suppose we could aggregate for each of the multiple options.
    - It's done.
        - ![image](https://gyazo.com/1c753d70f5991245592b218e234f7508/thumb/1000)
            - It's weird that the order of the legend and the color order of the stacked graphs are reversed, but...
            - The color scheme might look better with a heat-map-like gradient.
    - Just look at the 50% line and make a decision.
        - In this case, since both 50% lines are "rather good", plan B wins with the highest "number of votes above the median".
            - ![image](https://gyazo.com/c62cce74b55261a79b82755551807737/thumb/1000)
            - Actually, it would be better if the choices were sorted based on this ranking, so it would be easier to see which one is in first place, but I couldn't figure out how to do it.
                - Is it indeed necessary to use JS customization?
- Could not figure out how to limit one vote per person for multiple choices.
    - Especially what to do if there are "people who voted for Proposal A but not for Proposal B".
        - Proposal 1: Only counting all votes cast as valid votes.
            - I'm sorry to hear about the invalid votes due to an inadvertent oversight.
        - Proposal 2: Make it the median among those who voted.
            - I did so anyway in the above implementation, but wouldn't some kind of strategic manipulation be possible in this case?
        - Proposal 3: Make the choices odd-numbered, with no vote being neutral.
            - I think this is a sure thing.
            - Records for all voters are added in batches by the administrator, by neutral ballot.
            - Voters make edits whenever they like.
            - Just make sure you have admin rights to add records to the app.
                - The public can only browse and update
                    - ![image](https://gyazo.com/380806f458ab5b045ebc85fb96bf72b2/thumb/1000)
                - Furthermore, if you only have access to the records for which you are the designated voter, you will not be able to view other people's votes.
        - Proposal 4: Put them all in one record and make them all required answers, so there will be no partially voted status.
- Is it safe to publish the results during the process if it is strategically resistant?
    - If you're going to go to the trouble of using kintone to view aggregate data, it would be more interesting to visualize "how everyone is feeling at the moment" in real time.
        - Maybe that will further stimulate discussion?
        - Can I change my vote after hearing the discussion?
            - Something along the lines of, "At first I thought Plan A was very good, but I changed my mind when I heard the criticism."
- The assumption is that all those eligible to vote are told that the vote is being taken.

Relationship to Arrow's impossibility theorem
- Q: Hasn't it already been proven from [[Arrow's impossibility theorem]] that a vote of good nature is impossible?
- A: The theorem is a model in which voters give their preferences as a message
    - The "candidate B is preferable to candidate C and candidate C is preferable to candidate A" kind of thing.
        - MJ does not. One that expresses the desirability of each candidate on an ordinal scale (e.g., a value on a 6-point scale or a real number from 0 to 100).
        - Assuming that the meaning of this scale is shared among the voters, I think a rating of about 6 is a roughly realistic assumption.
    - Candidate B is preferable to Candidate C, and Candidate C is preferable to Candidate A" has no information on whether C is so good that it just barely loses to B, or so bad that it is not good at all and just barely beats A.
        - MJ's method can gather more information.
    - Some argue that Arrow's "independence from unrelated candidates" is too strong a request.
- To begin with, Arrow's impossibility theorem is not about strategy resistance.
    - Strategic resistance is involved in the [[Gibert-Saththwaite theorem]].
    - This is another mechanism that uses preferences as a message.

Discussion after the presentation
- A story about the many different patterns of majority rule.
    - [[Doubt the majority vote.]]
    - I'm comparing various scoring rules.
        - ![image](https://gyazo.com/44c42ffb3439544d86a1b14476bfa95a/thumb/1000)![image](https://gyazo.com/1b9a369478ed10a577152aac2809db29/thumb/1000)
            - p.58-59
- In fact, the author of this book [[Toyotaka Sakai]] is also the author of two reference books introduced in the previous [[Mechanism Design Study Group]].
    - 2008  [[Mechanism Design (Book)]]
    - 2015  [[Doubt the majority vote.]]
    - 2016 [The Bordal Rule, the best alternative to majority rule | The Economics of "How to Decide" | Diamond Online](https://diamond.jp/articles/-/96679)
        - > Majority rule has the fatal flaw of "vote splitting," which means that it does not even reflect the majority opinion... Therefore, Toyotaka Sakai, author of "The Economics of 'How to Decide'," proposes the "Bordal rule" method as an alternative. This is because it is "the method closest to unanimity.
    - 2019 [Twitter](https://twitter.com/toyotaka_sakai/status/1166885111838593024)
        - > Majority Judgment (MJ), which we will cover in tomorrow's Auction Lab. MJ is amazing. I used to think that social choice theory was for "election systems" and "polling methods," but now I can use it for business.
    - 2020  [[Win by mechanism design]]
- I asked a question and got an answer.
    - > nishio: I saw your 2015 "Doubting Majority Rule" 2016 "The Best Bordal Rule as an Alternative to Majority Rule" (Diamond Online) and 2020 "Winning by Mechanism Design".
        - >  Do you still think Boulder Rule is the best alternative to Majority Rule? Or do you think Majority Judgement is better?
    - > [toyotaka_sakai](https://twitter.com/toyotaka_sakai/status/1415316449531359242): as the number of choices increases, Borda is well aware that the difference between "each person's first and second place" (and its effect on the outcome) converges to zero. I feel that it is not. As a theorist, I should be clear in what sense it is "not good" and "feels" should be in the form of a theorem. But we have not done so.
        - > From a strategic operations standpoint, MJ is much better than Borda. So if I had to choose between MJ and Borda, it would be MJ. The reason why I didn't appreciate MJ so much before is because MJ is very different and cannot be described within the traditional Arrovian Social Choice framework. It took me a long time to accept it.
        - > The beauty of the Bordal rule, however, is that it can be conveyed in less than 10 seconds using only words: "The Bordal rule distributes 3 points for first place, 2 points for second place, and 1 point for third place. It can be communicated on the radio and in newspapers; MJ cannot be communicated on the radio or in newspapers; MJ can be communicated with a video, but it takes a minute of time that I can use to explain using a flip-flop.
    - > nishio: thank you for your answer! i personally like the fact that MJ made the voter's message more informative than the traditional preference order, but in theory, not following the traditional model led to the difficulty of acceptance. the difficulty of explaining MJ is a matter of having more experienced people. I think that time may solve the problem if we increase the number of people with experience.

pair-loss criterion
- Pair loser criterion: the property of not choosing a pair loser (a candidate who loses in any pair when two candidates are chosen)
- In "Doubting Majority Rule," it is assumed that only Boulder Rule satisfies the paired loser criterion.
- Q: Does MJ meet the pair loser criterion?
- A: The candidate who loses in any pair in MJ is the candidate with the lowest median value, so of course he/she loses overall (= satisfies the pair loser criterion).

---Notes below
majority rule
discrepancy between votes
Naming the majority vote
Seems like the majority would be happy, but it's not.

5 to 7 steps
It doesn't matter how many steps you take.
A two-step process is called an endorsement vote.
Historically, endorsement voting was studied in 1970, and an improved version of it is MJ

tie break
- Decide by the number of votes above the median.

Radical Opinion
Easier to get votes because there are no other candidates around with similar views.

median
- Strong strategic operation
- It's less susceptible to outliers.

Data containing lies is worthless.

No ideal voting system exists.

French presidential election
- [[What is a lie?]]


[Majority judgment - Wikipedia](https://en.wikipedia.org/wiki/Majority_judgment)

[Tactical voting - Wikipedia](https://en.wikipedia.org/wiki/Tactical_voting)


From One Person, One Vote to Majority Judgment [PDF](http://www.orsj.or.jp/archive2/or57-06/or57_6_295.pdf)
- > Recently, Balinski and Laraki have proposed a method called Majority Judgment to overcome the problems of conventional one-person-one-vote voting and social choice based on individual preference order. This paper introduces their discussion of its theoretical validity.
Keywords: one-person-one-vote, election, social choice, Majority Judgment, Arrow's theorem, rank function
- non-limitability of the domain of definition
- identity
- non-dictatorship
- Arrow's theorem
    - When there are more than three choices, there is no social welfare function that satisfies the above three
- Evaluation by common vocabulary
    - As long as the order is in the common vocabulary and the meaning is shared.
    - Or any real number between 0 and 100.
    - Social evaluation function
        - Properties to have
            - neutrality
            - Independence from irrelevant objects
        - If this is satisfied, then an aggregate function exists.
    - aggregate function
        - Properties to have
            - anonymity
            - identity
            - monotonicity
        - Strategic Operability
            - Strategic Operations
            - strategic inoperability
        - The rank function satisfies all the requirements
            - Why the ranking function satisfies strategic inoperability
        - Are there other functions that satisfy the request?
            - If the evaluation vocabulary is an interval of real numbers and continuity of the aggregate function is assumed, then only the rank function satisfies the requirement
        - On the manipulation of valuations without motive
            - There is at most one person who can raise or lower the social rating
            - At most one person can manipulate the evaluation, and the only aggregate function that can be manipulated by at most one person is the rank function
            - Note: Continuity is assumed.
                - If the vocabulary is a finite set, there can be other aggregate functions that satisfy the condition
    - So what order is best?
        - The property that when the majority evaluation is unanimously r, the social evaluation is also r.
            - Only the median has this.
        - If we look for an aggregate function that minimizes dissatisfaction with the discrepancy between one's own evaluation and the social evaluation, we find the median value.
- social experiment
    - An experiment with voters in the French presidential election
    - The candidates are the actual 12
    - Solicit to experiment on those who come out after voting.
    - 74% of 2383 people participated in the experiment
    - 1733 valid votes
    - I rated it on a scale of 6, but 86% used only 5, so that's good enough for me.
    - Most votes last less than a minute.
        - Satisfaction of being able to vote negative.


Balinski, M. and Laraki, R., 2007. A theory of measuring, electing, and ranking. Proceedings of the National Academy of Sciences, 104(21), pp.8720-8725.
[PDF](https://www.pnas.org/content/pnas/104/21/8720.full.pdf)
- Arrow's impossibility theorem
    - Satisfactory methods do not exist in the traditional voting model
- More realistic model
    - Laplace and Galton Origin
    - New Ways to Avoid Impossibilities
    - Realistically feasible methods
    - Majority Judgememt
- social choice
    - Collect multiple individual evaluations into a single evaluation
    - Two applications.
        - Voting: For example, choose one candidate from several, or choose one from several options.
        - Jury Desicion: for example, a jury decides the grade of wine or the score of a figure skating competitor
- Social Decision Function SDF
    - Takes the voter's message as input and returns the ranking of the winner or candidate
    - There are many variations.
- traditional model
        - Methods of [[condorcet]] 1299
        - [[Boulder Rule]] 　1433
    - Voter-ordered model
    - The meaning of the order is ambiguous.
        - There are three ways.
- real world
    - The voter's message is simply a message, based on preference but not on itself
    - [[Arrow's impossibility theorem]]
    - Based on the traditional model of voters expressing preferences
    - We have shown that there is no social rehabilitation function SWF that combines the three basic characteristics
        - Except in the case of two options
        - [[Amartya Sen.]]
        - Model in which voters enter real values
        - Utility, not preference
        - Interesting but impractical, utility complex concept
        - Arrow's impossibility theorem reproduced
            - Unless the utilities are comparable.
        - This model was used to prove the [Gibert-Saththwaite theorem
            - There is no social choice function where the dominant strategy is for voters to express their true preferences.
    - If the output is rank ordering, shouldn't the input be a preference for OVER rank orderings?
    - Various suggestions
        - Lull's Proposal Condorcet
        - Cusanus Proposal Boulder
        - approval voting
    - claim
        - 1: Arrow and other impossibility theorems indicate no solution in the traditional model.
        - 2: Traditional models don't adequately model the message or purpose in the first place.
        - 3: We need a new model.
    - The application of reality suggests another input.
        - Olympic figure skating, or wine ratings.
        - kelvin
        - Voting and Markets
            - Expression with money
    - lingua franca
        - Even if you personally prefer the wine, you may give it a lower grade.
        - In other words, input is not a preference but a rating by common language
        - Arrow's impossibility theorem is caused by the absence of a common language.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>This "common language" is written in such a way as to highlight the differences from the existing model, and it may make some people think, "Isn't a common language impossible? I think some people might feel like, "Isn't it impossible to have a common language?
        - If hypothetically we were ranking on a 100 point scale and everyone was using 40-60 and Mr. A outputs 80-100, what would happen?
        - All of Mr. A's messages will be ranked first, and the only effect will be to pull up the median by one.
        - In other words, messages that are far removed from the common language are simply less informative.
        - Realistically, a common language is something like a 6-point scale, so there won't be too many serious differences.



[https://www.kyoto-su.ac.jp/graduate/tsushin/t_ec/econ-journal/ronbun/pdf/ronbun07_04.pdf](https://www.kyoto-su.ac.jp/graduate/tsushin/t_ec/econ-journal/ronbun/pdf/ronbun07_04.pdf)




Characterizing Aggregate Functions [PDF](https://www.bunkyo.ac.jp/faculty/business/feature/journal/pdf/vol3/business_journal_vol3_02.pdf)
- > In this paper, we point out a problem with the aggregate function that plays a central role in the Majority Judgment proposed by Balinski and Laraki, and show that it can be resolved by relaxing the condition of strong monotonicity. Furthermore, we show that the aggregate function is uniquely determined by the social evaluation when the evaluator's evaluation is widely divided.

---
This page is auto-translated from [/nishio/Majority Judgement勉強会](https://scrapbox.io/nishio/Majority Judgement勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.