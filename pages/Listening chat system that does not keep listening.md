---
title: "Listening chat system that does not keep listening"
---

- [[Listening Chat System]], where the system initially asks a question for each statement, and later adds a mode called "Listen First" where the user listens by repeating a question without asking a question.
But this is a global switch between "100% questions" and "0% questions".
Isn't that what we really need?

One-shot question function
- Even in "listen first" mode, if I say, "Do you have any questions?" or "Go ahead," they'll ask a single question.

Question probability up/down
- Increase or decrease the probability of a question
- This may not be straightforward.
- If the user wants you to ask a question and the system incorrectly decides that it doesn't want you to ask a question now, it stops.
- If you're going to do it, I'd rather have an easy-to-understand rule base than complicated content-based guesses.
    - For example, if you wait one second after the user's input and the user makes a new input, you decide that you don't want the user to ask a question now.
    - The above "one-shot question function" is one of the easy-to-understand rules to "clarify when the user wants to ask a question".

If they don't respond all the time, there's no need to limit it to chat.
- For example, if you post a series of tweets on Twitter and then mentions it to the bot, it'll look at the last 10 or so tweets and throw a question at you.

---
This page is auto-translated from [/nishio/聞き続けない聞き出しチャットシステム](https://scrapbox.io/nishio/聞き続けない聞き出しチャットシステム) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.