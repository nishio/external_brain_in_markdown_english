---
title: "Scrapbox ChatGPT Connector Policy Consultation 2023-03-13"
---


consultation
- I would like to discuss the policy of [[Scrapbox ChatGPT Connector]].
    - I released the code with the intention of minimizing it to make it easier to understand rather than adding more functionality, but if it is truly minimal, it can be cut down even further.
    - On the other hand, I've seen various opinions from people who have used it, and I'm eager to try various new features myself.
    - It is preferable that the code for this new feature can also be easily shared.

summary
- The Scrapbox ChatGPT Connector was designed to be easy to understand with minimal code, but after seeing the feedback from those who use it, we wanted to try out some new features.
- We would also like to be able to easily share code for new features.
- Via UserScript, the selection text on Scrapbox can be retrieved and rewritten.
- Set up a server with the Scrapbox ChatGPT Connector API and hit it from UserScript.
- We would like to expand the functionality to meet user needs, such as updating the vector index and asking questions to multiple people.
- Create a separate develop branch from the main branch and add the code for the new functionality there.
- Implement new functionality in Python.



<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What would you like to see happen in this conversation? (GPT)
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I would like to discuss the policy of the Scrapbox ChatGPT Connector. I released it with the intention of keeping the code to a minimum to make it easier to understand, not to add more functions, but if it is really minimal, I can cut it down even more. On the other hand, I've seen a lot of feedback from people who have used it, and I'd like to try out some new features myself. I would like to be able to share the code for these new features easily.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>The "Scrapbox ChatGPT Connector" is a program that connects Scrapbox and GPT-3 and provides the ability to obtain GPT-3 responses on Scrapbox.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>No, getting the response on Scrapbox is one of the things I want to do. via UserScript, I can get the selection text on Scrapbox and rewrite it, so it would be interesting to use that.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How does it get the text of the selection?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I don't know
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What method do you use to get the text of the selection?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>UserScript calls do a good job.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What specific "UserScript" are you using to retrieve and rewrite the text of the selection on Scrapbox?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I haven't implemented it yet, but I'm going to set up a server with the Scrapbox ChatGPT Connector API and hit it from UserScript.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Regarding that "UserScript", what functionality is needed besides hitting the Scrapbox ChatGPT Connector API?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>No particular need, simple
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Is that "UserScript" a program that sends a request to a server with the Scrapbox ChatGPT Connector API?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Yes, sir.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Please tell us more about the Scrapbox ChatGPT Connector. What specific features does it have? And how are those features used?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Right now, only two functions: creating a vector index and using it to send questions to ChatGPT.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>ChatGPT" is a natural language processing model developed by Open AI that can generate sentences and complete sentences based on knowledge learned from a large corpus. The "Scrapbox ChatGPT Connector" is a program that connects Scrapbox and ChatGPT and provides the ability to retrieve ChatGPT responses on Scrapbox.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Question.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How do you collect information about this "UserScript"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>👎UserScript
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>The "ChatGPT" has many applications, not limited to the Scrapbox ChatGPT Connector, but the current "Scrapbox ChatGPT Connector" has two functions to create a vector index and use it to send questions to ChatGPT .......
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>User needs that I would like too: to update the vector index, to ask multiple people questions, to keep the conversation rally going.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>A "vector index" is a transformation model for vectorizing sentences for use with the Scrapbox ChatGPT Connector.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Question.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What would be a possible way to allow the "vector index" to be updated?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I have an idea of how to do it, but it's easier to write it down than to explain it in words.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Any specific ideas on how to update the "vector index?"
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Instead of updating it, it's better to reuse the old index and create a new one.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Understood. Can you give us more details on the specific steps involved in creating a new index?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>No. I'd rather write it in code. I prefer to write it in code, maybe create a separate develop branch from the main branch and put it there...
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>By "code," what code are you referring to? Please elaborate.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Python code.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Do you have any specific ideas on what changes would be needed to add new functionality to this Python code?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>There is. We're not getting anywhere, so as far as this place is concerned, let's get on with the implementation or...
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What do you mean when you use the expression, "we are not getting anywhere"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Summary.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>- The Scrapbox ChatGPT Connector was designed to be easy to understand with minimal code, but after seeing the feedback from those who use it, we wanted to try out some new features.
- We would also like to be able to easily share code for new features.
- Via UserScript, the selection text on Scrapbox can be retrieved and rewritten.
- Set up a server with the Scrapbox ChatGPT Connector API and hit it from UserScript.
- We would like to expand the functionality to meet user needs, such as updating the vector index and asking questions to multiple people.
- Create a separate develop branch from the main branch and add the code for the new functionality there.
- Implement new features in Python.


[https://keicho.netlify.app/#talk=e59nfBQZlBc4LAFFCyqX](https://keicho.netlify.app/#talk=e59nfBQZlBc4LAFFCyqX)
#KeichobotLog

---
This page is auto-translated from [/nishio/Scrapbox ChatGPT Connectorの方針相談2023-03-13](https://scrapbox.io/nishio/Scrapbox ChatGPT Connectorの方針相談2023-03-13) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.