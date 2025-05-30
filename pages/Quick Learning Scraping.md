---
title: "Quick Learning Scraping"
---

- Need to "collect data published on the Web."
- Assumes skilled people who can create things through trial and error.
- Indicates a knowledge pointer

- Separate the "collecting phase" and the "extracting only the necessary data from the collected data" phase.

Gathering phase

- Is the data in the HTML, or does JavaScript download and display the data separately after loading the HTML?
- The latter is an advanced version
- Write how to tell them apart if necessary.

- If the data is in HTML
    - In short, just download the HTML file.
    - Distinguish whether the desired HTML can be obtained by GET or requires POST
    - The former is the beginner level and the latter is the intermediate level.
    - If you copy and paste a URL from one browser to another and the same thing shows up when you stick it in another browser, then GET
        - Oh, and there's another intermediate version that says the page requires a login.
    - if you're a getter
        - Consider using `wget`.
        - Download the root page that can be reached by following N links from the URL specified by `wget -r -l N URL`.
        - For example, if you see [this](https://1000ya.isis.ne.jp/0487.html) and want to save this content at hand
            - Find if there is a page that lists the content you want to see.
                - There was [list](http://1000ya.isis.ne.jp/souran/index.php?vol=102)
            - I think I can get to the content with one link, so `wget -r -l 1 http://1000ya.isis.ne.jp/souran/index.php?vol=102` should do it.

Extraction phase.
    - Cut out by regular expression
        - It is a hand to cut with a regular expression, which is a dead tool, because "HTML written in the same format should have been scraped together".
    - Using BeautifulSoup4 with Python3
        - [Manual](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
        - If the HTML structure is clean, for example, "the body text is contained in a div with id=content," this is a quick and easy way to do it.
        - On the other hand, a page like "div? On the other hand, if the page is like "div?
        - There may be a need for the ability to convert HTML tagged material to plain text.
python

```
import requests
from bs4 import BeautifulSoup
r = requests.get("https://www.crummy.com/software/BeautifulSoup/bs4/doc/")
print(r.content) # The retrieved HTML is displayed
s = BeautifulSoup(r.content, "lxml")
q = s.find(id="quick-start") # Extract items whose id is "quick-start
print(q.find("p"))  # <p>Here’s an HTML document ...
# taking out the first p tag of quickstart.

print(q.find("p").getText())  # Here’s an HTML document ...
# It's plain text with HTML tags stripped out.
```

        - In this explanation, I'm using [requests](http://docs.python-requests.org/en/master/) directly to get to the Internet directly in the program, but it's shorter to save it to a local file and then parse it, which takes less execution time and is also more server-friendly for the other server. friendly to the other server.
    - Using [https://github.com/petitviolet/python-extractcontent](https://github.com/petitviolet/python-extractcontent), a text extraction library
    - Other


Other.
- I don't generally refer to "scraping" in the sense of information gathering, but I note that there are various needs.
    - It's futile to argue about "the definition of the word 'scraping.'"

- The image is displayed in the browser, but the CSS reads it as a background image and I can't save it from right click, can you do something?
    - Just take it from the browser cache.
    - [Retrieve once viewed images, videos and html files from Google Chrome's cache - Lowaivill Tech Blog](http://blog.lowaivill.com/web/google-chrome-cache/)
- Take a screenshot of the entire screen
    - [Chrome is the best way to take screenshots? | Developers.IO](https://dev.classmethod.jp/tool/chrome-de-screen-shot/)

- For dynamic page scraping, basically using browser automation
- There are two ways to use Selenium and, for example, Chrome's Headless mode (no screen).
- The former supports many browsers, while the latter only certain browsers such as Chrome
- In the context of software testing, you would choose the former because you want to support many browsers with a single piece of code, but in the context of scraping, you don't have to.
- [https://qiita.com/tomi_shinwatec/items/a68cf7840c3da002c6e0](https://qiita.com/tomi_shinwatec/items/a68cf7840c3da002c6e0)
#TODO
---
This page is auto-translated from [/nishio/速習スクレイピング](https://scrapbox.io/nishio/速習スクレイピング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.