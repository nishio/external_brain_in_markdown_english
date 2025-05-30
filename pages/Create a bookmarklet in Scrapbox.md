---
title: "Create a bookmarklet in Scrapbox"
---

- Bookmarklet is a good introduction to programming
    - A little writing would make my daily tasks easier."
- But the strict restrictions make it hard to see what it looks like, an extra cognitive burden.
    - It has to be on one line.
    - Must be URL encoded
- Scrapbox can be used to create bookmarklets with a clean look and feel.
    - Scrapbox has an API that returns the source code in the page
        - Source code written in `https://scrapbox.io/nishio/test_alert` is available at `https://scrapbox.io/api/code/nishio/test_alert/script.js`.
        - Create a bookmarklet that adds a script tag with this URL as src to the body

Code to add a script tag with the specified URL as src to the body
:

```
var url="https://scrapbox.io/api/code/nishio/test_alert/script.js";
var elm=document.createElement('script');
elm.setAttribute('src', url);
document.body.appendChild(elm);
```

A bookmarklet for it.
:

```
javascript: var url="https://scrapbox.io/api/code/nishio/test_alert/script.js"; var elm=document.createElement('script');elm.setAttribute('src', url);document.body.appendChild(elm); 
```


Advantages
- Fast cycle of modification and experimentation
    - The code can be modified while keeping it in a readable form.
    - I don't need to go through the hassle of making a single line or something.
    - No need to edit the bookmarklet.
        - Because the referenced script changes.
        - Because the bookmarklet itself is an instruction to "read the script at this location" and that won't change.
    - Easy to locate errors
        - ![image](https://gyazo.com/5bbf9072ea1c401a0e518318d696bab4/thumb/1000)


demerit
- Some services do not accept this type of bookmarklet
    - Facebook
    - Content Security Policy restricts script loading and does not include Scrapbox in its whitelist.
    - `Refused to load the script 'https://scrapbox.io/api/code/nishio/test_alert/script.js' because it violates the following Content Security Policy directive: "script-src *.facebook.com *.fbcdn.net *.facebook.net *.google-analytics.com *.virtualearth.net *.google.com 127.0.0.1:* *.spotilocal.com:* 'unsafe-inline' 'unsafe-eval' *.atlassolutions.com blob: data: 'self'".`
    - The same goes for Flickr.
    - `Refused to load the script 'https://scrapbox.io/api/code/nishio/test_alert/script.js' because it violates the following Content Security Policy directive: "script-src 'unsafe-eval' 'unsafe-inline' 'nonce-bace3aa55f7817dc19e2c90e7f842c1e' https://*.flickr.com https://s.yimg.com https://cdn.yahooapis.com https://yui-s.yahooapis.com https://de.adserver.yahoo.com https://fc.yahoo.com https://radar.cedexis.com https://*.braintreegateway.com https://*.sandbox.paypal.com https://*.paypal.com https://*.paypalobjects.com".`
    - Since both cases have unsafe-eval, should I just create a bookmarklet that takes it in xhr and then eval it?
        - The part that GETs with xhr is repelled as well.
:

```
var url = "https://scrapbox.io/api/code/nishio/test_alert/script.js";
var oReq = new XMLHttpRequest();
oReq.addEventListener("load", (x)=>{eval(x.target.response));
oReq.open("GET", url);
oReq.send();
```

            - `javascript: var url = "https://scrapbox.io/api/code/nishio/test_alert/script.js";var oReq = new XMLHttpRequest();oReq.addEventListener("load", (x)=>{eval(x.target.response)});oReq.open("GET", url);oReq.send();`


---
This page is auto-translated from [/nishio/Scrapboxでブックマークレットを作る](https://scrapbox.io/nishio/Scrapboxでブックマークレットを作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.