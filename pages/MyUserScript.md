---
title: "MyUserScript"
---

> I'm importing from my personal project because I don't want to age the page here due to the self-righteous element of personal customization [/villagepump/kuuote#621e530d4bb2e20000b69a5c](https://scrapbox.io/villagepump/kuuote#621e530d4bb2e20000b69a5c).
- I thought, "Well, that makes sense," so I imitated him.
- At first it was just UserScript, but now CSS has been added, and now it's a set of icons as well, so I don't think the name is appropriate.
- I wonder if renaming won't break links from other projects?

When I had a face icon on "my page," I didn't think much of the fact that every time I edited the code, a big card with my face on it would come up.
- I couldn't verbalize the discomfort, but it was psychological resistance to "something coming up that I didn't want you to see.
- I changed the face icon and it's a little more comfortable.
- As for this project, I pinned it and erased it with CSS.
        - [[Turn off favicon page with CSS]]

for new mypage

```
[https://gyazo.com/33506f42d0d01848cfb88ad9b785ab31]
[/nishio]

code:style.css
  @import "https://scrapbox.io/api/code/nishio/MyUserScript/style.css";
code:script.js
  import '/api/code/nishio/MyUserScript/script.js'
#member
```


---

- [[JS to summarize all pages that can be reached by following links]]
×script.js

```javascript
import '/api/code/nishio/JS/script.js' that summarizes all pages that can be reached by following links
```


[[PomodoroScrapbox]]
×script.js

```javascript
import '/api/code/nishio/PomodoroScrapbox/script.js'
```


[[open with porter]]
×script.js

```javascript
import '/api/code/nishio/open_with_porter/script.js'
```


[[ToMyProj]]
×script.js

```javascript
import('/api/code/nishio/ToMyProj/script.js');
```


[/takker/ PopupMenu to convert selection to Markdown notation and copy to clip board](https://scrapbox.io/takker/ PopupMenu to convert selection to Markdown notation and copy to clip board).
×script.js_disable

```
import("/api/code/takker/%E9%81%B8%E6%8A%9E%E7%AF%84%E5%9B%B2%E3%82%92Markdown%E8%A8%98%E6%B3%95%E3%81%AB%E5%A4%89%E6%8F%9B%E3%81%97%E3%81%A6clip_board%E3%81%ABcopy%E3%81%99%E3%82%8BPopupMenu/script.js");
```


[[AskChatGPT]]
×script_disabled.js

```javascript
import('/api/code/nishio/AskChatGPT/script.js');
```


[[ChatGPTToScrapbox]]
×script.js

```javascript
import('/api/code/nishio/ChatGPTToScrapbox/script.js');
```


2018-09-19 Date and time format to ←.
script.js

```javascript
scrapbox.TimeStamp.removeAllFormats()
scrapbox.TimeStamp.addFormat("YYYY-MM-DD")
```




CSS

imports
- [[indentation]]
style.css_disable

```
@import "https://scrapbox.io/api/code/nishio/%E3%82%A4%E3%83%B3%E3%83%87%E3%83%B3%E3%83%88%E8%A1%A8%E7%A4%BA/style.css";
```


[/noratetsu/● "Display line numbers" improved](https://scrapbox.io/noratetsu/● "Display line numbers" improved).
style.css_disable

```
/* Show line numbers -- applies to windows 768px wide or wider */
@media screen and (min-width: 768px) {
  .editor .lines { counter-reset: line }
  
  /* remove :not(.line-title) when counting from the title */
  .editor .line:not(.line-title) { counter-increment: line }
  
  /* remove :not(.line-title) when counting from the title */
  .app:not(.presentation) .editor .line:not(.line-title)::before { 
    content: counter(line); 
    position: absolute; display: inline-block; left: -110px; z-index: 10; 
    min-width: 50px; text-align: right; vertical-align: middle;
    
    /* Specify line number font, color, etc. here */
    font-family: monospace; color: grey }
  
  /* display the line number of the cursor line darker */
  .editor .line:not(.line-title)::before { opacity: .5 }
  .editor .line.cursor-line:not(.line-title)::before { opacity: 1; font-weight: bolder } }
```


---
This page is auto-translated from [/nishio/MyUserScript](https://scrapbox.io/nishio/MyUserScript) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.