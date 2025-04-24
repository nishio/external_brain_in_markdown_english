---
title: "Trial recording of #inajob talk16: AI assistant that reads its own wiki"
---

[https://open.spotify.com/episode/4XPoFcImONgMtPti44JY9A?si=EGh6lwLwTp6hrJg9DgM0Iw](https://open.spotify.com/episode/4XPoFcImONgMtPti44JY9A?si=EGh6lwLwTp6hrJg9DgM0Iw)

[Transcribed by LISTEN at](https://listen.style/p/inajob/itksdrx5)
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>

# 要約 ver.2
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- The author has recently been writing down [[work memos]] and daily thoughts on his [[Wiki]]. The tools he uses have changed, but currently his favorite is his Wiki.
- The author's wiki is inspired by "[[Scrapbox]]" and is being integrated with [[ChatGPT]] to add the ability to display related articles.
- Some people may see a wiki as a [[dictionary]], but the author sees it as a [[note-taking tool]] like [[Evernote]].
- Since many of the author's projects run concurrently, everything is documented in the Wiki.
- Each day, create a diary page in the Wiki and fill in a specific section.
- The main topic of this talk is the integration of an AI assistant into the Wiki. This idea is inspired by "[[Omoikane Project]].
- Nishio is a key figure in this project, researching digital-based intellectual production.
- There will be a discussion of the use of ChatGPT and the exploration of vectorization of sentences, as well as new technological advances.
- Information referencing is improved by identifying relevant pages and providing them to ChatGPT.
- Currently considering implementing new features for the Wiki.
- Advice can be sought from ChatGPT and past articles can be referenced.
- AI assistant provides useful answers from past texts.
- Vector indexes of people's Scrapboxes are collected and published, and can be used to reference others' pages.
- The advice in this system is abstract and sometimes "[[oracle]]-like."
- The use of AI to generate ideas is limited, but [[the process of asking questions makes the answers clear]].
- Similar to the ChatGPT UI, but the current UI is primarily collaborative editing.
- AI and podcasts have something in common as tools for organizing and deepening thinking.
- We are excited about the evolution of AI and expect to see even more useful responses as prompt engineering progresses.
- Experts such as Mr. Nishio give AI high marks. I myself see AI as an interesting tool, but it is difficult to present specific values.
- The combination of diary and AI is promising, and we see the significance of its implementation through chatting with AI and preparing podcasts.

prompt

```
read following bullet lists, those are lecture memo. 

1: Some words are misspelled. Correct them:
s/scrapbox/[Scrapbox]/g
s/wiki/[Wiki]/g
s/two hop link/ [2-hop link] /g
s/chatGPD/[ChatGPT]/
s/ Omoikane Project/ [Omoikane Project] /
2: Make them concise in Japanese.
###
```


# 要約 ver.1
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- The author has recently been in the habit of writing work notes and daily thoughts on his wiki.
- I have always loved writing, but the tools I use change from time to time. Currently, writing on wikis is my passion.
- Many sentences are accumulated in the diary.
- We have been working on combining diary and AI using ChatGPT for 3 weeks.
- The author has created an original wiki for his own exclusive use. The source code is dirty and there are security and bug problems, but he has improved it to suit his needs.
- The wiki is inspired by the "Scrapbox" service, but does not have collaborative editing capabilities.
- As a recent initiative, we are combining with ChatGPT and have added the ability to display related articles. This feature uses ChatGPT to suggest pages with similar sentence vectors.

- The author uses the wiki as a record of his work and daily notes.
- While many people may perceive a wiki as a dictionary like Wikipedia, the author sees it as a note-taking tool.
- The author uses wikis as a miscellaneous note-taking tool like Evernote, preferring a scrapbox-like tool with no specific format or editing mode.
- The author's lifestyle often allows only a small slice of time, and in order to effectively utilize the time, the author needs notes that allow him to quickly review past activities and future plans.
- Since many of the author's projects run concurrently, it is difficult to retain their progress and thoughts only in his mind. For this reason, he has adopted the method of jotting everything down in a scrap box.
- Although this method may seem cumbersome at first glance, it is used as the best solution given the author's situation and needs.

- Wiki as a working tool.
- Create a daily diary page.
    - Fill in specific sections using templates.
    - Examples: health, activities related to the past today, etc.
    - Include links to past diary pages and a look back.
- Write what you come up with and what you work on in your diary page.
- Certain important information should be divided into separate pages.
- The diary page is designed to be an easy place to write, making it easy to edit and organize later.
- The style of wiki use is influenced by the Scrap Box Project.
- Sudden ideas, such as a wish list, can be written in the diary page and retrieved later.
- Large projects and tasks should be carved out into separate "work pages" or "project pages".
    - Record related materials, progress, to-do lists, etc. in chronological order.
    - Reminders and date-related notes are also recorded.
- The use of wiki pages makes it easy to resume work.
- Citing an example from electronics: the analogy of storing physical parts and instructions in one box.
- Wiki is used mainly as a work log.
    - Private information will not be disclosed.

- Introduction to the main issue.
- I am looking to implement an AI assistant for my wiki.
- The project name is "AI Assistant Reading Diary.
- The original idea was inspired by the Omoikane Project.
- Brief description and transition of the Omoikane Project:.
    - Initially, the purpose is to discuss the future of AI and issues by having AI write science fiction prototypes and science fiction novels using AI.
    - The project is not just about creating science fiction, but also combines other themes.
    - Example: AI assistant and human collaborate to create sentences.
    - Consideration of having AI assist in cutting out the appropriate content from the minutes of a crowded discussion.
    - Activities are also underway to have AI provide answers to questions using knowledge in the text.
- Confirmation of the existence of people in the Omoikane Project who are engaged in the above mentioned activities.

- Mr. Nishio is the main person working on the project.
    - Research on the art of intellectual production, especially with regard to the acceleration of intellectual production using digital technology.
    - I feel that opinion carries weight and I am affected by it.
- About my efforts:.
    - A positive attitude toward new and interesting ideas.
    - "Second penguin-like behavior": joining later in new endeavors, the role of a good follower.
    - Considerations and efforts regarding AI assistants began with this thought.
- Awareness and use of ChatGPT:.
    - A vector of sentences can be created.
    - Vectorization can be used to measure relevance and distance.
    - My wiki and Nishio's scrapbox pages are also vectorized.
    - The ability to display related pages will be realized.
- Scrapbox related page feature:.
    - Need to remember human keywords.
    - However, the problem is that old memos and unusual vocabulary do not create links well.
- Document vectors and technological advances:.
    - The ability to complement relevance using vector proximity is useful.
    - New technologies such as chat GPT provide more accurate document vectors.
    - This was not possible with the old technology.
    - Unlike the two-hop link in the scrap box, they are complementary to each other.

- For a given page or string of text, it is possible to identify related pages.
- Providing this relevant data to the chat GPD improves knowledge referencing.
- We are currently considering implementing new features of the wiki system.
    - Thinking about which features to implement first and other good ideas.
- You can ask chat GPD for general wiki advice.
    - Example: Suggestion that adding a comment function would be a good idea.
- Provide articles and thoughts you have written in the past to the chat GPD and they will refer you to them for advice.
    - The chat GPD also referred to my previous written data to provide answers.
- Sometimes we forget information that we are supposed to remember.
    - It is useful for an AI assistant to read one's past sentences and provide answers on that basis.
    - They find it useful because it serves as a reminder of past information and provides new perspectives and angles.

- A vector index of scrapbox pages of various people will be collected.
    - Examples include the vector index of Mr. Nishio's page.
- These vector indexes are publicly available, and you can refer to another person's page for answers to your questions.
- There is a vector index that is also available to the public from the well field people and they can refer to them to answer questions.
- Experience mixing multiple vector indexes to provide the most appropriate response.
- However, we do not always get the answers we expect.
- As for the usefulness of this mechanism, we feel that it is not yet sufficient.
- However, it is useful as a catalyst for new ideas and inspiration.
- Advice from this system may be considered "oracle-like."
    - oracle-like advice = abstract advice or divinatory replies.
- This oracle-like advice serves as a catalyst to get things going in cases where the answer is within you.

- AI can also be used to make suggestions.
    - However, the replies come from a specific intelligence, and thus rarely bring new perspectives.
- Often, explaining the situation in order to ask the AI a question will clarify the answer.
    - In the process of explaining this, I can see the answer in my mind.
- The use of AI is similar to the example of robot vacuum cleaners.
    - Similar to the movement of cleaning a room before using a robot vacuum cleaner, organize your thoughts before asking the AI a question.
- The current UI is similar to that of ChatGPT, but with some differences.
    - ChatGPT is primarily concerned with the exchange of short messages.
    - Current efforts are in the form of collaborating with AI to think about and co-edit texts and topics.
- Sentence size is limited and long sentences are difficult to handle.
- This new form of conversation with AI is different from chatting, and its future remains to be seen.
- It is interesting to experience an AI commenting with its own and others' intelligence.
- Expectations in the current situation are similar to [[oracle-like advice]] or [[forced idea method]].

- Commonalities felt:.
    - There are similarities between the podcast and the AI experience.
        - [[similarities between podcasts and AI]].
- Podcast Experience:.
    - Topics are selected based on a summary of weekly events.
    - Gather information, build logic and prepare a story that leads to a conclusion.
    - New ideas and insights are generated during the chat.
- Effects of chit-chat:.
    - Chatting is one of the activities that evolve our thinking and enrich our lives.
    - Dialogue with the AI is also a kind of chatting, a chance to think and discover.
- What AI and Podcasts Have in Common:.
    - Putting thoughts out there, organizing and restructuring them to gain new insights.
    - Creating scripts and rethinking them with input from the AIs is the beginning of new discoveries.
    - AI and podcasts are tools to deepen and extend thinking.
- Recent experience:.
    - In putting together the podcast scripts, I noticed commonalities in the chats and podcasts.
    - There are many similarities with the idea method of using AI.

- Expectations regarding the evolution of AI:.
    - He expects the amount of text that AI will handle to increase in the near future.
    - As prompt engineering evolves, more effective responses will result.
    - He believes that AI has the potential to become more than a fortune teller.
- Excessive Expectations and Reality:.
    - While we avoid excessive expectations, we feel that AI has advantages.
    - Experts around intellectual production, such as Mr. Nishio, may have a high opinion of AI.
- My thoughts on AI:.
    - I think of AI as an interesting and life-enhancing tool, parallel to podcasts.
    - They want to find usefulness of AI as a tool to "ask around a bit".
    - At this point, he feels it is difficult to convey the clear value of AI.
- Relevance of diaries and AI:.
    - We feel that the combination of diary and AI is a life-enhancing activity.
    - By utilizing AI, it is conceivable to stop podcasting and just chat with AI.
    - Through the preparation of the podcast and this talk, I felt that the introduction of AI was the first step.

prompt: `read following talks and convert them into concise bullet lists`

# Comments on the quality of the summary
.
from [/villagepump/2023/09/13](https://scrapbox.io/villagepump/2023/09/13)
- I figured I'd put the summary in Scrapbox.
- Summary of the first step
    - A chunk of meaning is given to a human looking at it and cutting it out at random.
    - I counted and there were 10 lumps.
- Second step summary
    - The summarized version was not yet large enough to be thrown into GPT4 in one session, so it was re-summarized in two sessions.
- impressions
    - I think the summary of the first step is okay.
        - The oral word is compressed into the written word while retaining sufficient content.
    - I don't think the second step summary is good enough.
        - It is a good summary, but I think it is a fluffy story without specific episodes that would make it more persuasive.
        - For example, the expression "note-taking tool like Evernote" becomes simply "note-taking tool.
        - It's appropriate behavior as a summary, but subtle in its usefulness for the purpose I have implicitly.
        - So what purpose do I have?
        - Maybe it would be better if this could be verbalized and given prompts.
        - In the age of with LLM, metacognition and verbalization of one's thoughts and objectives may become highly sought after!
- No way to listen to it.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
    - I laugh at your impression of the summary.
    - I wanted to make the summary omni readable because it was a normal but informative talk to hear.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - I see,[/nishio](https://scrapbox.io/nishio)に文字で入っていれば今後なにかの思索のダシになるかもしれないですね<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
    - After this very thing, I put down the chat conversation and let the AI develop it, and I pulled up a transcription of the chatter about my behavior when I was playing werewolf years ago.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - It is beneficial to record everything.

PS
- > I put down a chat conversation and let the AI develop it, and it pulled up a transcription of a chat I had years ago about my behavior when I was playing werewolf.
        - [[One Night Werewolf Transcript 2-7 Discussion - AI Summary 3]].

---
This page is auto-translated from [/nishio/#inajob の試しに録音してみた talk16: 自分のWikiを読むAIアシスタント](https://scrapbox.io/nishio/#inajob の試しに録音してみた talk16: 自分のWikiを読むAIアシスタント) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.