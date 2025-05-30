---
title: "AI Baltasar Gracian Experiment"
---

[Have [[GPT3]] read [[The Art of Worldly Wisdom]] by [Baltasar Gracián.
- I really want to let people read this Scrapbox of mine, or data that is not on the internet (my book or someone else's book).
- However, the GPT3 tokenizer is currently not very suitable for handling Japanese ([[GPT3 reverses the information density.]]).
- So I'm going to do it in English.

## Preparation
py

```
documents = SimpleDirectoryReader('data').load_data()
index = GPTSimpleVectorIndex(documents)
"""
INFO:root:> [build_index_from_documents] Total LLM token usage: 0 tokens
> [build_index_from_documents] Total LLM token usage: 0 tokens
INFO:root:> [build_index_from_documents] Total embedding token usage: 74187 tokens
> [build_index_from_documents] Total embedding token usage: 74187 tokens
"""
```


## "Say something funny."
py

```
index.query("say something interesting:")
"""
INFO:root:> [query] Total LLM token usage: 3949 tokens
> [query] Total LLM token usage: 3949 tokens
INFO:root:> [query] Total embedding token usage: 4 tokens
> [query] Total embedding token usage: 4 tokens
"""
```


Response
> It is important to be aware of the power of first impressions, as they can often shape how we view a situation or person. It is also important to be aware of our own faults and to take steps to address them, as this can help us to become better people. Additionally, it is important to be aware of the power of words and to use them wisely, as they can have a lasting impact on those around us. Finally, it is important to be aware of the power of kindness and to use it to our advantage, as it can help us to build strong relationships with those around us. Additionally, it is important to be aware of the power of subtle policy and to grant favours before they are deserved, as this can be a proof of being obliging. Furthermore, it is important to never share the secrets of your superiors, as this can have serious consequences.
> (DeepL)It is important to be aware of the power of first impressions, as they can influence how we view a situation or person. It is also important to be aware of one's shortcomings and to improve upon them in order to become a better person. Furthermore, it is important to be aware of the power of words and to use them wisely. The power of words can have a lasting impact on those around us. Finally, being aware of and harnessing the power of kindness helps us build strong relationships with those around us. Furthermore, being aware of the power of subtle policy and giving before receiving is important because it is evidence of ingratitude. Furthermore, it is important never to divulge a superior's secrets, as this can have serious consequences.

I'm reading from `ccxvi Be Expressive.` to `ccxxxvii Never Share the Secrets of your Superiors.` (216~237)
- The original is a collection of aphorisms, so if you try to summarize it, it's just a series of short stories.
- The query, "Say something funny," is a mess.
- Let's try something a little more question-like.

## poses a question that did not exist at all in Gracian's time
.
Q: Some people compare AI generation of text to search and claim that AI generation is futile because it could be wrong.
Q: Some people compare AI generation of text to search and claim that AI generation is futile because it could be wrong. What do you think?
py

```
r2 = index.query("Q: Some people compare AI generation of text to search and claim that AI generation is futile because it could be wrong. What do you think?")
"""
INFO:root:> [query] Total LLM token usage: 4346 tokens
> [query] Total LLM token usage: 4346 tokens
INFO:root:> [query] Total embedding token usage: 29 tokens
> [query] Total embedding token usage: 29 tokens
"""
```


> I think that AI generation of text can be a useful tool, but it should not be relied upon as a replacement for human creativity and insight. AI generation of text can be helpful in providing ideas and inspiration, but it should not be used as a substitute for human judgement and analysis. AI generation of text can be a useful tool for quickly generating ideas and content, but it should not be used as a replacement for human creativity and insight. AI generation of text can be a useful tool for quickly generating ideas and content, but it should not be used as a replacement for human judgement and analysis. AI generation of text can be a useful tool for quickly generating ideas and content, but it should not be used as a replacement for human creativity and insight. AI generation of text can be a useful tool for quickly generating ideas and content, but it should not be used as a replacement for human judgement and analysis. AI generation of text can be a useful tool for quickly generating ideas and content, but it should not be used as a replacement for human creativity and insight. AI generation of text can be a useful tool for quickly generating ideas and content, but it should not be used as a replacement for human judgement and analysis. AI generation of text can be a useful tool for quickly
> (DeepL)AI text generation can be a useful tool, but should not be relied upon as a substitute for human creativity and insight.
>  AI text generation can help provide ideas and inspiration, but should not be used as a substitute for human judgment and analysis.
>  AI text generation can be a useful tool to help generate ideas and content quickly, but should not be used as a substitute for human creativity and insight.
>  AI text generation can be a useful tool for quickly generating ideas and content, but should not be used as a substitute for human judgment and analysis. (Repeat)
- I feel like a very stubborn old man.
- In addition, if you ask the same question to a live GPT3, he will say something more positive about the AI. w
- > I think that AI generation of text is a valuable tool that can be used to help generate ideas and find new ways of approaching difficult problems. Although it may not always be correct, it can be a valuable source of inspiration and can help to stimulate new thought processes and ideas. AI generation of text can also be used to help identify patterns and trends that may otherwise not be visible. Ultimately, I believe that AI is a valuable tool that should not be disregarded and can be used to enhance our creativity and problem-solving skills.
- > (DeepL)I believe that AI generated writing is a valuable tool to help generate ideas and find new ways to tackle difficult problems. It may not always be right, but it can be a valuable source of inspiration and help stimulate new thought processes and ideas. AI text generation can also help identify patterns and trends that might not otherwise be visible. Ultimately, we believe that AI is a valuable tool that should not be taken lightly and can be used to enhance our creativity and problem-solving abilities.

## What is wisdom?"
Let's ask a question about a theme that existed even in Gracian's time. What is wisdom?
py

```
r2 = index.query("Q: What is wisdom?")
"""
INFO:root:> [query] Total LLM token usage: 3833 tokens
> [query] Total LLM token usage: 3833 tokens
INFO:root:> [query] Total embedding token usage: 6 tokens
> [query] Total embedding token usage: 6 tokens
"""
```

> Wisdom is the ability to think deeply and critically about difficult topics, to recognize and understand the complexities of a situation, and to make decisions based on sound judgment and experience. It is the ability to use knowledge and experience to make informed decisions and to act in a way that is beneficial to oneself and to others. Wisdom also involves understanding the consequences of one's actions and being able to recognize when it is necessary to take a different course of action. Additionally, wisdom involves the ability to adapt oneself to one's company, to employ no more force than is necessary, and to recognize that excellence and achievement are the only foundations for immortality.
> (DeepL)Wisdom is the ability to think deeply and critically about difficult topics, recognize and understand the complexity of situations, and make decisions based on sound judgment and experience. It is the ability to use knowledge and experience to make informed decisions and act in ways that are beneficial to oneself and others. Wisdom also includes the ability to understand the consequences of one's actions and to recognize when one needs to act differently. In addition, wisdom includes the ability to adapt to company, the ability to use no more force than necessary, and the ability to recognize that excellence and achievement alone are the foundation of immortality.

I'm reading around here with similarity=0.82, good.
- > The wise man thinks over everything, but with a difference, most profoundly where there is some profound difficulty, and thinks that perhaps there is more in it than he thinks. Thus his comprehension extends as far as his apprehension.
- >  (DeepL)The wise man thinks everything through, but he thinks most deeply where there is some deep difficulty, and wonders if perhaps there is more to it than he thinks. Thus his understanding expands as much as he understands.
This source continues below. You can see that elements of this are also included in the answer.
> lviii Adapt Yourself to your Company.
>  There is no need to show your ability before every one. Employ no more force than is necessary. Let there be no unnecessary expenditure either of knowledge or of power. The
> (DeepL)lviii Adapt yourself to your company.
>  You do not need to show your ability in front of all people. Do not use more power than necessary. Let us avoid unnecessary expenditure of both knowledge and power. The
For a set of fragmented texts such as [[The Art of Worldly Wisdom]], I think it would be better to source each fragment separately so that similarity searches can pick up only what is truly relevant.
- Read the documentation on how to create an index!

## Cost
.
A note on costs
- Davinci is $0.02 for 1000 tokens, or about $3
- 70000 tokens for indexing, ¥2104
    - Indexing was cheaper because it was Ada [[embedding is $0.4 / 1M Token]].
    - English 278KB
- 4,000 tokens per question, 12 yen
- Note: ChatGPT Plus is a $20/month subscription
    - Save 250 exchanges per month.
    - A pretty good line
        - Before I started touching GPT3 directly, I would definitely have used that much, but when I wanted to get more creative, I hit GPT3 directly, so I use ChatGPT less often for that...
        - The advantage of ChatGPT is that it automatically titles and saves logs, and the chat-style UI is convenient to use from a smartphone.
        - I'll put Keichobot's chat UI over [[LangChain]]...

## split and read element by element
.
py

```
documents = StringIterableReader().load_data([
    """55: Wait. ....""",
    ...
])
```


By the way, similarity is determined here.
`vector_stores/simple.py class SimpleVectorStore(VectorStore) def query`
py

```
  items = self._data.embedding_dict.items()
  node_ids = [t[0] for t in items]
  embeddings = [t[1] for t in items]

  top_similarities, top_ids = get_top_k_embeddings(
      query_embedding,
      embeddings,
      similarity_top_k=similarity_top_k,
      embedding_ids=node_ids,
  )

  return VectorStoreQueryResult(similarities=top_similarities, ids=top_ids)
```

What you are returning is just a data class.

:

```
(Pdb) print(top_ids)
['75e061c7-eef9-4193-bd20-c871b328f69a']
(Pdb) c
INFO:root:> [query] Total LLM token usage: 189 tokens
> [query] Total LLM token usage: 189 tokens
INFO:root:> [query] Total embedding token usage: 4 tokens
> [query] Total embedding token usage: 4 tokens
Out[2]: Response(response="\nFortune is a concept referring to luck, chance, or fate. It is often used to refer to a person's success or wealth.", source_nodes=[SourceNode(source_text='55: Wait.\nIt\'s a sign of a noble heart dowered with patience, never to be in a hurry, never to be in a passion. First be master over yourself if you would be master over others. You must pass through the circumference of time before arriving at the centre of opportunity. A wise reserve seasons the aims and matures the means. Time\'s crutch effects more than the iron club of Hercules. God Himself chasteneth not with a rod but with time. He 1 spake a great word who said, "Time and I against any two."\nFortune herself rewards waiting with the first prize.', doc_id='a0ee19f2-281c-4109-9eff-97a7a2949b3b', extra_info=None, node_info={'start': 0, 'end': 556}, similarity=0.8087368600771996)], extra_info=None)
```


> Fortune is a concept referring to luck, chance, or fate. It is often used to refer to a person's success or wealth.

:

```
index.query("Why the precious metals are the heaviest?")
INFO:root:> [query] Total LLM token usage: 173 tokens
> [query] Total LLM token usage: 173 tokens
INFO:root:> [query] Total embedding token usage: 8 tokens
> [query] Total embedding token usage: 8 tokens
Out[4]: Response(response='\nThe precious metals are the heaviest because they are worth the most and require the most effort to obtain. This is in line with the proverb "Slow and Sure" which suggests that lasting success requires patience and hard work. The proverb also states that only excellence counts and only achievement endures, which implies that the precious metals are the most valuable and require the most effort to obtain.', source_nodes=[SourceNode(source_text='57: Slow and Sure.\nEarly enough if well. Quickly done can be quickly undone. To last an eternity requires an eternity of preparation. Only excellence counts; only achievement endures. Profound intelligence is the only foundation for immortality. Worth much costs much. The precious metals are the heaviest.', doc_id='48d11d5a-19f3-4150-8178-2392bb7f166b', extra_info=None, node_info={'start': 0, 'end': 306}, similarity=0.839387437323102)], extra_info=None)
```

> The precious metals are the heaviest because they are worth the most and require the most effort to obtain. This is in line with the proverb "Slow and Sure" which suggests that lasting success requires patience and hard work. The proverb also states that only excellence counts and only achievement endures, which implies that the precious metals are the most valuable and require the most effort to obtain.
> Precious metals are the heaviest because they are the most valuable and require the most effort to obtain. This is in keeping with the proverb "Slow and Sure," which suggests that enduring success requires perseverance and hard work. The proverb also states that only excellence matters, and only achievement endures, implying that precious metals are the most valuable and take the most effort to obtain.

---
This page is auto-translated from [/nishio/AIバルタサル・グラシアン実験](https://scrapbox.io/nishio/AIバルタサル・グラシアン実験) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.