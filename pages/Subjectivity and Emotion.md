---
title: "Subjectivity and Emotion"
---

[2019-10-16 Facebook](https://www.facebook.com/nishiohirokazu/posts/10219497436003079)
- Until now, I've kept emotions out of my program, thinking they were unnecessary.
    - [[Tomoya Tachikawa]] It was discussed that we need a module that is "[[Properly subjective]]".
- I am thinking about the difference between emotion and subjectivity.
- Primarily "I like it, I don't like it" #Likes and dislikes
    - With binary classification, anything without information is neutral.
    - They will ingest only what is pleasant.
- Add to this the elements of "hating all the same things" and "preferring new things".
    - [[curiosity]] and [[boredom]]" or "[[interesting]]."
- This factor of liking something new is also subjective because each person has different parameters.

- Filter for Notifications
    - User's like/dislike decisions as training data.
    - Through "Things You Might Like."
    - Neutral without data
- This system
    - The computer subjectively finds "something that still has little training data" "interesting."
    - "Isn't this interesting?" and show it to people.
    - Learn from their reactions.

- Normal learning if selected only by like/dislike factor
- Active learning when choices are made based on the curiosity factor alone.
- Neither is interesting to my realization.
- There must be a point where I get interesting when I mix them in the right mixing ratio.
- That's funny to me, but not necessarily to others.
    - →Subjective Interest

- Allow feedback of likes and dislikes as well as "that's interesting" feedback
- Parameters can be adjusted to make it more interesting to the user
- Then it would be interesting to see that notification screen, so teacher data would begin to be collected.
- I hope this one is more interesting than the raw Twitter timeline.
    - If data can be streamed through the API, data from Scrapbox and books can be included.

    - The [[Likes/Dislikes Module]] is just a binary classification, but I don't think the [[Curiosity Module]] is a good implementation of it
    - The likes/dislikes module is responsible for the expectations in terms of UCB1
    - Need a module responsible for the number of samples for this
    - In other words, a "positive because I saw it for the first time, negative because I saw it many times" module is needed.
    - If implemented naively, would it be expensive to save all past inputs and compare them with each other?
    - First of all, it's important to make it happen, so let's disregard cost.
    - Finding the k neighborhood for past data and the distance between them determines the novelty of the data.

- In the case of humans, when we are children, do we acquire the behavior of not repeating after the fact by repeating things that we find interesting and being disgusted by them?

- Human interaction is important, but what about when it works without interaction?
    - Filter out the interesting ones and read them again?
    - Resource allocation is a behavior, and you get to choose which data you want to study.
        - For example, if reading and processing data requires time resources, and processing all the data generated in a 24-hour period takes more than 24 hours, then discarding
        - For example, the action of crawling through someone else's Scrapbox becomes "boring" because there is no change even if you do it frequently, resulting in a decrease in frequency and a balance where appropriate.
        - If following what all your Twitter followers say is boring, you will leave the more interesting people and limbo the boring ones
        - [[Words you don't understand]] in a dictionary or reading Wikipedia may be more interesting than reading unconnected fragments of context
    - Pull out what you find interesting, write down what you think is interesting, and share it with others who might find it interesting
        - What is the purpose of making excerpts?
            - The act of creating a more concentrated source of input at a lower cost
            - When performing link discovery, humans do not use all historical data to determine similarity, but only the most recent input, which is the effect of enrichment.
            - Even those that are not the most recent input are rarely successfully linked, but I'm not sure why that is.
                - Is there a module responsible for it?
                - Or the past memories are randomly picked up in the dream and piled onto the most recent memory.
                    - A [[Incremental Reading]]-like [[step-by-step procedure]] algorithm is fine here, not random.
            - Limiting the history to reasonable values will limit the amount of calculations.

- Scrapbox page has a title, so a slightly more upscale structure, there should be a more primitive form to start with
    - Page with date as title
    - Just keep a journal.
        - A bot that reads various web pages on a daily basis and summarizes the interesting ones in a diary.

- Isn't this [[Independent Desire Device]]?

- The idea is to mix in something new, not just a like/dislike filter.
    - This could be similar to the direction that Gunosy and other news curation was thinking about
    - My interest is in better ways to accumulate knowledge, not so much in news.
        - If anything, I'd like to create a system that uses the best of the classics, ancient and modern, as input sources.

- Talk about the need to remember past input in creating a curiosity module, seems related to this in the past.
        - [[dimensionality reduction caution]]
    - When the inner product is large without Dropout, it becomes "not new" because it is "similar to past data".
    - By adding Dropout, "not similar at first glance but similar after dimensionality reduction" is discovered, which is [[Discover the analogy]].
            - Is it related to [[ASSOCIATIVE DEVICE]]?

- [[subject]] and [[emotion]].
- [[Properly subjective]]

---
This page is auto-translated from [/nishio/主観と感情](https://scrapbox.io/nishio/主観と感情) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.