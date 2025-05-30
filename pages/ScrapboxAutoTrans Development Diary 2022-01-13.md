---
title: "ScrapboxAutoTrans Development Diary 2022-01-13"
---

prev  [[ScrapboxAutoTrans Development Diary 2022-01-12]]

I'm sure some of the features would be beneficial to others, but I'm confused when I try to "meet my needs" and "meet the needs of others" at the same time, so I'm going to push forward with my use case first.

In other words, first change the routing part so that only your project is passed through the whitelist, and then use the URL patterns that you are now free to use without worrying about conflicts with other projects, for whatever you want to use.

---
`relatedPages.links2hop[].linksLc`
The contents of the
`relatedPages.links1hop[].titleLc`
may not be included in the
Specifically, if the page is a X→Y→Z link and Y does not exist.

such
- > ![image](https://gyazo.com/403dba866dcebf842d87fcba6fb93720/thumb/1000)

---
I want to rewrite the routing table, but I can't find any configuration files at all? I thought so, but I heard it's a style expressed by the arrangement of files.

The function with the default export is the view, and there are others that are exported with specific names, like getStaticProps.
---
I wonder how to make only a part of a static page dynamic, or how to make the menu only for the administrator.

---
Customized Top Page
- > ![image](https://gyazo.com/6438e371e7b01cb8423bfa790251ff14/thumb/1000)

Ah, the page title will appear, oh well...
The ability to hide code blocks with specific file names and the ability to render without titles would be nice

---
It's done.
> ![image](https://gyazo.com/8189ce957cf5d80098a337d384f40d19/thumb/1000)
The original data is [[INDEX_FOR_VERCEL]].

---
I have a feeling that a lot of interesting things could happen if multiple individual projects with different owners are merged, or if individual projects and open projects (projects that anyone can enter) are merged, but let's not blur the lines and accomplish our own goals first and foremost!

My goal is to "merge a Japanese personal project whose owner is me with an English personal project whose owner is me."
- [/nishio](https://scrapbox.io/nishio)
- [/intellitech-en](https://scrapbox.io/intellitech-en)

I was thinking of separating `/en/{title}` and `/en/{title}`.
- Is it really necessary to sort readers by whether they are Japanese speakers or not?
- How do you know if you are a Japanese speaker in the first place?

![image](https://gyazo.com/d6bf9335203efd3880b84ed7c1a01691/thumb/1000)

- I feel like this is the right thing to do.

---
I don't see any links showing up.
![image](https://gyazo.com/8773a16c6beae7df133ac0a39e2e4527/thumb/1000)
![image](https://gyazo.com/de08b80e7999936b7ce3d3bdd84929ab/thumb/1000)

Should I make it from links1hop?
fixed: [https://github.com/nishio/scrapbox-reader/commit/efbcdf50e15e41a4e6fbd1303863a401f74d6a25](https://github.com/nishio/scrapbox-reader/commit/efbcdf50e15e41a4e6fbd1303863a401f74d6a25)

---
The 2hop link does not connect in these situations (gray is a page that does not exist).
![image](https://gyazo.com/5ce3067b14ff6bb0dfd3edf56c660807/thumb/1000)

---
From a page in EN, click on a link to a page that is not in that project, and the JA page will now appear.
- So here's what I mean.
    - ![image](https://gyazo.com/9241812e18871f937d2632db37e74b7b/thumb/1000)
- However, reload is required after transition
    - Something must be wrong around the cache.
- [https://scrapbox-reader-six.vercel.app/en/Jiro_Kawakita](https://scrapbox-reader-six.vercel.app/en/Jiro_Kawakita)
    - ![image](https://gyazo.com/d5965a3448a5fbac3bb11779f65f8f48/thumb/1000)
- [https://scrapbox-reader-six.vercel.app/en/川喜田_二郎](https://scrapbox-reader-six.vercel.app/en/川喜田_二郎)
    - ![image](https://gyazo.com/3aabffe56e4d3c1337aff6431b14eb3d/thumb/1000)
        - ![image](https://gyazo.com/d9b8628e2daf55c2dbbf28055cb7fdc1/thumb/1000)
            - ![image](https://gyazo.com/511e592b4ce873bfa08034420d952f7c/thumb/1000)

---
> 2hop links are not connected in these situations (gray is a page that does not exist).
>  ![image](https://gyazo.com/5ce3067b14ff6bb0dfd3edf56c660807/thumb/1000)
- Then I thought, if you want JA to be connected, why don't you just make a page with no content? I thought.

before
- ![image](https://gyazo.com/6ea34b61ecec16f65e33eae43fe57ab0/thumb/1000)
do
- ![image](https://gyazo.com/eb7aff0abd31a7de3397a6caf8f8debe/thumb/1000)
after
- ![image](https://gyazo.com/6feeafba7920b550244aa90d0d3aa7a7/thumb/1000)
    - The double 2hop link is a simple bug.
- ![image](https://gyazo.com/8bbb2555e05cc52196682f4c5134dea9/thumb/1000)
    - So an empty page does not generate a 2hop link...
do
- I'll try to make it inside.
- ![image](https://gyazo.com/21fcc56e2dfd63118a2b31ca39fb80ca/thumb/1000)
after
- ![image](https://gyazo.com/e529fb4d4750fdff363b53a594e54ac9/thumb/1000)
    - 2hop linkage occurred.
- ![image](https://gyazo.com/1258baeaec252210c06b100e51c064c8/thumb/1000)
    - For pages that have both English and Japanese versions, both are displayed and the links between the pages are merged.

---
I made it clear which Scrapbox the content came from.
- ![image](https://gyazo.com/8d9ef170c10175410b8e85389620d2d1/thumb/1000)
- When machine translation is done, you can display something like "This is a machine translation of this page in Japanese" here.

---
[/villagepump/2022/01/13](https://scrapbox.io/villagepump/2022/01/13)
- The link feature I added to ScrapboxReader yesterday was buggy in a lot of ways.
- Contents of multiple projects can now be bundled and displayed
- In the case where there is a link from X to Y in project A, but page Y itself does not exist, and project B has page Y, the transition can be made without any particular problem (without being aware of the project boundary).
    - But now there's a bug where you have to reload after the transition.
    - You don't seem to have a good understanding of Vercel's cache area.

I was a little unsure whether to write the development diary in the well or here, but I thought it would be better to write it here without worrying about the volume, and then write a summary in the well at the end of the day.


---
This page is auto-translated from [/nishio/ScrapboxAutoTrans開発日記2022-01-13](https://scrapbox.io/nishio/ScrapboxAutoTrans開発日記2022-01-13) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.