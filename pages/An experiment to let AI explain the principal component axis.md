---
title: "An experiment to let AI explain the principal component axis"
---

2024-10-22
- Experiments were conducted using data from [[Polis-like visualization of the 2022 House of Councillors election]] to have the AI explain the principal component axis.


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
We want to generate a commentary on the principal component axis. The numbers are the coefficients that the question contributes to the first principal component axis. Explain what this axis is.
...
(Data here: [https://gist.github.com/nishio/217ab567c91926df9d5d07c337ce447f](https://gist.github.com/nishio/217ab567c91926df9d5d07c337ce447f) )

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
We see that this principal component axis reflects hard-line positions on economic and defense/security policies. In particular, it contributes significantly to economic structural reforms, such as curbing pension and healthcare costs (Q3_2), reducing protection of uncompetitive industries (Q3_3), and continuing monetary easing (Q3_5), as well as strengthening defense capabilities (Q4_1, Q4_2, Q4_3). In addition to this, conservative policies such as visiting Yasukuni Shrine (Q4_6), Henoko relocation (Q4_7), and even maintaining nuclear power plants (Q5_6) also have high coefficients, indicating a conservative yet positive policy orientation toward fiscal consolidation, strengthening military power, and maintaining traditions as a whole. On the other hand, they show opposition to liberal themes such as adherence to the three nuclear principles (Q4_5), married couples (Q4_24), and expansion of LGBTQ rights (Q4_25).

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In a nutshell, what is the first principal component axis?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The first principal component axis is the "conservative and hard-line policy orientation" axis.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What if we were to label both sides of the positive and negative?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>It is appropriate to label the positive side as "conservative/hardline" and the negative side as "liberal/tolerant".

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>(Do the same for the second principal component axis)

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
This principal component axis contrasts social and economic liberal and conservative positions.

First, items that have a positive contribution to mainly liberal policies appear strongly. For example, Q4_18 "Permanent foreign residents should be allowed local suffrage" (+5.04) and Q4_17 "Foreign workers should be allowed" (+3.74) strongly show positions in favor of immigration and multiculturalism. In addition, opinions that respect gender equality and diversity, such as Q4_24 "Married couples should be allowed to have separate family names" (+3.95) and Q4_25 "Same-sex marriage should be allowed" (+3.10), are equally liberal-leaning.

On the other hand, conservative policies show up as a negative contribution on this principal component axis. For example, Q4_6 "I want the prime minister to visit Yasukuni Shrine" (-4.73) and Q4_1 "Japan's defense capability should be further strengthened" (-4.56) indicate traditional conservative positions. Q5_7 "Government bond issuance should be curbed" (-4.84) and Q4_5 "Japan should uphold the three non-nuclear principles" (+4.45) also indicate a conflict between liberal and conservative viewpoints in economic and defense policies.

The major theme of this principal component axis is support for social liberal policies such as immigration, gender equality, and social welfare, while countering conservative defense and economic stability views.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In a nutshell, what axis is this principal component axis?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>This principal component axis is the "liberal vs. conservative" axis.

(E~~<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>)

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The first principal component axis was also liberal and conservative, looking for a different angle.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>This principal component axis can be thought of as a "market-based versus government intervention in fiscal and economic policy" cutoff. Specifically, it represents the conflict between a position that minimizes the role of government and emphasizes market freedom, and a position that actively intervenes by the government through welfare, public services, and fiscal spending.

For example, Q3_1 "Higher consumption tax rate" (+1.70) and Q4_13 "Higher taxation on people with high income and assets" (+2.53) are in favor of government intervention, while Q3_4 "Postponement of primary balance" (-3.27) and Q4_11 "Fiscal stimulus should be implemented as an economic measure" (-2 .59) indicate opposition to the position that government intervention should be restrained.

Thus, this principal component axis can be viewed as "[[market-based]] versus [[government intervention]].

----
impressions
- [Big government and small government.
- It is also possible to think that there is this traditional axis of conflict, or that the people making the survey questions are aware of it, so they include questions about it, and it is selected as the principal component because it has a large variance.
    - But maybe it's being reproduced by the political side positioning itself in that conflict.
            - [[Those who benefit from the difference have an incentive to maintain and expand the difference.]]
    - This analysis is based on the original data is a politician
            - [[public opinion map]] But since we have gathered data from about 1,000 people, it would be good to use that data to see the differences, since the questions are from party manifestos and the respondents are the general public.
        - Now, if you did a free submission Polis and did the same thing with that data, it might make a difference.
- When I first paid attention to the one-line summary, I thought, "Both sides are now conservative v. liberal, that's not funny..." But after reading the explanations, I realized that the "conservative v. liberal" axis that people think of as one axis of opposition may not actually be one-dimensional. I'm starting to get the feeling that this is not a one-dimensional axis.
    - In the experiment, I told the second principal component to change it by saying "make it something that isn't conservative v.s. liberal", but I'll tell the first principal component side to look for a different cut.

---
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>To find a different angle, it is useful to find an axis of opposition other than the traditional "liberal vs. conservative" one. Some possible axes include the following:

- Economic intervention vs. market-oriented
    - With regard to economic policy, one can set up an axis of positions that emphasize government intervention (e.g., emphasizing welfare and public works, strengthening regulations, etc.) and positions that state that market principles should be followed (e.g., liberalization, promotion of competition, tax cuts, etc.). In this case, raising the consumption tax, strengthening corporate taxes, and maintaining social welfare services would be in the direction of emphasizing government intervention over market principles, while emphasizing competition, deregulation, and fiscal discipline would contribute to the market-oriented side.

- Tradition-keeping vs. innovation-oriented
    - In terms of socio-cultural values, we can explore the opposition between positions that emphasize traditions and customs and those that promote innovation and diversity. Prayers to Yasukuni Shrine (Q4_6) and the relocation of the Futenma base (Q4_7) contribute to the maintenance of tradition, while advocacy for LGBTQ rights (Q4_25) and married couple surnames (Q4_24) are indicators of an innovation orientation.

- National Security vs. Human Rights and Individual Liberties
    - It could be centered on issues related to defense and security and issues related to individual rights and human rights. For example, the axis of conflict is between security-oriented positions such as enemy base attacks and defense buildup (Q4_2, Q4_1) and the emphasis on local suffrage for permanent foreign residents (Q4_18) and individual privacy (Q4_19).

- centralized versus decentralized power
    - We can also find an axis in terms of whether the central government should take the lead or emphasize local and citizen autonomy with regard to political decision-making. Centralization is emphasized in state-led measures such as fiscal and defense policies, while decentralization contributes to local participation and regionally driven policies (e.g., Q4_18, Q4_24).

By examining these axes, we may discover structures other than "liberal vs. conservative."

2024-10-25
Top 10 questions contributing to each axis

# PC1
Q4_2: 18.18: We should not hesitate to attack an enemy base if we expect an attack from another country.
Q4_18: -15.63: Permanent foreign residents should be allowed local suffrage
Q4_1: 15.40: Japan's defense capability should be strengthened further.
Q4_6: 15.15: I would like the Prime Minister to visit Yasukuni Shrine
Q5_6: -14.52: Nuclear power should be phased out immediately / Nuclear power should remain one of the sources of electricity in the future
Q4_27: -14.44: A quota system should be introduced to allocate a certain percentage of parliamentary seats and candidates to women
Q4_5: -14.37: The three non-nuclear principles should be upheld
Q4_7: 14.18: Relocation of Futenma base in Okinawa to Henoko is unavoidable
Q4_20: 13.01: Discharging treated water from Fukushima Daiichi plant into the ocean is unavoidable.
Q4_24: -12.98: The law should allow a married couple to each take their premarital surname after marriage if they so desire.

# PC2
Q4_2: -5.10: We should not hesitate to attack enemy bases if we expect attacks from other countries.
Q4_18: 5.04: Permanent foreign residents should be allowed local suffrage
Q5_7: -4.84: Government debt is stable and there is no need to worry about the budget deficit / The budget deficit is at a critical level, so government bond issuance should be controlled
Q4_6: -4.73: I would like the Prime Minister to visit Yasukuni Shrine
Q4_1: -4.56: Japan's defense capability should be strengthened more
Q4_5: 4.45: The three non-nuclear principles should be upheld
Q3_5: -4.39: BOJ will continue its quantitative easing policy, including JGB purchases
Q4_3: -4.28: Pressure should be prioritized over dialogue with North Korea
Q5_6: 4.23: Nuclear power should be phased out immediately / Nuclear power should remain one of the sources of electricity in the future
Q5_2: -4.14: China is a threat to Japan / China is a partner for Japan

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>PC2 has the same enemy base attack and nuclear power as PC1.
- I can see a way to use [[Sparse PCA]].

- [[AI Explanation of Principal Component Axis]]

---
This page is auto-translated from [/nishio/AIに主成分軸を解説させる実験](https://scrapbox.io/nishio/AIに主成分軸を解説させる実験) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.