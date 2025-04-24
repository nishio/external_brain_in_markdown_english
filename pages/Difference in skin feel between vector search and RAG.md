---
title: "Difference in skin feel between vector search and RAG"
---

from  [[Diary 2023-09-02]]
- Difference between [[vector search]] and [[RAG]] [skin feel

Recently, I have been using [[Extending the Red Link with AI]] because it is very useful, but there is a difference in my skin feeling from when I was using [[Vector Search in Nishio]], and I wondered what it was.
- [[Search results do not afford editing]]
- Written in Scrapbox [[Afford edits]].
    - That's because Scrapbox is a collaborative editing tool.
    - Not if it's a RAG or not.
        - The other side of the chat doesn't afford editing of the other side's statements either.
    - [[Output of ideas by scraping instead of writing]], the AI output needs to afford editing

RAG: [[RETRIEVAL-AUGMENTED GENERATION]]

8/29
> [kazunori_279](https://twitter.com/kazunori_279/status/1696336555215053072) I guess instead of messing around with fine tuning and RAG, we can simply do a vector search with emb and display the results. I thought, "Why not? I thought so.
> [What can and what can't be done with LLM fine tuning｜npaka](https://note.com/npaka/n/nec63c01f7ee8)
- > [nishio](https://twitter.com/nishio/status/1696396921903190238) I have always been of the "just do a vector search" school of thought, but I feel that RAG is better when used as an intellectual production assistant rather than just a question and answer tool. I feel that RAG is better for use as an assistant for intellectual production, not just for answering questions. The generation part functions as "[[summarizing the search results to suit your purpose]]". This assumes that the purpose is given separately from the query.
- > [kazunori_279](https://twitter.com/kazunori_279/status/1696424311870148981) Indeed, RAG is useful if the main service is to interact and assist users.

[[Search with description]]

__BELOW_IS_AI_GENERATED__
# ベクトル検索とRAGの肌感の違い
 2023-10-05 16:53 <img src='https://scrapbox.io/api/pages/nishio-en/omni/icon' alt='omni.icon' height="19.5"/>
## digest
.
Discusses the difference between using "vector search" and "RAG," arguing that Scrapbox is a collaborative editing tool and affords editing; AI output must also afford editing. Also introduced a discussion on Twitter about the difference between vector search and RAG.

## Relation to Fragment
.
The "next study group" fragment describes the advantages and disadvantages of vector search and relates to the difference in usability between the note "vector search" and "RAG." The fragment "cross vector search experiment memo 2023-09-20" describes an experiment in vector search and is related to the usability of the note "vector search. The fragment "RAG" describes the concept of RAG and relates to the usability of RAG in the notebook.

## deep thinking
The difference in usability between vector search and RAG may be due to the different "editorial affords" that each provides. Vector searches display results as they are, while RAGs summarize the search results and display them for a specific purpose. In this way, RAGs provide an environment in which users can easily edit information.

## summary of thoughts
The difference in the usability of vector searches and RAGs is due to the different "editorial affords" that each provides.

## Title
.
"Vector Search vs. RAG Usability Differences: an Editorial Afford's Perspective."

### extra info
titles: `["next study group"], "Cross-sectional vector search experiment memo 2023-09-20", "RAG", "In the end, what we need is to improve search accuracy", "pVectorSearch2023-04-29~05-31", "The reality of collaborative work with AI and S-curves"]`
- [[Intellectual Productivity Study Group by LLM]]
- [[Transverse Vector Search Experiment Memo 2023-09-20]]
[[RAG]]
- [[In the end, what is needed is improved search accuracy]]
[[pVectorSearch2023-04-29~05-31]]
- [[The reality of collaborative work with AI and the S-curve]]
fragments

```
### next study group
	Vector searches are good for vague searches in natural language conversations because they produce a flurry of hits, but they also produce hits for "the name of the company you visited on a sales trip" or "the product model number" because they produce hits for "different products that look very similar," which places a high cognitive burden on the user.


The following is a summary of the information entered[gpt.icon]
	7/29: AI writes to Scrapbox, introducing the concept of Scrapbox Agents.
	Early to mid-August: Omoikane study group, discussion on working with AI, writing research notes with AI, evolution of vector search, and topics on handling AI-generated pages.
	Mid to end of August: topics related to updating and search, taking into account multi-head, page memory, and user cognitive load.
	Beginning of September: Explore AI-user interaction, note management, and relevance between different content.
	Mid-September: various topics related to multi-head thinking, the intellectual production techniques of engineers, and working with AI.
	Late September: LLM vs. other models, discussion on human concepts, optimal use of Scrapbox, and feedback on non-public tools.
Overall, this period seems to focus on Scrapbox and AI integration, particularly the concepts of vector search and multi-heading, and AI thinking and interaction with the user.


### Cross-sectional vector search experiment memo 2023-09-20
Transverse Vector Search Experiment Memo 2023-09-20
We conducted an experiment to increase the number of data to be searched for in [Extending the Red Link with AI], which we have been running publicly on this Scrapbox.
	Searches include other people's Scrapbox data, books and papers
		relevance
		　 [Cross-sectional Vector Search] 
  		 [Talk about putting books in Scrapbox.] 
  		 [Individual and aggregated loops] 
	Since there might be some problems with publishing the generated results as they are without review, the output destination is a private project that is not open to the public.
　	Subsequent updates changed the search hits to output directly to Scrapbox, making it clearly unpublishable.

[https://gyazo.com/bb1a0bd6cb151fa1b6ffa2d7c498744c]
　The page is automatically generated by AI at the destination of the red link created like this

mounting
　Load from local pickle
　　It takes about 5 seconds to read 100,000 records
　About 7 seconds to perform a local vector search
　It's slow when you think of it as a web app response, but with the recent "throw a keyword or page that comes to mind, work on something else, and look at it after a while" style, it's not a problem.
　　There's about 10-25 minutes between when you throw the query and when I come back to check the results (I don't measure it).


### RAG
RAG
 [Combine Searches] in [Generative AI]

[Retrieval-Augmented Generation]
[Retrieval-Augmented Text Generation]



### In the end, what we need is to improve the accuracy of search

>[nishio https://twitter.com/nishio/status/1704379950743339227] Generation AI is effective when used properly for generation, but what do customers want to generate in the first place? When I think about it, most customers' needs are "to find the important parts among a lot of things that are hard to read", and even if they finally generate, there is "to find materials for generation" before the generation, so search is necessary after all.

>[nishio https://twitter.com/nishio/status/1704380927970009522] The story is slightly different and I don't think "conventional technology is better" at all. I already use neither conventional search nor my own vector search almost exclusively [RAG]. I think that the domain of competition is to combine and re-rank sparse and dens search when increasing the usefulness of it.



### pVectorSearch2023-04-29~05-31
　　　This looks interesting.
　　　　For example, loading a request with "false dichotomy" will return `https://gyazo.com/80d45ec33ca8cbb138108d71ad7eec02` in the response.
　　　　	[[誤った二分法.icon]]
　　　　 [blind spot card] can be drawn in a vector search in the sentence I'm writing, rather than randomly.
　　　　This is possible because of the accumulation of "image" and "text" pairs in the form of "pages" in Scrapbox
　　　　 [The image and text pair has value.] 

2023-05-04
  [Vector search your own Scrapbox and follow the 2hop link] 
		Examples of vector searching and looking at images

2023-05-11
	It would be interesting to [collect questions and improve].

2023/5/16
　A system that recognizes speech when you are speaking and automatically queries it to search this Scrapbox and display matches.
　Related Pages" for speaking
　　At first I thought "search only images", but then I thought I could just use Scrapbox's related page format to display pages without images.

2023/5/31
　 [Interaction of personal knowledge networks] 
　 [I want to search other people's Scrapboxes for vectors.] 
　Maybe it would be good to be able to do a "vector search including things other than yourself" based on this area.
　I can't really relate to the "Scrapbox by Yasukazu Nishio" vector search function, because it makes me see things differently from the way other people see them, and I have no sympathy for what they should be.


### Actual conditions of collaborative work with AI and S-curve
		It beats the experience of "writing it down to the last word and handing it over to the AI."
	On 9/1, he wrote "[Difference in skin feel between vector search and RAG]".
		Afford to [edit]."
	9/9 interpreted as "[Recommendation with context]"

__BELOW_IS_AI_GENERATED__
[*** AIとの協働作業の実態とS字カーブ] 2023-09-18 00:24 [omni.icon]
[** digest].
Collaborative work with AI detects periods of stagnation in thinking and throws the content to AI to move on to another task. Human thinking follows an S-curve, and AI can be helpful in times of stagnation; working with AI can smooth the transition from Task A to Task B. Also, collaborative work with AI can avoid stagnant periods in thinking by sensing when thinking is stagnant and throwing content to AI to move on to another task.

[** Relation to Fragment].
The fragment "Intelligent Collaboration Between AI and Humans" provides a specific example of AI-human collaborative work, which is directly related to the note. Specifically, the AI and human become team members and create a new form of teamwork, which is consistent with the collaborative work with AI described in the note.

[** deep thinking]
Collaborative work between AI and humans can avoid periods of stagnant thinking by sensing periods of stagnant thinking and throwing the content to AI to move on to another task. This is based on the characteristic of an S-shaped curve in human thinking, and demonstrates the effectiveness of collaborative work between AI and humans.


```

generated: 2023-10-05 16:53
---
This page is auto-translated from [/nishio/ベクトル検索とRAGの肌感の違い](https://scrapbox.io/nishio/ベクトル検索とRAGの肌感の違い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.