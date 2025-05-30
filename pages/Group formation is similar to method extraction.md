---
title: "Group formation is similar to method extraction"
---

[/intellitech-en/(5.2.5.4) Group organization is similar to method extraction](https://scrapbox.io/intellitech-en/(5.2.5.4) Group organization is similar to method extraction)
---

Programmers often perform a task called factoring.
Refactoring is the process of changing the structure of the source code without changing the behavior of the program.
Why do it.
That's because refactoring improves "ease of understanding."

Source code is "too much information," and it is necessary to reduce the cognitive cost of human handling of it, and programming languages have produced many tools for this purpose.
So are modules and interfaces. So are the methods introduced here and their predecessors, functions.

For those who have no programming experience, "method" here does not mean a means to an end. It is a set of instructions to the computer. A method has a name.

Method extraction is a type of refactoring.
Lump some related lines of source code into a new method.
The method is then given a "name" that expresses the content of the process.
This is similar to group organization and naming.

Using this analogy.
It is not a good idea to say, "This line is a conditional branch, so let's collect it."
It is also not a good idea to say, "These lines contain variables with the same name, so let's put them together."
It is correct to bundle lines of a program when they are related to each other and represent a single function.

There is no right answer to where to lump them. However, if you group them into good units and give them good names, subsequent programming will be easier. By bundling and naming, a "take" for thinking can be created. Many lines of source code are compressed into a single method name.

By compressing the code more and more in this way,
Humans are now capable of creating large-scale programs.

-----


- [[grouping]] is [method extraction

- [[The Intellectual Production of Engineers Additions]]
#Engineer's Intellectual Production_Additions
It might be better to put it next to "[[Group formation requires a change in thinking]]" on p. 160.

- While writing a program, I came up with a very good example to explain "[[grouping]] and [[nameplate]] in the KJ method" for programmers. When you write a program and then group it into functions, you group "code that is related to each other" in the form of functions and give those functions "names" that express what they do. That is what grouping and naming is all about.
    - In Java and C#, you can use the refactoring function to select a range of methods and extract them.
- That makes it clear that "collecting similarities" is a mistake. It doesn't make sense to collect if statements in the code and say "this is an if statement" and make it a function named "if statement.
- By "naming" a function with multiple lines of code, a series of processes can be "compressed" into a single function name. When the same process is used in multiple places in a program, the name can be used to call the function.
- By giving it a name, a "handle" for thinking is created.
- It is important to give it a good name.
- By compressing the code at the end in this way, it became possible to create large source code programs that could not all be deployed in the brain by a single person.

---
This page is auto-translated from [/nishio/グループ編成はメソッド抽出に似ている](https://scrapbox.io/nishio/グループ編成はメソッド抽出に似ている) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.