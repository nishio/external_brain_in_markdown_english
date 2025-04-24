---
title: "Test it now that it has been integrated with the traditional question generation algorithm."
---


# summarized by AI, modified by Human
.
- LangChain has a Max marginal relevance mouth
    - but the one that inherits the abstract class is not implemented.
- LlamaIndex can map an embedding vector to it by passing a list of texts.
    - When a query is issued, relevant documents are picked up based on a vector.
    - The vectorization for LlamaIndex text is stored in local JSON.
- LlamaIndex uses OpenAI's embedded API.
    - I don't know how the embedding API is implemented or if it is extracted from some layer.
- Use LlamaIndex because LangChain has trouble working.
    - Due to mysterious problems with FAISS, LlamaIndex is currently used.
- We have not yet confirmed the implementation of LlamaIndex.
- The next step is to review the LlamaIndex implementation and read and understand the code.

# summary by AI
.
- LangChain has a Max marginal relevance mouth, but the one that inherits the abstract class is not implemented.
- LlamaIndex can map an embedding vector to it by passing a list of texts.
- When a query is issued, relevant documents are picked up based on a vector.
- LlamaIndex uses OpenAI's embedded API.
- Use LlamaIndex because LangChain has trouble working.
- We have not yet confirmed the implementation of LlamaIndex.
- Due to mysterious problems with FAISS, LlamaIndex is currently used.
- When LangChain is trained, we do not know if it will be extracted from some layer.
- The vectorization for LlamaIndex text is stored in local JSON.
- The next step is to review the LlamaIndex implementation and read and understand the code.


<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What would you like to see happen in this conversation? (GPT)
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Test it now that it has been integrated with the traditional question generation algorithm.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Thank you very much. I hope you have success in testing the new algorithm.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>We talk a lot to decide what to do next.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What exactly would you like to talk about?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I've read about the LlamaIndex and LangChain implementations, and some of my predecessors have run into mysterious trouble when using FAISS with LangChain, so I think I'll proceed with the current LlamaIndex implementation for the time being.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Please tell us about your implementation of the "LlamaIndex". What exactly did you implement?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I haven't read much about that implementation yet. It works without any problems, and the vector index is placed in the local JSON, so it would be easy to experiment with features that the library doesn't provide.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>It's an implementation of "LlamaIndex" with a vector index placed on the local JSON.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Yes, LangChain has Max marginal relevance, which is promising, but there are a lot of classes that inherit from abstract classes and don't implement their methods, so I can't tell which ones I can do without seeing the specific class. seems to be able to do it.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>It is difficult to know which classes implement Max marginal relevance, since classes inheriting from the abstract class of "LangChain" do not implement Max marginal relevance methods, but it is possible that FAISS can be used. Is it possible to do it by using FAISS?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Yes. But, however, some people are having trouble moving with FAISS, so we're not going to go down the same road.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>You mentioned that the Max marginal relevance implementation of "LangChain" could be solved by using FAISS, but what exactly was the problem?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I deployed it to Heroku and it seemed to stop working even though the version was supposed to be aligned, and it died due to a function argument mismatch, so I'm thinking maybe it's supposed to be aligned but it's not.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What are the current problems with LangChain?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I'm not talking only about LangChain, but building a program on top of a library that is being updated daily is like walking on an unfrozen lake.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>You seem to be finding it difficult to create a program. What do you think is the reason why the work is not going well?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>When the cushion of thick abstraction layers is drawn so that even those who don't have a grounded understanding can easily do something, it's comfortable to sit on, but when you try to walk, it stumbles. That's fine for those who are content to just type in what the tutorial says and move it around, but not for those who want to move around.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Where is "LangChain" part of the library you use?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Putting that aside, ask about LlamaIndex.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>You said you were going to ask a question about LlamaIndex, can you elaborate on LlamaIndex?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>A method that allows ChatGPT to refer to external material by mapping vectors to text fragments, selecting the appropriate text for a query, and loading it into a prompt to ChatGPT.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How did you learn about "LangChain"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>👎LangChain
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you elaborate on the functionality of the "LlamaIndex"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>If you pass a list of text, you can create a VectorStore that maps an embedded vector to it. I think this is just hitting OpenAI's embedding API. When you issue a query, it picks up relevant documents based on the vectors. I believe this is inner product similarity, but I haven't checked.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you elaborate on the "vector" in "LlamaIndex?"
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>There is a technique that maps text to a vector of a little over 1000 dimensions that reflects its meaning. The vectors created by it.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How are "LlamaIndex" embedding vectors created?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Creating with OpenAI's API
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How does the API work with respect to the embedded vectors created by the "OpenAI" API?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I wonder if the Transformer is learned and then extracted from some layer? Don't know.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Where is the "LlamaIndex" vector stored?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It's stored in local JSON.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What kind of data is stored in the local JSON of the "LlamaIndex"?

[https://keicho.netlify.app/#talk=TqbPiBoeyzjYM4zuQsu8](https://keicho.netlify.app/#talk=TqbPiBoeyzjYM4zuQsu8)
#KeichobotLog

---
This page is auto-translated from [/nishio/従来の質問生成アルゴリズムと統合したのでテストする](https://scrapbox.io/nishio/従来の質問生成アルゴリズムと統合したのでテストする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.