---
title: "Law and programming treat undefined behavior differently."
---

[nishio](https://twitter.com/nishio/status/945115004419710976)
    - I was thinking about why [[law]] and [[programming]] have so much in common but seem to be so different, and I realized that there is a difference at the very core.
- In programming, the expression, "Do not do anything undefined" is used to say that "the devil will fly out of your nose if you execute [[undefined]] code.
- Laws, on the other hand, are "you may do undefined things" because they are designed to restrict only where there are hindrances, assuming that humans are free to act in principle. #Undefined behavior
- The more competent programmers are concerned about "what is [[Definition.]]," but they cannot find it by looking at or searching the articles, and eventually they come to a statement that "there is disagreement among legal scholars," which makes them wonder what the heck is going on.
    - If a situation arises where that definition is in question, you can go to court.
- [yoosee](https://twitter.com/yoosee/status/945118542499737600)
    - > I understand this feeling. On the other hand, in the case of a contract, undefined terms are vulnerable, so it is important to define and destroy them as well as possible.
    - In the case of contracts, "destroying vulnerability = restricting the other party's freedom."
    - There is no correct answer as to how much detail to put in the contract depends on how far you want to limit the freedom of the other party.
        - The contract is intended to override the stipulated value as defined in the Civil Code.
        - There is no need to write anything down. When you buy something at a convenience store, you do not sign a sales contract, but a sales contract has occurred.
    - I thought this was the same as "How much test should I write? Write as much as you want to risk.
    - > In practice, rather than binding them completely by contract .... I think it's more of an image of closing leaks so that undefined items are not abused, rather than defining everything strictly.
    - It's like covering only the important parts of the test!
    - > I think we may be similar in the way we leave things to operations and run away when we get in trouble...

[takao](https://www.facebook.com/nishiohirokazu/posts/10214120722668606?comment_id=10214123326853709&comment_tracking=%7B%22tn%22%3A%22R0%22%7D)
- > Because the API specification contains "rules that can be done," when you create a program that can do something, you only need to look up the relevant API, but I guess I'm not good at the image of having to know everything to find out if a thing is not caught by the "rules that can't be done" law. I wondered if it is because I am not very good at it. (I was reading the law, and I thought, "But I can't do that. (It's amazing how secure I feel when I'm reading a law and it says what I want to do after the "however.")
    - The opposite of "what it says you may do" in the program and "what it says you may not do" in the law makes a big difference in the cost of getting to confirm that what you are about to do is OK to do.
        - The cost of knowing that "the law does not prohibit it" is high
        - Is there a better way?

ref. # Commonalities between legal and programming education

---
This page is auto-translated from [/nishio/法律とプログラミングは未定義動作の扱いが異なる](https://scrapbox.io/nishio/法律とプログラミングは未定義動作の扱いが異なる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.