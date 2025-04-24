---
title: "OpenAI DevDay Keynote"
---

[https://www.youtube.com/watch?v=U9mJuUkhUzk](https://www.youtube.com/watch?v=U9mJuUkhUzk)
Experimenting with the efficiency of the intellectual production process of a Japanese person understanding this 45-minute video in English.

Copy and paste the YouTube Transcript.
- There are about 9,000 tokens.
- [https://platform.openai.com/tokenizer](https://platform.openai.com/tokenizer)
    - ![image](https://gyazo.com/b5d904533e44b854764d20fdefe0d68d/thumb/1000)

Put in gpt-4-1106-preview in Playground
- max length was short in default, so I maxed it out, it was 4095.
- [https://platform.openai.com/playground?mode=chat&model=gpt-4-1106-preview](https://platform.openai.com/playground?mode=chat&model=gpt-4-1106-preview)
prompt

```
[SYSTEM] Pick important features from following speech transcript and return bullet lists.
[USER] ...
```

![image](https://gyazo.com/2d1e46d0ea5667d026c7093d85156b42/thumb/1000)

result
![image](https://gyazo.com/f09160f596dd3ffd8949d3a3530aa1c8/thumb/1000)

result

```
- OpenAI DevDay Introduction 
  - Sam Altman welcomed attendees to the first-ever OpenAI DevDay.
  - OpenAI's history and connection to San Francisco.
  - Progress over the past year was highlighted.

- ChatGPT and GPT-4 
  - ChatGPT started as a research preview and evolved with the launch of GPT-4.
  - GPT-4 remained the most capable model available.
  - Launched voice and vision capabilities for ChatGPT.
  - DALL-E 3 released as the most advanced image model.
  - ChatGPT Enterprise introduced for business with enhanced features.

- OpenAI Usage and Growth 
  - 2 million developers on OpenAI's API.
  - Over 92% of Fortune 500 companies use OpenAI products.
  - ChatGPT reached approximately 100 million weekly active users.

- OpenAI’s Direction and Goals 
  - Focus on usability and practical impact of AI products on users' lives.
  - GPT-4 Turbo announced addressing developer feedback with new features.

- GPT-4 Turbo New Features 
  - Expanded context length of up to 128,000 tokens.
  - Better response control with JSON Mode and reproducible outputs.
  - Improved world knowledge with updated knowledge cut-off to April 2023.
  - New modalities like DALL-E 3 and text-to-speech API.
  - Customization via fine-tuning, with a new custom models program.
  - Doubling tokens per minute for established GPT-4 customers.

- Pricing Announcements 
  - GPT-4 Turbo made more affordable with a significant price reduction.
  - Improved affordability expected to drive more innovation and use cases.

- Future Commitments and Partnerships 
  - Ongoing partnership with Microsoft and a commitment to AI safety discussed.
  - The future of AI and agents, gradual iterative deployment emphasized.

- Introduction of GPTs 
  - Customized versions of ChatGPT tailored for specific purposes announced.
  - GPTs allow sharing and discovering ways to use ChatGPT.
  - Users can program GPTs with language, enabling broad accessibility.
  - The GPT store to be launched for public sharing and revenue sharing.

- Assistants API 
  - New API provides persistent threads, retrieval, code interpreter, and function calling.
  - Facilitates building agent-like experiences in apps.

- Acknowledgments 
  - Sam Altman thanked the OpenAI team for their hard work.
  - OpenAI's mission highlighted to revolutionize technology and society through AI, empowering individuals and humanity.
```


DeepL

```
- Introduction to OpenAI DevDay
  - Sam Altman welcomed participants to the first OpenAI DevDay.
  - OpenAI's history and connection to San Francisco.
  - Progress over the past year was highlighted.

- ChatGPT and GPT-4
  - ChatGPT began as a research preview and evolved with the launch of GPT-4.
  - The GPT-4 remained the most capable model.
  - Initiate audio and visual features of ChatGPT.
  - DALL-E 3 is presented as the latest image model.
  - ChatGPT Enterprise was enhanced and introduced for business use.

- Use and Growth of OpenAI
  - Two million developers use OpenAI's API.
  - More than 92% of Fortune 500 companies use OpenAI products.
  - ChatGPT reached approximately 100 million weekly active users.

- OpenAI Directions and Goals
  - Focus on the usability of AI products and their practical impact on users' lives.
  - GPT-4 Turbo announces that it will respond to developer feedback with new features.

- What's New in GPT-4 Turbo
  - Extended context length up to 128,000 tokens.
  - JSON mode and reproducible outputs provide better response control.
  - Updated knowledge cutoff in April 2023 improves global knowledge.
  - New modalities such as DALL-E 3 and speech synthesis APIs.
  - Customization with fine-tuning through a new custom model program.
  - For customers already using GPT-4, we will double the tokens per minute.

- Pricing Notice
  - GPT-4 Turbo is now more affordable with a significant price reduction.
  - With greater affordability, innovation and use cases are expected to expand.

- Future commitments and partnerships
  - Discussed ongoing partnership with Microsoft and their commitment to AI safety.
  - The future potential of AI and agents and gradual iterative development was emphasized.

- Introduction of GPT
  - Presented a customized version of ChatGPT for specific purposes.
  - GPT can share and discover how to use ChatGPT.
  - Users can program GPT in their language, allowing for a wide range of accessibility.
  - Open a GPT store for public access and revenue sharing.

- Assistant API
  - The new API provides persistent threads, search, code interpreter, and function calls.
  - Facilitates building an agent-like experience with the app.

- thanks
  - Sam Altman thanked the OpenAI team for their efforts.
  - He emphasized that OpenAI's mission is to empower individuals and humanity by revolutionizing technology and society through AI.
```


Let's delve into the areas of interest.
prompt

```
I'm interested in Assistants API. Explain it in detail.
```

result

```
The Assistants API is a new offering from OpenAI announced at the DevDay event. Here's an in-depth look at what it entails:

- **Persistent Threads**: This feature allows developers to create a continuous conversation thread for each user interacting with the assistant. Unlike the traditional approach, where you need to resend the entire conversation history with each API call, persistent threads manage the state of the conversation and context for you. This simplifies the development process by allowing a continuous dialogue with the AI without having to manage context windows or the serialization of messages.

- **Retrieval**: Assistants API now has the capability to parse and understand external documents. This feature enables the AI to access additional knowledge beyond the current user messages by ingesting long-form documents or databases. This is useful when the AI needs to reference information not contained in the prompt or its own knowledge base.

- **Code Interpreter**: A feature that expands the capabilities of the AI to write, execute, and even generate code during conversation. This allows developers to create assistants that can perform more complex tasks such as data analysis, calculations, and code generation in real-time, akin to having a Python interpreter right within the chat interface.

- **Function Calling**: The Assistants API enhances function calling abilities by ensuring JSON-valid output and enabling the calling of multiple functions simultaneously. This greatly improves the potential for developers to integrate the AI with APIs and third-party services, allowing for a range of actions and interactions within the application.

- **Multimodal Capabilities**: The Assistants API incorporates OpenAI's new modalities, such as DALL-E 3 for image generation and a new text-to-speech API for generating natural-sounding audio. This integration enables developers to build richer, multimodal user experiences.

- **Developer Dashboard**: The API offers a dashboard where developers can see the steps the tools are taking, which includes executing functions with specified parameters and managing uploaded documents. This feature provides transparency and control, allowing developers to troubleshoot and optimize their assistant's behavior.

- **Simplification and Efficiency**: The Assistants API is designed to streamline the process of building advanced AI assistants. It removes the complexity involved in managing conversation states, chunking algorithm setup, and custom backend systems for knowledge retrieval. This means developers can build sophisticated assistive agents with less effort, lower maintenance, and reduced development times.

- **Integration with Apps**: The Assistants API can be integrated into applications to provide users with an interactive AI that can manage conversations, invoke functionalities of the app, and even take real-world actions based on user requests.

As demonstrated in the event, the Assistants API can be put to practical use in a travel app where it answers user queries about destinations, retrieves book flight details or accommodation reservations, and even performs financial calculations for shared expenses.

The Assistants API is a significant step towards creating AI-enhanced user experiences that are more engaging, intuitive, and powerful. It is intended to help developers create not just chat interfaces, but intelligent agents capable of acting on behalf of the user, ultimately leading to the future of AI agents as envisioned by OpenAI.
```


DeepL

```
Assistants API is a new OpenAI service announced at the DevDay event. Here is a closer look at what it entails:
 
 - **Persistent Threads**: This feature allows developers to create a persistent conversation thread for each user interacting with the assistant; unlike the traditional approach that requires resubmitting the entire conversation history with each API call, persistent threads can be used to manage the conversation state and context. This simplifies the development process by allowing continuous interaction with the AI without having to manage context windows and message serialization.
 
 - Search**: The Assistant API now has the ability to parse and understand external documents. This feature allows the AI to access additional knowledge beyond the current user message by importing long documents and databases. This is useful when the AI needs to reference information not included in prompts or its own knowledge base.
 
 - Code Interpreter**: a feature that extends the AI's ability to write, execute, and generate code during conversations. This allows developers to create assistants that can perform more complex tasks such as data analysis, computation, and code generation in real time.
 
 - Function Call**: The Assistants API enhances function calling capabilities by guaranteeing JSON-valid output and allowing multiple function calls at the same time. This greatly increases the possibility for developers to integrate AI with APIs and third-party services, enabling a variety of actions and interactions within an application.
 
 - **Multi-modal capabilities**: The Assistant API incorporates new OpenAI modalities such as DALL-E 3 for image generation and a new speech synthesis API for natural voice generation. This integration allows developers to build richer, multimodal user experiences.
 
 - Developer Dashboard**: The API provides a dashboard that allows developers to see the steps the tool performs, such as executing a function with specified parameters or managing uploaded documents. This feature provides transparency and control, allowing developers to troubleshoot and optimize the behavior of the assistant.
 
 - Simplify and Streamline**: The Assistants API is designed to streamline the process of building advanced AI assistants. It removes the complexity involved in managing conversational state, setting up chunking algorithms, and custom back-end systems for knowledge retrieval. This means that developers can build sophisticated assistive agents with less effort, less maintenance, and shorter development times.
 
 - **Integration with Apps**: By integrating the Assistants API into your application, you can provide users with an interactive AI that can manage conversations, invoke app features, and even take actual actions based on user requests.
 
 As demonstrated at the event, the Assistants API can be put to practical use in travel apps, answering user inquiries about destinations, retrieving booked flight details and lodging reservations, and even performing financial calculations for shared expenses.
 
 The Assistants API is an important step toward creating a more engaging, intuitive, and powerful AI-enhanced user experience. The API is intended to enable developers to create not just chat interfaces, but intelligent agents that can act on behalf of users, ultimately leading to the future of AI agents as envisioned by OpenAI.
```



Now, with this in mind, let's see the video in action
- I know what it's about, so I'll listen at 1.25x.

- The abstraction of "threads and messages."
    - Server-side persistence
        - Do they digest only the most recent ones on their own, or do they[[MemoChat]]的な仕組みで検索するのか、どっちかな<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - I hope it's the latter.
- Guaranteed output in JSON format "without additional latency
    - You've applied a robust format guarantee fine tuning, and the probability of failure must be so small that it's negligible.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- The search demo doesn't really fit my needs (because it's a demo that is designed to be popular with the general public).<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Providing a startful API with persistent storage has drastically reduced implementation costs on the part of third-party developers.
    - I no longer have to think about chunking or context width.
        - I wonder if the contents of this persistent storage can be retrieved later, if not, GDPR will be pissed off, so maybe they can.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - Oooooh, I can see the list of threads on the developer dashboard.
- With Code Interpreter integrated, processes that are better written in Python than in natural language can be written in Python.
    - I looked at the available formats and they include C++ and Java...<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- The addition of audio input and output allows for impressive demonstrations.
    - I'm sure we'll be seeing more and more demonstrations of this in the future, and it will help to increase the "OpenAI is awesome" atmosphere in the world.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

## Try the Assistants API
.
Save PDF of my book [[The Intellectual Production of Engineers]] with Upload, Retrieval turned on
- The reason it takes a little longer is probably because it is chunking and building a vector index.
![image](https://gyazo.com/04b3f5bca54454f8ebbe8e72aaf79b30/thumb/1000)
I'm not sure if you referenced the PDF or not, so I'll try to make an explicit reference to it.
![image](https://gyazo.com/3f13cafc2bf284f161243604bf47a09e/thumb/1000)
Properly referenced.
- You can see where the reference is made.
    - ![image](https://gyazo.com/9035a9053d0ac580955711bc071fe7d9/thumb/1000)
        - Table of Contents.
I'll make a more explicit request.
- ![image](https://gyazo.com/ca223615727e5a649af21ba49e830412/thumb/1000)
- You make it sound so plausible.

Another question
- ![image](https://gyazo.com/6fe155ea2ad2e3b5b1cd74fa07ae8d65/thumb/1000)
- The link in the source display is probably garbled and cannot be seen in the UI: `[[9†source]]'.
    - The log itself doesn't come with any information about the search results.
    - If the link isn't broken, you can check the source from the UI, so there should be an API to get that.
        - Ah, so the information is originally given to the message in the form of annotations?

impressions
- It's super easy to create a permanent assistant just by throwing a PDF of a book at them and have them respond based on the book's content at any time.
    - The ability to buy books in PDF format will become a customer value in the form of "can I get an AI to read it?"
- For my personal research purposes, I want to tweak the details, so it's a bit useless.
    - > [nishio](https://twitter.com/nishio/status/1721800710134915476/quick_promote_web/intro) OpenAI DevDay reminded me of the days when Microsoft released Visual Basic and Visual C++, and the variety of "Windows apps" that were being created with them. I think that OpenAI has created a situation where the time cost for engineers to create "AI apps" is much cheaper.
    - Positioning WordPress as a way to create websites.

I summarized the SLIDE.
    - [[Programming Education in the Age of Generative AI Toward the Joy of Creating and Learning]]

> [nishio](https://twitter.com/nishio/status/1721857526990586203/quick_promote_web/intro) Put my book "The Intellectual Production of Engineers" into OpenAI Assistants API and ask a question. This is exactly what I'm talking about, the "efficiency of how to read books" feeling.
>  ![image](https://pbs.twimg.com/media/F-VEHiGakAEioDR?format=jpg&name=medium#.png)

---
This page is auto-translated from [/nishio/OpenAI DevDay Keynote](https://scrapbox.io/nishio/OpenAI DevDay Keynote) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.