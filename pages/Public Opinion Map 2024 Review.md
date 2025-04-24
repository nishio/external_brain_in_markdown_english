---
title: "Public Opinion Map 2024 Review"
---

Draft for Open Data README
- > [nishio](https://x.com/nishio/status/1859790144238407737) A large-scale practical example in Japan (used by more than 4,000 people in the House of Representatives election) of Polis, which became famous through vTaiwan and other digital democracy activities in Taiwan, " The details of the "Public Opinion Map" are now available! An explanation in English will be available soon!
    - [yoronchizu2024-data/README_ja.md at main · mielka/yoronchizu2024-data](https://github.com/mielka/yoronchizu2024-data/blob/main/README_ja.md)


What is a public opinion map?
Public Opinion Map is a service released on 2024-11-18 by Mielka, a Japanese non-profit organization.
Mielka is a non-profit organization founded in 2016 that aims to develop democracy in Japan through youth-led "visualization" of politics.
We have been operating JAPAN CHOICE, one of Japan's largest election information sites since 2017, with 1.6 million users in the 2021 House of Representatives election.

The Public Opinion Map is an experimental new feature of JAPAN CHOICE that visualizes the distribution of public opinion by allowing users to anonymously vote on individual issues in each party's manifesto during the 2024 House of Representatives election.

Within about two weeks, 4403 unique users had voted. This repository is designed to convert that voting data into open data.

![image](https://gyazo.com/d7595b4a39368f9f25e68de0ebed574a/thumb/1000)


Technical Details
This service uses Polis, an opinion-gathering tool developed by Colin Megill and his team, on the server side. The usefulness of this tool became widely known when it was adopted by the Taiwanese government for its citizen participation project, vTaiwan.

The front end was redeveloped in full scratch for the Japanese situation: JAPAN CHOICE's access analysis showed that 85% of the 3 million unique users were checking election information in a mobile environment. Therefore, it was imperative that the site be usable on the narrow screen of a smartphone.

Two additional features include
- Visualize party opinions with party icons
- Explanation of clusters by LLM

Visualize party opinions with party icons
The public opinion map extracted the opinions to be voted on from the manifestos of each political party. In addition, data on whether each party was for, against, or neutral on each opinion was converted into data and displayed according to the distribution of users' opinions.
![image](https://gyazo.com/b6559660f0438f533d7b45f0ac2e4db4/thumb/1000)


Explanation of clusters by LLM
The concern was that it would be difficult for the average user unfamiliar with data analysis to read what the clusters in Polis meant.
We then gave LLM the data on "opinions that characterize a cluster" that Polis extracts, and asked them to explain what opinions people in that group hold. We also had them name the group by summarizing it in one word, which was also displayed on the scatterplot.
![image](https://gyazo.com/7235d2847d36e691d32a3fb02f6eaad4/thumb/1000)![image](https://gyazo.com/fc670261b4570f11d66d57cbddf53a62/thumb/1000)





Interesting Findings

Existence of opinion groups not represented by political parties
![image](https://gyazo.com/e67a0d78d10544d8b61a0ace32624b06/thumb/1000)


This figure is a visualization of opinion clusters on economic policy. In the lower right-hand corner, we can see that there is a cluster without a political party icon. This suggests that the opinions of this group are not well represented by the existing political parties and that the will of the people has not been incorporated into national politics. The AI's description of this group is as follows

> Team Yellow Price pass-through cautious
>  🤖 This team is relatively more cautious than other groups about achieving wage increases by helping small businesses pass on prices. It is also clearly opposed to lowering or eliminating the consumption tax and is skeptical of providing benefits to low-income households.

Relationship between the number of votes and the number of clusters

From the observation of the Polis results so far, there was a concern about the possibility of convergence to two obvious opposition structures over time. This is a phenomenon in which the PCA results of the opinion distribution converge to a lumped ellipse with no clear boundary as the data increases, and the cluster that divides into two in the direction of the first principal component axis is selected in the clustering by the k-means method at a later stage.

However, in this experiment with the public opinion map, we observed cases where the clusters split into four, even though 4,400 people voted. Since the opinions to be voted for in the public opinion map are derived from the manifestos of political parties, this is a feature that does not increase during the voting period. This suggests that the problem of convergence to a self-evident conflict structure is not caused by an increase in the number of users, but by the higher dimensionality associated with the increase in the number of opinions to be voted for.

In this experiment, statistics were recorded every hour. Below is the relationship between the number of voting users and the number of clusters. It can be seen that about 2,500 users were needed before the number of clusters finally converged to 4.
![image](https://gyazo.com/2f3c70f6cc66736bdcdac672ff08cedb/thumb/1000)


digital democracy
Mielka's side set the opinions to be voted on regarding digital democracy, which is not yet fully described in the manifestos of the various political parties. For this map, it was decided not to display party icons so as not to cause problems due to lack of data.

![image](https://gyazo.com/11ecabc24900627ba68c458e1786e440/thumb/1000)

explanation
> Team Red Ad Regulation and AI Skeptics
> 🤖This team supports regulation of targeted advertising and other aspects of the Internet, while taking a cautious stance on policy making and automation through AI. The team's position appears to emphasize regulation and careful implementation over the convenience of technology.
> Team Blue Digital Collaboration and Efficiency Promotion Group
>  🤖This team strongly supports the use of my number to link administrative data and increase efficiency through online access, with an emphasis on using digital technology to speed up administrative services. There is also a commitment to promote the introduction of wearable cameras and AI.
>  Team Yellow AI utilization and individual optimization group
>  🤖This team is active in promoting the use of AI to automate policy making and means of visualizing public opinion. The team also seeks to use AI to achieve personalized responses and efficient decision-making processes, including enhanced tracking of individual results.
>  Team Green Privacy Protectionist
>  🤖This team has a strong interest in the protection of personal privacy, supporting the protection of the right to control one's own information and the strengthening of privacy laws on a European level. It also supports the regulation of Internet advertising and is oriented toward democratic decision-making through a citizen-participatory agenda proposal system.


Improvements for future digital democracy

The task of extracting opinions from each party's manifesto so that there would be no bias was done by human beings. It was a nerve-wracking and arduous task. It would be good if LLMs could support this part of the process, but careful experimentation is necessary because of the serious consequences of halucination. An experiment was conducted with an LLM-generated public opinion map on digital democracy, but we did not use it because we judged that it was not of sufficient quality.

Because of concerns that the LLM's halcyonation during the election period would create misinformation unfavorable to a particular party, it took the form of a human review before publication, and was updated three times during the election period. This gives up the fun of real-time updating that Polis had.

The LLM tended to explain this cluster as "more agreeable". The expression of the data given to the prompts needs to be devised.

For the same reason, we did not accept user submissions. [Although "open up agenda-setting authority to the people" is an ideal to be achieved, accepting and reflecting the submissions in real time raises issues of quality assurance, countermeasures against misinformation, and higher dimensionality with the increase in the number of opinions to be voted on. Further research is needed.

---
This page is auto-translated from [/nishio/世論地図2024振り返り](https://scrapbox.io/nishio/世論地図2024振り返り) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.