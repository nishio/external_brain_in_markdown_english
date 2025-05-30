---
title: "Regroup, a tool to support thinking by writing and moving the contents of your mind to organize your thoughts Presentation materials"
---

Regroup, a tool to support thinking by writing and moving the contents of your mind to organize your thoughts Presentation materials
![image](https://gyazo.com/b10cd56fea740d96570e5dfa4b90fd5f/thumb/1000)

![image](https://scrapbox.io/files/60bc70042db18a001f7c101a.png)

![image](https://scrapbox.io/files/60bc701c5640e0001c160b93.png)

![image](https://scrapbox.io/files/60bc7533eed1c9001ccbab7c.png)








Similar existing services
- Miro: Online Shared Whiteboard Service
- Sticky note functionality has also been added.
- Why not just call it Miro?"
- Let's give it a try.

![image](https://gyazo.com/1e51bd941b040f15565a4b6018d2fe2b/thumb/1000)

![image](https://gyazo.com/18a22ff689255775b4b3907aa2358db5/thumb/1000)





## ![image](https://scrapbox.io/files/60bc757f5417fc001c26ce24.png)
## ![image](https://scrapbox.io/files/60bc75b604bffd002346e0dd.png)

![image](https://scrapbox.io/files/60bc76c2680d92001cf112eb.png)

assumption
- Assumed zone of around 100 sticky notes
- You can do about 20 of them, either by sticking sticky notes on a whiteboard or by Miro.
    - But the more sheets, the harder it is to do.
    - Limiting the number of sticky notes limits human potential.
    - Just like doing work on a PC on a smartphone reduces productivity.


What I'm struggling with now (1)
- Can we assume that it's "for one person's use?"
    - The backend is Firestore, so casual collaborative editing is still possible, which is surprisingly convenient.
        - One person can both list on the wide screen of a PC and handwrite on an iPad + Apple Pencil.
        - When you want to show others what you have organized, you can send them the URL and share the latest status.
        - It's not made properly, so if you edit it at the same time, it will be overwritten.
    - The fact that tools that support thinking are supposed to be used by one person may be a captive of the idea that thinking is something to be done by one person.
    - On the other hand, the "make it possible to edit together well" line requires a complete change of the server side to our own implementation, and I'm not sure if I should do that.

What I'm struggling with now (2)
- The current prototype was built while studying React and TypeScript.
- Dirty code, many bugs in minor functions
- Should we rebuild it?
    - Isn't it an escape to think that if you rebuild it, it will be better?
    - Even if you rebuild it, won't it be full of bugs again at the same scale?
---
This page is auto-translated from [/nishio/頭の中身を書き出し動かして考えを整理する思考の支援ツールRegroup 発表資料](https://scrapbox.io/nishio/頭の中身を書き出し動かして考えを整理する思考の支援ツールRegroup 発表資料) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.