---
title: "Mechanism Design Study Group"
---

- [[Cybozu Labs Study Session]]  2021-05-28
- [[mechanism design]]
book
- ![image](https://gyazo.com/c887895f175ad0c8ebb46252bf6cc879/thumb/1000)
    - [[Mechanism Design (Book)]] A book about doing things mathematically and properly.
    - [[Win by mechanism design]] A book like a transcript of a roundtable discussion, the content is biased towards auctions.

flow of this time
- I don't want to start from the definition of the mechanism, because I don't think I could spend an hour to get to an interesting story if I did it properly.
- First, a quick look at the applications
- Think of a specific algorithm for a specific problem.
- I'll derive from that and talk about the auction.

Before that, a quick explanation of key concepts
- Definition of Strategic Resistance
    - A system that does not benefit from lying ([[fairness]]!)
- Efficient see [[Definition of efficiency]].
    - A nice mechanism (miscellaneous)
    - Mechanisms that can lead to the conclusion that "you can't improve someone further without making them worse off."

Mechanism Design Applications
- public decision-making
- exchange economy
- auction
- fair share
- non-dividend goods exchange
- matching

public decision-making
- Voting and all that.
- I'll give more details next time.

exchange economy
- exchange of goods
- Hurwitz Theorem, "None of the social choice functions that satisfy efficiency and individual rationality satisfy strategy resistance."
- Strategic maneuvering is inevitable, but the impact of strategic maneuvering is reduced if there are more people

auction
- Procedure to determine the successful bidder and the amount to be paid
- There are many variations, e.g.
    - Sell one non-divisible good to the person who values it the most.
- This is interesting and we'll talk about it a lot later.

fair share
- The problem of allocating nondivisible goods with a transfer of money
    - Example: one person does the work for everyone else and the others pay the price
    - Example: A team defeats a monster and finds a rare item; one person receives the item and pays the other members for it.
- Auctions of non-divisible goods also involve the transfer of money
    - The difference is.
        - In the case of an auction, money goes to the "seller" who offered the item.
        - Fair sharing is money going to other "people who could have received it".
- ![image](https://gyazo.com/5bdc94205ef340933eb5b83319be7076/thumb/1000)
    - Non-enviable resource allocations are invariably efficient" (Svensson 1983).
    - Efficiency and strategy resistance are incompatible.
    - You can't weaken efficiency to horizontality.
    - Weakening the strategic resistance to [[Bayesian incentive compatibility]] also satisfies [non-envy


non-dividend goods exchange
- Exchange of non-divisible goods without transfer of money
- Example: Swap dorm room assignments
    - [[Top Trading Cycle Algorithm]] (1974)
        - Find [strong core allocation
        - Strong core allocation is the only social choice function that satisfies efficiency, individual rationality, and strategy resistance
    - Abdulkadiroglu and Sonmez (1999)
        - We can have alumni and new students.
- This algorithm is being applied to kidney transplants.
    - Non-divisible goods exchange: exchange of non-divisible goods without transfer of money
        - Kidneys are non-divisible goods
        - Assumption that money should not be exchanged.
            - Organ trafficking is allowed in the Philippines, though.
        - Exchange?
            - Someone willing to donate one kidney for a family member in need of a kidney transplant.
            - But the types don't match and can't be directly transplanted.
            - Pair exchange: (A,B) and (B,A) exchange donors with each other
            - List exchange: (,B) gets priority on the waiting list instead of (A,B) giving a kidney to (,A) on the kidney transplant waiting list
    - TTC's improved algorithm for efficient, strategy-resistant exchange

matching
- One-to-one matching Marriage problem see [Stable marriage problem - Wikipedia](https://ja.wikipedia.org/wiki/%E5%AE%89%E5%AE%9A%E7%B5%90%E5%A9%9A%E5%95%8F%E9%A1%8C)
- Many-to-one matching Enrollment issues
        - The [[Gale-Chapleau algorithm]] is already being used to solve real-world problems.
        - Hospital assignments for residents and undergraduate assignments for students entering Waseda University from high school.
            - [https://www.jrmp.jp/](https://www.jrmp.jp/)
        - Honest expression of one's own preferences is the dominant strategy → strategy resistant.

Summary so far
- How to make decisions about issues involving more than one person
- It's been mathematically proven that "no solution with good features exists" in some problem settings.
    - →Discussion will be held on how far to loosen the conditions to find a solution.
- In some problems, "algorithms that lead to solutions with good features" have been found
    - → This could be applied to current products.
- One of the "good traits" is "strategy resistance."
    - No good comes from lying.
    - So everyone acts honestly.
    - Individuals no longer have to think, "What lie is advantageous?" The individual does not have to think about "What lies are advantageous?
    - A system that makes everyone [[fairness]] in the Cybozu way.

- [[King Solomon's dilemma]]
- problem-solving
    - There's one baby.
    - Two women, A and B, both claiming to be "my children."
    - Fine tuning: true mother wants to pay 10 million to get her child back, false mother does not.
- King Solomon's Solution in the Old Testament
    - Cut the kid in half and divide it between you two."
    - One of them identified that one as the true mother because the mother offered the child to the other, saying that it was better than the child dying.
    - If this approach is discovered, it will not work.
        - If it is known that "the one who presents is identified as the True Mother," then both the True Mother and the False Mother "are against the child!" insist that
    - In the first place, it's possible that the false mother also felt that the child's survival was of greater value than zero, in which case the false mother could have offered up the child as well as the true mother.
- The messy decision-making process that Nishio just created.
    - The child shall be the king's and sold for 10 million.
    - A true mother pays 10 million to buy a child.
    - This will make it possible to "return the child to the True Mother," but the problem is that it will cost her 10 million yen.
    - I can't refund the money later.
        - After all, "If they know how to do it, they can't use it."
        - If it's known that I'm going to get a refund, then my fake mother will say, "I want to buy it!" and say, "I want to buy it!
    - [[Glaser-Marmanism]] (1989)
    - Ask A which is True Mother.
        - If you answer "B," the child belongs to B.
        - If you answer A, ask B which one is the True Mother.
            - If you answer A, the child belongs to A.
            - If you answer B, B pays 10 million to the king to get the child, A pays some fine to the king.
    - What happens when it is executed
        - If A is the true mother, A answers that she is the mother and B admits it
            - Because B doesn't want to pay 10 million.
        - If B is the True Mother, A answers, "B is the True Mother."
            - Because if you don't, B pays 10 million to receive the child and you have to pay only the fine without getting the child, which is a loss.
        - In both cases, the child goes to the True Mother without anyone paying.
    - [[Mihara=Ching=Yang mechanism]] (2012)
    - Auctioning off children
    - Impose a small participation fee payment on the loser of the auction
    - What happens when it is executed
        - True Mother will be at the auction.
        - Fake mothers don't participate in auctions.
            - You can't win if you participate.
            - You get nothing and have to pay the entry fee.
            - Choose "do not participate in the auction" because this is a loss.
        - Only True Mother will participate in the auction, so it will be uncontested.
    - Are auctions relatively easy to apply for various purposes?

auction
- ![image](https://gyazo.com/5cc6750c0d631e66a2cbbf4aa38cdfc2/thumb/1000)
- I want to sell my non-divisible goods to the person who appreciates their value the most.
- But how much each person values it is not observable because it's all in their head.
    - = [information asymmetry
    - I want to make a mechanism (mechanism) that determines "who to sell to and at what price" as a result of each person's selfish behavior.

Sealed Auctions
- If you do a bidding, you'll know who appreciates it the most, but you'll need to synchronize in time for that to happen.
    - Large transaction costs
- Can we instead use a system where each person puts a piece of paper with the amount of money written on it in a box?
- Select the buyer who wrote the largest amount of money.
    - This is, well, self-evident.
- How much should that person pay?
    - The amount of money I wrote for naive thinking.
    - Is that really a good way to make decisions?

Auction and Strategic Resistance
- Bidding higher than what you're assessing is a loss, so don't raise your bid.
- If you are the second or lower bidder
    - No loss in lowering the price since you can't buy it anyway.
- If you are the first place bidder
    - If you lower your bid, you get a lower price for it.
- It creates an incentive to bid lower than the honest valuation!
    - = This mechanism is not strategy resistant.

- [[Second Price Auction]]
- Auction where the highest bidder pays the second highest bid
- Proof of Strategic Resistance
    - ![image](https://gyazo.com/5ffd5628b02f00421db4027f8f770f90/thumb/1000)
    - Let each participant's perceived value $v_i$, bid amount [$ b_i
    - The maximum value of bids other than your own [$ m_i = \max_{i\neq j} b_i
    - As shown in the figure above, vi bids are equal to or better than other bids
    - Therefore, it is best to bid honestly on perceived value ([[weak control strategy]]).
    - from  [Game Theory [[3rd ed.]]  p.498

Bidding and Second Price Auctions
- ![image](https://gyazo.com/b5d379edf8aaab9601050e073d15a3da/thumb/1000)
- In fact, bidding up and second price auctions coincide.
    - There is a bit of a difference in the real world auctions.
        - The bidding heats up and you end up paying a higher price than you would have if you were calm.
        - Large increments in the bidding price increase the margin of error.
        - Update your own valuation by looking at other people's bids and seeing if the information is "more/less popular than expected".
    - Humans do not always act rationally...

Auctions and other topics
- Transparency in the pricing process.
    - This transparency contributes strongly to a sense of conviction.
- For example, the sale of real estate
    - Tend to let multiple brokers get quotes and leave it to the one with the highest price.
    - But brokers don't buy it themselves.
    - Unless there is a special sales channel, if there is no difference in the set of buyers, then we would choose "a vendor who estimated the buyer's valuation poorly and incorrectly estimated it high.
    - In an auction, the price is determined directly by the group of buyers, so there is no room for the artifice of intermediaries (at first glance).
- shill bidding
    - If someone from the operation who knows the bidding prices of others participates in the bidding, he/she can fish out the second price.
- Post-Auction Execution
    - I don't want a buyer at an auction and then say, "I don't want to pay it.
    - Hopefully it will run automatically.
    - → [[smart contract]]
- Multiple Homogeneous Goods Auction
    - For example, issuing government bonds.
- Simultaneous Bidding Auctions
    - I want to sell different goods, e.g. sell 3 houses.
    - A buyer, for example, might think "one house is enough."
        - →If you inadvertently win more than one bid, it's a problem.
    - At this time, individual auctions are conducted in parallel and bids are accepted until everything stops
    - Auction is a matching model with contract
        - Simultaneous auction and stable matching [[Gale-Chapleau algorithm]] have the same structure
            - A kind of [[generalized acceptance withholding algorithm]] ([Sakai 2011](https://link.springer.com/article/10.1007/s10058-010-0105-8))

public decision-making
- How to decide together, voting, etc.
- I'll give you the details next time.
    - [[Majority Judgement]] is interesting.
        - Rate on a scale of n instead of choosing one of the options.
        - Select the candidate with the highest median
        - Meet a little loosened strategy resistance
        - [[Gibert-Saththwaite theorem]] : A social choice function satisfying efficiency and [[Maskin monotonicity]] is [[dictatorial]]
        - There's been a lot of research on how to avoid the unfortunate consequences of this.
            - [[unimodal preference]]
        - stochastic environment
            - Equality Probability Dictatorship

question
- Q: Are the mechanism and algorithm the same?
    - No, it's not.
    - Mechanism is a mathematical model see [[Mechanism Definition]].
        - They argue, for example, "If we assume this model, there exists a way to make decisions that satisfies the strategic resistance requirement."
        - Whether it exists or not is the issue.
    - Even if the existence of a solution can be shown mathematically, it does not necessarily mean that a method for finding that solution exists.
    - In fact, [Top Trading Cycle Algorithm
        - Shapley and Scarf proved that there exists a convenient "mathematical function of determination" in a certain mathematical model.
            - > strong core allocation is the only social choice function that satisfies efficiency, individual rationality, and strategy resistance
        - It was Gale who created the specific calculation method for that function.
            - I found a way to actually build it, not just exist.
- Difficulties in conducting auctions [[decentralized]].
    - If deposits are to be collected in advance, the entity collecting them must be trusted.
    - Auctions may be based on the assumption that the subject is trustworthy.
- Are we screwed up if people aren't rational?
    - At least when it comes to auctions, bidders who act unreasonably lose money.
    - In a strategy-resistant mechanism, if an individual does not act rationally, that individual will only lose out.
    - In an auction, if someone bids one digit more than they want, the goal of "selling to the highest bidder" will not be achieved, which is still a problem.
    - On voting and rationality
        - Even if "efficient" solutions are obtained by mechanism design, it only means that "individual preferences are satisfied in a good way", so if individual preferences are not rational, then we will get irrational decision-making results.
            - If you vote in a group of people who all like to party without getting vaccinated, of course that's what they'll choose.
            - Whether this consequence is rational or not is outside the model.
        - What is wrong with ordinary majority voting as a mechanism
            - 40% do not want to vaccinate, 60% want to vaccinate
            - Three candidates A, B, and C for "vaccinate everyone" and one candidate D for "do not vaccinate everyone."
            - In this situation, with 20% of the votes each for A-C and 40% for D, D would be elected and everyone would not vaccinate.
- Many-to-one matching, or many-to-many?
    - The term "many to one" refers to the fact that N people are assigned to one company in a settled state.
    - It's many-to-many during matching, even one-to-one matching.
- The bidding process in Yahoo! bidding method is a mechanism called "automatic bidding".
    - [Yahoo! HELP](https://support.yahoo-net.jp/PccAuctions/s/article/H000005267)
    - The system automatically bids up when you put in the maximum amount.

---
This page is auto-translated from [/nishio/メカニズムデザイン勉強会](https://scrapbox.io/nishio/メカニズムデザイン勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.