---
title: "WebUI creation work memo day 1"
---

from  [[WebUI creation work memo]]
- `$ npx create-react-app keicho-webclient --template typescript`
    - [[create-react-app]]
    - It seems `--typescript` no longer works.
- There's a new one called [[reportWebVitals]].
- I'll put the routing aside for now and try to make the main screen.
    - If it's App last time, I'll be careful because it got bloated when I went to write it.
- [[Material-UI]]
    - `$ npm install @material-ui/icons`
    - AppBar
        - ![image](https://gyazo.com/62a1e988dfad4221136ab2c511f7c8d1/thumb/1000)

    - [[nisbot]]

    - [[Chat CSS]]
    - [How to display a LINE-like chat screen (conversational style) in an article using HTML and CSS (with 41 Line Stamp illustrations that are really for sale) | Nako's Blog | nako-log](https://nakox.jp/web/coding/chat_line_css)
    - `To import Sass files, you first need to install node-sass`
    - `$ npm install node-sass`
    - `Error: Node Sass version 5.0.0 is incompatible with ^4.0.0.`
    - `$ npm install node-sass@4`
    - ![image](https://gyazo.com/eee5a71e72b876bcd337ef628ebdea3b/thumb/1000)
- ![image](https://gyazo.com/fe2db5ea616df69c9278731d91291575/thumb/1000)
- ![image](https://gyazo.com/935fc3a9900b74d9bfee6f495941bc56/thumb/1000)
- The chat portion was carved into components.
- Consider later: I'm concerned about the different gaps between posts.
- Consider later: only the bot's remarks extend longer than the content.
    - ![image](https://gyazo.com/4afe81b382d97816b4010ebe489a6eb1/thumb/1000)


Put it on Github and deploy with Netlify.
- Just follow the Netlify wizard
- I put a badge on it.
- ![image](https://gyazo.com/a94c447f431e167c874b1fcc8d5f0510/thumb/1000)



What to do next
- When I open it on my phone, I zoom in when the text is small.
    - Fixed.
    - ![image](https://gyazo.com/07cce875ba995cb4ed0d7c3d656f46bf/thumb/1000)
    - I didn't want to stretch only what the bot said, so I stretched it all out.

- Add remarks with line breaks in text area
    - ![image](https://gyazo.com/b217f31537d832458e4216eddfc0b3b1/thumb/1000)
        - word-break: break-all; (since I am a Japanese user)
- Hit the server with a new line in the text area.
    - [[Flask-CORS]]
    - 400 Bad Request -> [[400 Bad Request by hitting Flask from JS]].
- Show response
    - At any rate, I made it return nop and was able to display it successfully.
    - ![image](https://gyazo.com/6fb9804c98e4fdbd44c2ee5ffd949259/thumb/1000)
- Make it so that a new env object is created when the page is opened.
    - Requires env creation API
    - Create a new one and return ID
    - When I tweak a server, I want to try it out locally without deploying it every time.
            - [[Flask to HTTPS]]
        - Wasn't necessary.
- It's working.
    - local
        - ![image](https://gyazo.com/8b13f63872d28ec0d8caa502f21e399b/thumb/1000)
    - server
        - ![image](https://gyazo.com/2703587bc408d7c3c5157aacbee267e7/thumb/1000)
- I've sorted out some of the more subtle expressions like local and server.
    - ![image](https://gyazo.com/032a384998c7547e0048897b9549e552/thumb/1000)
    - The above screener says he tried the TypeScript client both locally and remotely and it worked fine.
    - The latter is accessed from a smartphone, not a development PC.

What to do next
- Allow logs to be displayed
    - Import into Regroup, put on Scrapbox, etc.
- Make it testable
    - Maybe you'll want to tinker with the internals a bit, but tinkering without testing is hell.
        - I want to tinker with it to make it into training data or to import it into Regroup.
- Allow data accumulated in Firebase to be downloaded locally for analysis
- We discussed which one to do.
        - [[Conversation Log 20210120]]
    - Log output in a form that can be imported into Regroup is important.

---
This page is auto-translated from [/nishio/WebUI作成作業メモ1日目](https://scrapbox.io/nishio/WebUI作成作業メモ1日目) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.