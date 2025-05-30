---
title: "Scratch"
---

Let's try Scratch for a bit during lunch break. I've touched some of the derivatives and old stuff, but after thinking about it, I realized that I don't know the latest version of the original.

I guess I can create an account here: [https://scratch.mit.edu/](https://scratch.mit.edu/)

Make a list
- We found that there is a per-sprite scope and a global scope outside of it.
- ![image](https://gyazo.com/91640da3d32314448ea3a93b30daece5/thumb/1000)

Stack machines were built.
- ![image](https://gyazo.com/ad3f12799bbb97c41bd08ab177eb0241/thumb/1000)

I recognized from an article on the net that you can define functions, but I wonder if you can only define procedures that do not return values...
- > abee2: User-defined blocks have arguments but no return value (that's why they are procedures, not functions). Built-in functions (rounded reporter blocks at both ends, pointed boolean blocks) have return values. It is said to be one of the seven wonders of Scratch that people have been pointing it out all along but it has never been introduced. [Twitter](https://twitter.com/abee2/status/1371293853358039040)
- [[Snap!]]

Messages can be sent and received, but messages don't seem to have arguments.
- Is it possible to put the parameters in a shared space and use messages only for notifications?
- I was thinking of dinging the push/pop out of the stack, but I'm not particularly happy with this method.

Can't you put whitespace in literals?
- It didn't, on the contrary, I mistook the variable for a literal variable name.
- ![image](https://gyazo.com/f9b0f4cfa373a896572dc4d83a8c710e/thumb/1000)
- Putting variable names as literals in places where they should be put, resulting in expressions that are always false.

I've put the list in length of x. The same name but red block to get the length of the list.
- ![image](https://gyazo.com/b4d5fafffcdedff2640532a1e1735762/thumb/1000)
- If you pass a list to a function that returns the length of a string, it will return "the length of the stringified item".


String can now be parsed and added/subtracted, a subset of FORTH.
- ![image](https://gyazo.com/9ce2efabcbfb529cb64e3d33d048d7a3/thumb/1000)

A function that returns a value can be realized by preparing a variable that holds the value.
- ![image](https://gyazo.com/75c6b2394566896c89bac4dc6ee1d2ca/thumb/1000)

We can do a roundabout way lol.
- ![image](https://gyazo.com/005e0b80cc9db1bde4e11f0fa63725dd/thumb/1000)
- No, wait, you made nx or something else a global variable because you can't use local variables, so it gets overwritten during other calls.

Since there is no local variable, it is not possible to "put the return value in another variable immediately after the function call", so I decided to put the return value on the stack and retrieve it when I need it.
- ![image](https://gyazo.com/83eb45f492c9a69c958c7e4095c8c550/thumb/1000)
- I wanted a step execution and watch expression (see below).
    - I forgot that "the last execution result is on the stack top" and reversed nx and nz, resulting in a non-stopping function.

I'm wondering if there is a way to make a block like a partial application of a function, since there is no local variable, or more precisely, "no new assignment can be made in the block" and the argument is a local variable.
- ![image](https://gyazo.com/d97eef4ac78091828b83b2fb1c65aeba/thumb/1000)
- I could have done it, but.... . w
- I'm not sure which is easier to understand, the method of loading the stack or the method of loading the stack.
- The latter approach can be interpreted as easy because it can be converted mechanically as "every time you bind a value to a new variable, you call a function with that value and all the values needed for execution there and beyond as arguments" (really?).

I would also like to create as many lists of indefinite length as I want in my program, but there are two ways to do that: one is to make it a string, and the other is to create a linked list within a single list.

I wonder if the next assignment is "Given a string consisting of opening and closing brackets. Determine whether the parentheses correspond" and the next one is "Perform a calculation expressed as an S-expression"?

- [[Sending messages to individual sprites in Scratch]]

---
This page is auto-translated from [/nishio/Scratch](https://scrapbox.io/nishio/Scratch) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.