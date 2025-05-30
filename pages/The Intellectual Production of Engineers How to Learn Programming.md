---
title: "The Intellectual Production of Engineers How to Learn Programming"
---

Some excerpts from the chapter "[Introduction: [https://scrapbox.io/nishio/%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%8B%E3%82%A2%E3%81%AE%E7%9F%A5%E7%9A%84%E7%94%9F%E](https://scrapbox.io/nishio/%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%8B%E3%82%A2%E3%81%AE%E7%9F%A5%E7%9A%84%E7%94%9F%E) 7%94%A3%E8%A1%93_%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB]". Learn more about the book: [The Intellectual Production of Engineers [https://scrapbox.io/nishio/%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%8B%E3%82%A2%E3%81%AE%E7%9F%A5%E7%9A%84%E7%](https://scrapbox.io/nishio/%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%8B%E3%82%A2%E3%81%AE%E7%9F%A5%E7%9A%84%E7%) 94%9F%E7%94%A3%E8%A1%93_%E8%91%97%E8%80%85%E5%85%AC%E5%BC%8F%E3%83%9A%E3%83%BC%E3%82%B8@Scrapbox]

# How to Learn Programming
.

In thinking about the art of intellectual production, it is inevitable to learn about "how to learn". But this is abstract, so let us first think more concretely about how to learn programming. I believe that the process of learning programming is a repetition of the three elements of "information gathering, modeling, and verification.

![image](https://gyazo.com/42ebd9375c1d3ff9ff1bffe69918fad6/thumb/1000)
Figure::Learning is an iterative process of information gathering, modeling, and verification

## First, gather specific information
.

The first step is to gather specific information.

When learning programming, most people first read programs written by others. In addition to reading, "sutra copying," a technique in which the programmer imitates the text, is also often used. This is "concrete information gathering. This book also introduces a number of intellectual production issues and their solutions. This is like sample code for programming.

## abstract and model
.

Once you have gathered concrete information and have the material in your brain, the next step is abstraction. Abstraction is strongly associated with finding common patterns among multiple pieces of concrete information and determining what is important and what is a branch.

Comparing multiple things and finding commonalities can help with abstraction. Let's look at the "code that displays "Hello, world!"" written in the Python programming language.

python: displaying "Hello, world!

```
print("Hello, world!")
```


Output result

```
Hello, world!
```


Even those with no Python experience will notice commonalities when comparing this code with the output results. This is the discovery of a pattern.

python: Patterns you found

```
print("I bet you can see what I wrote here.")
```


If you want to output "Bye, world!" then you know where to rewrite it. In other words, having discovered the pattern, you have the ability to modify the program to suit your own purposes.

The following code is also written in Python and displays "Hello, world! (Note: A person with good intuition might compare code 1 with code 2 and think that the complex code starting with "".join is creating the string "Hello, world! That is correct. That is correct, but this book is not a Python textbook, so I will not explain it in detail.) The following is an example of a Python code that is used in the "Hello, world!

python: Displaying "Hello, world!

```
print("".join(map(chr, [72, 101, 108, 108, 111, 44, 32, 119, 111, 114, 108, 100, 33])))
```


In this book, we hope to help you create your own model of intellectual production by comparing intellectual production techniques.

## Practice and verify
.

Now you have the ability to find a pattern and come up with, "If I want to output "Bye, world!" in Python, why don't I just write it this way?" You now have the ability to come up with "If I want to output "Bye, world!

python: Patterns you found

```
print("I bet you can see what I wrote here.")
```


python: code that would output "Bye, world!

```
print("Bye, world!")
```


However, this is only a hypothesis. Whether the objective of "outputting 'Bye, world!'" can really be achieved in that way cannot be determined without actually trying it out. When you try it, you will find that the objective can be achieved for this specific example.

What if we want to output "Hello, (newline) world!" on multiple lines? If our hypothesis is correct, we should write

python: code that would output "Hello, (newline) world!

```
print("Hello,
world!")
```


If you try it, you will see that this code will result in a syntax error and will not work as expected. This is not a failure. You have discovered specific information that says, "This method does not work. This is a learning opportunity. Why isn't it working the way I want it to?" ─ ─ By thinking this way, you will gain a deeper understanding.

![image](https://gyazo.com/2c0a945150a3de486b822e725d3d5a6d/thumb/1000)
Figure::Found [[gap]] between expectations and reality

In this example, we discovered the fact that when we want to print a line break, simply breaking the line does not work. The next step is to find a solution to this problem. For example, we can use a search engine (note: specifically, we can do a Google search for "Python line feed print"). ), you will find sample code that may contain useful information. The sample code will not directly tell you how to accomplish your goal of printing "Hello, (newline) world! It is probably code that displays something else. However, if you compare this new sample code with the information you have gathered so far, you will find a pattern, and you will generate a new hypothesis: "Well, then, if I implement it this way, it should accomplish my goal.

We gathered specific information, compared and found patterns, practiced and verified, discovered gaps between expectations and reality, and gathered information again. By repeating this cycle, you learn programming skills. By repeating the cycle, you develop the ability to create new programs. The same is true of learning intellectual production skills. You learn by gathering specific information, comparing it to discover patterns, and repeating the process of practicing and verifying.

- [[The Intellectual Production of Engineers Author's official page]]
Next: [[The Intellectual Production of Engineers Flow of this book]].

---
This page is auto-translated from [/nishio/エンジニアの知的生産術 プログラミングはどうやって学ぶか](https://scrapbox.io/nishio/エンジニアの知的生産術 プログラミングはどうやって学ぶか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.