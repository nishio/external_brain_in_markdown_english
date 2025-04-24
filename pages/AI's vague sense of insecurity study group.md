---
title: "AI's vague sense of insecurity study group"
---

Purpose of this time
- Resolve "[[feelings of]] unfamiliarity" and "[[vague]] anxiety" about AI.
- There is a possibility that emotions may swing negatively after seeing this lecture, but we cannot take that into consideration beforehand!
    - Fear is always born of ignorance. [Knowledge is the antidote to fear.
    - A "vague sense of insecurity" may be resolved, only to be replaced by "[[a]] clear sense of insecurity."
        - [[The problem is the gap between ideal and reality]]
        - There are facts and interpretations.
        - If the interpretation is not verbalized, it becomes "blurred" and "vague.
        - Share verbalized interpretations


My first encounter with GPT
- Unexplored Junior in 2022
    - > Noxicel is an AI-based application for learning English vocabulary through English composition. Noxicel allows users to memorize English words with context and grammar by writing English compositions. It also uses OpenAI technology to provide suggestions on grammar and usage so that users can easily write English compositions in situations where a teacher is not available.
    - [https://jr.mitou.org/projects/2022/noxicel](https://jr.mitou.org/projects/2022/noxicel)
- It's open to the public in November, but of course we cared about it during the application process in May.
- I was watching the project as it was adopted and tried out the API myself around the summer.
- At that time, the completion API was used in the Playground.
- At the time, I thought, "I see, it can do a lot of things I didn't expect. But it can be used for English, but not yet for improving intellectual productivity in Japanese, which is what I want to do.
- Then came ChatGPT in November.
- This is a "[pessimistic misunderstanding"!
    - [[Reinforcement Learning Part 1]] 2017-01-13 @ Machine Learning Study Group
    - ![image](https://gyazo.com/4787915e5f1d45d41bdcac568e537415/thumb/1000)
    - ![image](https://gyazo.com/46db2b3ae5615b9283790beb9b22b655/thumb/1000)![image](https://gyazo.com/6fe8963c09ac65df72477caceba6a8ad/thumb/1000)
    - ![image](https://gyazo.com/fde07f3096855a4cdcce74aaa150b2f5/thumb/1000)![image](https://gyazo.com/d337683f062f8075462b1d2748dbb676/thumb/1000)
    - ![image](https://gyazo.com/4e15e58d1a52aa92e20e805fea5a92f7/thumb/1000)
    - ![image](https://gyazo.com/e365e373b77c9c66d3bc6689ff3218e8/thumb/1000)![image](https://gyazo.com/9bf9e05ce092b6d167c53e15005a050a/thumb/1000)
- After 10 tries each, about 40% still choose "do nothing".
    - Try 100 times and you'll get rather good results.
    - Ten attempts are not enough to understand the difference in value (success probability, expected value) of 1.5 times.
    - If the value of a small sample size is underestimated, no action will be taken to further increase the sample size, so there is no escape from the state of ignorance
- → I reflected on my pessimistic misunderstanding and decided to spend a lot anyway.
- Tip: Although this experiment is "random", it actually has the effect of "the more you use it, the better you get at using it = higher expectations".


Performance difference between English and Japanese
- We did more and more experiences using ChatGPT.
- I felt the performance difference between English and Japanese.
- The 5/2 GPT4 release made it clear that it's not just about "feeling."
- ![image](https://gyazo.com/9ca6bce95209e6482df37dc987a79e4b/thumb/1000) [GPT-4](https://openai.com/research/gpt-4)
    - [/nishio/stop thinking you know what you're doing by trying ChatGPT in Japanese without paying for it](https://scrapbox.io/nishio/stop thinking you know what you're doing by trying ChatGPT in Japanese without paying for it).
- ![image](https://gyazo.com/33d7682854815155719d77b07ed13bc5/thumb/1000)
    - Even when using the same system at the same cost, speakers of minority languages such as Japanese get less than English speakers
- Will this gap widen or narrow?
    - ![image](https://gyazo.com/d922292d7f81ae2f6a362666019d9da7/thumb/1000)
    - A: Spreading out
        - A straightforward interpretation of exponential development
    - B: For some reason, the lagging side accelerates and catches up
        - Like a kamikaze?
    - C: Saturate somewhere and catch up late
        - Interpretation of the idea of S-shaped development
    - It's impossible to know if it's an A or a C.
        - (B is... wishful thinking...)
- Assuming that A.
    - English-speaking countries and teams receive greater benefits from AI advances than Japanese-speaking countries and teams.
    - When considering international competitiveness, using a minority language such as Japanese is a disadvantage
    - However, I don't think "Well, let's make English the official language of the company" will work.
        - Because it raises the bar for output and inhibits communication.
    - I don't know what to do, but for now, I created a system to automatically translate my Scrapbox into English at DeepL every day (3/25).
        - [[pScrapboxAutoTrans2023-03-25]]
        - Will soon switch to translation using GPT
- Meiji Japan considered it important to make higher education available in its own language
    - In the before LLM era, it looks like it was a good decision
    - after I'm worried that this will be a curse in the age of LLM.
    - English-speaking developing countries will directly benefit from the "educational innovations" that will occur in the future in English-speaking developed countries
        - The problem of interactive interactions in education concentrating the load on "human teachers" is solved by using AI to assist teachers to scale.
    - Minority language speakers will lag behind in this innovation.
- Not 0/1, but also a trend that was already occurring before the LLM
    - Software engineers often had to "read English" when trying to use new libraries or check global standards for languages and browsers.
    - The people and fields covered by it are expanding.
- Q&A
    - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>There is an overhead from using minority languages, but it does not spread exponentially, so if the overall utility spreads exponentially, the percentage of the total will decrease.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Surely there's that world line, the one where the two lines between A and B are parallel.
    - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Theory of getting by with machine translation
        - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>There is no guarantee that terminology, in-house terminology, etc. will be restored.
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In business practice, there are many words that are not used in the world and many unique keywords such as "what is the company" or "what is Mr.". To what extent are they destroyed by translation? For example, "Nishio Yasukazu" cannot be restored to its original w
    - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>As time goes on and AIs exchange information with each other, English may no longer be the first language.
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Maybe it will be Simpified English mixed with JSON and Python.
- Related: [[Competitive Advantage of English-Speaking Countries]].

fragmentation of information
- I connected my Scrapbox to ChatGPT on 3/8, so that ChatGPT can refer to this Scrapbox and respond back to it.
    - Now it's called RAG, and it's a buzzword.
- 3/24  [[Story study session about connecting my Scrapbox to ChatGPT.]]
    - Toolformer: LLM's direction to use external tools
    - spoke about the future direction of the project.
    - ChatGPT Plugins] released on the same day.
    - > [bentossell](https://twitter.com/bentossell/status/1638961888003489792/photo/1)
    - >  ![image](https://pbs.twimg.com/media/Fr7DEc0WcAgD7V6?format=jpg&name=small#.png)
    - Some companies were informed about Plugins in advance, others were not.
        - > [gdb](https://twitter.com/gdb/status/1638986275800879104) Thank you to our amazing set of launch partners — Expedia, FiscalNote, Instacart, KAYAK, Klarna, Milo, OpenTable, Shopify, Slack, Speak, Wolfram, and Zapier. Each has built a very cool integration!
        - >  ![image](https://gyazo.com/9a1b08484fb77e6ef3efcb57ddd27f5d/thumb/1000)
        - ![image](https://gyazo.com/b623b59a9baf00fb43ee174e5edea94c/thumb/1000)


Torn of the world
- I wrote [[The speckled future does not expand.]] on 3/21, shortly before this event on 3/24, and [[After the world is torn apart]] a little later on 3/25.
- It was during this period that the concept of the "tearing of the world" crystallized.
- Let's trace the thoughts of this period.
- What is a speckled future?
    - [[The future already exists in speck.]]
    - > I'm from the future.  [Hiromi Okuda's lecture begins with these words. Of course, I did not come in a time machine from the year 2050 or something. [The future exists "speckled" in the real world, and some [[visionary leaders]] can already see "the future they want. Not only can they see it, they are already living it.
        - [https://www.okudahiromi.com/](https://www.okudahiromi.com/)
    - > The future is already "[[speckled]]" in the real world... I can already see "the future that I want to be" for me, and I am practicing some of the ways of working in that future through childcare and caregiving. I always say "I'm from the future" in the sense that it will become common knowledge in a few years.
        - However, the reality beyond that point is spreading rapidly, and [[**]] reality is being destroyed rapidly. In that destroyed place, the people of the future are living in "speckled" areas. I am one of those "speckled" [[man of the future]].
        - [https://www.okudahiromi.com/blog/20180328/2565](https://www.okudahiromi.com/blog/20180328/2565)
- 3/21  [[The speckled future does not expand.]]
    - The world with "[[speckled future]]", I used to think it was going from A1 to A2, but what I'm observing now looks like a change from B1 to B2.
    - ![image](https://gyazo.com/3ec376e93509a9239553d49e9d837d01/thumb/1000)
- 3/25  [[After the world is torn apart]]
    - ![image](https://gyazo.com/9c21e3a0e0505b2b2ae0acfb289be1a2/thumb/1000)
    - What happens after the stretched world is torn apart?
    - The old world that was torn away and left behind [[People who settle down]].
            - [[Isolated farming village]]
        - The climate is changing and slowly becoming less suitable for farming.
        - Although slowly fading [[boiled frog]].
    - What will "[[People on the move]]" do when they visit that world?
        - I don't know.
            - Almsgiving Patterns
                - The village is losing its agriculture, but is able to survive thanks to the charity of the travelers.
                    - [[basic income]]
                    - [/tkgshn/samaltman is doing UBI with Worldcoin in anticipation of a world line after AGI is reached](https://scrapbox.io/tkgshn/samaltman is doing UBI with Worldcoin in anticipation of a world line after AGI is reached).
                        - [[Worldcoin]]
                - [[Tourism Nation]]
            - Patterns that are no longer worth visiting.
                - Neglected villages decline and perish.
                - Take [Talented young people
                - The villagers may interpret it as [[abduction]] or [[cheater]] seducing them.
                - The traveler's side interprets it as rescuing a young man with a future from a dying village.
                - The young man interprets this as choosing the side he finds [[interesting]].
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>It seems like a win-win to take them with you.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It could be a win-win situation for the young people who leave the village and the travelers who take them with them, and the people who stay in the village get very angry.

Formation of early adopter groups
- 2022-11-19  [[Formation of early adopter groups]]
- time series variation
    - ![image](https://gyazo.com/021b423bfcdd114680ded6b77d30c194/thumb/1000)

    - t=0 More "close or distant" due to existing relationships ([[human network]])
        - I think in general it's a higher dimension, but for illustration purposes, I'm lining it up in one dimension.
    - t=1 First penguin A [movement
        - Only those nearby observe it.
    - t=2 [[early adopter]] population is created by following the observers
        - Related [[Movements are created by followers...]].
    - t=3 Some of the observed people move and some do not.
        - Person B, who does not move, blocks the transmission of information so that people beyond him cannot observe his movement.
    - t=4
        - ![image](https://gyazo.com/e62a32d5e773893447c488ef6d7aabfa/thumb/1000)
        - A new [[human network]] is formed among this "group of early adopters" that appears here and there.
            - [[Early adopter enrichment effect]]

- Independent of whether the destination of the move is correct.
    - Just look at your surroundings at the destination and if you think it's not good enough, just move on further.
    - This "two-step-ahead world" becomes full-blown [[Difficult to observe]] from those in the original world.
        - =  [[Torn of the world]]
    - It is rather less important whether the world is better one step ahead, and the value of maintaining information connections with those who are less hip may be more weighty?
            - [[Why do social networking sites rise and fall?]]
            - [[People on the move]]
            - [[weak ties]]
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Do those who have moved two steps ahead not call out to those who have moved zero steps ahead?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>That's what I think of as "travelers visiting a village."
        - The same applies to discussions about whether or not there are benefits, etc. If there are benefits, we do it, if not, we don't.
        - Tsunami Tenden is also connected to the image of "we can't afford to do that at the stage of running away" and "rescue operations will be carried out when we can afford to calm down".


The question of how to live
- 3/29  [[flood of tsunamis]]
    - When the tsunami hits, you must all run to high ground, one by one, as quickly as possible.
        - [Run away, even if it's just one of you.
        - It doesn't matter if others move or not, I'll make my own decision.
    - Appropriate balance between self-interest and altruism
        - You sounded a disaster announcement, you called out to people within earshot, and that's enough.
            - Don't delay your own escape by engaging in [[people who don't listen to what others have to say]] or [people who don't move
    - [[tsunami]], it is known that you can escape to "high ground".
    - However, there is also a type of variation where [Where should I run to?
        - Added on 9/16/2023
            - Need to [[widen the range of observation]].
            - Often [[movement]] is important
            - [[The move must begin before the destination is determined.]]
- 11/6  [[I bet on the tsunami coming.]]
    - It is uncertain whether a tsunami will hit or not.
        - Assuming you're coming, run to higher ground.
        - Don't stay to convince those who are staying to assume they won't come.
        - Related: [[Pascal's Wager]].
            - The story is that it is more profitable to bet on the existence of God.
    - This is betting = uncertainty management
        - Often [[Barbell Strategy]] is better [antifragile
        - Unlike the physical body, it can be divided into fractions, so you can bet on multiple options.
- LLM meetup(4/10)
    - > [takahiroanno](https://twitter.com/takahiroanno/status/1645426627780947969) I went to an LLM meetup at a place in Tokyo and it was great. It was a highbrow meetup where all participants were required to bring a demo related to LLM, but about 50 people showed up. It was a highbrow meetup where all participants had to bring a demo related to LLM, but there were about 50 people there, and it was just distilled down to a lot of [[LLM Unemployed]]. It felt like the beginning of an era to me.
    - > [takahiroanno](https://twitter.com/takahiroanno/status/1645427231710416898) LLM unemployed = people who unintentionally quit their job after seeing how great LLM is (including people who recently started their own business)
    - > [kenn](https://twitter.com/kenn/status/1645570470547456001) I am also LLM unemployed! Seriously, the beginning of a startup is no different from being unemployed, so if you're going to be unemployed anyway, it's better to start a company. It's a good idea to start a company if you're going to be unemployed. Once you start a company, you can get by, and even if you don't, you were unemployed to begin with. LOL!
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>nishio, you also have to wonder how to live your life.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The problem is the gap between the ideal and the reality, so the higher the ideal, the greater the problem.
        - I think I can manage to survive on my own, but I don't want to go through the hassle of changing jobs, so ideally, I would like Cybozu to remain in a sound management position for another 20 years. I think it is natural to think that there will be about the same level of change. (even if we don't take into account the possibility of acceleration by AI).
        - And if change is inevitable, the question becomes, "How should we change?
        - Related: [[worry about one's life]].


Negative feelings about writing books
- The first book, "Jython Programming," was upgraded while being written, and became obsolete a few years after publication.
- I wrote "The Technology Behind Coding" (2013) with the intention of writing a book that would not become obsolete for 10 years.
- Talks of a revised edition were brought up this year, proof of 10 years of continuous sales.
    - I was going to undertake this because the fact that a revised edition is coming out is signaling that the book is beneficial.
    - In January, I was preparing for "Changes in Programming Languages in the Last Decade."
    - But I quit. When I thought about it in the scope of the next 10 years, I couldn't see the raison d'etre in the medium of books.
- Are books appropriate as a form of knowledge transfer?
    - 4/6  [[Easier to write for LLM than to write for humans.]]
    - > [nishio](https://twitter.com/nishio/status/1643812867773452290) The technology is already in place and will soon come down to the average consumer "[[Ability to give LLMs a knowledge package of your area of interest]]" will come down to the general public soon. When that happens, authors of new languages will create knowledge packages for LLMs, and people who want to use the language will be able to load them into LLMs and use them.
        - I wrote this and implemented it in [[ChatGPT Plugins]] on 4/7, and it was provided at [[OpenAI DevDay]] on 11/7 under the name [[Assistants API]].
    - > [nishio](https://twitter.com/nishio/status/1643813597792071680) Creating knowledge packages is actually easier than creating documents for human readers. Because humans have limited short-term memory, it is necessary to provide knowledge in a "good order", and this is very hard for the author.
            - [[Writing is one-dimensional]]
    - > [nishio](https://twitter.com/nishio/status/1643813862008033283) Rather, it is better to identify "what information is missing" based on users' questions and add it, and it is important to create a system to do so. It is important to build a system to do that.
- Promptly publish it in Scrapbox, translate it into English the next day, and six months later mention, "I wrote this and published it six months ago at this time, but
    - [[knowledge casting nets]].
    - [[Cultivate territory and raise a flag]].
        - [[Cultivation of the Nowhere Sphere]]


RAG: Retrieval-Augmented Generation
- Even if LLMs are smart, they don't know about internal information that is not publicly available.
- The RAG approach is to supplement knowledge with search
- It is worthwhile to improve this search!
- 7/18 Azure Cognitive Search
    - ![image](https://gyazo.com/8e2fa02e91d9ee1566bd48aeb6008048/thumb/1000)
- The feeling of having Roman soldiers at the end of the road, thinking they had found a way to make a living.
    - Roman Empire = Microsoft Empire


Rome wherever you go
    - [[The scale of demand makes a difference in the efficiency of GPU use.]]
    - > GPUs are expensive resources and there is a limit to the throughput a single GPU can deliver, so service providers with sufficient demand from the entire world can use GPUs efficiently by leveling the load, and service providers without sufficient demand can let GPUs idle during low loads, resulting in many times less efficient use of GPUs.
        - A service provider whose customers are concentrated in Japan, for example, will use resources many times less efficiently than a service provider whose customers are scattered across the world's time zones.
    - Nov 16 [[[Breaking News]] Microsoft Announces Azure Maia, a Uniquely Designed AI Chip Optimized for AI Learning and Inference.Ignite 2023 - Publickey [https://www.publickey1.jp/blog/23/aiazure_](https://www.publickey1.jp/blog/23/aiazure_) maiaaiasicignite_2023.html]
        - > "Maia is ... and is already being used by many of our services, including GitHub Copilot. We're going to start using it in our workloads first, and then we'll roll it out to third-party workloads.
        - [[vertical integration]].
        - > Vertical integration refers to the process by which a group of companies incorporates value-added processes along the value chain to supply products and services.
    - Related: [We spoke to a fusion power startup that has signed a deal with MS and is also funded by Sam Altman | Business Insider Japan](https://www.businessinsider.jp/post-270857)
        - 5/10 [Helion announces world’s first fusion energy purchase agreement with Microsoft | Helion](https://www.helionenergy.com/articles/helion-announces-worlds-first-fusion-ppa-with-microsoft/)
        - From power and chips to services, integration is underway.


- [[Appropriate level of abstraction for groupware in the LLM era]]
- > To assume the current product design and consider adding LLM functionality as a generic feature is to implicitly assume the current level of abstraction.
- At Cybozu Days Keynote, he said, "This is like the dawn of the Internet.
    - Time for 0→1 [[business model search]] is needed.
    - We still don't know what "what we need to find" is, but don't assume it's continuous with existing products.
    - [/nishio/search for keys under the street light](https://scrapbox.io/nishio/search for keys under the street light).
        - >  A man was looking for something under a lamppost in a park. A person passing by asked the man what he was looking for. The man said, "I lost my house key and I am looking for it. The passerby felt sorry for him and searched with him for a while, but could not find the key. The passerby then asked the man if he had really lost his keys here. The man replied in a nonchalant manner, "No, I didn't lose my keys. No, I lost the key over there in the dark, but it's too dark to see anything over there, so I'm looking over here where the light is shining.

- [[Explanation of AI Unemployment in Factorio]]
- > [nishio](https://twitter.com/nishio/status/1723855066975617148/quick_promote_web/intro) People who are [[0/1 thoughts]] like "[AI will take your job, I think you should do [[Factorio]] to improve [[Understanding the System]].
- A conversion device that used to produce an output of 2 for an input of 1 will now produce an output of 3, which is an increase in productivity.
    - ![image](https://gyazo.com/7e43ba6b41944dfd1a204ba4b60c6ceb/thumb/1000)
    - If there is enough demand in the downstream network at this time, efficiency will increase.
        - For example, in a situation where there are many features to be implemented but not enough engineers to implement them, more features can be implemented.
        - There's a lot of unmet demand out there.
    - But if there's no demand, downstream inventories build up, conveyor belts fill up, and the utilization rate of that production equipment goes down.
        - The task of tax processing for companies is usually fulfilled and the demand does not increase by 1.5 times.
        - So if a 1.5-fold increase in productivity occurs, one out of every three people will no longer be needed.
    - At this time, the U.S. fires people who are no longer needed.
        - In Japan, [[layoff restrictions]] for regular employees are strict, so [[personnel change]] and transfer to other areas.
            - > [nishio](https://twitter.com/nishio/status/1723935186742579465/quick_promote_web/intro) White-collar workers who have been underutilized have the option of agility in the form of picking up the ball that is overflowing, taking on a voluntary dual role, or creating a new department. I feel that if you are strongly bound by job descriptions, it will hinder the agility of the employees.
            - It is a groupware staple (see below).
- ![image](https://gyazo.com/10b5f769e2fcdf566daec049ad5a437f/thumb/1000)
    - from  [[New and required course "Information I" useful for work]]
    - Whether spontaneously or at the behest of the company, "individual movement within the company" will occur.
    - Where we are moving to:.
        - 1: Systems Development (leading to the story at the beginning of this book where "[[Mandatory Programming Education]]" took place)
        - 2: Work in the "[[interface with the world]]" part that is not directly systematized (bottom of the figure)
        - 3: Entering the "know-how" arrow [[to extract and propagate information]] role
        - PS: A few, of course, will move to "management."


What should I do?
- What is the right thing to do?
- Discussion probably won't lead to consensus.
- I think waiting to come to a consensus is a bad idea.
- I'm going to do a lot of things on my own.


My current target: Summary
- What is taking place in the process of reading and understanding your book?
    - It's becoming a less data-intensive expression than the entire book.
        - Broadly speaking, "summary."
    - On top of that, there is a link connection in place.
    - [[Summary is an ambiguous concept]]
    - There are probably several different tasks that can be described by the word "summary
    - Difficulty in giving verbal instructions to LLM because the words to express them are not mature
    - On the other hand, it is also difficult to express what we want Few shots to do in the case study because it is a "task that receives large inputs"
    - Creating data and fine tuning
- I don't know if this policy is the right one, and in a few months we may be doing something else.
    - But thought has brought us to the threshold of the forest of "things you don't know unless you try," and we must partake.


Q&A
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>I'm not sure it changes that much.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Maybe so, maybe not. [[normalcy bias]], and cognition tends to be biased toward the "no change" side.
        - [Normalcy bias - Wikipedia](https://ja.wikipedia.org/wiki/正常性バイアス)

---
This page is auto-translated from [/nishio/AIの漠然とした不安感勉強会](https://scrapbox.io/nishio/AIの漠然とした不安感勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.