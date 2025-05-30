---
title: "Chat UI is effective when the user does not recognize the object"
---

Hypothesis that chat UI is more effective than object-based UI when the user is not aware of the object

> [tkgshn](https://twitter.com/tkgshn/status/1347953146203570176): Object oriented is effective when "the user knows what he/she wants to do", but "procedural" is more effective when "the user cannot perceive the objects in the first place or does not know how they work even if they are just put together", isn't it? However, if the user cannot perceive the objects in the first place, or does not know how they work even if they are just lined up, then "procedural" may be more effective, right? This hypothesis was the starting point for the conception of [[Civichat]], a [[Chat UI]].
- ![image](https://gyazo.com/bc2f05d1dfd516c43404315c30f5202a/thumb/1000)
    - > [tkgshn](https://twitter.com/tkgshn/status/1347955199357243392): image taken from. [sociomedia | OOUI's Eyes on You](https://www.sociomedia.co.jp/8740).
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Supplement: aufheben for [[OOUI]]'s criticism of "task-based UI" (procedural UI)
        - ![image](https://gyazo.com/89c53c2e0fdacb550b2f806b8ae41865/thumb/1000)
- > [tkgshn](https://twitter.com/tkgshn/status/1347954192845979649): "I don't know what to do with nani {noun}, but I want to do 00 {verb}", such scenes are common in the support system.
    - > That is precisely the selective cognitive gap that was the starting point for Civichat, "How do I know what I don't know?" is the origin of the procedural type (CUI, or chat UI in modern times).
- > [tkgshn](https://twitter.com/tkgshn/status/1347956692672077824): I think that the chat UI (procedural type) (which is the drop-off point when chatting is implemented in software to expand the range of cognition) is ideal for "exploration" of public systems that are related to choice disparities and the like. I think it is best suited for "exploration" of public systems where choice disparities, etc. are involved.
- > Therefore, it is essential that the structure is not a normal data structure, but one that can accommodate procedural types as well.
- > [tkgshn](https://twitter.com/tkgshn/status/1348148919088205834): summarized wisdom. A related item,
- > Object-Oriented, [[OOUI]].
- >  Procedural type
- >  ・Natural language
- >  Prolog
- >  Formal Semantics
- >  [[cognitive gap]].
- >  Data Structure
- I think > and other topics are in scope. We are still looking for references in these areas.
    - [https://scrapbox.io/tkgshn/search/page?q=手続き型](https://scrapbox.io/tkgshn/search/page?q=手続き型)
- > [tkgshn](https://twitter.com/tkgshn/status/1348151202064732161): will information architecture deal with the scope of algorithms and data structures? That's a crazy interesting field.

Summary by the person
- [/tkgshn/ The design of the service to find support systems that came out of the Cabinet Secretariat's measures to combat loneliness and isolation is mismanaged](https://scrapbox.io/tkgshn/ The design of the service to find support systems that came out of the Cabinet Secretariat's measures to combat loneliness and isolation is mismanaged).

--the impetus for putting this together.
> [tkgshn](https://twitter.com/tkgshn/status/1455502083193389061): More confirmation of the hypothesis that chat-based UI is effective when the person is not aware of the object itself. twitter.com/hokutoyokoyama...
- > [tkgshn](https://twitter.com/tkgshn/status/1456926479133016068): I had a meeting to touch and talk about it again, so I took note of my findings.
- > This service is lost because the flow of questions is constructed according to "what the person wants to find". Because the user is not directed to what he/she is looking for itself.
    - > [tkgshn](https://twitter.com/tkgshn/status/1456929340462039044): nota's Helpfeel is better for this requirement

- > [tkgshn](https://twitter.com/tkgshn/status/1456926480361947136): On the contrary, our Civichat only listens to the person's information (so it doesn't get lost), searches all available institutions (logical space) from it, and discards is left to the user. This creates a situation where "everything that is displayed is available".
    - > [tkgshn](https://twitter.com/tkgshn/status/1460928884988211201): good explanation by Mr. [/sta/public-systems-matrix](https://scrapbox.io/sta/public-systems-matrix)
    - > [tkgshn](https://twitter.com/tkgshn/status/1460953623161368577): a chatbot is definitely not suitable for this wide range of information (the public system and the QA that would be actively reached are shown in the same context), If it's the latter, I guess I'd better use [[Helpfeel]] or something like that. pic.twitter.com/Kf2dkpkx3y
    - My interpretation:.
        - With OOUI, a list of operation targets is first shown, and the user selects the target, and then a list of possible operations on the target is shown.
        - However, since the object of operation is not in the system, the user must first upload it to the system. Since it is difficult for a person without knowledge to create and upload structured data at hand, the process of building data needs to be interactive step by step, for which a chat UI is suitable.
- > [tkgshn](https://twitter.com/tkgshn/status/1456927317041680388): As for concepts like "chat UI and objects", it is difficult to do modeling without doing OOUI properly, but I am I have implemented it after disclosing all hypotheses on this area, so please include us in the specification meeting so that our twists and turns will not be in vain.
    - refer
        - Referring to the opening tweet here.

> [tkgshn](https://twitter.com/tkgshn/status/1461315311697739778): The Cabinet Secretariat's Office for Loneliness and Isolation Countermeasures recently released a tool (aka "Cabinet Secretariat The data of the "Chatbot" tool (a.k.a. "Cabinet Secretariat Chatbot") was extracted manually and is now available to the public.
> The copyright, etc. was CC BY, so I clearly stated the source of the quote. So there should be no problem.
> github.com/Civichat/notal…

> [tkgshn](https://twitter.com/tkgshn/status/1461318388949549058): totally feeling this right now. twitter.com/kaicho121/stat...
- refer
    - > [kaicho121](https://twitter.com/kaicho121/status/1456393782035828736): Yuiseki wrote: "The more liberal society becomes, the more complex it becomes, and the more unwritten rules such as poly-collections become, the more people with low IQ will fall behind. I wonder how many poly-college liberals actually have a sense of crisis (or even a sense of reality) in their own skin.

> [tkgshn](https://twitter.com/tkgshn/status/1461318516754161667): the support system itself is too complicated twitter.com/yuiseki_/statu...
- refer
    - > [yuiseki_](https://twitter.com/yuiseki_/status/1456257978969911306): My question: "What causes poverty and inequality in developed countries like Japan, not in developing countries like in the Economics of the Poor? What should we do about it? The answer to my question is, "It may be ...... an innate difference in IQ ............? I'm too reluctant to say that. I was too reluctant ...... pic.twitter.com/YtpMR6MfCe
    - > [yuiseki_](https://twitter.com/yuiseki_/status/1456259525627953164): I thought this was pretty important because in developed countries like Japan, it reads as "the more liberal society becomes (e.g., the gender field increases to male, female, other, don't want to answer, etc.) and the more complicated it becomes, the more people with low IQ fall behind. The more complicated the society becomes (e.g., the more gender fields are increased to "male", "female", "other", "don't want to answer", etc.) and the more unwritten rules such as poly-collections are increased, the lower IQ people will drop out, so it is reasonable to be anti-liberal and anti-pollections.
    - > [yuiseki_](https://twitter.com/yuiseki_/status/1456261114707079172): Needless to say, the real world is diverse and complex, and an ideal social system must be able to tolerate that diversity and complexity. But how to deal with the fact that some people cannot keep up with the complexity and fall behind? The role of code (software) is to augment this. I took this to mean that the code (software) is responsible for augmenting the complexity of the social system.

---
This page is auto-translated from [/nishio/ユーザが対象物を認知していないときはチャットUIが有効](https://scrapbox.io/nishio/ユーザが対象物を認知していないときはチャットUIが有効) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.