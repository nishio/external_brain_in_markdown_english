---
title: "Listening chat -> Sticky note division -> Regroup"
---

2021/1/22 Lab Study Session
I'm going to talk about a natural language processing algorithm that carves sentences into sticky notes of up to 20 characters, but I'll start with the big picture

Regroup
- Tools to help you organize your mind
- Organize information in fragments by arranging them in two dimensions and moving them freely
- An electronic version of the method Nishio uses for writing books and preparing lecture materials.
    - Important stickies can be made larger with two clicks.
- You have to gather some fragments before you can feel the effects.
    - You need to be familiar with creating fragments to use them.
    - If you can't use it, you won't have the skills to make fragments.
    - It's a chicken and egg relationship!

Segmented Sticky Note Algorithm
- So I would observe "what Nishio does when he makes stickies" and program it.
- You put in a sentence, and a sticky note comes up."
    - How do you prepare that sentence?
- People in this study group are pretty good at verbalization compared to the average in the world.
    - A lot of people don't write blog posts or anything.
- For those who are not good at verbalization, "preparing sentences" is difficult in the first place.
    - It is difficult to write down the fuzzy, unorganized thoughts in your head, so Regroup's story is to first write them down in fragments, and then rearrange them to create sentences.
    - The chicken and the egg relationship in "Prepare the text first."

Listening Chat System
- The program asks questions to the human and the human answers them.
- Apply keyword extraction to the user's responses, and ask in-depth questions for keywords that seem important.
- I made it before and had it live as a chatbot in Mattermost's unexplored junior chat.
- If I put the logs on Scrapbox from time to time, there were a few people who wanted to use them, but since it's a closed chat, I can't let them use them.
- This time, some features have been removed and ported to the web.

Combine these three elements
- Conversation logs for the listening chat system,
- Sticky note with split sticky note algorithm,
- Import and organize in Regroup

Just completed on Thursday, January 21.
- Good and clear transition between divergent and convergent phases
    - Need a bigger screen to organize
    - Chat can be used on your phone while taking a walk.
    - "I'm going for a walk, chatting and venting."
    - I'll organize it on my PC/iPad when I get home."
- There are still many holes in the split-stickying algorithm.

The Future
- There is a lack of data stored in the chat system, so the keywords extracted during the chat are not being utilized very well.
- The part that uses machine learning and the part that spits out training data for machine learning was removed during this porting -> fix it.
    - Specifically, "Is the user excited about the question?" and "Under what circumstances would the user be excited if I chose which question?"
- Now every time I start a conversation I get amnesia.
    - It would be better if it had a per-user memory.
    - Or "keywords this person uses a lot."
    - Ultimately, it would be nice to be able to interact with stickies on Regroup by utilizing information such as how large they are or how adjacent they are.
    - I won't memorize anything right now, so I'll start with the easy part first.

Algorithms.
    - [[Assistance in dividing long sentences into stickies]]

---
discussion
    - [[Mechanical and Craftsmanship Division]]
    - [[Sentence organization process using Regroup]]
    - Originally derived from the KJ method, but no longer misleading to call it the KJ method
    - KJ Method "group formation" is clear inside and outside the group
    - This method has no clear group boundaries
    - They don't even do the process of bundling and putting a nameplate on it.
    - The emphasis is on "even if we cannot explicitly verbalize what the relationship is, we can express that it is somehow related by placing them close together.
- Won't I read the spatial arrangement I made six months later and not know what it means? Won't others get the message?
    - It is a temporal part of the writing process and does not need to be conveyed.
- What happens in the chat when this Regroup?"
    - [[conversation log 20210121#60097864aff09e0000100886]]
    - It's a bit of an awkward question for Japanese, but it prompted me to notice
    - Until you asked me this question, I was imagining only a one-way flow of "ask in chat -> split -> put in Regroup".
    - I realized when you asked me that it could be in the opposite direction.

---
This page is auto-translated from [/nishio/聞き出しチャット→付箋分割→Regroup](https://scrapbox.io/nishio/聞き出しチャット→付箋分割→Regroup) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.