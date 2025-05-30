---
title: "Finding links between multiple projects"
---

2021-05-04
An experiment to pick up keywords from the most recent one-day update in Scrapbox's Project A and present pages containing those keywords from Project B.
- In this case, A is this public project and B is a private project of about 400 pages

If it seems to have a good effect, run it regularly once a day.

context
    - [[Diary of 2021-05-04]]
    - [[About Scrapbox private to public transfer]]

What we did.
- Get ✅public's most recently updated pages
- ✅Extract keywords from its content
    - Just the one that is explicitly bracketed for now.
    - You can get it from the API.
- ✅Find and present ✅from different sources that contain those keywords.
    - There are two ways to search on your own after exporting to JSON or by hitting the search API.
    - This time, the search API
- How to present
    - Create a page in private
        - Because the search results of a private project cannot be made public
    - There is an option to send a DM in Slack.
    - ✅ this time I printed it and pasted it into Scrapbox by hand

result
- (of) good appearance
- I thought it was a private memo repository with not much information, but there were some surprisingly interesting pages.
    - I got some hits from the experiment, like the one where I transcribed a recording of a video conference.
- 105 keywords extracted from 24 hours of activity
- The number of hits found in the search is 11.
    - The search API yields the hit rows.
- There are some not-so-good keywords.
    - Research, Organization, Scrapbox, Unexplored Jr.
    - Too many hits.
    - It is better to display only the information "many hits" if the number of hits exceeds a certain level.
    - In the original project, it is only connected if both pages are bracketed, which is not a large number.
    - Three of the four cases were bracketed.
        - So, if you have a lot of search results, you can only show the number of results instead of the number of results, and bracket that search term instead.
        - Always do search keyword bracketing.
        - Rather, "Is there already a link?" and if so, is it better not to search?

impressions
- relatively good
- There are a number of other projects that seem to have a lot of interesting content dead in the water.
    - I want to have more than one target project.

additional experiment
- I was thinking mainly of my public/private collaboration, so I couldn't publish the results because one of them was private.
- I realized I could do both public.
    - And with the current version, which uses search instead of export, you can target other people's projects without any permission.

