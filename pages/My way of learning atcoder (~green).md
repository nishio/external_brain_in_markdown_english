---
title: "My way of learning atcoder (~green)"
---

Written on 6/25:.
After doing [[atcoder]] for about 5 weeks, I was able to verbalize what kind of learning I am doing, so notes
Let's read it back and tweet it when it turns green.
→Tweeted with tidy additions as it turned green on 7/5.

- Enter the contest first
    - Because learning after testing is better for memory retention. see [[Testing is a means of memory]].
- Write with the intention of explaining to others how you solved it.
    - Because it strengthens my memory and gives me the opportunity to organize and understand better. see [[teach others]].
    - While I was writing the explanation, I thought, "Hey, I thought it was A, but that's not necessarily true, is it?" or "I messed around and finally decided to write AC this way, but looking back, I wonder if this part of the code is not necessary. In retrospect, this part of the code may not be necessary.
- View the official explanation PDF
    - There could have been a better approach to the problems I was able to solve.
        - I can look at it after I solve it once and say, "I see!" I see!
        - Compared to reading a textbook, it has a stronger sense of "self" and is more easily absorbed into the brain.
    - Know the policy for problems you couldn't solve.
        - If you can now say, "I see!" then solve the problem again.
- See the code of strong people
    - Especially when you say, "Hey, the algorithm shouldn't be wrong, but it TLEs.
        - Search for "AC code in Python for that problem," sort by speed, and look from fastest to slowest.
        - Now I've learned how to use [[Numba]].
    - There was one short code search.
        - E of [[ABC171]].
        - I thought, "There must be a more concise way to write."
        - But I haven't done it since, because the code hit me with a golf-like readability dump, and it's hard to read.
    - I'm not aware of the author at first, but as I repeat myself, I notice "someone I've seen a few times".
        - When information is recognized not by itself, but by the "person who created it" behind it, the source of information can expand from there
        - For example, Python's fast code ranking often has maspy
        - I happened to see a blog by maspy, and was glad to find a detailed explanation. It's called "[[Finding quality sources of information]]".
        - This experience creates a learning behavior of "let's see if maspy's blog has written about this".
    - When the code written by others is not clear at a glance
        - Save it locally and use vscode's variable renaming function to rename it to an easier-to-understand name as you read it.
- Refer to others' code for implementation.
    - Don't look and copy, don't look and write.
    - 1: Read it, understand it, and say "I see, that's how you do it", then write it yourself without looking at it.
    - 2: If you can't write it, look at it right away.
    - I'm spinning fast in a little cycle called
    - This is the effect of doing "small tests at the level of a few lines" first, which has the effect of "testing first reinforces memory." see [[Fast test cycles]].
    - For example, when you are writing, you may think, "Huh? Does this subscript need to be -1? Do I need -1 for this subscript or not? I think it's necessary in my opinion" and write it, and then I look at your example and confirm, "Oh, sure, it's -1. Someone else's code says, "Good, good, good! You're headed in the right direction!" The image of a voice saying to you, "You're on the right track! It's easy to stay motivated because the rewards are given in a short period of time.
    - At this time, prepare the variable names and code for your future reading self.
        - Use variable names that are easy for you to understand, not those written by others
        - Change the writing style to one that is easy to understand
            - For example, if I see something written with ternary operators and I think it's hard to understand, I write it with if statements to make it easier for myself to understand.
            - I'd supplement the omitted else clause and add, "In this condition, you don't have to do anything because
        - When your future self thinks, "Oh, isn't this the same problem I solved before?" and reread it, the code should be easy to read.
            - I don't know if there will ever come a time to read it back, but this rewriting process in itself helps me understand it better.


7/6
I've noticed something else since writing the above article.
- [[Verbalization of Awareness]]
- Different people see the same problem statement and start implementing different programs.
    - [[ABC172C]] is a problem set up to take one from each of two mountains A and B.
    - The most naive form is to implement what is written in the problem statement exactly as it is written, but this often TLEs
    - I saw this problem, and I was unconsciously transformed.
        - When I saw someone solving it naively, I realized, "Okay, I was deforming unconsciously.
    - I was curious what caused this unconscious transformation.
        - So I started experimenting with naming the techniques used in the deformation process and making them tags on Scrapbox.
        - In the case of this problem, "[[route-independent]]"
            - A then B, B then A is the same.
            - Then there is no need to distinguish which came first.
                - (As I write this, I noticed that it is related to "[[Unordered columns are multisets]]," and like this, after the fact, "Oh, this and this are related," and a network of knowledge is created in the brain.)
- This is something we've been trying for a while now, so I can't quite explain what the effect is yet, but it feels beneficial.


7/11
- I was solving DP problems [[Educational DP Contest]] without any hesitation, but they were getting harder and harder, and when I saw the sign that said "If you AC all of them, it is equivalent to yellow," I felt I made a mistake in selecting the difficulty level.
- I found that I can see the recommended difficulty level in atcoder problems, so I look at that.
    - easy is indeed easy, moderate is about "easy if you notice it, but it feels difficult because you don't notice it", solving this seems like a good idea.
#atcoder
- [[How engineers learn]]
- [[way of learning]]

---
This page is auto-translated from [/nishio/僕のatcoderの学び方(〜緑)](https://scrapbox.io/nishio/僕のatcoderの学び方(〜緑)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.