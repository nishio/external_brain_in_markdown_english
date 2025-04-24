---
title: "Omoikane Study Group"
---

2023-08-04　 [[Cybozu Labs Study Session]]
- Up to now.
    - 2023-03-24  [[Story study session about connecting my Scrapbox to ChatGPT.]]
        - ChatGPT's API is now open to the public, so I talked about doing it.
    - 2023-05-12 [[Plurality and Polis Study Group]] (mainly explained the context of [[Plurality]])
    - 2023-06-23  [[Polis Study Group]]
- Today I'm going to talk about the [[Omoikane Project]] I've been working on recently.
    - For Thumbnails:.
        - ![image](https://scrapbox.io/files/64cbd8e0f223a1001c80bbc8.png)
- But first, a topic of current events:.
    - 7/24 [Worldcoin project launches](https://worldcoin.org/blog/announcements/worldcoin-project-launches)

# [[Worldcoin]]
- 7/24 [Worldcoin project launches](https://worldcoin.org/blog/announcements/worldcoin-project-launches)
    - OpenAI CEO [[Sam Altman]]'s [posted at](https://twitter.com/sama/status/1684297687708098565?s=46&t=gkSZtjGEtUZPO0JCzBxCBw)
        - 'Scanning my retinas gives me virtual currency? What does that mean?" I see people who are like.
    - > [[World ID]], a privacy-preserving digital identity designed to help solve important, identity-based challenges, including proving an individual’s unique personhood
        - (DeepL) World ID is a privacy-preserving digital identity designed to help solve important identity-based challenges, such as the unique [[Proof of Humanity]] of an individual.
        - > World ID is a new privacy-first [[decentralized identity]] protocol.  --- [Introducing World ID and SDK](https://worldcoin.org/blog/announcements/introducing-world-id-and-sdk)
        - It's been talked about a few times before [[distributed ID]].
            - (I haven't read the protocol, it will be a big Identity Provider <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>)

    - > [[Worldcoin]] token (WLD), where laws allow, the first digital currency to be freely distributed to people for just being a unique human*
        - (DeepL) World Coin Token (WLD): the first digital currency* that is freely distributed to people just for being a unique person, as far as the law allows.
        - Sam Altman has been advocating [[Universal Basic Income]] for years.
        - [[American Equity]]: [[Sam Altman]] 2017
            - > Every adult American citizen should receive a share of the U.S. [[GDP]].
        - [[Moore's Law for Everything]]: [[Sam Altman]] 2021
            - > The sources of wealth are 1) companies, especially [[companies using AI]] 2) land in fixed supply
            - >  [[Let's tax capital, not labor.]]
            - The claim is to use this [[asset taxation]] as a source of [[Universal Basic Income]].
        - This one is also in the context of [[UBI]].
            - Basic income for people proven to be human by World ID
- network effect
    - Cites "the unique [[Proof of Humanity]] of the individual" as a "key challenge based on identity."
    - For example, [[SybilRank]].
        - > SybilRank is computationally efficient... Scalable to graphs with hundreds of millions of nodes
        - ![image](https://gyazo.com/cdc9b35a99ccc5919bdb81c4ffd7dd33/thumb/1000)
        - "[[Trust Seeds]]", an algorithm that propagates trust from highly trusted accounts.
            - Efficient algorithms have been created, and it's time to make it practical to apply them to the entire human network.
        - How can "accounts that correspond to retinal scans" be "Trust Seeds" with a high degree of trust?
    - It is more beneficial for an individual to be part of a larger network
        - Businesses that have built large networks can compete favorably as platformers.
            - The [[network effect]] story has been repeated over and over again.
        - Elon Musk tried to buy the giant social network Twitter and turn it into X
        - Sam Altman's strategy is to take a platform by scattering
            - Like [[PayPay]] [10 Billion Yen Giving Campaign
            - Disperse through virtual currency payments issued by the company itself.
            - The expectation that the virtual currency will create value in the future allows for cost-free disbursement.
                - Smart...
- Personally, I think [[UBI to avoid monopolizing access to AI]], but that's a long story, so I'll pass.

# [[Omoikane Project]]
- [/omoikane](https://scrapbox.io/omoikane)
- In a nutshell, "a project that combines SF prototyping and AI technology to create a better discussion mechanism."
- Create a better discussion mechanism([[deliberation support system]])
    - Democratic Inputs to AI," which [[OpenAI]] called for in May, which we talked about last time.
        - AI has far-reaching economic and social implications
        - It is not right that [[decision-making]] of "what AI should be" is done by "[[a]] few people" (like the management of a for-profit company).
            - Should be shaped by "[[Diverse perspectives]]" that reflect [public interest (e.g., public good)
        - Recruit a [[team]] to develop a [[proof of concept]] for a [[democratic process]] to take the first steps in this direction
        - We (OpenAI) want to learn from these experiments and use them as the basis for a [[more global, more ambitious process]].
            - It is interesting to look at the Worldcoin news at the beginning of this article in light of this statement in May
    - The founding members of the Omoikane Project have repeatedly discussed applying for this [Democratic Inputs to AI
        - We had a very interesting story, so we started working on it without waiting for it to be adopted.
        - Unfortunately, the result was not accepted, but by that time, interesting things were happening in the online community, so we decided to continue with fine-tuning the plan.
    - We talked about [[Polis]] in the last and previous workshops.
        - Polis is a beneficial component
        - However, it is not a stand-alone deliberation support system.
        - Pre- and post-stage design is required
    - As a preliminary step, [[share the world view]] in SF prototyping.
        - ![image](https://gyazo.com/def130484660e621bd11bf759c7c88c0/thumb/1000)

- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>What is SF, Space Fantasy?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Science Fiction here is Science Fiction, but I don't think it's worth worrying about since the term itself doesn't have a clear definition to begin with.
        - If I had to describe it in my own words, I would say that it is "a story of what is likely to happen in the near future.

# [[SF Prototyping]]
- What is Prototyping?
    - > The idea is to create a rough model that represents the concept using materials at hand. You can use blocks, foam core, tubular material, strong adhesive tape, whatever seems useful.
            - [[A company that conceives]]! - Innovation techniques from IDEO, the world's best design firm Tom Kelly p.74
    - The idea is to get the "experience" of having the product in your hands faster by making a low-cost "approximation" of the final product
- So how can we prototype not a physical product, but a vision of the future and the direction we should go in the future?
    - The method is SF prototyping.
        - To put it crudely, "make an approximation of the future by means of a near-future science fiction short-short."
        - Can sympathize or rebel with the protagonist's "experience".
    - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Interesting interpretation that SF can be prototyping.
- Moreover, this process can be assisted by AI.
    - ![image](https://gyazo.com/a9cbed512af0304482aea9a095782782/thumb/1000)
    - In fact, several people in the Omoikane project have published their own AI-generated science fiction novels
        - [/omoikane/AI Novel: "AI's Classroom for Improving Communication Skills"](https://scrapbox.io/omoikane/AI Novel: "AI's Classroom for Improving Communication Skills").
        - [/omoikane/memory-mountain](https://scrapbox.io/omoikane/memory-mountain).
        - [/omoikane/AI Novel: make future 2ea176d2-0d4f-4a4a-b4b6-0b667b11e906](https://scrapbox.io/omoikane/AI Novel: make future 2ea176d2-0d4f-4a4a-b4b6-0b667b11e906)
        - [/omoikane/AI Novel: Jolene](https://scrapbox.io/omoikane/AI Novel: Jolene).
        - [/omoikane/AI Novel: "Interstice: Beyond the Conversation" (Interstice: Beyond the Conversation)](https://scrapbox.io/omoikane/AI Novel: "Interstice: Beyond the Conversation" (Interstice: Beyond the Conversation))
        - [/omoikane/AI Novel: Maki's Silent Pot](https://scrapbox.io/omoikane/AI Novel: Maki's Silent Pot).
        - All different authors.
- Surprisingly easy, let's look at some concrete examples
- Prompt: you are a science fiction writer. Write a near-future science fiction story. Constraint: The protagonist works for a software company whose motto is "creating a society full of teamwork. The story begins when he hears a researcher claim that prototyping the future by having an AI write science fiction is beneficial.

# Title: "Future Prototypes"
.

- Chapter 1: "Encounters with AI"

    - The main character, Itsuki, is an engineer at the software company TeamWork Tech. His creed is to create a society full of teamwork. One day, he becomes interested in a researcher's claim that AI is prototyping the future by writing science fiction. His heart leaps that this may be the key to shaping a new vision.

- Chapter 2: "Teamwork and Future Projections"

    - The tree will launch a project to find ideas for how to utilize the AI's capabilities to instill teamwork in society. That AI, named Asimov, Asimov's task is to write a prototype of the future based on the data and goals provided by Tree and his team.

- Chapter 3: "The Future as Depicted"

    - The future envisioned by Asimov is one in which collaboration shapes society. Individual ideas intersect and generate new ideas. But Asimov's story also contained a warning: a warning about the shrinking role of humans in a future dominated by AI.

- Chapter 4: "The Need for Coordination."

    - Trees will challenge against this future envisioned by AI. Emphasizing that teamwork stems not only from AI, but also from the connections between humans, he seeks a future that uses AI's capabilities but does not lose its humanity.

- Epilogue: "The Future of Teamwork"

    - Ultimately, Trees and Team envisions a future that combines human creativity with AI's predictive capabilities. It is a future where teamwork takes center stage and AI provides support. And it is also the beginning of a new science fiction, a prototype of the future.

- This story illustrates the possibilities of AI and humans shaping the future together and offers readers a new vision of the future.

# Comments
.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Is this an unadjusted AI-generated text on the site? That's a pretty interesting sentence.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Yes, I didn't modify anything except the indentation, no trial and error, one shot out: [chatlog](https://chat.openai.com/share/7f7ca59b-1fe8-40af-889e-2652375875b1)
- "AI and humans will shape the future together."
    - That's a nice phrase!
- Collaboration as "the intersection of individual ideas to generate new ideas."
        - Interesting that you describe [[collaboration]] this way.
- "The future of teamwork" / "A future where teamwork is central and AI provides support."
    - What does "[[teamwork]]" look like in this world?
    - It could be something different from the "before GPT" teamwork.
    - Teamwork... also derives from the connections between people.
        - I feel like this is an important perspective.
    - Would it be interesting to build a sci-fi prototype on the issue of the unclear definition of "teamwork" and the future of teamwork?
        - Postscript:.
            - I asked ->[/omoikane/the future of teamwork](https://scrapbox.io/omoikane/the future of teamwork).
- "Write future prototypes based on data and goals."
    - No data or goals were given in this prototyping process.
    - Sure, it's possible to make better prototypes by giving them data and goals...
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>It sounds very plausible as a synopsis, but I'm not sure what exactly it will be about.
    - Is this good enough as long as it is prototyping?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I think the prototype is complete at this stage.
        - The "novel as entertainment" and the "novel as prototype" offer different kinds of value.
            - Entertainment fiction doesn't have to generate controversy, as long as it's interesting to read.
                - Interesting, but nice to have a MUST to make you think.
            - Novels as prototypes are valuable for generating discussion, even better if they are interesting, but just being interesting is futile.
                - Make you think is MUST and interesting is nice to have.
        - Since GPT4 is writing the story instead of me thinking up the story, unexpected stories and phrases come up for me.
            - This time I read it myself and wrote my thoughts, but I can do that because I'm not 100% in control of the story.
            - Like, "I see what you mean, it's important to be based on data and goals."
        - I can't share with others if I'm just mulling around in my brain, but I can share this sci-fi prototype and the verbalized impressions triggered by it.
            - Sharing triggers thoughts in others.
            - If doing a vague "let's all think together" or "let's all come up with ideas" doesn't work very well, then making something readable first will lead to more concrete discussions.
            - So I suggest we do SF prototyping first before discussion.
            - I'm already convinced that this would be beneficial to me, after trying it myself first in making my proposal.
            - The cost of the work is lower than expected, and when you see what comes out, you say, "Oh, well, I didn't have that perspective.
- Do you think this usage is teamwork with AI?
    - I think it's a new form of teamwork, but it's also an interesting story, and I think the world is divided on it!
    - In Japan, there is a culture of recognizing the personalities of non-human things, such as [[Doraemon (dwarf planet)]] and [[artifact spirit]], and I resonate with that.
    - On the other hand, there are those in the world who believe that tools should not be allowed to have personalities and that AI's capabilities should be limited, and from that perspective, AI will never be a team member.
    - I believe that AI can be a team member and that we should have more conversations with AI as a team member.

# [[Prototypes activate thinking]]
- Even when used alone, ChatGPT will create unexpected stories to activate it.
- Share your [[prototype]] with others to stimulate conversation.
    - This explanation, which I just introduced, was given in "Chapter 4: Ultimate [[brainstorming]]".
        - > The idea is to create a rough model that represents the concept using materials at hand. You can use blocks, foam core, tubular material, strong adhesive tape, whatever seems useful.
                - [[A company that conceives]]! - Innovation techniques from IDEO, the world's best design firm Tom Kelly p.74
    - Instead of "thinking," "ideating," and "discussing" in a vague way, making things visible and touchable allows for more concrete thinking, more concrete ideas, and better discussions.
- So, in creating a better discussion mechanism([[deliberation support system]]), it is a good idea to "do SF prototyping first before discussion".
    - This was only an idea at the proposal stage, but became a conviction as we tried it out.
    - The cost is lower than expected because prototypes like the above example are really quick and easy to produce.
- There are two supp projects that will delve into this.
    - [/omoikane/「EBSFP: 根拠データに基づくSFプロトタイピング」プロジェクト](https://scrapbox.io/omoikane/「EBSFP: 根拠データに基づくSFプロトタイピング」プロジェクト)<img src='https://scrapbox.io/api/pages/omoikane/siramatu/icon' alt='/omoikane/siramatu.icon' height="19.5"/>
        - Create search keywords based on SF prototypes and load the prompts with the abstracts of the papers hit by the search with those keywords and have them refined.
        - This is the direction suggested earlier in the SF prototype "write future prototypes based on data and goals".
    - [/omoikane/自治体や大学などでSFプロトタイピングの実証実験したい](https://scrapbox.io/omoikane/自治体や大学などでSFプロトタイピングの実証実験したい)<img src='https://scrapbox.io/api/pages/omoikane/hal_sk/icon' alt='/omoikane/hal_sk.icon' height="19.5"/>
        - Nagoya Institute of Technology [Advanced Community Creation B](https://cms7.ict.nitech.ac.jp/moodle40a/syllabus/view.php?id=76650) is being considered for implementation.
        - Workshop for teachers scheduled for the end of September
- [/omoikane/Polis preliminaries with SF prototypes will lower the hurdle for Polis](https://scrapbox.io/omoikane/Polis preliminaries with SF prototypes will lower the hurdle for Polis).
    - > [/omoikane/Polis:AI小説:「ファントム」](https://scrapbox.io/omoikane/Polis:AI小説:「ファントム」)で初polis！<img src='https://scrapbox.io/api/pages/omoikane/teyoda7/icon' alt='/omoikane/teyoda7.icon' height="19.5"/>
    - >  I had seen it in <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>'s project and knew it existed, but felt the hurdle and hadn't been able to vote for it.
    - >  Would it lower the hurdle if it's your opinion of a creative work?
    - Consideration 1: With political topics, there are cases where people hesitate because they think they don't have enough prerequisite knowledge to vote.
        - If it's "please read the novel and vote on what you think," then once you've read the novel, you can assume that you have enough prerequisite knowledge.
    - Consideration 2: The hurdle was high because of the "must write a correct opinion" atmosphere
        - This time, by being called "impression," I can express how I felt, not how "right" I was.

##  Q&A
- What are the specific ways in which AI will assist? For example, in what areas will the AI assist with plot generation, character development, dialog creation, etc.?<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
    - GPT is General Purpose Technology, so people are trying different things.[/omoikane/人々による探索的研究が現場で起こっている](https://scrapbox.io/omoikane/人々による探索的研究が現場で起こっている)<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Personally, I like the use of having a near-future science fiction plot created, cost-effective.
            - This is because I consider "effectiveness" to be "prototyping".
            - I feel that [/omoikane/value as an entertaining novel](https://scrapbox.io/omoikane/value as an entertaining novel) and [/omoikane/value as a prototype](https://scrapbox.io/omoikane/value as a prototype) are two different things.
                - There is a sense of narrative: [/omoikane/AI novel "Pink Float and AI Summer"](https://scrapbox.io/omoikane/AI novel "Pink Float and AI Summer").
                - No sense of narrative: [/omoikane/AI Novel "Meeting a Transfer Student: A Shift in Vision"](https://scrapbox.io/omoikane/AI Novel "Meeting a Transfer Student: A Shift in Vision").
        - Another favorite usage is "[/omoikane/explanation for those unfamiliar with Japanese culture](https://scrapbox.io/omoikane/explanation for those unfamiliar with Japanese culture)".
            - Prompted for various keywords, "Explain in English for people who are not familiar with Japanese culture.
            - [/omoikane/convincing](https://scrapbox.io/omoikane/convincing).
                - > "Convincing" is a richly nuanced Japanese expression that cannot be directly translated into English.
            - [/omoikane/annoyance](https://scrapbox.io/omoikane/annoyance).
                - >  The Japanese word "nuisance" (meiwaku) translates directly to "nuisance" or "trouble" in English. However, the cultural meaning of the word goes beyond these translations in the context of Japanese society. In Japan, [[social harmony]] and [[collectivism]] are greatly emphasized...
            - When Japanese people are thinking in Japanese, they unknowingly think "[[everyone knows]]" [[common sense concepts]], but they often realize that these [[Galapagos concepts]] are only accepted in the [[minority]] inner circle when viewed from a global perspective.
            - I made him read this commentary [/omoikane/尊王攘夷](https://scrapbox.io/omoikane/尊王攘夷) and write [/omoikane/尊王攘夷2.0](https://scrapbox.io/omoikane/尊王攘夷2.0).

- What specific insights or lessons learned from the written science fiction stories?<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
    - [/omoikane/story in which protagonists with different ideas act out of the same situation](https://scrapbox.io/omoikane/story in which protagonists with different ideas act out of the same situation).
    - In a setting where local government has gone digital due to a lack of manpower, we created a storyline of those in favor of digitalization and those opposed to it.
    - [/omoikane/ChatGPT wants to make it a good story](https://scrapbox.io/omoikane/ChatGPT wants to make it a good story) has had a positive effect
        - At first I subconsciously thought that older people who resist change are unhappy by their choice.
        - When I saw that ChatGPT generated a happy ending with that constraint, I realized I had an [[unconscious bias]].

- What are the main benefits of using AI to create stories?<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
    - To create a near-future science fiction story is to start from the current situation and create a prediction of the future by connecting small steps that "such a thing is likely to happen.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - (I'm not talking about [/omoikane/ value as an entertaining novel](https://scrapbox.io/omoikane/ value as an entertaining novel) here.)
        - Some people are not very good at making these future predictions in the first place, or they make narrow predictions based on unconscious assumptions.
        - Mechanical support here has the effect of reducing costs and broadening horizons.
- This is the first half of the story so far, so I'll question it.

Post-Polis phase
- We think of it as an "[[improvement cycle]]."
    - ![image](https://gyazo.com/c24a617eaefe6f4124accce7f2cb7d18/thumb/1000)
        - [[Gradual improvement]] by [[iteration]] in an [[agile]] manner.
    - SF prototype corresponds to [[Minimum Viable Product]] in [[Build-Measure-Learn Loop]] of [Lean Startup
        - Minimal product" that can be learned by releasing it to others and observing their reactions.
- By reading the novel and doing Polis, you can realize that "different people feel differently even though they read the same thing".
    - Read [/omoikane/AI Novel: "Phantom"](https://scrapbox.io/omoikane/AI Novel: "Phantom") and vote for it at [/omoikane/Polis:AI Novel: "Phantom"](https://scrapbox.io/omoikane/Polis:AI Novel: "Phantom")!
        - ![image](https://scrapbox.io/files/64cba5450400ec001cd713bd.png)
        - I voted and was in the minority, so I wanted to write my opinion.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - After that, I wanted to make SF based on that opinion, and this became the first SF prototype for <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>!
                - [/omoikane/deep-dive: mine-memory](https://scrapbox.io/omoikane/deep-dive: mine-memory).
- I wanted to improve this "Novel to Polis" process.
    - Polis does not show visualization until 7 people have voted, and there is no feedback for those who have taken voting action, so it is difficult to increase the number of votes in the middle
    - For example, opinions on why the clusters are divided into clusters are shown on the visualization screen, but this cannot be retrieved via the API.
        - It would be interesting to have the AI role-play the opinion clusters as virtual personas, but the only way to do that is to copy-paste them into each other.
    - The needs in this area led to the list of "areas for improvement" in the previous [[Polis Study Group]].
    - This "improved Polis-like system" was later named "Komorebikagami".
    - A mirror that collects and reflects (reflects/contemplates) the "emotional data" that leaks out of people like sunlight leaking through a tree.
        - (GPT4 named: [/omoikane/naming of Komorebikagami](https://scrapbox.io/omoikane/naming of Komorebikagami))

Japanese cockchafer (Melolontha japonica)
- ✅Return immediate feedback on ballots
- ✅You can check your own past votes.
- ✅Can update ballot content
    - I think of this as "a system that helps people update their thoughts", it's only natural that people with updated thoughts would want to update their votes, so I supported that.
- ![image](https://gyazo.com/3598f4f5c65e11b910a734ff7400eb2c/thumb/1000)
- (Planned) to be able to share on Twitter and vote directly...
    - I'm still waiting to see if Twitter will turn into X or not...
    - You can vote against Bluesky with a script, but...
    - In the end, it's not about which social network, but about being able to share easily on each platform where people are congregating.
- In the case of Polis, it was "a visualization is read by a human, a thought is triggered, and a post is written (by some people)"
    - Polis clusters are virtual personas, so GPT could read them directly and role-play them.
    - Virtual personalities played by AI's could argue with each other.

Community-centric AI
- [/omoikane/"Building Community-Centered AI" Project](https://scrapbox.io/omoikane/"Building Community-Centered AI" Project).
    - > The "[[Community-Centered AI construction]]" project is an attempt to create a "[[Community AI]]" ([[Community-Centered AI]]). This refers to an AI that learns the history, culture, challenges, and opinions of a particular community and understands and represents them. Specifically, it will interact with people involved in the issues facing the community, providing an environment that not only provides knowledge, but also creates a forum for discussion and leads to the creation of solutions. Our initial goal is to create an AI for the Omoikane community.
    - What we called "[[Japanese Culture AI]]" at the time of grant application
    - As a result of the iteration, a lot of data was accumulated by community members, and we thought it would be interesting to turn it into a chatbot with [[Retrieval-Augmented Text Generation]].
        - To use a figurative expression, "the AI is watching every conversation in the community."
        - When spoken to, "remember the similarity" and respond with reference to it.
        - This "recall of similarities" is [[vector search]].
    - How it works, which I discussed in March at [Story study session about connecting my Scrapbox to ChatGPT.
        - [/omoikane/Omoikane Embed](https://scrapbox.io/omoikane/Omoikane Embed)
        - At that time, the vector index was updated manually.
        - They only experimented with personal Scrapboxes.
        - This is "automatically updated once a day" for "community groupware that is updated by multiple people".
    - I started automatically updating from the Omoikane Project's Scrapbox once a day in June.
        - ✅Vector search function is already in service release, chat function is not yet added.
        - Essentially, there is no need for it to be Scrapbox.
            - It would be good if the text data of the exchange could be automatically extracted from the communication platform (= groupware) that the community primarily uses.
        - I'm using Scrapbox right now because it's convenient and automatable to export in JSON format.
        - Scrapbox is also a good place to find several communities in the public
            - Groupware for corporate use is generally not allowed to disclose its contents.
            - If a public community is used as a test case, it is easy to introduce a case study that says, "This is what happened when we introduced the system to this kind of community.
        - As a start, anything with text data is good.
            - For example, the Taiwanese civic tech community [[g0v]] has its minutes published on HackMD, which you can crawl
                - [[Cybozu style]] article crawls, it becomes a chatbot that talks about Cybozu culture
            - But even if you build a chatbot that learns these things as a start, it's not very interesting if you can't build a feedback loop for it.


Building a feedback loop is important.
- What is a feedback loop?
    - ![image](https://gyazo.com/e2ef115531a07b58e362c723f59f3e16/thumb/1000)
    - 1: AI reads groupware
    - 2: When someone speaks to you, answer based on your memory of 1.
    - 3: This exchange is automatically written to the groupware.
    - 4: Vote on it in Komorebikagami and additional discussion will take place.
    - ✅The current implementation is to update the vector index (1), then the AI will post its impressions of the past day's updates to Scrapbox (3'), and then you can write your impressions (4').
    - [Reinforcement learning from human feedback, from [[Human in the loop]] to [People in the loop
- Anonymous Comorebikagami for AI output is superior in three ways
    - Compared to "the case against human speech."
        - No hesitation to argue because the opponent is not a human but an AI.
    - Compared to verbal rebuttals or submissions with apparent names.
        - I am anonymous so I don't have to worry about putting my opinion out there.
    - Since it's a "yes/no" vote
        - Unspeakable "faltering" and "[[uncomfortable feeling]]" can be honestly expressed.
- The "community atmosphere" changes from "vague and only vaguely understandable" to one where questions can be explicitly asked.
    - You can ask questions without social risk, and the AI will answer them first.
    - Whether the answer was good or not, and how it should be improved, will be the subject of discussion in the community.
    - In this process, no one human is attacked and the "virtual character" called AI is "improved by everyone" [[cooperative game]].
- Bringing "[[a]] better discussion mechanism" in a Japanese culture that values consensus rather than top-down direction, but fears conflict with others.
    - Also, the GPT portion absorbs language differences, which should support cultural integration of teams across different language areas
- This is what Nishio wants to create with the Omoikane Project
- However, the Omoikane Project is a group of volunteers, unlike a corporation, so it may be more difficult than in the case of a corporation.
    - Participation is open-ended, allowing participants to work freely based on their own interests.
    - It increases diversity and creativity, leading to new discoveries and results.
    - When looking back at the past after a period of time, it becomes clear "what was produced".
        - [[Connecting the Dots]]
    - We cannot predict in advance what will be born, we can only create an environment conducive to birth.

The "Thinking and Making the Future While Reading and Writing" Project
- The most meta of the Omoikane project's sap projects (by <img src='https://scrapbox.io/api/pages/omoikane/niryuu/icon' alt='/omoikane/niryuu.icon' height="19.5"/>)
- SF prototyping is a tool that allows us to think more concretely and deeply about the future by concretizing the future in the form of a novel.
- But this "act of reading and writing SF" of "SF prototyping" itself is already evolving into a new form in this Omoikane project
- The act of writing science fiction
    - AI assistance has lowered the bar.
    - The writing process, which used to be handled in a black box manner in the minds of science fiction writers, is now shared as a chat log with GPT.
    - And then people who had never thought they'd ever have the time to write their own novels got involved in writing science fiction.
- The act of reading science fiction
    - If you read science fiction in a book, your impressions are made in a different medium than the book
    - But by reading on the Scrapbox, which can be co-edited, your impressions become content on the same page as the science fiction, and conversations with other readers and links to other science fiction occur.
    - Voting on what you read in Polis and Komorebikagami, and being counted and clustered is an experience not found in existing novels.
- And many other things going on that I can't classify.
    - Ideas and plots that have not reached completion are shared,[/omoikane/shared-universe](https://scrapbox.io/omoikane/shared-universe).
    - Add development in the form of answer songs to those made by others, and use image-generating AI to create illustrations.
    - Interactive fiction, abstracting and transforming the novel
- Clearly a unique social interaction is occurring here.
    - This is the emergence of a new culture. In other words, a new future is being born here.
    - A project to observe and understand this phenomenon itself from a social scientific perspective.
- In designing this community, we were aware of [[Legitimate Peripheral Participation]].
    - It's more legitimate peripheral participation than I'm aware of.
    - Start with [[Peripheral Participation]] of "reading" and "reading and writing feedback" and gradually move on to "writing".
    - The acquisition of this "way of writing" is not only through abstract knowledge transfer, but also through participation and experience in specific contexts and situations "[[Situation-embedded learning]]."
    - The result is a "[[community of practice]]" of people with common interests.

Everyone is welcome to participate.
- Join [/omoikane/omoikane](https://scrapbox.io/omoikane/omoikane).
- Currently 45 people, 614 pages

---
This page is auto-translated from [/nishio/オモイカネ勉強会](https://scrapbox.io/nishio/オモイカネ勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.