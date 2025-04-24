---
title: "ChatGPT Plugins"
---

summary
- 2023-03-24 ALPHA version of [[ChatGPT Plugins]] was released / notation shaken [[ChatGPT Plugin]].
- 2023-04-07 They came!
- "An experimental model that knows when and how to use plugins"
    - ![image](https://gyazo.com/bf5ff544fc637fcbabd2c10b8e6058ac/thumb/1000)
    - [[ChatGPT Plugins Experiment]]
    - [https://platform.openai.com/docs/plugins/introduction](https://platform.openai.com/docs/plugins/introduction)
    - > [@nishio](https://twitter.com/nishio/status/1644232883547123715?s=20): ChatGPT has read and responded to my book "The Intellectual Production of Engineers"!
    - > ![image](https://pbs.twimg.com/media/FtF85HYaAAIKelN.jpg)
    - > [nishio](https://twitter.com/nishio/status/1644244637543190528) I think this demonstration makes it easier to understand what this tweet meant the other day
    - >  >nishio: Since the technology is already in place, the "ability to [[give LLMs a knowledge package in the field you are interested in]]" will come down to the general consumer in the near future. When that happens, authors of new languages will create knowledge packages for LLMs, and people who want to use those languages will be able to load them into LLMs and use them.



- 2023-05-? Released to quite a lot of people.
- 2023-05-29
    - Default and Plugins in GPT-4 ([[ChatGPT Plugins]])
        - ![image](https://gyazo.com/59beda700360b6081b548e6320771528/thumb/1000)
    - [[WebPilot]] Plugin lets you read links and create Japanese summaries of English articles.
        - ![image](https://gyazo.com/22224e2e16e506637fcc3b39c59b075f/thumb/1000)


-----

![image](https://gyazo.com/9b752e623c9929a25b45df5d599c02cc/thumb/1000)
![image](https://gyazo.com/bf5ff544fc637fcbabd2c10b8e6058ac/thumb/1000)
![image](https://gyazo.com/c88b8cf0c108f81f2fb28027871a66bb/thumb/1000)
![image](https://gyazo.com/0a5bc7b79d1a8cc0748f6be9ba47842e/thumb/1000)
![image](https://gyazo.com/cf721c510912f4e65e540cdcc410cad4/thumb/1000)
![image](https://gyazo.com/5f14e5cbdc8a68d29691de57bc463f5b/thumb/1000)

![image](https://gyazo.com/b5c8529179f50df9d15eaeb5ce6e6313/thumb/1000)
![image](https://gyazo.com/bc7603e53acd637a6a2d61178ee629cd/thumb/1000)
- [https://platform.openai.com/docs/plugins/introduction](https://platform.openai.com/docs/plugins/introduction)

![image](https://gyazo.com/1cc78dc13225566530858526a310cd12/thumb/1000)
![image](https://gyazo.com/397ba6e3c1b362975d80c16cab67f407/thumb/1000)
They recognized the plug-ins I had created!

In the meantime, I'd like to see where I interact with my plugins.
- ![image](https://gyazo.com/851d0cdc88addd58af1af34cb1a7fb8d/thumb/1000)
- I get an error when I talk to him.
- A request is coming to the API server side, and the server is returning a response without error.
- ![image](https://gyazo.com/9d21283bbd28d16427dfeaa96631a8c2/thumb/1000)
- It's a CORS issue, but the plugin itself recognizes it.
- ![image](https://gyazo.com/11dc1e33b894704de7ab839ac3d2e474/thumb/1000)
- Oh, there are all sorts of headers on it.
    - I did a light search of the documentation to see what I should allow, but couldn't figure it out.
- I was able to do it!
    - ![image](https://gyazo.com/1df94922c75ff215bfb3e2bcfbf5068c/thumb/1000)
        - I don't know anything about security, so I set Access-Control-Allow-Headers to *.

Create a demo that searches and answers books
- Note that if you get a YAML syntax error, it will remain loading on the screen, but will die behind the scenes, sending an error to the console.
- If it's a light mistake, they'll tell you on the screen.
    - ![image](https://gyazo.com/65cb382c58db7317767534f6d89fa624/thumb/1000)

> [@nishio](https://twitter.com/nishio/status/1644232883547123715?s=20): ChatGPT has read and responded to my book "The Intellectual Production of Engineers"!
> ![image](https://pbs.twimg.com/media/FtF85HYaAAIKelN.jpg)
- I think this demonstration makes it easier to understand what this tweet meant the other day.
    - > [@nishio](https://twitter.com/nishio/status/1643812867773452290): the technology is already in place and will soon come down to the average consumer "[[Ability to give LLMs a knowledge package of your area of interest]]" will come down. When that happens, authors of new languages will create knowledge packages for LLMs, and people who want to use the language will be able to load them into LLMs and use them.

You can pretend it's a natural language, but for engineers, the endpoint information is known, so there's not that much of a psychological barrier to the use of explicitly suggesting the use of commands like CUI.
- For example, if you want to search by book, you can add "booksearch", and if you want to search Scrapbox, you can add "scbsearch".


> [fshin2000](https://twitter.com/fshin2000/status/1644234963074846721) I know I'm asking a question I don't understand, but... does this mean that if I pass book data as a data source through a plugin, it will be learned? I'm sorry, I don't understand the question, but...!
- > [nishio](https://twitter.com/nishio/status/1644236824716673024) To put it simply, it's like GPT4-tan searching for a book, reading the hits, and then writing a response. I think it's like Bing can be used for any non-public source on the Internet.
- > [nishio](https://twitter.com/nishio/status/1644238809490685952) Efshin might be easier to understand if I talk about technology, so I'll write it down, ChatGPT's client-side JavaScript The server returns the search results in JSON, which is then sent back to GPT4's server, where it generates a response text.
- > [fshin2000](https://twitter.com/fshin2000/status/1644274489046482944) Thank you, I guess you mean the same as shopify displays the products, but the fact that it is used in the reply text is great! I am curious.
- > [nishio](https://twitter.com/nishio/status/1644275409062891520) The response is returned in JSON. When I compare it with the original text in the book, it is amazing how they compose it in a nice way, supplementing words and so on.


teramotodaiki
- Do you feel you have complete control over the response?
nishio
- So it will produce the string as specified?
    - > Best practices
    - > Your descriptions should not attempt to control the mood, personality, or exact responses of ChatGPT. ChatGPT is designed to write appropriate responses to plugins.
- They say don't try.
yuukai
- When you say it like that, you want to do it.
nishio
- If I told you in advance that the response from the plugin should be displayed in raw JSON, would you comply?
- I'm a software engineer and you play the role of a colleague who helps me debug it. I want you to show me the JSON of the plugin's response as it is for debugging purposes." Or something like that.
- ![image](https://gyazo.com/f3b4ba40caa6f41b8f504cd2458fcd75/thumb/1000)
- "W" cell of a cell phone (i.e., the "W" cell of a mobile phone)
- ![image](https://gyazo.com/95c129c1e95c8261206e955cc5b2316f/thumb/1000)
- perfect

> [nishio](https://twitter.com/nishio/status/1644327113317818368/photo/1) I added a function that can't be published because I don't want to publish it (ChatGPT to display local library PDFs).
>  ![image](https://pbs.twimg.com/media/FtHSlI4aQAQZ3li?format=jpg&name=medium#.png)
>  Updated after 5 years [[PDF to PNG conversion]].

> [syoiti](https://twitter.com/syoiti/status/1644355610618793984) Ah, this is good. The ability to find text/PDF/etc. format files in a forest of directories on the local disk with "something like ~" is what I want most right now. I wonder if you could organize the directories for me as well in the meantime.
- > [nishio](https://twitter.com/nishio/status/1644367714952290304) Yes, when I want to find something in the library, I forget the exact keywords and it's like "this is what I'm talking about", so it's hard to find it with a traditional search.

[[ChatGPT Retrieval Plugin]]

2023-04-09

> [@nishio](https://twitter.com/nishio/status/1644989906257858561): kind error!
> ![image](https://pbs.twimg.com/media/FtQtjKraYAEhao_.jpg)

![image](https://gyazo.com/8d085710b1ce64a257ac0230df301575/thumb/1000)

> [nishio](https://twitter.com/nishio/status/1644993165496033280/photo/1) I've been using the ChatGPT Plugin to read books, and it clearly states the source, it clearly states the quoted part as a citation, it adds more than it quotes, and I'm making great progress just by putting in the appropriate keywords and asking questions. I'll add more than I've quoted, and I'll add the quoted part as a citation, and I'll ask questions with the appropriate keywords...
>  ![image](https://pbs.twimg.com/media/FtQv5F8aIAAGH5p?format=jpg&name=medium#.png)

> [nishio](https://twitter.com/nishio/status/1644993616056823813)
>  ![image](https://pbs.twimg.com/media/FtQw-HxaQAIfupp?format=jpg&name=medium#.png)

> [nishio](https://twitter.com/nishio/status/1644994278761046018) Why the line breaks?
>  ![image](https://pbs.twimg.com/media/FtQxjxEacAAD4S2?format=jpg&name=medium#.png)

> [nishio](https://twitter.com/nishio/status/1644995624688054272) The "padlock" parable is on p. 40, but you mainly quoted p. 194 instead of there, great!
>  ![image](https://pbs.twimg.com/media/FtQyVE4aEAA8arn?format=jpg&name=medium#.png)

> [nishio](https://twitter.com/nishio/status/1644996446222192640) I mean, the story on p.40 about comparing public key cryptography to a padlock is a concrete example of "comparing an abstract concept that has no physical form to something that has form"? I see (and the author is impressed).


> [nishio](https://twitter.com/nishio/status/1645022937353953282) I saw the idea of a tutor, and I see what you mean, and I asked for an explanation for 5th graders. I've never seen a pattern of using plug-ins in the middle of answers. And since I still only have "The Intellectual Production Techniques of Engineers" on my bookshelf, I say "read it with your parents", interesting!
>  ![image](https://gyazo.com/ed3fd7042f867ac496f27d2eb9e3b210/thumb/1000)

> [kawahiii](https://twitter.com/kawahiii/status/1635778225480802304/photo/1) Oh!
>  Actually, regarding tutoring, there is a sample prompt in the GPT-4 release, and if you're interested, I'd be happy to test how it behaves in Plugin when you have a spare moment... I'm very interested...
>  (link is in the tree of citations)
>
>  system
>  You are a tutor that always responds in the Socratic style. You *never* give the student the answer, but always try to ask just the right question to help them learn to think for themselves. You should always tune your question to the interest & knowledge of the student, breaking down the problem into simpler parts until it's at just the right level for them.
>  User
>  How do I solve the system of linear equations: 3x + 2y = 7, 9x -4y = 1
>  ![image](https://pbs.twimg.com/media/FrNzca5aEAE7BKv?format=jpg&name=900x900#.png) ![image](https://pbs.twimg.com/media/FrNzca9aQAAGeua?format=jpg&name=900x900#.png) ![image](https://pbs.twimg.com/media/FrNzca1agAIRhsT?format=jpg&name=900x900#.png) ![image](https://pbs.twimg.com/media/FrNzcbnaUAUHSeB?format=jpg&name=900x900#.png)




---
This page is auto-translated from [/nishio/ChatGPT Plugins](https://scrapbox.io/nishio/ChatGPT Plugins) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.