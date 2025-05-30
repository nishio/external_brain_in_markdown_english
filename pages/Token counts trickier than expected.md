---
title: "Token counts trickier than expected"
---

> [nishio](https://twitter.com/nishio/status/1641356506296909824) Am I right in understanding that when stream=true in ChatGPT API, we can no longer get information such as the number of tokens consumed, which we can get when stream=false? Is that correct?

> [teramotodaiki](https://twitter.com/teramotodaiki/status/1641417233162465280) Maybe so.
>  This is troubling... from OpenAI's point of view, maybe they want us to "count it ourselves".

> [nishio](https://twitter.com/nishio/status/1641431712331870214) I counted them in tears.
>  ![image](https://pbs.twimg.com/card_img/1641431666811113474/Fo9SzE4D?format=jpg&name=medium#.png)

> [nishio](https://twitter.com/nishio/status/1641437886221516808) I wish they would put it at the end of the stream...

> [nishio](https://twitter.com/nishio/status/1641439360821366785) Oh, you'll mock this up if you deploy to Vercel...

> [nishio](https://twitter.com/nishio/status/1641441384950566916) I'm only using it as an API so it would work on the server side (not sure...

> [nishio](https://twitter.com/nishio/status/1641460004606853120) Ok, I got it, Astro's settings specified to use Vercel's Edge Function, but this seems to be too restrictive to use fs. I guess that means I can't use fs because of the restrictions. I thought, "Why don't I just change to Serverless Function then?

> [nishio](https://twitter.com/nishio/status/1641484059749797889) GPT4 "Serverless Function is AWS Lambda, so it doesn't support streams."
>  I see...

> [techtalkjp](https://twitter.com/techtalkjp/status/1641632088351993856) There was an article just the day before yesterday that said it was addressed.
>  ![image](https://pbs.twimg.com/card_img/1640817875966476291/eJ0x0a_Y?format=jpg&name=medium#.png)

> [nishio](https://twitter.com/nishio/status/1641636218327945216) Thanks! I don't know GPT4 about the day before yesterday, so it's important to have a human tell me!

> [kenn](https://twitter.com/kenn/status/1641643844583452673) Doesn't this mean that it's via Edge, which means it's caught by the 30 second limit instead of 60 seconds? I think it's quite possible to be lazy for 30 seconds or so with the slow response of GPT-4.

> [jrsyo](https://twitter.com/jrsyo/status/1641670036317417473) As for Edge Functions, as long as the initial response is returned within 30 seconds, there is no hard limit on the stream response after that. However, since Serverless Functions are Lambda, it is possible to continue streaming for a certain length of time. However, since Serverless Functions are Lambda, the maximum Lambda execution time will continue to apply even if the same thing is done.

> [jrsyo](https://twitter.com/jrsyo/status/1641670584034816005) It's mentioned in passing around here
>  [https://vercel.com/docs/concepts/functions/edge-functions/limitations#maximum-initial-response-time…](https://vercel.com/docs/concepts/functions/edge-functions/limitations#maximum-initial-response-time…)
>
>  Some examples of use are here
>  ![image](https://pbs.twimg.com/card_img/1641067548702547969/qQBzHK8z?format=jpg&name=medium#.png)
> [https://github.com/Nutlope/twitterbio/blob/main/utils/OpenAIStream.ts](https://github.com/Nutlope/twitterbio/blob/main/utils/OpenAIStream.ts)


---
This page is auto-translated from [/nishio/トークン数カウント思ったより厄介](https://scrapbox.io/nishio/トークン数カウント思ったより厄介) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.