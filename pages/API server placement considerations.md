---
title: "API server placement considerations"
---

what is appropriate to do?
- Heroku
    - If you use it infrequently, you can go with the free plan.
        - 1,000 hours per month
        - Sleeps if not used for 30 minutes
    - For $7/month, you'll be up and running all the time.
    - That's what I'm doing for the most part right now.
    - Return time from sleep could be an issue.
    - If the file size is too large, it may not fit in the free range
        - > 500MB storage size for free slots on Heroku
            - [Using python+mecab+ffmpeg on Heroku - Qiita](https://qiita.com/Sashimimochi/items/2da79bda71dfc1b555cd)
    - HTTPS with wildcard certificate
- AWS Lambda
    - I know it's an option, but haven't tried it yet.
    - > MeCab uses native binaries in its code, so if you want to create a Python deployment package, please use the Amazon Linux AMI available at the following link to build an environment equivalent to the Lambda execution environment and create the package on that OS Please create the package on that OS.
        - [Running MeCab with AWS Lambda | Developers.IO](https://dev.classmethod.jp/articles/aws-lambda-with-mecab/)
        - [[[Revision]] Running MeCab with AWS Lambda | Developers.IO []](https://dev.classmethod.jp/articles/improved-aws-lambda-with-mecab/)
- Netlify Function
    - I can't use Python, so it's not suitable for natural language processing.
    - I often use Netlify for static delivery of HTML+JS UI parts, so it would be better if I could consolidate them.
- AWS EC2


---
This page is auto-translated from [/nishio/APIサーバの置き場所考察](https://scrapbox.io/nishio/APIサーバの置き場所考察) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.