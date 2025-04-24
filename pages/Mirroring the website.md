---
title: "Mirroring the website"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>When downloading a site with wget, there is /foo and /foo/bar, and the file is created in /foo, so /foo/bar cannot be saved and an error occurs. Is there any way to work around this?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>WGET alone has limited ability to solve this problem directly. Instead, several different approaches are possible to work around the problem.
- Use another tool: In addition to wget, there are other tools for [[Mirroring the website]], such as httrack or curl. These tools may handle the files in a different way and may avoid the problem.
- Use scripts: Before downloading files using wget, you can write a script that generates a URL list, identifies problem files and directories, and handles them individually....

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What would curl do?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>When using curl, unlike wget, it primarily executes a single HTTP request and either outputs the result to standard output or saves it to a specified file. By default, curl does not have the ability to mirror the structure of a website or recursively download multiple resources. Therefore, it also does not have the ability to directly handle problems where files and directories of the same name exist.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How do I use httrack on my Mac?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>...
`$ brew install httrack`
...

---
[[httrack]]をbrewで入れて使うことにした<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- It served its purpose easily.

I tried the same input on Google, but it didn't tell me httrack (all search results are wget), below are the results of [[SGE]].
![image](https://gyazo.com/1e3a81034430cb0c93636612225f72e4/thumb/1000)

---
This page is auto-translated from [/nishio/ウェブサイトをミラーリング](https://scrapbox.io/nishio/ウェブサイトをミラーリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.