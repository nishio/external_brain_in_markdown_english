---
title: "X API"
---

    - [[X API Rate Limits]]
    - [[X Cost of API]]
- Q: I have an API Key and API Key Secret for the X API, how do I get a Bearer Token?
sh

```
curl -u 'API_KEY:API_KEY_SECRET' \
     --data 'grant_type=client_credentials' \
     'https://api.x.com/oauth2/token'
```



---
This page is auto-translated from [/nishio/X API](https://scrapbox.io/nishio/X API) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.