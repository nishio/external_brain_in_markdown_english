---
title: "hosting"
---

[[pRegroup-done-2019]]
- `$ npm run build`
- [Trial and error process of creating a deploy script for a React web app to AWS - Qiita](https://qiita.com/Kazunori-Kimura/items/d006692f6ba38f0a4813)
    - They say you can upload it to AWS S3 and host it on CloudFront.
    - The explanation is about automation, but for now I'd like to do it manually once and then think about it.
- [Hosting static web pages on AWS S3 - Qiita](https://qiita.com/dogwood008/items/a92abae789f4b0466f38)
    - Apparently, CloudFront is not necessary for HTTP.
    - Drag and drop upload to S3
    - I initially uploaded the build directory by itself.
        - The build created by npm run build references something like `/static/foo.js`, so if I open /build/index.html in a browser, loading JS from there fails
        - This is how it works.
:

```
The project was built assuming it is hosted at the server root.
You can control this with the homepage field in your package.json.
For example, add this to build it for GitHub Pages:
 "homepage" : "http://myname.github.io/myapp",
```

    - Place the contents of the build directory in the root of the bucket
        - →I got it.

- [[Automated deployment operations]]
[Let CloudFront reference the contents of a subdirectory path in an S3 bucket - Qiita](https://qiita.com/naoiwata/items/3c6626cbeacbb44d4aa8)

---
This page is auto-translated from [/nishio/ホスティング](https://scrapbox.io/nishio/ホスティング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.