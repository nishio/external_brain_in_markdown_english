---
title: "TTTC commentary manuscript"
---

from  [[Diary 2024-07-09]]
TTTC commentary manuscript

Technical explanations and source code will be provided.


Talk to the City
NPOs in the U.S.
AI Objectives Institute
It is open source software provided by
The license is the Affero GPL, a strong copyleft. Simply put, what it means is "If you use it, release the source code under the same conditions. So, the source code that we publish in this article will be released under the same conditions.


There are two types of turbo and scatter, but I used Scatter this time.


Trouble building the environment
in advance

Too difficult to build an environment.
Python Version
Python on Windows
To distribute sample data
Git LFS

Thorough LFS usage or not.
We decided not to use it in this use case.



Internal Preview
I didn't notice this when I was trying it out on my own.
Mr. A makes
Share internally and have Mr. B check it out before publishing.
Public work.

It does static rendering, so if you want to preview it on your own
If you want to go public.

The hurdle was that I needed a paid plan to deploy from a private repository on GitHub Pages when I wanted to share privately.


Situations that are not public but can be shown to others
GitHub Pages
Public Repository

Push to GitHub.
Share preview page URL on Slack



Netlify
Continuous deployment from private repositories is a paid functionality, but we were able to run it free of charge because we had a one-month trial period.
![image](https://gyazo.com/eb709c123dce0553a5edd075b60ca72b/thumb/1000)
Oops, that's the end of the day!
![image](https://gyazo.com/60597a606429d82b3549ec66c15a106d/thumb/1000)


[https://gist.github.com/nishio/d4e5d46a54a84bed680713a3d3af1404](https://gist.github.com/nishio/d4e5d46a54a84bed680713a3d3af1404)

![image](https://gyazo.com/f236dd7a42c884c8966e409101c576a8/thumb/1000)



Japanese localization patch
Multilingualized
No ability to default to Japanese (probably)
Worried that people will leave the site if they are asked to switch to Japanese by clicking the language switch button in the upper right corner after the English display.

Whether to go multilingual and make Japanese the default

How to solve this is a vexing problem. The ideal broad listening philosophy, which listens to all people's opinions, would be to accept opinions in all languages and provide translations in all languages. But that would be infinitely costly.
Since this is our first attempt, we decided to provide the service in Japanese only, thinking that we should first experiment with the least expensive method and improve it through repeated experiments, and if so, it would be better not to intervene in the translation process, which would magnify uncertainty.

Japanese translation data for the UI was embedded in the code accordingly.

[Make UI Japanese (for Talk to the City Scatter)](https://gist.github.com/nishio/d943564e36d7891cf4e24604ed27f30a)

---
This page is auto-translated from [/nishio/TTTC解説原稿](https://scrapbox.io/nishio/TTTC解説原稿) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.