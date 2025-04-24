---
title: "Publication of TTTC results"
---

Github Pages
- [GitHub Pages | Websites for you and your projects, hosted directly from your GitHub repository. Just edit, push, and your changes are live.](https://pages.github.com/)
- Easy if you want the repository to be public, private, you need to pay for it.
- By default, it is assumed that the file is written in Jekyll, so put `.nojekyll` to turn off Jekyll.

Netlify
- [Scale & Ship Faster with a Composable Web Architecture | Netlify](https://www.netlify.com/)
- One way to share privately
- [How to use Talk to the City in the Tokyo Gubernatorial Election 2024｜NISHIO Hirokazu](https://note.com/nishiohirokazu/n/n0661204bda5b)
    - > We developed an internal preview server and hosted it on Netlify, which also offers continuous deployment from private repositories as a paid feature, but we had a one month trial period so we were able to run it for free during the election period.


Amazon S3
- [Amazon S3](https://aws.amazon.com/jp/pm/serv-s3/)
- One way to share privately
- The drawback is that the URL will be something like `http://<bucketname>.s3-website-us-east-1.amazonaws.com/`.
- Used in [[in-house TTTC]].
- Results are assumed to be available only to employees and not to the public.
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>After uploading index.html to S3, perform the following steps to publish it as a static website.
    - Enable bucket static website hosting:.
        - In the S3 console, navigate to the target bucket.
        - Open the "Properties" tab and find the item "Static Website Hosting" and activate it.
        - Specify index.html as the index document.
    - Permission settings:.
        - index.html must be publicly accessible.
        - In the "Permissions" tab of the S3 console, set the bucket policy to allow public access.
        - As an example, add the following policy (replace your-bucket-name with the actual bucket name)
json

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

    - Confirm public URL:.
        - When "Static Website Hosting" is enabled, the specified URL will be displayed.
        - You can access index.html using this URL.
- The HTML site hosted on S3 is now publicly accessible.

[[Talk to the City]]
---
This page is auto-translated from [/nishio/TTTCの結果の公開について](https://scrapbox.io/nishio/TTTCの結果の公開について) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.