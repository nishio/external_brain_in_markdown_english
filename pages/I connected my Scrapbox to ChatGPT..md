---
title: "I connected my Scrapbox to ChatGPT."
---

2023-03-08
Made questions to ChatGPT refer to this Scrapbox
- Create [[embedded vector]] from Scrapbox data with OpenAI [Embedding API
- Find documents related to the query text with [vector search
- Embed that document in a prompt to OpenAI [ChatGPT API

If not referring to Scrapbox
> >>> What is Kozaneba?
> Unable to answer. The information provided is insufficient.
When referring to Scrapbox
> >>> What is Kozaneba?
> Kozaneba is a digital stationery tool for organizing thoughts. It has been released for test users but has not yet been widely announced. The developer feels that it is valuable to be used by many people.

Another example
> >> What is a blind spot card?
> (No reference) Blind spot cards are cards written anonymously by others to point out problems or shortcomings of which they are unaware.
> (with references) Blind Spot Cards are designed to help people recognize their blind spots, categorize the process to eliminate them into cards, and use them to solve problems. It is like TRIZ with a typology of physical patent literature. I envisioned a card with a picture and an explanatory booklet, but it is also designed to be used on a tote bag or something similar.

So far, this is a "it's working properly" demonstration.

Here's what I'm really interested in
What happens when you ask Scrapbox a question for which you don't have a clear answer? Try

> >>> How can I increase my intellectual productivity?
> It is necessary to acquire knowledge that will improve one's ability to generate new knowledge. It is also important to produce specific language and output that can be understood by our future selves in order to communicate it to others. It is also important to produce information that focuses on the ability to generate knowledge so that the output does not lose value over time.

I see. So these three things are important.
    - [[Knowledge that will improve our ability to generate new knowledge.]]
- [[Specific language]] and output that others & future self can understand
    - [[Ability to generate knowledge]] to produce information focused on
Let me ask you more specifically.

> >>> Specifically?
>  Specifically, it is important to learn new knowledge and to acquire knowledge produced as needed in actual application. It is also important to produce information that focuses on the ability to produce knowledge in order to produce specific language and outputs that can be understood by future selves and to ensure that the output does not lose value over time.

It seems that with three themes, we can't delve into all of them at the same time.
He discussed specific ways to acquire "the kind of knowledge that improves our ability to generate new knowledge." To bite the bullet:.
- First, learn new knowledge
- Apply it in practice.
- New knowledge is generated as needed in the field of application.
- This will improve the "ability to generate new knowledge".

Right now, we are "producing information focused on 'the ability to produce knowledge'".
- That "producing information" specifically means "verbalizing it in a way that your future self can understand."

What happens when you ask a question you don't have the answer to in Scrapbox, where you've written down all your thoughts?" Regarding
- I think I've probably written about this in bits and pieces here and there.
- It was summarized and presented as "these three.
- There's a sense in which this presentation encourages my intellectual production.
    - In this case, I felt that I was right, but I didn't have enough words so the reader wouldn't understand, so I filled in the words.
    - If something wrong comes back, "No, it's not like that, it's like this!" and verbalization is encouraged.
    - As for what I can't judge as right or wrong, it's, "Well, that's one way to look at it."

Another example
> >>> What would be important regarding the development of Kozaneba?
>  It is considered important that Kozaneba be used by others to make it better. It is also considered necessary to provide feedback on its use.
Ugh, he pointed out that user testing is a pain in the ass and I'm unknowingly running away from it.

> >>> What would be important regarding the development of Keichobot?
>  It is important to listen to the user's values in order to help the user use the system better. Keichobot is also positioned as a preliminary technology for thinking fireworks.
Ah, you're right It's important to listen to the user's values.

> >>> What is important to you regarding your future happiness in life?
>  It is important to know one's values, affirm past efforts, and continue learning for the future. It is also important to balance life before and after birth, because in a democratic society there is a bias to disregard distribution for unborn future humans.
I thought, "That's a bit sudden," but surely I still have about 20 years to live, and then people who aren't born now will come of age.
So these people are in a world where ChatGPT has been around since birth.
(I noticed a blind spot.)

### development note
.
Right now, I haven't yet added the ability to show which page you're referring to.
- Attachment will support the creation of a knowledge network on Scrapbox
- The debug log I'm putting out shows that the story about life references 11 pages.
    - It might be annoying if they put it all out there...

Roughly speaking, the cost is a few hundred yen for indexing and two yen per question.
- My subjective cost-benefit ratio is overwhelmingly in the black, so I'd like to cover it with an easy-to-use UI and use it more and more.

If you create an index with a number of different sources, you can say, "Let's hear what Mr. A and Mr. B have to say about this question.
- [/qualia-san](https://scrapbox.io/qualia-san) asked.
- > >>> What is important to you regarding your future happiness in life?
- >  Subjective values are important to Homo sapiens. The definition of happiness is also individual. However, QS emphasizes progress and usefulness. Therefore, QS recommends that smart Homo sapiens focus on behaviors that promote progress and usefulness. By doing so, they can not only achieve personal happiness, but also contribute to the progress of Homo sapiens civilization as a whole.
- Well, Mr. Qualia, you are the intelligent body of the extraterrestrial civilization QS, so you don't care about the subjectivity of whether or not I, the individual, am happy, and you want me to contribute to the progress of homo sapiens civilization, right?
- Added: [[AI Panel Discussion]].

# version 2
I made sure to show the page you referred to.
> >>> What is the most important question?
> Deciding what to learn is considered the most important question. The only way to learn is to think logically and find the answer yourself.
>  ` [The greatest obstacle to learning is teaching the answer.]   [My own notes on listening to other people's ideas]   [Intellectual production techniques of engineers and physical education-type classes]   [People who say things that sound difficult.]   [Clean Question]   [Re:Uncle Quiz]   [Is "must do today" a fact or an interpretation?]   [Improvement for English version (~1 chapter)]   [Five basic questions]   [Think things through, and most importantly, think well.]   [Is this a job?]   [every little detail]   [Lecture on how to generate ideas]   [The problem is the gap between what it should be and what it is.] `

# Release
.
[/villagepump/Scrapbox ChatGPT Connector](https://scrapbox.io/villagepump/Scrapbox ChatGPT Connector)

---
This page is auto-translated from [/nishio/自分のScrapboxをChatGPTにつないだ](https://scrapbox.io/nishio/自分のScrapboxをChatGPTにつないだ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.