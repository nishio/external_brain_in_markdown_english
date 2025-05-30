---
title: 'VSCode: Solution to "Cannot edit read-only editor'
---

He told me that he had learned C++ in high school with Visual Studio and wanted to create a development environment on his Mac at home for review.
[Building a C++ development environment using only Visual Studio Code | Klein's IT Memorandum [https://klein-itblog.com/mac-cplusplus-development/?fbclid=IwAR29XwpqmTBmCDJXmStbNeo5](https://klein-itblog.com/mac-cplusplus-development/?fbclid=IwAR29XwpqmTBmCDJXmStbNeo5) jCzPlvcxQFj4_9Uki67x2hUwTusB7BKn7Vc]
Visual Studio Code and its extension Code Runner can be used to easily create a development environment.

However, when I try to input data into a program I created using this, I get an error message that says, "Read-only editors cannot edit.
This is because the default configuration works as follows.
- execute a program
- → Display the result in read-only mode

The following two-way exchange is required to run the "program that receives input.
- Receive user keystrokes → input to program
- Program output → display on screen for users to see

This program that receives the user's keystrokes and displays them on the screen is often called a "terminal.

You may see words like stdin, stdout, etc. in your programs.
- This stands for standard input, standard output.
- In Japanese, "standard input" and "standard output
- Reference: [Standard stream - Wikipedia](https://ja.wikipedia.org/wiki/%E6%A8%99%E6%BA%96%E3%82%B9%E3%83%88%E3%83%AA%E3%83%BC%E3%83%A0)

By connecting this to the terminal, two-way communication is possible.
- The terminal receives the user's keystrokes and enters them into the stdin of the program you wrote
- What you output to stdout appears in the terminal

Here's how to set it up: [Cannot edit in read-only editor VS Code - Stack Overflow [https://stackoverflow.com/questions/54856374/cannot-edit-in-read-only-](https://stackoverflow.com/questions/54856374/cannot-edit-in-read-only-) editor-vs-code?fbclid=IwAR1vkc88bCXyukgOmUVtgOXK2tpNe_L_pWEJLywjdwNfA8z0x-9jvcTzIl8]

---
This page is auto-translated from [/nishio/VSCode: "読み取り専用のエディタは編集できません"の解決法](https://scrapbox.io/nishio/VSCode: "読み取り専用のエディタは編集できません"の解決法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.