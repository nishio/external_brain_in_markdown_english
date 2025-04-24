---
title: "Make it while listening to ChatGPT"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Vercel environment, how to create it?
<img src='https://scrapbox.io/api/pages/nishio-en/ChatGPT/icon' alt='ChatGPT.icon' height="19.5"/>... Create a project
From the Vercel dashboard, create a new project.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>(Oh well, let's see the Vercel dashboard)

![image](https://gyazo.com/4e6eeef706027e08d3beabafc2050d00/thumb/1000)

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is the difference between Next.js and Nuxt.js?
<img src='https://scrapbox.io/api/pages/nishio-en/ChatGPT/icon' alt='ChatGPT.icon' height="19.5"/>Next.js is a React framework and a framework for developing React-based web applications. Nuxt.js, on the other hand, is a Vue.js framework and a framework for developing web applications based on Vue.js.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I created a Next.js project in Vercel and it was created in JavaScript, what if I want to do it in TypeScript?
<img src='https://scrapbox.io/api/pages/nishio-en/ChatGPT/icon' alt='ChatGPT.icon' height="19.5"/>5. convert the code to TypeScript
Finally, the JavaScript files in the project must be converted to TypeScript files. This is done by changing the extension to ".ts" or ".tsx". You will also need to convert the JavaScript types in your code to TypeScript types, if necessary.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Huh?

Erase and rebuild

[https://nextjs.org/docs?utm_source=create-next-app&utm_medium=default-template&utm_campaign=create-next-app](https://nextjs.org/docs?utm_source=create-next-app&utm_medium=default-template&utm_campaign=create-next-app)
`$ npx create-next-app@latest --typescript`

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>No inputs were found.
<img src='https://scrapbox.io/api/pages/nishio-en/ChatGPT/icon' alt='ChatGPT.icon' height="19.5"/>...

[https://stackoverflow.com/questions/41211566/tsconfig-json-buildno-inputs-were-found-in-config-file](https://stackoverflow.com/questions/41211566/tsconfig-json-buildno-inputs-were-found-in-config-file)
> You can also try to restart your code editor. That works well too.
OK

`$ npm run dev`
OK

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I want to create a chat screen-like thing in Vercel, what should I do?
<img src='https://scrapbox.io/api/pages/nishio-en/ChatGPT/icon' alt='ChatGPT.icon' height="19.5"/>
- Selecting a front-end framework
    - First, to build the chat screen, you need to choose a front-end framework to use: React, Vue.js, Angular, etc...
- Select a backend
    - Next, you need to choose a backend for your real-time application; Vercel provides serverless functions that make it easy to build a backend for your real-time application. Serverless functions can use languages such as JavaScript and TypeScript.
- Design the chat screen UI
    - Next, the chat screen UI must be designed. This includes sending and receiving messages, listing messages, and displaying user information.
- Set up real-time communication
    - Real-time applications require that communication take place in real time. This can be done using protocols such as WebSockets. Libraries and frameworks can also be used to implement real-time communication.
- Deploy with Vercel
    - Finally, you need to deploy the front-end and back-end code in Vercel: from the Vercel dashboard, create a project, upload the code and deploy it.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I think you could create a chat screen-like thing in React and call a serverless function in Vercel with a submit button.
<img src='https://scrapbox.io/api/pages/nishio-en/ChatGPT/icon' alt='ChatGPT.icon' height="19.5"/>
Below are the basic steps to implement this feature.
- Create React components
    - First, create a React component to design the chat screen UI, which includes a message list, a message input field, and a send button.
- Create serverless functions
    - Next, create a serverless function in Vercel. This function is used to receive and store messages, and to handle requests and responses.
- Handle form submission events
    - When the submit button is pressed, a form submit event is handled in the React component. Within this event processing, a message is sent to a serverless function.
- Calling serverless functions
    - Within a React component, the fetch function is used to call a serverless function. fetch allows you to send a message to a serverless function. The fetch function can also process the response from the serverless function.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Make a sample code.
<img src='https://scrapbox.io/api/pages/nishio-en/ChatGPT/icon' alt='ChatGPT.icon' height="19.5"/>...

![image](https://gyazo.com/626fdae932fd17bfbeac0b5d52f54024/thumb/1000)

![image](https://gyazo.com/2c644bf92d4416fa0dc3f7734a534aa2/thumb/1000)

Hmmm, I wonder if someone at the level of asking this question, would be able to see the implicit any error and know that it needs to be properly typed.
As for the second error, you said you have id and content as properties when you initialized it with a string to begin with.



---
This page is auto-translated from [/nishio/ChatGPTに聞きながら作る](https://scrapbox.io/nishio/ChatGPTに聞きながら作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.