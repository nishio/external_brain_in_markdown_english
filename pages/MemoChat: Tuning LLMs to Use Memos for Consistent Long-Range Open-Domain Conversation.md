---
title: "MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation"
---

> We propose MemoChat, a pipeline for refining instructions that enables large language models (LLMs) to effectively employ self-composed memos for maintaining consistent long-range open-domain conversations. We demonstrate a long-range open-domain conversation through iterative "memorization-retrieval-response" cycles. This requires us to carefully design tailored tuning instructions for each distinct stage. The instructions are reconstructed from a collection of public datasets to teach the LLMs to memorize and retrieve past dialogues with structured memos, leading to enhanced consistency when participating in future conversations. We invite experts to manually annotate a test set designed to evaluate the consistency of long-range conversations questions. Experiments on three testing scenarios involving both open-source and API-accessible chatbots at scale verify the efficacy of MemoChat, which outperforms strong baselines. Our codes, data and models are available here: this https URL.
(DeepL) We propose memo chat, a pipeline for instruction refinement that allows Large Language Models (LLMs) to effectively use self-synthesized memos to maintain consistent long-range open domain conversations. We demonstrate long-range open-domain conversation through an iterative "memorize-retrieve-respond" cycle. This requires careful design of tailored instructions for each step, teaching LLMs to remember and retrieve past conversations in structured memo-chat, thus enhancing consistency in engaging in future conversations. We ask the expert to manually annotate a test set designed to assess the consistency of long-distance conversational questions. Experiments on three test scenarios involving both open source and API-accessible chatbots validated the effectiveness of [[MemoChat]] over a strong baseline. Our code, data, and models are available at this https URL.

> [ai_database](https://twitter.com/ai_database/status/1692403982734594175/photo/1) A "MemoChat" pipeline has been developed to allow LLMs to (1) remember "my story" in systematic notes for the long term, (2) recall it as needed, and (3) send a response. MemoChat" has been developed as a pipeline that allows LLMs to (1) remember "my story" in systematic notes over time, (2) recall it as needed, and (3) send a response.
>
>  A group of researchers from Tencent and other companies have announced that
>  ○ Junru Lu et al. MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation
>
>  The current LLM chatbot is not very good at returning "consistent responses" when the conversation is getting long.
>
>  So researchers are trying to solve this problem by having people make "structured notes" for long conversations involving a variety of topics.
>
>  The following is a summary of the methodology. All of the actions are on the LLM side.
>  ■Subdivide conversations by topic and write notes
>  ■ Review notes in response to new conversation queries
>  ■Responding to current and past stories in light of
>
>  In our experiments, we outperformed against four open source LLMs.
>
>  This technology is useful when you want people to talk to each other according to "my story" rather than complex chatbots that provide "neutral answers" drawn from a large resource.

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes a MemoChat method to enable large language models (LLMs) to make consistent responses with memos in long-term open-domain conversations. The main contents of the paper are as follows.
- MemoChat aims to conduct long-term conversations through a "memoize," "search," and "respond" loop. This allows past conversations to be stored as structured memos, which can be searched and referenced as needed for consistent responses.
- The public dataset was restructured to create instructional data for fine-tuning the open-source LLM to suit the MemoChat methodology.
- A new dataset for evaluation of the consistency of long-term conversations was created, annotated by an expert.
- Evaluation experiments were conducted using chatbots available through public APIs and open source LLMs to confirm the effectiveness of MemoChat.
- Experiments showed that the larger the LLM, the better the ability to use memos in zero-shot/few-shot, and that fine tuning with directed data further improves performance.

As described above, MemoChat is a method for long-term open-domain conversations with LLMs through the autonomous use of structured memos.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How do you divide the chat range by topic?
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/> In the paper, the following task instructions (Memo Writing Instruction) are given to the LLMs in order to divide the conversation based on the topic.

1. summarize all possible topics in the conversation in brief words (spans).
2. determine the chat ranges for each topic. These ranges should be a set of end-to-end intervals that are connected in sequence, with no overlap.
3. conclude each chat with a short summary.
4. report the results of the topic, summary, and range in JSON format, using the keys 'topic', 'summary', 'start', and 'end'.

For example, if the conversation in line M talks about "bananas" from line 1 to line N and about "mangoes" from line N+1 to line M, the task results in the following

[{'topic': 'banana', 'summary': 'user talks banana with bot.', 'start': 1, 'end': N},
{'topic': 'mango', 'summary': 'bot brings mango for user.', 'start': N+1, 'end': M}]

These task instructions are given to the LLM and through supervised learning, the LLM is able to autonomously divide the conversation into topics and output a summary and range for each topic. This allows for a structured conversation history.
---
This page is auto-translated from [/nishio/MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation](https://scrapbox.io/nishio/MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.