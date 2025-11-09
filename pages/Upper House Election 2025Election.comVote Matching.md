---
title: "Upper House Election 2025Election.comVote Matching"
---

![image](https://gyazo.com/aa48471a2bd225711b50a68d5ab9e6f7/thumb/1000)
[https://votematches.go2senkyo.com/sangiin_2025/](https://votematches.go2senkyo.com/sangiin_2025/)

> [About the political parties and organizations listed
>  The following is a list of political parties and organizations that have responded to the Election.com policy questionnaire at this time.
>  Japan Reform Party is not listed because it has not responded at this time. We will post their responses as soon as we receive them.
>  This ballot matching is for political organizations that have filed lists for proportional representation in addition to national political parties that meet the party requirements. Political organizations that have candidates in only some electoral districts are not listed.
>  ● 27th House of Councillors Election Calculation of Vote Matching
>  The "distance" between the party's answer and the user's choice is used to calculate the degree of matching. For example, if Party A answers "Agree" and Party B answers "Slightly Agree" to a question for which the user chose "Agree," Party A will receive more points than Party B because of the greater distance between the two parties' answers.
>  *(7/13) We received a response from the Japan Seishinkai and have added it to the ballot matching.
>  *(7/6) We received a response from Team Mirai and have added it to the ballot matching.


2025-07-14
[https://www.facebook.com/kuchii.jun/posts/pfbid02n4znvqwg4Tr8g1FgDQiJqpE34ZMjFKrZpBAbXcnPkSwdsR92j1coe3LareSk1moXl](https://www.facebook.com/kuchii.jun/posts/pfbid02n4znvqwg4Tr8g1FgDQiJqpE34ZMjFKrZpBAbXcnPkSwdsR92j1coe3LareSk1moXl)
- Very interesting analysis (I wanted to do it myself, but I don't have time...)<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - Perhaps there has been a bias that "observed opinions are biased toward the radical side" due to the fact that "the more radical the opinion, the more likely it is to be communicated"
    - The political parties made policy decisions in accordance with the "radical distribution of opinion" based on that biased observation, and as a result, each party's opinion became more radical.
    - The distribution of opinions among "those who use vote matching" rather than "those who transmit opinions" was actually more "no strong opinions"
    - As a result, the probability of clustering users into parties that give moderate answers to radical so-called "ideological" questions of division may have increased
- This time, it's possible that it's [[vote matching optimization]] in a [[search engine optimization]] sense, although it's not being triggered for this itself (first published: [[Diary 2025-07-14]] , moved).
- I think we will have to have a discussion soon about what kind of vote-matching mechanism is preferable for the public. I think this disclosure of information by [[election.com]] is a good starting point for the discussion. (First published in [[Diary 2025-07-16]] , copied)

2025-07-20
20 5-step questions
Criticality Survey of Enforcement
> Of the following 20 questions you answered, please select three that are of particular importance to you. (Required)

If you choose all central, and the first three for the mandatory importance survey.
![image](https://gyazo.com/fbb439357de15a2d97337bddf90b4531/thumb/1000)![image](https://gyazo.com/f1a4b53fb5521f44a8064d1b2cad38ad/thumb/1000)

![image](https://gyazo.com/ec85b5ad86ce4150b322b660a7586c2d/thumb/1000)

![image](https://gyazo.com/86c2df70449c038db8d079eb4f7cdada/thumb/1000)

- After researching the phenomenon of Team Mirai being unexpectedly suggested by Election.com's vote matching, the observation was made that when neutral is selected for all answers, the match with Team Mirai is 79%.
- While public opinion as visualized on social networking sites is divided, the silent majority is more moderate, and Team Mirai's moderate responses to questions that are fueled by a policy of not fueling division seems to have matched those silent majority clusters as a result.
- Related discussions: [[Division and the Silent Majority]].

2025-07-24
- The opinion of a political party or user can be regarded as a point in a -2~+2 hypercube in 20 dimensional space
- Probably the Euclidean distance.
    - The three focus questions would expand that axis.
- Each party divides the space
    - By considering "everyone's aggregate result" as the amount of points in the space, we can roughly obtain the distribution of users' opinions.
        - It's messy to assume a uniform distribution within each space, but it should work.
        - I'm not sure if it's possible to consider it as a superposition of normal distributions and use the EM algorithm to estimate it.
    - Once the distribution has been estimated, we can calculate "how to change the answer to any question to increase support."
        - [[Vote Matching Optimization]]

---
This page is auto-translated from [/nishio/参院選2025選挙ドットコム投票マッチング](https://scrapbox.io/nishio/参院選2025選挙ドットコム投票マッチング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.