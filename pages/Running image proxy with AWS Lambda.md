---
title: "Running image proxy with AWS Lambda"
---

- Consider whether AWS Lambda can run the proxy server written in [[Canvas Pollution Solution Edition]].

The requests don't work in the raw environment, so you need to put them in or rewrite them without using them.
`$ pip3 install requests --target .`

Returning binary data like the image from Lambda requires doing a lot of additional work.
- What a pain in the ass...
- 2020/01/07 I just checked and it looked like I could do a pass-through.
    - [https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-payload-encodings-configure-with-console.html](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-payload-encodings-configure-with-console.html)

- **New feature] Using Amazon API Gateway to control AWS Lambda over HTTPS without SDK ｜ Developers.IO [https://dev.classmethod.jp/cloud/aws/lambda-restful-api-by-](https://dev.classmethod.jp/cloud/aws/lambda-restful-api-by-) using-api-gateway/**
- [loading external modules into lambda | hack notes](https://hacknote.jp/archives/48083/)
- [image - How to return binary data from lambda function in AWS in Python? - Stack Overflow](https://stackoverflow.com/questions/44860486/how-to-return-binary-data-from-lambda-function-in-aws-in-python)

---
This page is auto-translated from [/nishio/AWS Lambdaで画像プロキシを動かす](https://scrapbox.io/nishio/AWS Lambdaで画像プロキシを動かす) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.