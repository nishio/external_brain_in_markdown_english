---
title: "Current impressions and thoughts on OMNI"
---

Kozaneba
- ![image](https://gyazo.com/7d6eed9b756f95558259b3ba75fa9f85/thumb/1000)

from  [[Diary 2023-11-01]]
My current impressions and thoughts on [omni
- Good "[[sometimes up coming page]]".
        - [[page sometimes emerging]].
    - The form of expression is problematic.
    - Currently, I'm "keeping it all" as an experiment, but it's clearly not good.
    - After all, we're only looking at the most recent generation, so we don't need the one in front of us.
        - If you haven't read the part in the foreground, you should.
        - You might want to look back and read it, but it doesn't have to be all unfolded from the beginning.
    - Frequency gap is too large.
        - And it is not a good idea for that change to be made by a change in title
            - Not that there is anything wrong with that per se, but the problem is that you are treating the page with the changed title as a "newly added page".
                - [[omni spec bug]]
            - Seems a bit cumbersome to solve this problem with Scrapbox.
- [[Iterative Commenter]]
    - As expected, the "behavior of slowly extending branches to the surrounding area" is occurring.
            - [[Neri Neri's value is slowly decreasing.]] occurs, it slowly spreads outward over more time
    - The original [[Recurrent Notes]] does not have the "[[KJ legal effect of repeated summary]]" that it had.
    - Iterative Commenter should be moved to private.
            - [[The Serendipity of Random Reading]] because the system causes
- About the original data
    - There's a big difference between having 60 books worth of my Scrapbox articles and 100 books worth of real book-derived data.
        - What's the difference?
        - Books assume a one-dimensional context.
            - It implicitly assumes that the reader has read the previous sentence.
            - So "what are you assuming we know of what has appeared up to that point" is not explicitly stated.
        - Scrapbox, on the other hand, makes no assumptions about what the reader is reading in the foreground
            - So relevant content is explicitly made into a link.
                - Ideally, the first thing to do is to put a large one-dimensional item, like a record of an event or lecture material, on the table. [[Event article is dying]].
    - what should be done?
        - One idea: [[Leverage memo]].
            - Given page k-1 and k, make a leverage memo for page k
            - This is a little over 500 tokens of input.
            - [[Summary is an ambiguous concept]]
            - Not a good idea to think of leverage memos as "making summaries".
                - Leverage memo is not a summary [[extract reusable components]].
                - Returning null is often the correct answer.
                - They're not trained on that kind of data set.
                - There is no data set for this purpose, do you want to make one?
            - Context-Specific Summaries
                - I want to take out where the context matches.
- Markdown conversion
    - Simple format conversion
        - This is boring.
    - Stylistic Conversion
        - From fragmentary notes to blog post
    - Conversion to English
    - And determine if it should be targeted as a preliminary step?
- Relation to search hits
    - ![image](https://gyazo.com/b300b107c18718ba2de3d6e5387628f8/thumb/1000)
    - There are smaller units than the current chunk of 500 tokens.
    - Scrapbox's brief article is "it".
            - [[Evergreen notes should be atomic.]]
    - The string of 500 tokens cut from the book is not it.
- Maybe I'll stop working with Github Action once and for all.


from  [[Diary 2023-11-02]]
Current impressions and thoughts on OMNI

Iterative Commenter is running on Github Actions.
- omni-private is working locally.
    - It's easier to experiment that way.
    - The code is shared with public omni.
- >  Iterative Commenter should be moved to private.
- ✅Stop working with Github Actions once

public /nishio → Github
- Save for now
- Cleaned up articles are available separately.
- Wikignome of maintenance should be made in 3.5.

Machine-generated duplicate content subtle

ideal
- About embed
    - Use cache
    - Does not carry over unused cache
    - Do not target machine-generated content
- About Update
    - Maintain telomeres
    - Or overwrite without logging.
        - If you want to see the past, use History.
- search results
    - viewable
    - Shouldn't be shown from the beginning.
        - too much
        - More DIGEST
            - Manpower DIGEST will be data for future FTs.

Lost in the meadow, which way to go?
- State with more than one attractive goal.
    - If it's one thing, go that way.
- The problem of knowing which way to go when many goals are in different directions.
- Situations that should be Kozaneba

- [[Dynamic Semantic Web and Thinking Fireworks]]
- [[Development by association]]
        - [[RAG]] from [[vector search]]
    - [[Development by delusion]]
    - [[Positive Halcynation]]

Joint activities with AI
- Not much has been done.
- With omni-private, you just throw a query and the AI generates it and reads it.
    - Just a single request response
    - And they're doing it in Scrapbox, which is unsuitable.

AI Reading Notebook
    - Let the AI do the activity of [read a book
    - [[What is reading?]]
            - Creating a [[Knowledge Network]].
            - What kind of network is needed?
                - [[backlink]] Should be, maybe.
                - [[2-hop links]] There should be
                - Why?
                - This [[Scrapbox reminds me of what I've forgotten.]]
- Landing it in the context of nishio?
    - A system that allows people to find connections between books, and if you let people read the output of 60 books of NISHIO, you can land the books in NISHIO's context as a result.
        - You don't have to make it explicit.
        - Well, if you want to experience this effect, you must first have a reasonable amount of output, so it's not for the average person at all.
            - You shouldn't aim for the general public first.
Kozaneba
- I have always used it when I need a non-written form of expression.
    - Rather "functional enough"?
        - It would be useful to write notes as sentences.
        - Browser compatibility issues rather than functionality like I want to be able to use it from my iPad.
        - I'm doing the chopping of the text, humans have done it, and I'm thinking that by doing it, it has the effect of "better understanding is created by reading while processing" like sutras or active reading.
            - but it may be an assumption.
            - If LLM helped you, you might say, "I should have done this sooner!" I might be able to
- I use it all the time, but it's not the type of tool I use every day.
    - Tools to retrieve when needed
- Should there be an interconnection with Scrapbox?
    - Scrapbox's "link by string" and Kozaneba's non-verbal "link by placement" and "link by line" are complementary
- Scrapbox side of the view is not very customizable, so another view is needed
    - More development of [[mem.nhiro.org]].

Keichobot
- A system that encourages verbalization by asking humans questions.
- Focus on bringing it out from scratch.
    - so it is not connected to existing conversations or Scrapbox stock.
    - There is of course the possibility that it would be good to be
- I put the chat logs in Scrapbox.
    - It was chopped into chunks and entered into the vector index.
    - This had merit.
    - Right now it's chopped at 500 tokens, so the granularity is rough, but this exchange is QA, so it might be good to index it in the form of a QA pair or something.

---
> Kozaneba situation to be
# Kozaneba
![image](https://gyazo.com/ae0d7e4e737b9a456622fc739151b5e9/thumb/1000)

![image](https://gyazo.com/3d702a0302c4af25356bcd1d81dc7cd8/thumb/1000)

![image](https://gyazo.com/5147d879ea14d5f577b768d674f95b83/thumb/1000)

This is a bit of a leap.
- Too drawn to the specific idea of "leveraging memos."
- Overly specific implementation images
- Given a page in a book, if the LLM can find links to what is related to what in the story up to that point in the book, the LLM can create a network structure while reading a one-dimensional book.


![image](https://gyazo.com/f63de6308625d08119272a5347a0bf32/thumb/1000)

![image](https://gyazo.com/57798542ee925e3b8c24a7353c2a4f80/thumb/1000)
![image](https://gyazo.com/3e5d0699752e9fd5f1868dceda0f8355/thumb/1000)
![image](https://gyazo.com/05cc6af6d14c3b0e98abcad88efe1477/thumb/1000)
![image](https://gyazo.com/cf2857d393f24abe26ed5a05be74dc41/thumb/1000)
There is a link to Scrapbox, so there should be a backlink
- Scrapbox does not have the ability to display it so there should be a new view

![image](https://gyazo.com/ff1555a81ebc3413f4fd063287e21597/thumb/1000)

![image](https://gyazo.com/c8921c65abd0239638be23a1d3f1bb89/thumb/1000)

![image](https://gyazo.com/fca06da9d2a3f9dcb7a1c4582d0fcb4b/thumb/1000)

---
![image](https://gyazo.com/aca81f67b5fbc799e3069c38c41abd08/thumb/1000)
![image](https://gyazo.com/226ef03e389b3994ac44e6d324aa85d5/thumb/1000)

![image](https://gyazo.com/5f22c3e8d4ccd49636b98deb4d723725/thumb/1000)

![image](https://gyazo.com/7d6eed9b756f95558259b3ba75fa9f85/thumb/1000)
[https://kozaneba.netlify.app/#view=lhq9ixTHLRlLh55wFcT7](https://kozaneba.netlify.app/#view=lhq9ixTHLRlLh55wFcT7)


- [[Refine the concept of summary]]
- Create reusable components
    - You can return null.
- Finding connections between context and a given sentence
    - What is context?
        - Previous page before the page you are currently reading in the book
        - Books I'm reading now and others
            - Which is the context?
        - Ideas and books in Scrapbox

Support at Kozaneba's LLM
- Where the text is engraved
- Where to title the group

---
This page is auto-translated from [/nishio/omniに関する現時点での感想と思考の整理](https://scrapbox.io/nishio/omniに関する現時点での感想と思考の整理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.