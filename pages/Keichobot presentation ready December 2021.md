---
title: "Keichobot presentation ready December 2021"
---

12/2 12:00-13:00

    - [[Hope you're ready for the results briefing.]]
    - [[Eugene Gendlin's Metaphor Concept]]
    - [[It would be good to get organized on the concept of metaphor.]]
    - [[Eugene Gendlin's Metaphor and Nishio's Metaphor]]
- In other words, we used to recognize the metaphor of "catching a big fish under the surface of the water by driving many hooks into it," but that was based on the assumption that we could see the shadow of the fish, and instead, by dividing the sea like a fixed net, we can narrow down the area where "fish are likely to be found in this area.
        - [[Hooks to fish for what has not yet been verbalized.]]
- > I can't pinpoint the part where languageization is facilitated by scooping up fish [src [https://scrapbox.io/nishio/%E6%88%90%E6%9E%9C%E5%A0%B1%E5%91%8A%E4%BC%9A%E3%81%AE%E6%BA%96](https://scrapbox.io/nishio/%E6%88%90%E6%9E%9C%E5%A0%B1%E5%91%8A%E4%BC%9A%E3%81%AE%E6%BA%96) %E5%82%99%E3%81%8C%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%A8%E3%81%84%E3%81%84#619dd397aff09e0000dcc6ec]
    - By setting up a net, "scooping up fish" is facilitated.
    - The question is where to cut out for [[making finite]].
    - [[I want to put Keichobot in context.]]
        - [[I want to put Keichobot in context (with a secondary commentary)]]
        - [[Kozaneba:I want to put Keichobot in context.]]
- Title:
- Keichobot, the title of the page I had given before was "A chatbot that brings out your thoughts", but after digging deeper, I found that users do not want to be "brought out of their thoughts" (I think so, but I am a rare user), but rather "listened to what you have to say". I switched the title based on my hypothesis.
    - The small-start foot-in-the-door is to be able to talk to a chatbot that listens to you when you feel "I'm not ready to talk to [[a flesh-and-blood person]] yet...I don't have it all together..." and as you talk, the fuzziness will take shape and you will be able to "draw out your thoughts" after the fact. As you talk, the fuzziness takes shape, and after the fact, "ideas are drawn out".

Written Information

Groupware facilitates the distribution of words.
⇔Moyamoya that cannot be put into words well will not be circulated until it is put into words.

Putting Moya Moya into words.
Some people find it unskilled.
I want to help you put it into words.
That is good for "teamwork abounding".

One way: Listen to them.
- A refinement of this approach is called "listening" or "coaching."
- Clean Language, a coaching technique
    - Use only the words used by the speaker.
    - I don't take the liberty of changing one word to another.
    - Listeners don't give their opinions, only questions.

Do you think it's expensive? I'd have to take a professionally trained person for two hours to do a job that requires so much concentration for me alone...

Software Listening
Isn't software better at this than humans?

Mimicking the Behavior of a Human Coach in Software
- Quality, of course, goes down.
- Instead, another benefit arises.

Advantages of being software
- I want you to listen to me! You can use it as soon as you feel
    - Unlike a live person, you don't have to make appointments.
- More situations where it can be used.
    - It can be used while taking a walk in the early morning.
    - Can be used while bathing late at night.
- I don't feel "bad for them."
    - There are those who suffer alone, saying things like, "I'm not organized enough yet to get people to listen to me..."
    - It's a real shame that the means to help the situation are not used due to the reticence of "it's bad for the other person".
    - The fact that the other party is not a person has its own advantages.
    - Can be used late at night and early in the morning.

Instead of going on to talk about metaphors here, it's better to talk about mechanisms and specialized modes.
- Metaphors are so abstract that after listening to a short lecture, "it just doesn't add up."
- We should talk about specifics.
- [[I want to lightly organize how Keichobot works.]]
- [[It would be good to have an organized explanation of the special mode.]]

Extract key phrases (one word or a series of words that make up a block of meaning) from the user's input
Determine which are the key phrases to dig into most now
Generate a response by fitting it into a question template

Enclosed phrase

While using Yahoo's keyphrase extraction API for basic noun keywords, Perceptron and rule-based extraction is used for verb phrases that are insufficient for basic noun phrases.

Strictly speaking, a score is assigned to "a combination of a question template and a key phrase" and the highest scoring combination is selected.
The number of key phrases used varies from 0 to 2 depending on the question template
It's not the same as "asking a randomly chosen question for a randomly chosen key phrase," which is often misunderstood, but we don't use random numbers.
There is an internal state transition diagram, with different candidate questions used in each state. For example, a question asking about the relationship between two things is only asked after the individual key phrases have been fully explored.

Basically, a scoring system that says "key phrases that appear repeatedly in a conversation are likely to be important


Keichobot can be used for any purpose (general purpose mode)
For those who are unfamiliar with the system, "You are free to use it however you want" may be too much of a challenge.
So we created a mode dedicated to a specific purpose.
- Writing support mode
- Reflection support mode
- Proposal support mode for making

- [[Reflection support mode]]


General-purpose mode for any purpose
Maybe it's hard for the uninitiated to do if it's "you're free to use it how you want"?
There are three.

KPT mode
What is [[KPT]]?

What is KPT: A framework for organizing thoughts when reflecting
Write down good things (Keep), bad things (Problem), and things you want to try (Try)

The framework is a one-way street where humans only fill in the blanks, but when combined with Keichobot, it asks questions about what the user has written.
The user may answer the question or ignore it and enter the next item

Become a "framework that listens back."


Template-based methods are often rewritten in the form of questions, so if you put a template in the form of a question on the Keichobot system, you get a "template that listens back."

framework
Ordinary templates are one-way, but Keichobot asks questions about what the user has written. The user can answer the question or ignore it and enter the next item.

Nishio, who is already accustomed to using the generic mode, cannot make a judgment, so please try it and give me your feedback, positive or negative!

---
When you talk about it as a story, there are leaps and bounds, so fill in the blanks there.
- We need to put the mumbo jumbo into words.


---
This page is auto-translated from [/nishio/Keichobotプレゼン準備2021年12月](https://scrapbox.io/nishio/Keichobotプレゼン準備2021年12月) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.