---
title: "Organize Twitter in Scrapbox"
---

- [[Twitter]] The discussion above is hard to read, so I'd like to summarize it in Scrapbox.
- We want to make that process of putting it together easy.
    - I tried a bot to put it all together, but it didn't work to my satisfaction.
    - Is it better to run JS in the browser than to do it via API?

How to do it from the Togetter edit screen
- Sorting and removal can be done in a natural UI.
js

```javascript
tweets = document.querySelectorAll('.choices_box li[data-type="tweet"]');
get_name = (tweet) => tweet.querySelector(".user_link .status_name").innerText.substring(1);
remove_mention = (text) => text.replace(/@\w+\s+/g, "");
concat_line = (text) => text.replace(/\n+/g, " ");
text = Array.from(tweets).map(x=> {
    name = get_name(x)
    url = x.querySelector(".link[target='_blank']").href
    body = x.querySelector(".tweet").innerText;
    body = remove_mention(body)
    //body = concat_line(body)
    return `>[${name} ${url}]: ${body}`;
}).join("\n\n")
document.querySelector(".title_input").value = text
```



-----
From Togetter
js

```javascript
tweets = document.getElementsByClassName("list_box type_tweet")
```

js

```javascript
get_name = (tweet) => tweet.querySelector(".user_link .status_name").innerText.substring(1)
// e.g. getName(x) => "nishio"
```

js

```javascript
count = {}
tweets.forEach(x=>{
    name = get_name(x);
    count[name] = (count[name] || 0) + 1;
})
// e.g. {nishio: 26, YukiMihashi: 8, maltonn_: 1, ukkaripon: 3, teramotodaiki: 2, …}
```

js

```javascript
name_or_icon = (name) => name in use_icon ? `[${name}.icon]` : name;
// name_or_icon("nishio")
// "[nishio.icon]"
// name_or_icon("foo")
// "foo"
```

js

```javascript
text = Array.from(tweets).map(x=> {
    name = name_or_icon(getName(x))
    body = x.querySelector(".tweet").innerText;
    return `${name}\n${body}`;
}).join("\n\n")

```

js

```javascript
navigator.clipboard.writeText(text)
// on Devtool: Uncaught (in promise) DOMException: Document is not focused.
```


matome
js

```javascript
tweets = document.getElementsByClassName("list_box type_tweet")
get_name = (tweet) => tweet.querySelector(".user_link .status_name").innerText.substring(1)
count = {}
tweets.forEach(x=>{
  name = get_name(x);
  count[name] = (count[name] || 0) + 1;
})
```

js

```javascript
tweets = document.getElementsByClassName("list_box type_tweet")
get_name = (tweet) => tweet.querySelector(".user_link .status_name").innerText.substring(1)
use_icon = {nishio:0, YukiMihashi:0, ukkaripon:0, teramotodaiki:0}
name_or_icon = (name) => name in use_icon ? `[${name}.icon]` : name;
text = Array.from(tweets).map(x=> {
    name = name_or_icon(get_name(x))
    body = x.querySelector(".tweet").innerText;
    return `${name}\n${body}`;
}).join("\n\n")
document.write(`<textarea>${text}</textarea>`)
```


I heard that iconic notation is not available in Helpfeel, so I guess I'll just have to do it this way for now.
js

```javascript
tweets = document.getElementsByClassName("list_box type_tweet")
get_name = (tweet) => tweet.querySelector(".user_link .status_name").innerText.substring(1)
use_icon = {nishio:0, YukiMihashi:0, ukkaripon:0, teramotodaiki:0, kyasbal_1994: 3, mitoujr: 2, yasulab: 1}
name_or_icon = (name) => name in use_icon ? `[${name}]` : name;
text = Array.from(tweets).map(x=> {
    name = name_or_icon(get_name(x))
    body = x.querySelector(".tweet").innerText;
    return `${name}:\n${body}`;
}).join("\n\n")
document.write(`<textarea>${text}</textarea>`)
```





[[test_fromTogetter]]

---
This page is auto-translated from [/nishio/TwitterをScrapboxにまとめる](https://scrapbox.io/nishio/TwitterをScrapboxにまとめる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.