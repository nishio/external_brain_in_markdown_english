---
title: "Try ✅scrapbox-Duplicator"
---

Try [tkgshn/scrapbox-Duplicator: a tool that automatically "transfers pages" which is troublesome when operating separate private and public projects in Scrapbox](https://github.com/tkgshn/scrapbox-Duplicator)

- [[Create an account for the ✅Scrapbox Bot]]

Deploy Heroku back to [tkgshn/scrapbox-Duplicator [https://github.com/tkgshn/scrapbox-Duplicator](https://github.com/tkgshn/scrapbox-Duplicator)
![image](https://gyazo.com/9971a5dc5b06ebf15343a825af573e6e/thumb/1000)
App name must be unique in the world.

![image](https://gyazo.com/7952649d590a3d4a7a94d1d4df4968a6/thumb/1000)
Put the SID you wrote down earlier here.
In the future, we would like to be flexible with the transfer source project, but well, experiment first.

Create a test page while waiting for deployment.
![image](https://gyazo.com/47223c88ec45cca53dced30c585820f0/thumb/1000)

[/bluemountain-theme/extended script to transfer pages](https://scrapbox.io/bluemountain-theme/extended script to transfer pages).
Oh, this is the type that is loaded on the BODY. I wonder what the upper length limit is.

`$ heroku run -a scrapbox-duplicator-nishio npm run transfer`
:

```
Running npm run transfer on ⬢ scrapbox-duplicator-nishio... up, run.1786 (Free)

> @ transfer /app
> node index.js

(node:21) UnhandledPromiseRejectionWarning: Error: Request failed with status code 403
  ...
```


Hmmm, I'm not sure, so I'll run it locally first.
`$ git clone https://github.com/tkgshn/scrapbox-Duplicator.git`
`$ npm install`
`$ node --trace-warnings index.js`

You've got the csrfToken in the bot account properly, but you're failing on the export request...
Oh, I get it, only the project owner can export Scrapbox.
- ![image](https://gyazo.com/da658fdcb7bc4444f91a10d4534f02ee/thumb/1000)
Hmmm, maybe I'll change it to get the last 100 posts with the [[Page List API]].

No. Imports are only owners, too.
- ![image](https://gyazo.com/5431a68fcc3ec46893e2e62ce30f41dc/thumb/1000)

I could do it if I used my SID.
![image](https://gyazo.com/8ac5358bc01b5918c68e2c8acea5a2dd/thumb/1000)![image](https://gyazo.com/678b95f9af743015291f5aecf2c4683b/thumb/1000)


> @blu3mo: I think if you give the subaccount admin privileges you can export etc!

I see!
![image](https://gyazo.com/28f7262a969ad465b184a30fa8fc838f/thumb/1000)

It's done!
![image](https://gyazo.com/65d6018a839bcb20352309744eb0fedf/thumb/1000)


memo
`waitFor is deprecated and will be removed in a future release. See https://github.com/puppeteer/puppeteer/issues/6214 for details and how to migrate your code.`

---
This page is auto-translated from [/nishio/✅scrapbox-Duplicatorを試す](https://scrapbox.io/nishio/✅scrapbox-Duplicatorを試す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.