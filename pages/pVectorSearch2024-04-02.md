---
title: "pVectorSearch2024-04-02"
---

Vector search for [/plurality-japanese

prev
- Improvement of [/plurality-japanese/vector-search](https://scrapbox.io/plurality-japanese/vector-search).
    - [[pVecSearch2024-03-22 look back]]

reading
- [/omoikane/Omoikane Embed into other projects](https://scrapbox.io/omoikane/Omoikane Embed into other projects).

`$ git clone https://github.com/nishio/omoikane-embed-core plurality-japanese-embed`

`$ pip install -r requirements.txt`
`ModuleNotFoundError: No module named 'distutils'`
> Ensure distutils is Installed: distutils is included with the standard library for Python versions prior to 3.10. For Python 3.10 and later, distutils has been deprecated and is not included by default. If you're using Python 3.10 or later, consider using setuptools instead for package management and distribution.
Ha, I see.
When I made it, it was 3.10, now it's 3.12.

It worked with various modifications.
- The openai library itself has a different interface in 1.0.
- [https://github.com/nishio/plurality-japanese-embed/commit/9302de05d31c734d2b047d42607206638192bae7](https://github.com/nishio/plurality-japanese-embed/commit/9302de05d31c734d2b047d42607206638192bae7)
- I also reduced it to omoikane-embed-core.

:

```
% python make_vecs_from_json/main.py
processing 769 pages
100%|██████████████████████████| 769/769 [00:05<00:00, 139.02it/s]
total tasks: 7470,  0.0% was cached
processing 7470 tasks in 150 batches
100%|██████████████████████████| 150/150 [06:29<00:00,  2.60s/it]
```

![image](https://gyazo.com/da4c33d3103a54406c134ebe32bb64be/thumb/1000)

upload
:

```
% python upload_vecs/main.py 
uploading plurality-japanese.pickle
100%|██████████████████████████| 74/74 [00:24<00:00,  3.06it/s]
OK
```

before/after
![image](https://gyazo.com/dcb1513199fa74784453c96692aec52a/thumb/1000)![image](https://gyazo.com/f1a444a10303d546657536e1847c8c99/thumb/1000)

Experiment with blocksize=100
- Developing views in parallel while waiting for results

result
:

```
% python make_vecs_from_json/main.py
processing 769 pages
100%|██████████████████████████| 769/769 [00:03<00:00, 224.82it/s]
total tasks: 19866,  13.4% was cached
processing 17205 tasks in 345 batches
100%|██████████████████████████| 345/345 [12:19<00:00,  2.14s/it]
% python upload_vecs/main.py        
uploading plurality-japanese.pickle
100%|██████████████████████████| 239/239 [01:18<00:00,  3.05it/s]
OK
```

![image](https://gyazo.com/981c5c414d3b13486c9157782bbd9554/thumb/1000)

![image](https://gyazo.com/662cc912e1027805fdf3f25e9d8f09d2/thumb/1000)
About $0.36 for a smaller chunk run.

# view
`% git clone https://github.com/nishio/omoikane-vecsearch plurality-vecsearch-ja`

`% npm install`
- I did audit fix --force and returned it to omoikane-vecsearch.
- `% npm run dev`
    - and make sure you can search properly locally.

`% git remote rename origin upstream`
`% git remote add origin https://github.com/nishio/plurality-vecsearch-ja.git`
`% git branch -M main`
`% git push -u origin main`

Open the Vercel dashboard
![image](https://gyazo.com/1f5d0e71feb72f20c23be48ea2cf03d2/thumb/1000)

I was able to build and deploy, but I don't see the search target project set up.
- [https://plurality-vecsearch-ja.vercel.app/](https://plurality-vecsearch-ja.vercel.app/)
- I think it's supposed to be put in the Vercel environment variable.
- ![image](https://gyazo.com/0193ff3be6131ed5d5346259555e3215/thumb/1000)

before / after
![image](https://gyazo.com/ccba715dbfd382f9a0e661d556b07a09/thumb/1000)![image](https://gyazo.com/7580efcc7f532c7bd99c46670ac371a3/thumb/1000)
after
![image](https://gyazo.com/952990172f413224ca7e7f329219eac6/thumb/1000)
hmm
Well, we can improve this place later.

Release!
- [/plurality-japanese/⿻VecSearchJA](https://scrapbox.io/plurality-japanese/⿻VecSearchJA)

What we did today from [/plurality-japanese/vector-search-improvement
- Create a separate service with only ✅ Japanese language
- Chunk Improvements
    - ✅Include ✅chunks of 100 tokens as well as the 500 tokens that have been used so far.
    - Only ✅1 chunk of hits from 1 page
- Adding Data
    - ✅1: First, this Scrapbox

[Vector search results for "vector search"](https://plurality-vecsearch-ja.vercel.app/result/i1jxgHrJjWN9ASonM2mY)
- "Vector Search" and other matches are also found.

2024-04-04
## Fix issue with GitHub Actions not working
.
> build
> Node.js 16 actions are deprecated. Please update the following actions to use Node.js 20: actions/checkout@v3, actions/setup-python@v4. For more information see: [https://github.blog/changelog/2023-09-22-github-actions-transitioning-from-node-16-to-node-20/.](https://github.blog/changelog/2023-09-22-github-actions-transitioning-from-node-16-to-node-20/.)
[actions/checkout: Action for checking out a repo](https://github.com/actions/checkout)
[actions/setup-python: Set up your GitHub Actions workflow with a specific version of Python](https://github.com/actions/setup-python)

:

```
The conflict is caused by:
    The user requested protobuf==5.26.1
    grpcio-tools 1.62.1 depends on protobuf<5.0dev and >=4.21.6

To fix this you could try to:
1. loosen the range of package versions you've specified
2. remove package versions to allow pip attempt to solve the dependency conflict
```

[diff](https://github.com/nishio/plurality-japanese-embed/commit/2b122239108d8220eca3f768450fe47010223cd4)

- [[push to a branch with a different name]]

![image](https://gyazo.com/7578bc6c498598fb16415cbf4aa82bd3/thumb/1000)

![image](https://gyazo.com/a8c2b43a31c515aa6007d0e09b9af411/thumb/1000)![image](https://gyazo.com/617b9542c44a057e07b0981ac36192c6/thumb/1000)
![image](https://gyazo.com/c97e93de76deefbf8539d2409d7703f7/thumb/1000)

![image](https://gyazo.com/dc258ece7db18a91955ce376400f8321/thumb/1000)


---
This page is auto-translated from [/nishio/pVectorSearch2024-04-02](https://scrapbox.io/nishio/pVectorSearch2024-04-02) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.