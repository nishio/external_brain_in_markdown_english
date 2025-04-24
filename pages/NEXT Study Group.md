---
title: "NEXT Study Group"
---

10/6
        - AI has been writing a report once a day in Scrapbox since 7/29 at [[Omoikane Project]].
        - It's been two months of barreling through this and improving on it.
    - The last [[Omoikane Study Group]] (8/4) was right after that.
    - Summarize what you experienced and felt during the two months
- Up to now.
    - 2023-03-24  [[Story study session about connecting my Scrapbox to ChatGPT.]]
    - 2023-08-04  [[Omoikane Study Group]]

This block will be refined later.
- What did you experience and what did you feel?
    - 9/2  [[Difference in skin feel between vector search and RAG]]
    - 9/6  [[Raw ChatGPT and omni use cases are different.]]
    - 9/27  [[Thoughts on using a private OMNI]]
    - Difference in sense of public and private omni







Current Topics: Azure Cognitive Search
- 9/18 [[Azure Cognitive Search: Outperforming vector search with hybrid retrieval and ranking capabilities]]
    - ![image](https://gyazo.com/8e2fa02e91d9ee1566bd48aeb6008048/thumb/1000)[src](https://techcommunity.microsoft.com/t5/azure-ai-services-blog/azure-cognitive-search-outperforming-vector-search-with-hybrid/ba-p/3929167)
    - Talk about combining both and reranking (≈reordering after looking at the search results) is far better than the common "keyword only" search, or vector search.
- It's been known for a while that "it's better to combine and rerank."
    - from  [[Combine Searches]]
        - [AI King - Japan's No.1 Quiz AI Competition and won 3rd place｜PKSHA Delta](https://voice.pkshatech.com/n/n83343d0e00e0) 2023-01-04
            - > ![image](https://gyazo.com/763fb9ae8f7e017772460b9ef471e515/thumb/1000)
            - Talk about combining searches.
                - I'm combining [[DPR]] and [[BM25]].
                    - DPR is a messy [[vector search]].
                        - > [[Dense Passage Retriever]] (DPR)... Dense vector-based using pre-trained models
                    - BM25 is, in a crude way, "modern TF-IDF" BM25: Lexical Match-based.
                    - Very small overlap in search results for both DPR and BM25
                        - → Good of both.
                    - Vector search is available in:.
                        - Strong semantic similarity
                        - Missing low-frequency words / Significant performance degradation outside the distribution (OOD)
                    - Weak on low-frequency words (=weak on proper nouns, technical terms, and product names), so need to combine normal search
                - FiD=[[Fusion In Decoder]]
                    - A text generation system that reads 100 search results
- Vector search, good for ambiguous search of natural language conversation because of fluffy hits, but "the name of the company you visited in sales" or "product model number" is a high cognitive load for the user because it also hits "different things that look very similar".
    - I was thinking that the groupware needs to improve this problem if it is going to use vector search.
    - [[Azure Cognitive Search]]
        - 7/18 Public Preview begins
        - I'm thinking of trying it soon.
    - If you look at the configuration, [[BM25]] + [[HNSW]] + [[rerank]] is a royal configuration.
        - HNSW ([[Hierarchical Navigable Small World]]) is a vector neighborhood search method also used in Qdrant and Pinecore.
- What is "search?"
    - What is the value you are creating for your customers?
    - The "search UI" we provide to users now is probably not the best way to provide customer value
    - Relanker ≈ "a midget who looks at 200 search results and sorts them in good order."
    - Fusion in Decoder ≈ "a little guy who reads 100 search results and writes sentences"
    - The era in which these things are becoming available
    - Especially in the reranker section, a style that takes into account things other than "text explicitly entered by the user," such as operations on the groupware immediately before, may lead to differentiation.

vector search
    - [[Vector Search in Nishio]]
    - Vector search for this Scrapbox project, published 2023-06-05
- For me, the usefulness of vector search is [[empirically obvious]], but maybe I should present a case study for those who have not yet experienced vector search
    - [[Cases where vector searches were useful]]
    - Case 1
        - It's all about "social security spending."
        - I recall a past lecture in which he said, "I've talked about the high cost of Social Security."
            - The focus was on the ratio of investment to science and technology.
        - I'd try to find it, but I can't find it by searching for "social security payments".
            - [[Vector Search in Nishio]] for "Social Security Funding Scientific Research" [hit](https://nishio-vecsearch.vercel.app/result/3YZTFccqWXMj6lR6OVkr)
            - ![image](https://gyazo.com/34b6beae7ed4d7d5d95fd0d4d08aaff6/thumb/1000)
            - The expression was "38 trillion for medical care, 24 trillion for welfare and others, and 120 trillion in total."
                - There's also "Science and Technology" a little further down the road.
        - I made an excerpt page with "Social Security Expenses" in the title.
                - [[Comparison of Social Security Expenditures and Science and Technology Expenditures]]

    - Case 2
        - I'm trying to come up with a story about a hole in the wall, and I'm searching for wall or hole, but I can't find it.
        - Vector search for "hole in the wall, you have to get close to see it."
        - Second candidate found.
        - ![image](https://gyazo.com/9c55e099867137986e3be8ead02a9fdb/thumb/1000)
            - [The fact that there is a wall ahead is not a reason not to proceed. [https://scrapbox.io/nishio/%E9%80%B2%E3%82%80%E5%85%88%E3%81%AB%E5%A3%81%E3%81%8C%E3%81%82%E3%82%8B%E3%81%](https://scrapbox.io/nishio/%E9%80%B2%E3%82%80%E5%85%88%E3%81%AB%E5%A3%81%E3%81%8C%E3%81%82%E3%82%8B%E3%81%) 93%E3%81%A8%E3%81%AF%E9%80%B2%E3%81%BE%E3%81%AA%E3%81%84%E7%90%86%E7%94%B1%E3%81%AB%E3%81%AF%E3%81%AA%E3%82%89%E3%81%AA%E3%81%84]
                - It's a match between "you can't see it unless you get closer" and "you could see it if you got closer."
            - The nuance of not being able to see the hole in the wall unless you get close to the wall.
        - The hole in the wall was pictured, but not texted.
            - I'll add a note.
        - There is also another page on the "hole in the wall" metaphor, which does not fit the purpose of this article, but I'll link it for future reference.

    - Case 3
        - Vector search on "unfeasible ideas seem original".
        - The one I was looking for was the fifth hit.
            - ![image](https://gyazo.com/395e22955d484b244995604e4b1664fb/thumb/1000)
            - > A layman's idea may appear original in an oral presentation, but it is not feasible.
            - > This paper compares amateurs who have never used Mindstorms with robot contest winners and runners-up (hereafter referred to as "experts") in the task "Build a robot that makes creative progress with Lego Mindstorms..."... There was no difference in originality between the genin and the amateurs... However, most of the amateurs failed to realize their ideas.
            - Didn't hit on the swing between "original" and "originality," between "unfeasible" and "unfeasible."
            - When we try to specify the search target with search keywords, we tend to use [[noun form]] keywords such as "unfeasible," but in reality, they are sometimes described by opening them to verb form.
        - There is a lot of very relevant content in the candidates above this one: [result](https://nishio-vecsearch.vercel.app/result/jZZIQiDcvPLdpv8EPsc2)
            - The pages of this experiment are episodic, which would make them memorable and easily recalled.
        - I created a new page with "[Unfeasible ideas seem original.

    - Case 4
        - Vector search on "kintone talks around data"
        - No.1:.
            - > I think the ideal situation would be to have the same collaborative editing capability for database schema and customization JavaScript.
        - No. 4: The
            - > Reforming Municipal Operations with Digital Solutions for Public Utilities
                - > Both municipalities used Cybozu's "kintone" as a digital solution. kintone allows users to build business applications without programming knowledge, as long as they have a working knowledge of Excel. It allows you to integrate email, Excel, and disparate information and create a unique business environment with your own ingenuity.
                - > I see - I was wondering how to explain kintone, but you explain it as "email and Excel integration".
                - I like the term "email and Excel integration."

    - Case 5
        - "Bias to measure only what is easy to measure."
            - > While cost is easy to measure numerically, quality is harder to measure and therefore easier to underestimate.

    - Looking Back
        - It's now possible to search by "this is what I meant" instead of "I must have written this 'string'."
        - Nishio himself is adapting to the vector search system.
            - Early cases search by fragments, as in "social security funding scientific research" and "hole in the wall, you can't see it unless you get up close."
            - As I get used to it, I'm searching for "short sentences that express meaning" like "unfeasible ideas seem original," "kintone is a conversation around data," and "bias to measure only what is easy to measure."
        - The other day, when I asked a user to use this vector search while sharing the screen on Zoom, the user typed, "Tell me about your experience of cooking for yourself," and I thought, "Oh, you don't understand how to use this at all.
            - I don't know the difference between a vector search and an LLM that is [[Instruction Tuning]].
            - Maybe this is a distinction most people in the world don't make.
            - Only those that have undergone additional learning ([[Instruction Tuning]]) to "regard user input as instructions and follow those instructions" will follow the instructions in the underlying language model.
            - Similar input just because ChatGPT does.
        - The user then typed in "description about cooking" and found my terrible cooking story, which is a good thing, right?
            - Not much vector search goodness.
                - Because the "meaning" in the query is in effect one word of "cooking", so it is no different from a keyword search.
            - Now when I search for "I made a terrible dish" [lots of terrible past dishes](https://nishio-vecsearch.vercel.app/result/N6IhY622RdHNl9ebCXSQ)www

- [[Omoikane Project]]  6/4~
- [[Omoikane Embed]] see [/omoikane/Omoikane Embed](https://scrapbox.io/omoikane/Omoikane Embed)
    - Mechanism for creating [[vector index]] for [Omoikane Vector Search
        - [[Github Action]] at 6:00 a.m. Japan time
        - Automatically export JSON from Scrapbox
        - Vector embedding by inscribing on 500 tokens
        - Upload to [Qdrant
    - Began operation on 6/9, now running daily.
    - I started writing reports in Scrapbox on 7/29.
        - The previous [[Omoikane Study Group]] (8/4) was just starting to get up and running.
    - 8/9 Organized code to make it easier to put into other projects.
        - People actually showed up to try it.
        - I put this [/nishio](https://scrapbox.io/nishio) in this [/nishio
            - This is omoikane-embed-nishio, or [[omni]] for short.
        - It's been two months since we've made a lot of improvements to this omni.

- [[Intelligent collaboration between AI and humans]]
- 8/16  [[Intelligent collaboration between AI and humans]]
    - ![image](https://gyazo.com/9d448f09d2d3c47287128ca2efef61dd/thumb/1000)
        - AI writes a note in Scrapbox, AI reads the note the next day, and writes another note.
        - Repeat intellectual production activities in the same way as humans in the collaborative editing space called Scrapbox
    - Implemented on 8/12,
            - [[AI writes research notes daily]]
            - [[Co-operation with AI]]
    - Wrote "[[Intelligent collaboration between AI and humans]]" on 8/16 and spoke at 8/20 (Unexplored Junior Interim Camp) and 8/21 (Lab Youth Camp).
- 8/21 [[no need for humans to pull the trigger]].
    - AI's once-a-day note-with-comments communication style has the advantage of "no human triggers to pull".
        - Even when humans are too busy to write comments, AI goes ahead on its own.
        - Even if you write some comments, there is no "send" action.
            - I may come up with something after that and add more.
            - No need for human decision-making on when is "the end" or "completion".
        - Not sure if it would be better without the "send" action.
            - Personally, I think it's better to have it, and can be accomplished by running scripts in the development environment when you're in front of a PC.
            - I'm on the train to get to the camp site, and I feel like triggering from my phone in these cases.
                - → Later that function was added ([[Pioneer Mode]]).
- 8/21  [[I want to fork a page.]]
    - →8/21  [[multi-head]]  /  [[page memory]]
    - ![image](https://gyazo.com/ee4e571fa7c0ea7aad70ad241c79ed47/thumb/1000) from  [[page memory]]
    - AI created a style of adding to the same page instead of creating a new page.
        - After that, the style of creating new pages was DISABLED (8/31 main branch stopped).
    - This allowed "multiple topics" to develop in parallel
        - Write a note that a human thinks "I'd like to develop this topic" as a seed and treat it as an AI note (with 🤖🔁 in the title in the implementation at the time).
- Talk if you can afford it (I can't afford it)
    - 8/21 [[page memory]] →8/23 Ignore used pages from all history →8/26 [[Pinning effect on the topic]].
    - 8/25 Update page limit -> 8/31 [[Update Interval of AI Notes]].
    - Changed the method of addition: 9/11 [[Difference between Recurrent Notes and Iterative Commenter]].

- [[Extending the Red Link with AI]]
- 8/30  [[Extending the Red Link with AI]]
- ![image](https://gyazo.com/4d69e9d9b57633554d06698e00c3ca29/thumb/1000) from  [[Extending the Red Link with AI]]
        - [[AI writes research notes daily]] Useful use cases for the system that were not originally intended.
- History
        - If you create a [[red link]] (an empty link) and then specify the red link, the page is now created using the results of a vector search on the link title.
    - This is useful
        - What kind of experience does it bring?
            - I think I've written something like this before."
            - (Sometimes assisted here by Scrapbox link suggestions)
                - If not, you had to use search and other methods to find them.
                - We can leave that to AI.
    - Further Development
        - When there is a good "long phrase" in the AI's generation or in the past descriptions that the AI has uncovered, make it a link, like a marker.
        - Naturally, it would be a red link.
            - This is a long one, so one would expect that it would not be a natural connection.
            - So we will "red-link extension" this.
- Specific example 1
        - [[🌀Exchange Form D]], the AI "reaffirmed the importance of exchange in the problem-solving process."
    - I didn't know what "the importance of exchange in the problem-solving process" was, so I red-linked it and stretched it.
    - AI said, "Problem solving bridges the gap between the ideal and the current situation, and the exchange of information in the process is important." and I understood, "I see, you mean exchange of information is exchange."
    - I wrote about this realization in [Information exchange is exchange
        - (The meaning of this realization is probably not conveyed, but that is a case study for later, so I won't explain it here.)
    - After a while, "[Is the exchange style of knowledge exchange A?" The question arose
    - The "[[Public as the object of the gift]]" that was created there was extended by making it a red link.
- It can be called "[[search with description]]".
    - Search with explanation of why it was shortlisted.
    - Instead of a human directly reading the search results, the AI reads them first and writes a description.
    - 9/2  [[Difference in skin feel between vector search and RAG]]
        - > [kazunori_279](https://twitter.com/kazunori_279/status/1696336555215053072) I guess instead of messing around with fine tuning and RAG, we can simply do a vector search with emb and display the results. I thought, "Why not? I thought so.
        - > [nishio](https://twitter.com/nishio/status/1696396921903190238) I have always been of the "just do a vector search" school of thought, but I feel that RAG is better when used as an intellectual production assistant rather than just a question and answer tool. I feel that RAG is better for use as an assistant for intellectual production, not just for answering questions. The generation part functions as "summarizing the search results according to the purpose". This assumes that the purpose is given separately from the query.
    - I find it different and more useful than a simple vector search.
- It could be called "decoupling search and action."
    - Now "searches" don't involve updating, so if I don't update my Scrapbox with the search results, the search never happened!
        - Implicitly required that "humans read the results and act on them before they forget they searched."
        - Search and action were coupled.
    - AI extends the red link" is a human writes the "intention of search" and the AI does the "search, reads it, and writes a beat of explanation", so the human action after the search is optional.
- 9/4 [[Pioneer Mode]]
    - > Pioneer Mode is a development of "Extending the Red Link with AI
    - >  If you put a link on the "✍️🤖" page, the AI will check it periodically and generate it automatically.
    - I can now use it from my phone.

- [[Raw ChatGPT and omni use cases are different.]]
- 9/6 I realized I was unconsciously using ChatGPT and [[omni]] differently.
- So there is a difference in the utility that the two provide, what is the difference?
- from  [[Raw ChatGPT and omni use cases are different.]]
    - Since most texts in the world are written in "expressions that many people can read and understand", whereas my research notes are written in "expressions that I can understand", an AI that [[RAGs]] with the latter accelerates my personal thinking much more efficiently than ChatGPT
    - In my research notes I don't write explanations for words I know, so the AI that reads them doesn't write explanations for what I know either. [[Concepts are tools for economy of thought]], so it is more efficient to use them without explanation in one's thinking.
    - It is useful to use ChatGPT when explaining it to others
- Case 1
    - <img src='https://scrapbox.io/api/pages/nishio-en/omni/icon' alt='omni.icon' height="19.5"/>To improve knowledge productivity, we need to understand the importance of collaboration and the importance of sharing tacit knowledge prior to planning."
        - I can tell that this "collaboration" is "the story of Ikujiro Nonaka's [[SECI Model]]". This can be read to compensate for a little poor Japanese.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Please put in terms that the average person can understand, "In order to improve knowledge productivity, we need to understand the importance of collaboration and the importance of sharing tacit knowledge prior to planning."
    - <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>To use knowledge effectively to get things done, it's important for everyone to work together, to share information, and for everyone to share their own experiences and tips before the actual work begins."
        - Most people will find it easier to understand.
        - From my subjective point of view, it is clearly degrading. Maybe GPT4 doesn't understand the cooporation correctly.
- Example 2 ("Information exchange is an exchange" as you just said)
    - I interpret the word "interchange" as "I'm talking about Yukito Emiya's [[interchange format]].
    - Very rough description.
        - Exchange Form A: Giving a Gift in Return
        - Exchange Form B: Obedience and Protection
        - Exchange Form C: Pay the price and get the goods
    - Information exchange is an exchange" is a realization that "since information is also a good, information exchange can be considered within the framework of Gyoto Emorya's exchange theory.
        - "So [Is the exchange style of knowledge exchange A? →No, I think information sharing using [[a place of sharing]] instead of DM is [[New Exchange Style]] because there is [[Public as the object of the gift]], isn't it?" This led to the realization that
- Supplemental (if time permits)
    - Technically, I think that by loading a lot of the prompts with RAGs, the "chat-ness" is gone and it's closer to a "summary task," and the pressure by [[RLHF]] to make the expression more palatable to the general public is down.

- [[Thoughts on using a private OMNI]]
- 9/20 I started to make [[private omni]] because I found omni running on public /nishio useful enough.
    - To include items (e.g., books) that cannot be placed in the public domain in the search results.
        - [[Transverse Vector Search Experiment Memo 2023-09-20]]
- 9/27  [[Thoughts on using a private OMNI]]
- Vector search alone is pretty interesting.
    - If you imagine "a system in which books pop up and related pages open when you talk in front of a bookshelf," you will understand how interesting it would be.
    - If someone else's Scrapbox is hit, I read it interestingly, "Mr. X, I didn't know you wrote about this," which may lead to subsequent communication.
- Difference in sense of public and private omni
    - I'm still using it differently.
        - So you must feel different utility, what is it?
    - Feelings differ depending on whether the data is primarily of your own origin or not.
    - When it's self-derived, it's like the AI and the human are driving the thinking as a unified entity.
        - I feel like I'm accelerating."
        - Feel like you're "seeing things from a different perspective."
    - When derived from others, the feeling of "Oh, so this is what Mr. X said about this subject..."
        - I feel like I "found someone else's statement."
    - case
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Should scientists who do basic research operate on their own dime, or should the government invest in them as public infrastructure that is underinvested if left to the market?
        - <img src='https://scrapbox.io/api/pages/nishio-en/omni/icon' alt='omni.icon' height="19.5"/>The "anti-fragility [[sic]] [[sic]]" fragment suggests the idea that government investment should be directed toward nonobjective activities, rather than research in general.
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Oh, I don't know if that's what you're talking about, I'll read it.
        - > What the government should be spending money on is non-objective tinkering, not research --- Anti-Fragility [[top]], p. 375
    - Fragments derived from oneself are reconstructed once chewed up inside oneself, so there is a sense of smooth connection. Fragments derived from others still have a hard surface.
        - However, it may be possible in the future for LLMs to do the "chewing and reconstructing", "melting together", and "smoothly connecting" themselves by fine-tuning with their own origin data.
            - 10/3  [[Teaching LLM to Knowledge Brewing in Scrapbox]]
    - Fragments of different viewpoints originating from oneself drive the zinthesis more strongly than fragments of different viewpoints originating from others
        - Is it because I'm naive enough to pass off things of other people's origin as "that's one way of thinking" even if it differs from my current opinion?
        - The "it's normal for others to have different opinions" runaround?
        - If your self-derived opinion differs from your current opinion, since you are both you, "Why do we disagree?" Since they are both me, does this strongly trigger the question, "Why do we have different opinions?


Vector search is an opportunity to cut out
- ![image](https://gyazo.com/3f316a9871d2f7ca09716b09a257d512/thumb/1000)
- 9/2  [[Hitting part of a series that has not been carved out provides an opportunity for carving out]]
- Countless beneficial events that have occurred
    - Diaries, chat logs, lecture materials, transcripts of conversations, and other "time-lined descriptions
    - AI searches on a topic and hits that "in the middle of the sequence" and mentions it there.
    - The person who sees it cuts out that part of the page and creates a new page.
- [[Topic oriented cutout from time-ordered description]].
    - > The balance between time-based and topic-oriented is an important issue in organizing and interpreting information. While organizing information along a time axis is good for reliving the flow of information, it may be necessary to destroy the structure of the time series to create a new topic-oriented structure when exploring a particular topic or thematics. Topic-oriented organization, on the other hand, allows information to be organized based on a specific theme or context. Finding the right balance between these facilitates efficient organization and understanding of information.<img src='https://scrapbox.io/api/pages/nishio-en/omni/icon' alt='omni.icon' height="19.5"/>
- Difficult to do in advance
        - [[The appropriate way to cut out the need is determined after the need is identified.]]
- Explanation of the concept of "[[cutting]]" as many people may be unfamiliar with it.
    - In the realm of personal knowledge management, there is a belief that a short page on a single topic is preferable
        - Example: [[Evergreen notes should be atomic.]].
            - > This makes it easier to form connections across topics and contexts!
        - Similar to the [single responsibility principle
    - So the act of extracting a "single topic" from a "page with multiple topics mixed in" is performed.
    - In Scrapbox, this can be done by selecting multiple lines and choosing New Page from the balloon menu.
        - This is commonly known as "cutting out" and as the name suggests, "cutting" and creating new pages and linking them to each other
            - Whether "cut" or "copy" is better is debatable, and I don't always think cut is better either, there is value in keeping lecture materials readable through.
                - With the minutes being placed in groupware, or something like that, users would be resistant to editing them.
                - Scrapbox's philosophy of "[[Not a warehouse for dead text.]]" would say, "Don't use it that way."
- Due to the fact that it is a vector search for fragments inscribed in chunks
    - I'm chopping at 500 tokens right now, which is about the size of a page in a book.
    - With chat logs, it's not an entire thread or one specific person's statement, but a unit of "several exchanges".
    - The search returns "the most dense mentions of the topic" in a long conversation.
    - Create a new page by discarding the parts of that chunk that you don't want, picking the relevant ones around it, or writing new opinions inspired by it, which is useful


[[Vector search serves as a tool for cognitive resolution]].
- ![image](https://gyazo.com/5a0d0f0ccf1c48f4060d7fd62f099afa/thumb/1000)
- from 10/3  [[Teaching LLM to Knowledge Brewing in Scrapbox]]
    - > [nishio](https://twitter.com/nishio/status/1709155663342186538) from my own research notes [[vector search serves as a tool for cognitive resolution]].
    - >  That's because "similarities" are presented [[to observe what we are thinking about now from a slightly different direction]]... The process of "verbalization" includes "increasing the resolution to describe the world" and "re-describing the understanding obtained by observation at a higher resolution in a form that can be conveyed to others", which are two different things and need to be considered separately.
        - Observing what you are thinking about from a slightly different direction" increases [[Cognitive Resolution]] by thinking "[Similarity -> What is the difference?
    - [[Similarity -> What is the difference?]]
    - >  Patterns of thought that are beneficial for increasing [Cognitive Resolution
    - > When you feel "[[Similar.]]" for two concepts, the fact that you did not feel "this is exactly the same thing" indicates that you feel "[[difference]]" there.
    - > The "difference" is not [[verbalizing]] at this time.
    - > "What is the difference?" and then you can [[observe things in more detail]].
- Vector search works as a "mechanism to scrape together fragments of similar topics.
    - Similar to the KJ method of "gather fragments that may be related in one place, and then think about what kind of relationship they may have.
        - [[Small convergent moves and divergence from them]]
    - There is a difference between "similar topics" and "similar opinions."
        - Opposing opinions on similar topics are rather close in terms of vector search
            - [[Conflict is a close relationship]]




Below are my notes before writing
The following is a summary of the information entered<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- 7/29: AI writes to Scrapbox, introducing the concept of Scrapbox Agents.
- Early to mid-August: Omoikane study group, discussion on working with AI, writing research notes with AI, evolution of vector search, and topics on handling AI-generated pages.
- Mid to end of August: topics related to updating and search, taking into account multi-head, page memory, and user cognitive load.
- Beginning of September: Explore AI-user interaction, note management, and relevance between different content.
- Mid-September: various topics related to multi-head thinking, the intellectual production techniques of engineers, and working with AI.
- Late September: LLM vs. other models, discussion on human concepts, optimal use of Scrapbox, and feedback on non-public tools.
Overall, this period seems to focus on Scrapbox and AI integration, particularly the concepts of vector search and multi-heading, and AI thinking and interaction with the user.

Jul 29 AI writes to Scrapbox
    - [[Agents living in Scrapbox.]]
8/4  [[Omoikane Study Group]]

8/11 [/omoikane/ consulted GPT4 on how to proceed after this 2023-08-11](https://scrapbox.io/omoikane/ consulted GPT4 on how to proceed after this 2023-08-11).

8/12
    - [[Co-operation with AI]]
- Findings: [/unnamed-project/AI's pace is so fast that humans can't keep up](https://scrapbox.io/unnamed-project/AI's pace is so fast that humans can't keep up)

8/12  [[AI writes research notes daily]]
8/16  [[Nodal point of thought on Scrapbox and AI 2023/8/16]]
8/16 Stacking Vector Search Results
8/16 [[overwrite mode]].
8/18 Ignore AI-generated pages from vector search
8/21  [[multi-head]]
    - [[page memory]]
8/23 Ignore used pages from all history

8/25 Update page limit
8/26  [[Pinning effect on the topic]]

8/29 Lift Ignore from Vector Search on AI-generated pages
8/30  [[Extending the Red Link with AI]]
8/31 Main branch stopped
8/31  [[Questions encourage verbalization, but there are different kinds of questions.]]
8/31  [[Introduction to ENCHI]]
8/31  [[Clarification of AI's role is important.]]
8/31  [[Update Interval of AI Notes]]
8/31  [[A case study of SF prototyping for a junior high school student's work experience]] <img src='https://scrapbox.io/api/pages/villagepump/mtane0412/icon' alt='/villagepump/mtane0412.icon' height="19.5"/>
9/1  [[Page as a fluid process]]
9/1 [[Trade-off between speculation and development]] # distress
9/1  [[What is the role of AI in this project?]]
9/1  [[Is there an AI with multiple personalities?]]
9/1  [[Why not specify the purpose of each page of the AI note?]]
9/1 [[It's buried at the bottom of the AI page.]] # Cause of distress
9/1  [[Discovering connections between different content]]
9/1  [[Summon other people's AI to your diary]] <img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
9/2  [[Difference in skin feel between vector search and RAG]]
9/2  [[Hitting part of a series that has not been carved out provides an opportunity for carving out]]  +1
9/2 [[AI can't rest because it will develop endless thoughts.]] # Cause of distress
9/2  [[The realization that you can read the URLs of other projects]]

9/2  [[Multi-head thinking]]  epoch
9/2  [[Pages that sometimes emerge]]


9/3
    - [[Multi-Head Thinking" and "The Engineer's Art of Intellectual Production."]]
    - [[Small convergent moves and divergence from them]]
    - [[Write the summary above.]]

9/4
    - [[___BELOW_IS_LESS_INTERESTING___ to ___BELOW_IS_AI_GENERATED___.]]

- [[🌀Multi-head thinking]]
- [[🌀AI Dejima]]

[[Iterative Commenter]]
[[Pioneer mode]]

~
- [[AI Shaman]]

9/11
[[LLM Course by Matsuo Lab]]
- [[Examples of AI providing different perspectives]]
- [[Experiments in having AI interpret lyrics]]
- [[Difference between Recurrent Notes and Iterative Commenter]]

9/12
- [[Letting AI twist and turn unclear, long-term tasks]]
- [[PDF to Scrapbox]]

9/13
- [[Business is Matching Seeds and Needs]]
    - [[Meta-discussion: Business is a Matching of Seeds and Needs]]
        - [[Market and Individual Needs]]
        - (9/5)  [[In-Depth Value Exploration: Collaboration and Growth]]

- [[Letting AI develop pages]]

9/15
- [[Consideration of the long sleeping oracle]]
- [[Recent Morning Routine 2023-09-15]]

9/16
- [[Collect lyrics about life and pick out your favorite phrases.]]

9/18
- [["Which parts are AI and which parts are human?" The question is "Which part is AI and which part is human?]]

9/20
Integration in private project
- [[Transverse Vector Search Experiment Memo 2023-09-20]]

2023/9/22
- [[Have them verbalize the difference between what is similar to LLM]]
- [[(Tentative) Operation not yet named]]
- [[Restructuring Thinking and Communication with Scrapbox]]

2023-09-24
- [[The concept of "human" is vague.]]

2023-09-29
- [[Thoughts on using a private OMNI]]

- [[Teaching LLM to Knowledge Brewing in Scrapbox]]

---
This page is auto-translated from [/nishio/next勉強会](https://scrapbox.io/nishio/next勉強会). If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.