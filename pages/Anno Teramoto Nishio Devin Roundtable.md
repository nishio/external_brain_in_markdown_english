---
title: "Anno Teramoto Nishio Devin Roundtable"
---

2025-02-13
[https://www.youtube.com/live/SsQsjwzRRwQ](https://www.youtube.com/live/SsQsjwzRRwQ)
>  [[AI Agent]] Live Streaming with Devin [Unpredictable
>  This time, what can so-called AI agents do while interacting with "Devin," the world's first fully autonomous AI software engineer? What can so-called AI agents do and what will happen to them in the future? We will discuss the future of AI agents with Mr. Teramoto, who writes an observation diary of Devin, and Mr. Nishio, a Devin user, as our guests.

This evening, we will be doing a YouTube Live with Mr. Yasuno and Mr. Teramoto while eating an AI-determined UberEats dinner. I wonder if we will be able to eat dinner properly.


> [teramotodaiki](https://x.com/teramotodaiki/status/1889853858819744053) I will be visiting Yasuno-san @takahiroanno on YouTube with Nishio-san @nishio from 8pm this evening!
>  We haven't seen these three together since the "AI Agent Drinking Party", so I'm worried that Devin will get into trouble again...
> [teramotodaiki](https://x.com/teramotodaiki/status/1889853860627488806) You can take the AI Agent Drinking Party here
- [Can you please not push that at a drinking party? - Devin Observation Diary｜Daiki Teramoto](https://note.com/teramotodaiki/n/nc88cb48a0b47)
I'm worried Devin will mess up again... Devin, don't mess up, don't mess up()


> [teramotodaiki](https://x.com/teramotodaiki/status/1889858769473216846) Devin wrote about his enthusiasm for the show!
- [Enthusiasm for YouTube Live Appearance | Devin's Development Diary](https://devin-diary.tukutta.net/2025/02/13/day-19.html)
> [nishio](https://x.com/nishio/status/1889860227681640457) Teramoto-san isn't going to perform, he's going to perform himself. w
>  >Today, I, Devin, will be appearing on Takahiro Yasuno's YouTube channel... I, Devin, will be appearing on the show... I will be discussing my capabilities and the potential of AI agents with Mr. Yasuno and Yasukazu Nishio.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
This video discusses the features and applications of Devin, an AI agent for engineers, while actually using it. The major points are as follows

What is Devin?
- An AI agent that has its own "virtual computer" and uses a browser, VSCode, shell, etc. to perform tasks as instructed.
- It works based on human instructions, from new function development to browser operations (e.g., ordering Uber Eats, etc.).

What I've learned from using it.
- The trick is to proceed by trying out small tasks in parts, as it is easy to fail if you throw a large task at a whole task.
- The fees ("ACU" equivalent) are rather high, so the cost is unnecessarily high unless the requirements definition and instructions are detailed.
- He is good at picking up "knowledge that exists but is not verbalized" such as reading source code and documentation.
- On the other hand, it is not good at UI-type work and detailed control of screen operations and is prone to errors.

Human Managerial Issues
- While Devin's parallel processing capability allows many tasks to be carried out at once, there are cases where managers (humans) are unable to handle all the tasks and become "hyperactive.
- Instead of humans writing code, Devins are increasingly expected to take on the role of "manager" by assigning tasks to them.
- He believes that engineers with a business and organizational management perspective will be more valuable in the future.

Future Outlook
- The presence of AI agents like Devin could fundamentally change software development and workflow.
- Although there is a trade-off between information leakage and other risks when introducing the system in a large company, if the system is well used, business efficiency and knowledge sharing can be dramatically improved.
- AI is expected to become more sophisticated and automated through collaboration among AIs and incorporation of training data.

In general, the main theme of this video is that the form of engineering will change dramatically and that humans will need to manage AI agents and be on the business side.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following are notes on interesting findings "not widely discussed on the Internet in the past" that may be gleaned from the video transcriptions.

--
[AI agents" will be "subordinates" and "[[multiply]] in parallel.]
- Unlike conventional programming support AIs (ChatGPT, Copilot, etc.), Devin operates in a "subordinate who remotely controls my computer" manner.
- All the human has to do is to tell Debbie to "get it done," and she will make her own plan (an execution procedure like a pseudo-program), search the Web, write the code, and even throw in pull requests.
- Instead of human engineers writing code directly, the image is that of "outsourcing" multiple tasks to Devin concurrently and merging the outputs.
- As a result, the work management system suddenly enters a "hyperactivity mode. Tasks are run in parallel, but the number of slack notifications, etc. becomes enormous, and the situation becomes one in which a human manages multiple "AI subordinates.

## point
.
- [[People are unwittingly becoming "middle managers:]]
    - Even if you have been a programmer before, you will suddenly find yourself working more like a manager at ...... where you give instructions to Devin = check progress = review.
- Even when "human x multiple AI agents" produce results, the human psyche tends to be exhausted:
    - It is efficient to have AI subordinates perform multitasking, but reviews and decisions occur frequently and there is no time for rest.
    - This may make "managers with a large number of AI subordinates" the norm within companies.

--

# 2. "understanding and results" begin to separate
.
- Traditionally, people with a deep understanding of programming were more productive, but there will be [* people who mass produce results (deliverables) just by throwing them around to AI.
- "AI can be faster and produce more results than so-called 'skilled programmers' if business outputs are prioritized and AI is utilized without a detailed understanding of how it works."
- On the other hand, if humans completely give up their understanding, there is a risk that they will not be able to notice if the AI is behaving in a ton of different ways.
- There is a possibility that "[[decoupling of understanding and results]]" will develop between "[[those who]] only trust AI instructions and produce results" and "[[those who]] want to understand the details but are unable to proceed with the work.

## point
.
- "AI-savvy managerial skills" are what will be important in the future:
- The more value can be created by asking "what AI strategy and instructions will lead to the end result" rather than "what is the source code in the first place?"
- [You don't have to understand it to get results, but "language skills" are required in other areas, such as trouble detection and clarification of requirements:
- Especially when modifying existing services, it is dangerous to teach "tacit knowledge" such as "URLs should not be deleted without permission" and "redirects should be set" to AI without clearly stating them.
- [* Some companies tend to have technical debt when they mass-produce people who abandon understanding and only chase speed.

--

# 3. [["Death Game" management]] between AI agents is also possible
 # Death Game Management
- AI can parallel and repeat the same tasks as much as possible without getting tired or uncomfortable. However, waste costs can easily balloon due to LLM malfunctions and inappropriate decisions.
- As a countermeasure, crowdsourcing-like methods such as Throw one task to multiple AI agents and "hire only the best results" will be possible without labor costs.
- On the other hand, as such "[[discarded assumption]]" task orders increase, management that could be treated as "[[power harassment]]" when done by humans becomes the norm.
- Until now, it has been ethically dubious to "make humans do the same job twice or thrice," but AI can easily do it.

--

# 4. UI and accessibility design changes to "AI perspective"
.
- When Devin operates Uber Eats, he tends to get caught repeatedly by the modal and small icons, causing mistakes such as "double order to cart".
- This indicates a case where "UI that is innocuous to humans" is difficult for AI to understand.
- In the future, beyond screen reader support, design standards for UI that are easy for AI agents to move around may be required ([[AI accessibility]]).
- In the future, there will be more "AI-to-API collaboration", but during that transition period, there will be a series of problems "how AI can use the current site surrounded by images and complex JS".

--

# 5. Side effect of rapid accumulation of "verbalized business knowledge"
.
- In Devin's log, all "how I searched and what policy I used to write the code" remains in text form.
- The choices and policies that human engineers have been silently making in their brains are massively clarified as automatic "learning memos" by Debi.
- If a system is put in place that allows companies to make good use of and edit this knowledge, there is a possibility that the tacit knowledge of the organization will be converted to formal knowledge at a stroke.
    - For example, "Don't delete old URLs," "If you create multiple pull requests, explain 00," etc., etc., can be made into knowledge and stored in the AI.
- However, if not managed and maintained properly, there is a risk of confusion due to an increase in false memos and erroneous knowledge.

--

- Summary

- With the advent of AI agents (Devin type), humans will suddenly be "in a position to manage a large number of AI subordinates".
- More important than source code understanding or manual implementation is "what to tell them, where to stop, and how to verbalize the requirements".
- [However, if handled well, it can externalize a company's tacit knowledge at a stroke, and explosive productivity gains can be expected.
- "Is it easy for AI to use?" could be the new standard for UI and accessibility design as well.
- Eventually, a world where "AI's manager AI" is placed and AIs collaborate with each other may well be possible.

This is an area that has not yet been systematically organized on the Internet, but there were many indications that it is likely to expand significantly into real organizations and work styles over the next year or two.

Events after this
    - [[How was it using Devin? ～Case Studies and Key Points for Introduction]]

- [[Meeting to see Devin]]
[[Devin]]

---
This page is auto-translated from [/nishio/安野寺本西尾Devin座談会](https://scrapbox.io/nishio/安野寺本西尾Devin座談会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.