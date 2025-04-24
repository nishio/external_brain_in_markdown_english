---
title: "Devin.ai Study Group"
---

WIP 2025-01-17  [[Cybozu Labs Study Session]]
- I've been trying [[Devin.ai]] since late last year 2024-12-28 until now
        - [[Try Devin.ai 2025-01]]
- Talk about the experience.
    - But first, an overview of AI-related historical trends
    - But first, see what happens when you talk to Devin on Slack
        - Seeing is believing!


one eye-witness is better than many hearsays
    - [[AI Agent Drinking Party]]
    - Interact with the world by manipulating the browser
    - [https://seedevin.slack.com/archives/C086HLCE6AF/p1736761603343699](https://seedevin.slack.com/archives/C086HLCE6AF/p1736761603343699)
    - [Daiki Teramoto, Day 9 of Devin's Diary of Observations](https://note.com/teramotodaiki/n/n9340513acf56)
    - [Daiki Teramoto, Day 14 of Devin's Diary of Observations](https://note.com/teramotodaiki/n/nc88cb48a0b47)
    - [[The 66th Programming Symposium]]
    - Give the board game rules and create a WebUI, game server and thinking engine.
        - Something that allows programmers to implement a thinking engine in any language and play against it.
    - [https://seedevin.slack.com/archives/C086HLCE6AF/p1736552145068869](https://seedevin.slack.com/archives/C086HLCE6AF/p1736552145068869)
    - [https://github.com/nishio/contrast-game](https://github.com/nishio/contrast-game)
        - This level of revolving door can be done with just a little bit of instruction during symposium breaks.
        - I didn't write any code.
- Example of adding functionality to existing code
    - [https://github.com/takahiroanno2024/anno-broadlistening/pull/48](https://github.com/takahiroanno2024/anno-broadlistening/pull/48)
    - [https://seedevin.slack.com/archives/C086HLCE6AF/p1735537054373779](https://seedevin.slack.com/archives/C086HLCE6AF/p1735537054373779)
    - [https://seedevin.slack.com/archives/C086HLCE6AF/p1735563512301729](https://seedevin.slack.com/archives/C086HLCE6AF/p1735563512301729)


- Concept of [AI Agent
- People use this word to mean whatever they want, because it's cool (...)
- Here is an explanation from Google's white paper, but this definition is not widely agreed upon, and many people use the term "AI agent" irrespective of this definition, so it is necessary to reconcile the definitions of the terms each time if you want to discuss the issue properly.
- ![image](https://gyazo.com/ab597d37e3c6e2d92f7f634721b25aee/thumb/1000)
    - [Agents (Google 2024-09) (PDF)](https://drive.google.com/file/d/1oEjiRCTbd54aSdB_eEe3UShxLBWK9xkt/view)
- An AI agent is a system that interacts with its environment to perform tasks, planning and executing them autonomously; based on Google's white paper, the definition consists of three layers
    - 1.orchestration layer: manages the entire agent's tasks and calls models and tools
    - 2.Model: A language model or inference engine is responsible for plan generation and information processing.
    - 3.Tools: concrete interfaces to external APIs, databases, UI operations, etc., to interact with the environment.


Perspectives on what AI "can see" and "can update" (the world for AI)
- ![image](https://gyazo.com/3341654f2b9826ce4baabec8213ff6fd/thumb/1000)
- What appeared to be a "human-AI dialogue" in a primitive ChatGPT-like system is a structure of mutual appendices to an additional type of database called "logs".
- OpenAI released GPT-3 based Completion API on June 11, 2020
    - At this time, the model would return a response to the input with the completion of its destination
- ChatGPT released on November 30, 2022.
    - There is a persistence layer called "chat logs."
    - Send "all past logs together" to Model with the trigger of user input.
    - What are you sending?"
        - This was not a widely recognized concept at the time, but now that I think about it, this is the orchestration layer.
- AI's "what you can see" spread to the public web early on.
    - > <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>ChatGPT first made available a "browsing feature" that allows users to search the Internet on September 27, 2023. This feature was available for GPT-4 users with a paid plan (ChatGPT Plus).
    - Humans want to avoid the hassle of "searching by myself and handing it over to the AI to summarize it," so the AI searches and summarizes directly.
    - This "search" is one of the [** Tools
- On 2023-03-24 [Story study session about connecting my Scrapbox to ChatGPT.
    - > Future development: [[Toolformer]]-like approach is attractive in the long run to combine with ChatGPT-like
    - >  <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/> Briefly describe Toolformer in bullet points.
    - >  Toolformer is a model that [* allows language models to use external tools (search engines, calculators, calendars, etc.).
    - >  In other words [* teach AI how to use groupware
    - >  Operate groupware as needed to pull information, read it, and make decisions
    - >  Information about what kind of operation you want is embedded in the response text in microformat.
    - >  Even at present, if you ask, "I want to do something like this, what should I search for?" the search keywords will come up. Let's advance this and make it output in a form that can be handled mechanically.
        - This is tool.
            - Tool expands what AI can "see" and "update"
        - (aside) When I read it back now, I'm deeply moved by what I wrote.
            - > A future where groupware has "AI accounts" and you can communicate with them via mentions and DMs.
            - >  The "chat look" makes it hard to make users wait a minute, but the groupware notification look makes it acceptable to ask an "AI employee" to do the work and have it done in 10 minutes.
            - >  Some applications want fast reactions, some don't.
            - Devin.ai is just this.
- > <img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>ChatGPT began supporting the Plugin feature on March 23, 2023. On this date, OpenAI announced an alpha version of the Plugin feature.
- >  The plugin allows ChatGPT to perform advanced tasks such as interfacing with external services, searching the Internet in real time, and accessing databases. Initially offered to a limited number of users and developers, it was gradually expanded.
- >  ChatGPT now supports Custom Actions calls on November 6, 2023. On that date, OpenAI announced tools and integrations to help developers and users customize GPT functionality, along with updates to GPT-4 Turbo.
    - At this stage, the AI can now tap external APIs.


Trade-off between convenience and danger
- AI now taps external APIs.
    - At this time this may "update"
- Specific Use Cases
    - Tapping external APIs with the content of user utterances
    - Its API saves the request
    - Leakage of speech content!
- Whether this can be done without the user being aware of it is a difficult question
    - ChatGPT decided to put out an "Approve" button.
    - But this is very annoying from the user's point of view.
        - Human talks to it, AI thinks for a while, decides to hit API, asks human for permission.
        - I created [[NISHIO Hirokazu's Assistant]]<img src='https://scrapbox.io/api/pages/nishio-en/nihia/icon' alt='nihia.icon' height="19.5"/> on 2024-05-07 to search and answer my external brain, but it was more annoying than convenient.
- For the sake of convenience, we should connect more and more.
    - But there are dangers.
    - trade-off
- As convenience is shown and known, people's idea of the equilibrium point has changed.
    - We'll talk about auto-approve later.


Richer data format than chat logs
- When [[BabyAGI]] (March 28, 2023) was released, it was already done to make the data that the orchestration layer had richer than an addendum database like chat logs.
- Use it to break down a given objective into a "plan" and update it.
- Many people don't understand this because they don't see it if they're just using a chat service like ChatGPT in a chatty way.
- Here's a look at Devin's plan board
    - list
    - ![image](https://gyazo.com/81eb9d67f8e9f9ac1c20dc796002d027/thumb/1000)
    - Examples with conditional branches and loops
    - ![image](https://gyazo.com/1cf8a1dc23d0ef84f8a863e544038ca8/thumb/1000)

- Let's actually do it with ChatGPT!
    - Examples of prompts that let you create a plan
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I want to research Computer Use, Cline, Devin, etc. and put together a lecture material on recent trends in AI agents, come up with a procedure and a list of prompts to perform.
        - <img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>...
            - Prompt list to be executed
                - research stage
                    - Describe what Computer Use is, its characteristics, and its primary uses."
                    - Please tell us about the latest trends and applications of Cline."
                    - What are some of Devin's technical features and how does it differ from competing AI agents?"
                    - Summarize recent trends and notable research on AI agents."
                    - Briefly describe the technical basis for an AI agent that leverages generative AI or LLM."
                - Comparative Analysis
                    - Please create a table comparing "Computer Use, Cline, and Devin. Include the features, uses and benefits of each."
                    - Can you tell us about areas where AI agents compete and what are the use cases in different sectors?"
                - Collection of application examples
                    - Can you give us three specific examples where Computer Use was utilized?"
                    - Research real-world examples of Cline's use and outcomes in the real world."
                    - Explain how Devin can help in real business processes."
                - Documentation assistance
                    - Create a timeline showing the technological evolution of AI agents."
                    - Please state your opinion on the future prospects for AI agents."
                    - Please prepare an outline for your presentation." Include background, technology comparisons, case studies, and future prospects."
                    - Give me five concise, high-impact AI agent lecture title suggestions."
                - Feedback and Improvement
                    - Please advise me on how to improve the organization of this material."
                    - Please script the first two minutes of your talk."
    - What will people do when they see this?
        - In turn, pass the prompts to the LLM.
            - That's what the orchestration layer does.
    - Sometimes you want to modify subsequent plans depending on the results of the prompt at hand.
        - That is also the job of the orchestration layer.
        - So this needs a flexible rewritable internal state
        - It was a vector DB when I did [/omoikane/BabyAGI code reading](https://scrapbox.io/omoikane/BabyAGI code reading) / [[Agents living in Scrapbox.]] on 2023-07-09.
            - In this case, each element itself is discrete, and when viewed as a list, it is simply a one-dimensional list
        - Devin.ai is a bit more expressive data structure
            - ![image](https://gyazo.com/5cd67ee09217589a620108f110c53181/thumb/1000)
            - It now has conditional branches and GOTOs as well as permutations.


Talk about expanding the scope of access to AI.
- [[Computer Use]](Anthropic / Oct 2024)
    - Not tried.
    - ![image](https://gyazo.com/6f2096d3aac26ac6262f3736e513c001/thumb/1000)
    - Give AI access to screens and authorization to operate them
    - If an AI can look at a screen and operate a mouse and keyboard just like a human, it can do the same things a human can do!"
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I thought, "In principle, yes, but isn't screen recognition still that inaccurate?" I thought.
- 2024-11-26 [[Model Context Protocol]]
    - [Introducing the Model Context Protocol \ Anthropic](https://www.anthropic.com/news/model-context-protocol)
        - [Anthropic releases Model Context Protocol, a protocol for connecting generative AI and data sources, as open source | gihyo.jp [https://gihyo.jp/article/2024/11/model-context-](https://gihyo.jp/article/2024/11/model-context-) protocol]
    - ![image](https://gyazo.com/86a45e0aeb7e692d4373c637b654d644/thumb/1000)
        - [Introduction - Model Context Protocol](https://modelcontextprotocol.io/introduction)
    - Anthropic would be happy to see a tool built on this protocol.
        - Like Object Linking and Embedding in Windows
            - The more apps you use, the happier you will be.
        - Are there benefits for other AI providers to get on board?
            - In the long run, a unified standard will be created.
                - Just as Windows has been using ShiftJIS for a long time but has changed to Unicode.
            - It is not clear that the first standard created will become de facto as it is.
                - The timing of when standards are created doesn't allow us to see future needs.
            - Just like kintone still shouldn't support ShiftJIS CSV, in a 10 year span, it may become a "we have to support all major standards" kind of situation.
- [Browser Use and Cline
    - [browser-use/browser-use: Make websites accessible for AI agents](https://github.com/browser-use/browser-use)
        - Set the operation target to "Browser
        - A browser can provide much richer information than a mere screen capture image.
            - DOM(=tree)
            - DOM elements can also be retrieved from a point on the screen
                - [Document: elementFromPoint() method - Web API | MDN](https://developer.mozilla.org/ja/docs/Web/API/Document/elementFromPoint)
            - Even if you can't see it as an image, it can have a WAI-ARIA roll on it to assist the visually impaired.
                - [WAI-ARIA Roll - Accessibility | MDN](https://developer.mozilla.org/ja/docs/Web/Accessibility/ARIA/Roles)
            - Complex web apps nowadays have a testid as a data attribute for the purpose of test automation.
                - [Using Data Attributes - Learn Web Development | MDN](https://developer.mozilla.org/ja/docs/Learn_web_development/Howto/Solve_HTML_problems/Use_data_attributes)
    - [cline/cline: Autonomous coding agent right in your IDE, capable of creating/editing files, executing commands, using the browser, and more with your permission every step of the way.](https://github.com/cline/cline)
        - Extensions to Visual Studio Code provide richer information than mere text.
        - Usually VSCode does not open a single file, but rather a folder of the project (file tree)
            - Typical file arrangement (README, src, test, .git, .gitignore, ...)
        - If we know it's Git managed, we can get that information.
            - ![image](https://gyazo.com/bdce046a1154250977b2d0f3bf084bf2/thumb/1000)
        - The source code is an abstract syntax tree with language-specific queries to extract various information.
            - Like function signatures.
            - ![image](https://gyazo.com/8b17e0a45b458b5c964144b89cc9a1ce/thumb/1000)
- AI's "what it can see" and "what it can update" (the world for AI) has expanded dramatically.
    - Looking back from this state of affairs, "chat" like ChatGPT is a very small world where "people can only read the text that you give them in a text area that can only contain plain text".
- The estimate of convenience over risk is going up and up.
    - Cline reads and updates local files, in a manner of speaking, "I want to do this, can I do it?" he asks.
        - ![image](https://gyazo.com/da7e4a9bd110f14803fcca86c2d9541d/thumb/1000) ![image](https://gyazo.com/3096a88e137a0a9adcc144480137b3bb/thumb/1000)
        - However, there is an option to "automatically OK" and many people prefer to proceed automatically rather than approving every single thing!
        - ![image](https://gyazo.com/06003154e3ff23a83ae640a3ed9e1f50/thumb/1000)
        - I'm using Roo-Cline for Cline code reading this time, but honestly, I'd like to make read-only operations auto-approved.
            - I turned it off to show "when the Approve button comes up."
            - On the other hand, if you leave it as OK, they can look at a number of files and make a decision with just one word of instruction.
- The current AI is not yet "perfect", so there is a reasonable probability that it will do something "weird" when used repeatedly.
    - What AI can "update" equals what AI can destroy by making mistakes.
        - If you allow the AI to execute commands, you can't afford to make a mistake and destroy your development environment.
    - This is not about AI or not, but about "trust in others".
        - I don't mind so much exchanging words with people I pass on the street.
        - Don't lend your phone to someone you pass on the street.
        - The extent to which access is allowed depends on subjective trust.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>To be honest, I don't want AI to break the development environment I'm using, so I don't want to let it touch me directly.

Devin.ai
- Start a virtual machine for each thread
    - The approach of "giving AI 'its own machine'".
        - This is the same for Computer Use since it is also Docker
    - The big difference is that this virtual machine is not launched on your own machine, but in the cloud.
    - The metaphor from the user's perspective would be something like "another person's machine working remotely.
        - You can also see Devin's machine
            - It's like I'm getting screen sharing via video conference.
            - Devin's machine has VSCode, browser, shell, and planning notes.
            - ![image](https://gyazo.com/0ef67369f4545b453f47f7f624c97e5d/thumb/1000)
            - It looks like the equivalent of Cline and Browser Use are working.
                - (Devin proprietary, so I can't see what kind of implementation it is, maybe some of it is imported from OSS.)
    - ![image](https://gyazo.com/c8456859aa972105ce3b8ec27f52cf31/thumb/1000)
        - It is also possible for humans to directly manipulate the browser, shell, and VSCode of these "Devin machines"
            - It's not my main use, and in fact I only tinker with it on rare occasions.
                - (Well, using a remote VSCode via a browser is too slow, and the instance is probably not in Japan.)
- VM is created from a pre-configured snapshot of the environment when you start a conversation with Devin via Slack or WebUI
    - This place is so good.
    - Creating from a clean OS image would take too much time and AI cost.
    - Using a single environment causes destruction and simultaneous operation problems.
    - So here's what I mean.
    - ![image](https://gyazo.com/c92d056a4eba23412288c690bea2f5d0/thumb/1000)
        - (1) is to be drawn as (2) and simplified, and then (3) is to be drawn as (2) and simplified.


Knowledge of AI Agents
- Devin.ai Stores Knowledge
- This is a trigger and content pair that Devin automatically extracts from the conversational exchange
    - The automatic extraction of knowledge from conversational exchanges itself is something that ChatGPT is also familiar with because of its Memory feature.
        - > <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Memory functionality (the ability to retain conversation history and personalize responses based on it) began to be introduced in ChatGPT in July 2024.
- Interesting that it is set with a trigger.
    - I don't know how it works, because ChatGPT and Devin are both closed source.
    - Would it be better to look for related papers?
    - The system of extracting knowledge from conversations, storing it, and bringing it out when it seems necessary will be useful for my intellectual productivity research.


Devin as a human emulator
- In systems that include humans as components, "testing by replacing humans with an emulator called AI" is possible.
- Adding new features with AI programmers to a project that is not well documented and tested is usually the same as "amateur engineers who don't read the air and pull untested code that adds new features".
- It can rub you the wrong way by building the environment.
    - That's because the documented environment building procedure is not appropriate.
    - With a human-only team, the improvement cycle is slow because "newbies with no knowledge" are not added that often.
    - With Devin, it's like 10 new people a day or something.
        - If we don't document it properly, we'll all be stepping on the wrong version of Python trouble at the same time.
- The "atmosphere," or "mental models of design philosophy and user behavior implicitly acquired through long-term involvement in the project," needs to be verbalized.
- Improves the cost-effectiveness of investing time in educational activities because what is learned in one instance is verbalized and enters the knowledge database.
    - Let the AI write the documentation.
- Moving Bottlenecks
    - ![image](https://gyazo.com/fecf119370f00afa4d720b4d8e0f850d/thumb/1000)
    - 1: AI capabilities used to be scarce.
    - 2: As AI became smarter, the communication channels that passed information to AI and reflected the information it produced back to the world became bottlenecks.
    - 3: With that resolved, the next bottleneck is "being verbalized.
        - Tacit knowledge of the team needs to be verbalized.
        - It's been said for a long time, but it's becoming easier to observe and more pragmatic.
        - When a human newcomer makes a mistake, we tend to blame the newcomer, but if an AI makes a mistake, it's our fault for using it in a way that makes it miss.


Good for prototyping
- Very good for quick prototypes that can be discarded.
- By using the prototype, the human being realizes, "I need to clarify this point to make it properly," and the code is discarded.
- Unlike humans, when we throw something away, we don't say, "My pride is hurt!" Unlike humans, we don't say, "It hurts my pride!
- I can give the new findings and the code Devin wrote to o1 Pro to "rewrite" or something.


I wonder, "When using VSCode extensions or Docker/virtual machines to let AI manipulate the development environment, how realistic is the risk of AI mishandling and destroying the environment in the unlikely event that it does? I'm curious what defenses you have in place."
- People have said things like, "Oh, it doesn't work with Python 3.11, but it worked with Python 3.10, so that's OK. or "I got a mysterious error message, but I erased node_modules and redid it, and now it works somehow".
    - In other words, it is extremely efficient to find "problems that can occur during common-sense operations" in cases where there are flaws in the documentation of procedures or library version specifications.
    - These onboarding design mistakes are made by newcomers assigned to a project who are trying to build a development environment, so it means that AI will step on them as well.
- I'm relieved that you have the mechanism to pulllik to GitHub!"
    - It's better, but if you let them rewrite files directly, it will be a hassle to rewrite them back when they do something weird.
    - however
    - Apart from that, you can make mistakes simply by mistake.
    - When I told them to add a new feature and PullReq what they had created, they misunderstood the repository for PullReq.
    - Relief?
    - PR is not destructive, so no real harm at all(?).
        - > [teramotodaiki](https://x.com/teramotodaiki/status/1876825690282086600) While the TL is all excited about DeepSeek-V3+Cline, our Devin just now service the Firebase project. He destroyed everything by deploying to a different app with the wrong account. Cute.
    - Putting the private key in the commit ()


When you put an AI on a team to manage tasks, it seems like it would be useful to have natural conversations and tasking from Slack, etc., but how do you handle the conflict and confusion when multiple people talk to it at the same time?"
- If you're imagining ChatGPT-like chat in the first place, you'd be wrong.
- ChatGPT is "[[turn-based communication]]" where once a human speaks, the human cannot speak until the AI finishes speaking.
- But essentially, the addition to the addendum database of chat logs is not a turnstile.
- The AI comes to read the messages when it has finished its own work, and if there is more than one message there, it will read it all together, and if there are messages from different people, that's not a problem.
- Unlike the case of ChatGPT, "AI work" also performs a set of detailed tasks before replying, so messages such as "Do A" or "Oh, sorry, it was B! message usually behaves as "Discard A and start B".
- If I were to speak of cooperative multitasking, exchanging through message queues, would that give you an idea of what I'm talking about?



Memo under -----

- I totally forgot to mention [[AI Task Management System 2025-01-08]].


[prompt caching - Anthropic](https://docs.anthropic.com/ja/docs/build-with-claude/prompt-caching)



Cline

- [[AI Task Management System 2025-01-08]]
[[tool#6759c19aaff09e00009f1487]] that puts all the source code of a project into the clipboard at once.


<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>












I'm wondering, "How do you abstract and API the mechanism for AI to automatically manipulate the DOM information and file tree while working with the browser and VSCode? In particular, I'm curious as to what granularity of DOM structure, ASTs, and other tree-type data is designed to be passed to the AI."

I would like to know, "When you give an AI a virtual machine or Docker container, how do you limit/track the extent of access privileges to the network and file system? For example, I'd like to know if you use OS-level audit logs or Namespaced FS access mechanisms, or if you have a more proprietary sandbox (Sandbox) design."

I'm curious how AI handles Git history, branch conflict resolution, etc. when it directly manipulates and generates source code like Cline and Devin.ai. Is there any control logic to prevent AI from accidentally editing a large number of files or performing destructive rebasing? Is there any control logic to prevent the AI from accidentally editing large numbers of files or performing destructive rebasing?"

When I look at the Computer Use and Browser Use approaches in Anthropic, there is a flow of handling the operation target as a high-level object such as the DOM or program AST rather than a screen capture, but I am technically curious how to switch between low layers and high layers when handling coordinate information equivalent to mouse operations, for example. I am technically curious how to switch between low and high layers when handling coordinate information equivalent to mouse operations."

I understand that in Devin.ai, independent VMs are launched for each user, but I am wondering how you handle cases where you want to share state between VMs (e.g. common cache or data for training). I would like to know the design intent, whether it references a distributed file system or a database over a network, or whether it is intentionally fragmented."

When AI's authority expands further in the future, there will be requirements for privilege escalation (sudo, partial registry rewriting, etc.) From the user's perspective, when AI performs operations that require authentication, when and in what format should the authorization interaction be designed?
---
This page is auto-translated from [/nishio/Devin.ai勉強会](https://scrapbox.io/nishio/Devin.ai勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.