- [[interest]] :
- [/rashitamemo/interesting](https://scrapbox.io/rashitamemo/interesting)([query](https://scrapbox.io/rashitamemo/search/page?q=面白さ)): 24 hits
- [[detection]] :
- [/rashitamemo/found](https://scrapbox.io/rashitamemo/found)([query](https://scrapbox.io/rashitamemo/search/page?q=発見)): 88 hits
- [[awareness]] :
- [/rashitamemo/noticed](https://scrapbox.io/rashitamemo/noticed)([query](https://scrapbox.io/rashitamemo/search/page?q=気づき)): 10 hits
- [[spontaneous]] :
- [/rashitamemo/spontaneous](https://scrapbox.io/rashitamemo/spontaneous)([query](https://scrapbox.io/rashitamemo/search/page?q=自発的)): 11 hits
- [[intellectual production]] :
- [/rashitamemo/intellectual-production](https://scrapbox.io/rashitamemo/intellectual-production)([query](https://scrapbox.io/rashitamemo/search/page?q=知的生産)): 100 hits
[[Puppeteer]]:
- [/rashitamemo/Puppeteer](https://scrapbox.io/rashitamemo/Puppeteer)([query](https://scrapbox.io/rashitamemo/search/page?q=Puppeteer)): 1 hits
- [[puppeteer]]:
    - puppeteer
    - [GoogleChrome/puppeteer&#58; Headless Chrome Node API](https://github.com/GoogleChrome/puppeteer)
    - > Puppeteer is a Node library which provides a high-level API to control headless Chrome or Chromium over
    - [[https://codeburst.io/a-guide-to-automating-scraping-the-web-with-javascript-chrome-puppeteer-node-js-b18efb9e9921](https://codeburst.io/a-guide-to-automating-scraping-the-web-with-javascript-chrome-puppeteer-node-js-b18efb9e9921)
    - A Guide to Automating & Scraping the Web with JavaScript (Chrome + Puppeteer + Node JS)]
[[Heroku]]:
- [/rashitamemo/Heroku](https://scrapbox.io/rashitamemo/Heroku)([query](https://scrapbox.io/rashitamemo/search/page?q=Heroku)): 1 hits
- [[TODO.txt]]:
    - [I studied about the task management method "Todo.txt" | Tofu mentality does not collapse](https://wbtmiu.herokuapp.com/2014/09/21/oWpZGaCLPI/)
[[Headless Chrome]]:
- [/rashitamemo/Headless Chrome](https://scrapbox.io/rashitamemo/Headless Chrome)([query [https://scrapbox.io/rashitamemo/search/page?q=Headless](https://scrapbox.io/rashitamemo/search/page?q=Headless) Chrome]): 1 hits
- [[puppeteer]]:
    - [GoogleChrome/puppeteer&#58; Headless Chrome Node API](https://github.com/GoogleChrome/puppeteer)
    - > Puppeteer is a Node library which provides a high-level API to control headless Chrome or Chromium over
    - It can also be configured to use full (non-headless) Chrome or Chromium.
    - It is thought to be a headless Chrome that can be operated from the command line.
    - [[https://codeburst.io/a-guide-to-automating-scraping-the-web-with-javascript-chrome-puppeteer-node-js-b18efb9e9921](https://codeburst.io/a-guide-to-automating-scraping-the-web-with-javascript-chrome-puppeteer-node-js-b18efb9e9921)
    - A Guide to Automating & Scraping the Web with JavaScript (Chrome + Puppeteer + Node JS)]
- [[research]] :
- [/rashitamemo/research](https://scrapbox.io/rashitamemo/research)([query](https://scrapbox.io/rashitamemo/search/page?q=研究)): 100 hits
[[MVP]]:
- [/rashitamemo/MVP](https://scrapbox.io/rashitamemo/MVP)([query](https://scrapbox.io/rashitamemo/search/page?q=MVP)): 1 hits
    - [[Blog 2.0]] :
    - fbclid=IwAR3LXwnspP4W9R79YvAjlC760Q62f_kgBMVpUmRP9WmYok8_xWEMVLkjyZM]
- [[(late Edo-period) culture of debauchery]] :
- [/rashitamemo/tomatology culture](https://scrapbox.io/rashitamemo/tomatology culture)([query](https://scrapbox.io/rashitamemo/search/page?q=豆論文化)): 1 hits
    - [[Kurashita output in April 2021]] :
    - [Sigotano not tasked with bean theory culture!](https://cyblog.jp/43424)
- [[campfire (usually large, and for gathering and singing, etc.)]] :
- [/rashitamemo/campfire](https://scrapbox.io/rashitamemo/campfire)([query](https://scrapbox.io/rashitamemo/search/page?q=キャンプファイヤー)): 1 hits
    - [[June 2019 Idea Line]] :
        - [I want to spread more people to use the most powerful time management technique that saved my life, "Task Shoot Time Technique" - CAMPFIRE (Campfire) [https://camp-fire.jp/projects/view/162572](https://camp-fire.jp/projects/view/162572)
- [[gated community]] :
- [/rashitamemo/gated-community](https://scrapbox.io/rashitamemo/gated-community)([query](https://scrapbox.io/rashitamemo/search/page?q=ゲーテッドコミュニティ)): 3 hits
    - [[gated community]] :
    - gated community
    - > A gated community is a residential area with a gate (gate) and a wall around the perimeter to restrict access to the property by non-residents, thereby preventing through traffic and improving security.
    - The concept of a gated community itself is not new; there have been concessions and U.S. military houses in the past, and it is merely a redefinition of the term. In Japan, it is also referred to as a gated town[[1]] or gated community[[2]]. `
    - [[Walled Garden Model]] :
    - → [[gated community]]
    - [[gated content]] :
    - → [[gated community]]
- [[organization]] :
- [/rashitamemo/organization](https://scrapbox.io/rashitamemo/organization)([query](https://scrapbox.io/rashitamemo/search/page?q=組織)): 84 hits
- [[decline]] :
- [/rashitamemo/decline](https://scrapbox.io/rashitamemo/decline)([query](https://scrapbox.io/rashitamemo/search/page?q=衰退)): 8 hits
- [[elimination]] :
- [/rashitamemo/exclusion](https://scrapbox.io/rashitamemo/exclusion)([query](https://scrapbox.io/rashitamemo/search/page?q=排除)): 14 hits
[[Scrapbox]]:
- [/rashitamemo/Scrapbox](https://scrapbox.io/rashitamemo/Scrapbox)([query](https://scrapbox.io/rashitamemo/search/page?q=Scrapbox)): 100 hits

Updated to account for the case where the output project and the project to be searched are different.
- The `[1]` in the quote from rushitamemo has become a search keyword.
- Should it be `~``? I fixed it by hand for now.`
- The output of a machine should not be fixed by hand and maintained for a long period of time.
    - I'm only doing it now because it's an experiment.
        - It's confusing the links for this project, so I'll eventually kick it out to gist or something.
    - Hopefully, if nothing is done, it will be overwritten after a day and disappear.
    - Any useful links should be noted on a separate page

- [[interest]] :
- [/shokai/interesting](https://scrapbox.io/shokai/interesting)([query](https://scrapbox.io/shokai/search/page?q=面白さ): 1 hits)
- [/shokai/remote-work](https://scrapbox.io/shokai/remote-work):.
    - (Do we need to be funny about how we do things?)
- [[detection]] :
- [/shokai/found](https://scrapbox.io/shokai/found)([query](https://scrapbox.io/shokai/search/page?q=発見): 25 hits)
- [[awareness]] :
- [/shokai/notice](https://scrapbox.io/shokai/notice)([query](https://scrapbox.io/shokai/search/page?q=気づき): 3 hits)
- [/shokai/not a warehouse where dead texts are kept](https://scrapbox.io/shokai/not a warehouse where dead texts are kept):.
    - It's hard to realize, but it's a complete waste of time and effort, because the tedious procedure somehow gives you a sense of doing your job and a mysterious sense of satisfaction.
- [/shokai/tempura-takao](https://scrapbox.io/shokai/tempura-takao):.
    - I noticed that there is also a store in Joynas, Yokohama, and I have been going there about once every two weeks since then.
- [/shokai/Milkcocoa](https://scrapbox.io/shokai/Milkcocoa):
    - I realized that I had no motivation to create libraries for devices I didn't use, and I resolved to only create things I would use from then on.
[[Heroku]]:
- [/shokai/Heroku](https://scrapbox.io/shokai/Heroku)([query](https://scrapbox.io/shokai/search/page?q=Heroku): 39 hits)
[[Headless Chrome]]:
- [/shokai/Headless Chrome](https://scrapbox.io/shokai/Headless Chrome)([query [https://scrapbox.io/shokai/search/page?q=Headless](https://scrapbox.io/shokai/search/page?q=Headless) Chrome]: 1 hits)
- [/shokai/roppongi.js#1](https://scrapbox.io/shokai/roppongi.js#1):
    - Headless Chrome library was created and got 2000stars by [[yujiosaka]].
    - [https://speakerdeck.com/yujiosaka/hetudoresuchromedekurorawozuo-tutahou-falsehua-1](https://speakerdeck.com/yujiosaka/hetudoresuchromedekurorawozuo-tutahou-falsehua-1)
    - [https://github.com/yujiosaka/headless-chrome-crawler](https://github.com/yujiosaka/headless-chrome-crawler)
- [[research]] :
- [/shokai/research](https://scrapbox.io/shokai/research)([query](https://scrapbox.io/shokai/search/page?q=研究): 26 hits)
[[1]]:
- [/shokai/1](https://scrapbox.io/shokai/1)([query](https://scrapbox.io/shokai/search/page?q=1): 100 hits)
[[2]]:
- [/shokai/2](https://scrapbox.io/shokai/2)([query](https://scrapbox.io/shokai/search/page?q=2): 100 hits)
- [[organization]] :
- [/shokai/organization](https://scrapbox.io/shokai/organization)([query](https://scrapbox.io/shokai/search/page?q=組織): 14 hits)
- [[decline]] :
- [/shokai/decline](https://scrapbox.io/shokai/decline)([query](https://scrapbox.io/shokai/search/page?q=衰退): 1 hits)
- [/shokai/Mob Programming](https://scrapbox.io/shokai/Mob Programming):
    - [The decline of management without technology and what to do about it - The Methodologist's Blog](http://simplearchitect.hatenablog.com/entry/2017/06/19/080036)
- [[elimination]] :
- [/shokai/exclusion](https://scrapbox.io/shokai/exclusion)([query](https://scrapbox.io/shokai/search/page?q=排除): 7 hits)
- [/shokai/Internet language can be rough because of the short term nature of the recommendation service](https://scrapbox.io/shokai/Internet language can be rough because of the short term nature of the recommendation service):: [/shokai/Internet language can be rough because of the short term nature of the recommendation service](https://scrapbox.io/shokai/Internet language can be rough because of the short term nature of the recommendation service).
        - [[Eliminate all features that stimulate approval.]]
- [/shokai/eliminate all functions that lead to the stimulation of the need for approval](https://scrapbox.io/shokai/eliminate all functions that lead to the stimulation of the need for approval):.
    - Eliminate all features that stimulate approval.
- [/shokai/wiki never works if you use the URL of the page as an ID](https://scrapbox.io/shokai/wiki never works if you use the URL of the page as an ID):.
    - I want to eliminate all the elements that would spawn a lackey/administrator within WiKi and have to ask before I edit.
- [/shokai/press-release](https://scrapbox.io/shokai/press-release):: [/shokai/press-release
    - This and the idea of [Eliminate all features that stimulate approval.
- [/shokai/I lose my reason when I look at a human face](https://scrapbox.io/shokai/I lose my reason when I look at a human face):.
    - I use Scrapbox to eliminate those elements that are obscured by the appearance of real human faces.
- [/shokai/want to reduce elements that block thinking](https://scrapbox.io/shokai/want to reduce elements that block thinking):: [/shokai/want to reduce elements that block thinking
    - Like most editors, I've eliminated switching between edit and view modes because it's only a brake on my thinking, and if there are other toolbars for text decoration, I spend more time fiddling with the font size than writing text.
    - It is thoroughly eliminated because the time is more and the acceleration is lost.
- [/shokai/media whose memory is reset every time](https://scrapbox.io/shokai/media whose memory is reset every time):: [/shokai/media whose memory is reset every time
    - I especially recommend [[scrapbox]] among the wikis because it allows you to write at the speed you think and eliminates the elements that get in the way of your thinking.
[[Scrapbox]]:
- [/shokai/Scrapbox](https://scrapbox.io/shokai/Scrapbox)([query](https://scrapbox.io/shokai/search/page?q=Scrapbox): 100 hits)
- [[Hatena Diary]] :
- [/shokai/Hatena Diary](https://scrapbox.io/shokai/Hatena Diary)([query](https://scrapbox.io/shokai/search/page?q=はてなダイアリー): 1 hits)
- [/shokai/Internet language can be rough because of the short term nature of the recommendation service](https://scrapbox.io/shokai/Internet language can be rough because of the short term nature of the recommendation service):: [/shokai/Internet language can be rough because of the short term nature of the recommendation service](https://scrapbox.io/shokai/Internet language can be rough because of the short term nature of the recommendation service).
    - I think the exchange of opinions should be done on Hatena Diary or Hatena Blog.
[[dotenv]]:
- [/shokai/dotenv](https://scrapbox.io/shokai/dotenv)([query](https://scrapbox.io/shokai/search/page?q=dotenv): 2 hits)
- [/shokai/dotenv](https://scrapbox.io/shokai/dotenv):
    - dotenv
    - [http://npmjs.org/packages/dotenv](http://npmjs.org/packages/dotenv)
    - Can be loaded with `require('dotenv').load()`.
- [/shokai/dotenvify](https://scrapbox.io/shokai/dotenvify):
    - dotenvify
    - [https://www.npmjs.com/package/dotenvify](https://www.npmjs.com/package/dotenvify)
    - Transform of [[Browserify]] that executes [[dotenv]] just before executing [envify
    - `$ browserify -t dotenvify src/index.js -o build/index.js`
    - When `.env` is missing, [[dotenv]] gives warnings
    - It can be suppressed with the silent option, but dotenvify does not have the ability to pass options to dotenv
    - Added functionality: [https://github.com/shokai/dotenvify/tree/dotenv-options](https://github.com/shokai/dotenvify/tree/dotenv-options)
    - `$ npm i shokai/dotenvify#dotenv-options -save`
    - `$ browserify -t [ dotenvify --silent --path local.env ] src/index.js -o build/index.js`
[[Secure]]:
- [/shokai/Secure](https://scrapbox.io/shokai/Secure)([query](https://scrapbox.io/shokai/search/page?q=Secure): 1 hits)
- [[bookmarklet for pasting pull requests from /shokai/Github to Scrapbox]]:: bookmarklet
    - [Use secure protocol instead of http #79](https://github.com/shokai/tw/pull/79)
        - [[https://github.com/shokai/tw/pull/79](https://github.com/shokai/tw/pull/79) Use secure protocol instead of http by sachin21 · Pull Request
[[HttpOnly]]:
- [/shokai/HttpOnly](https://scrapbox.io/shokai/HttpOnly)([query](https://scrapbox.io/shokai/search/page?q=HttpOnly): 2 hits)
- [/shokai/Heroku to do Socket.IO](https://scrapbox.io/shokai/Heroku to do Socket.IO):.
    - Version=1; Expires=Tue, 15-Nov-2016 11:51:24 GMT; Max-Age=86400; Domain=staging.scrapbox.io; Path=/; HttpOnly
- [/shokai/sticky-session](https://scrapbox.io/shokai/sticky-session):
    - Version=1; Expires=Tue, 15-Nov-2016 11:51:24 GMT; Max-Age=86400; Domain=staging.scrapbox.io; Path=/; HttpOnly
[[requests]]:
- [/shokai/requests](https://scrapbox.io/shokai/requests)([query](https://scrapbox.io/shokai/search/page?q=requests): 1 hits)
- [/shokai/login with Passport to GHE operated with ole SSL certificate](https://scrapbox.io/shokai/login with Passport to GHE operated with ole SSL certificate):: [/shokai/login with Passport to GHE operated with ole SSL certificate](https://scrapbox.io/shokai/login with Passport to GHE operated with ole SSL certificate):: [/shokai/login with Passport to GHE operated with ole SSL certificate
    - [Adding ability to specify an agent for OAuth2 requests by PhilipSkinner · Pull Request #324 · ciaranj

impressions
- It's nice to see other people's presentations on technical keywords that I'm interested in and have written down.
- We all think we are using the same Japanese, but there are differences in the choice of words we use to express our thoughts.
    - In my project, I use the word "exclusion" to refer to the removal of a person from a group of people (this is not my word either, but something I wrote down after seeing other people's expressions).
    - On the other hand, shokai is used to refer to "removing harmful features or functions from software.
    - By comparison [[Notice the difference]].
- If you look at the keywords displayed and tweak the page in various ways, of course it will be an "updated page" tomorrow, and the same thing will be displayed.
    - This must be boring.
    - Remember what you put out once and don't put it out for a week to a month, and so on.

source [https://github.com/nishio/scbot/blob/0.2/scbio.py#L113](https://github.com/nishio/scbot/blob/0.2/scbio.py#L113)

---
This page is auto-translated from [/nishio/複数のプロジェクト間のリンクを見つける](https://scrapbox.io/nishio/複数のプロジェクト間のリンクを見つける) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.