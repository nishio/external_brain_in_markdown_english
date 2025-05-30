---
title: 'Draft addition to "The Difference Between Named Type Systems and Structural Type Systems"'
---

warp and weft
- At a TypeScript study session, I was told, "I study types at [[Technology Supporting Coding]].
- I checked and found that there is no mention of "the difference between nomenclature type systems and structural type systems" in the technology supporting coding. I would like to add this, but the media makes it difficult to make major additions, so I will place a draft here.
- The subject to be added is Chapter 8, "Type."
    - [[Proposed Technical Additions to Support Coding]]
        - [[True story due to misunderstanding of nomenclatural and structural types]]

rehearsal
![image](https://gyazo.com/df9ab60204aa68fff5318dccb0c6a6da/thumb/1000)
- Just having a row of 0s and 1s in memory does not tell you whether it is an integer or a floating point number.
- Static typing is used to attach information such as "this is an integer" to a variable by declaring it as `int n;` or something like that.
- Dynamic typing attaches the information "this value is an integer" to the value.
    - (Aside: some people think "this is not typing, it should be called dynamic inspection", but I give preference to the terminology that the reader is more likely to see. Reference: [[Dynamic typing is dynamic inspection]])

On p. 129, "Dynamic Typing > Advantages and Disadvantages," I wrote
- > Handling value types in this way allows for flexibility that was not possible with traditional statically typed languages. It is now possible to not determine the type until runtime, or to change the type at runtime. However, this was also a disadvantage. With statically typed languages, types were determined at compile time and type consistency was checked at compile time. Thanks to this type checking, some bugs could be caught before execution. With dynamically typed languages, however, this is no longer possible.

There was a growing need to resolve this disadvantage. This need was particularly strong in JavaScript.
- With the decline of Flash, the need to provide a sophisticated user experience in the browser was solved by JavaScript, and large programs were written in JavaScript.
- Most JavaScript is executed in the browser at the user's fingertips. Therefore, it is more difficult to gather information after the fact to solve problems when they occur, compared to programs that run at the programmer's fingertips. We want to be aware of problems in advance.
- JavaScript, which runs in the browser, is often displayed graphically and accepts input from the user. Users often perform operations that are not expected by the programmer. Also, procedures involving human interaction are difficult to automate for testing.

There are two approaches to eliminate this disadvantage.
- A: Add type information to the existing language in a way that does not affect processing, and use it for static inspection.
- B: Write a program in a statically typed language and convert it to a dynamically typed language

Approach A
- For example, Python, a dynamically typed language, provided type checking as a standard library in 2015. The language itself remains dynamically typed, but type information can be added, and the system warns when there is inconsistent handling of that information.
- In JavaScript, Google Closure Compiler released in 2009 adopted this approach: function argument and return types are declared in the form of comments that do not affect execution as JavaScript. The compiler reads the commented source code and performs type checking.
    - (If I can find out what services Google was using Google Closure Compiler for, I will add it)
        - Gmail, Google Calendar, Google Maps, Google Docs
    - For example, Cybozu's kintone implementation had 100,000 lines of JavaScript code as of 2012. Type checking for this was done using Google Closure Compiler.

B Approach
- Haxe was released in 2005; Dart was released by Google in 2011. TypeScript was released by Microsoft in 2012.
- Many other languages were created in addition to these three, but I will not describe them here.
    - Even the majors Dart and TypeScript have their rankings reversed depending on the statistical method.
        - TIOBE Programming Language Ranking (Search Engine Hits Statistics)
            - As of 2014
                - JavaScript 2%, Dart 0.3%
            - As of 2019
                - JavaScript 3%, Dart 0.5%, TypeScript 0.2%, Haxe % unknown as it is below 50
        - [Statistics by activity on GitHub at](https://www.benfrederickson.com/ranking-programming-languages-by-github-users/)
            - JavaScript 23%, TypeScript 4%, Dart not ranked
        - [Stack Overflow Trends (Statistics on the number of questions on StackOverflow)](https://insights.stackoverflow.com/trends?tags=typescript%2Cdart)
            - ![image](https://gyazo.com/b802e536503898b1cf8f4d767468c63b/thumb/1000)

### "Static typing" is not a monolith
.
The "statically typed" part of "writing a program in a statically typed language and converting it to JavaScript" varies from language to language; Dart was released in 2011 and was re-released in 2018 with a different type mechanism. Also, the term "statically typed" is often associated with "a typing mechanism like Java," but this is not necessarily true.

When I wrote this book in 2014, I could explain it in a simple composition of "dynamic typing v.s. static typing"; as of 2019, we are in a transitional period where concepts that once could be summed up in one word "static typing" are being broken down into finer pieces. There are examples, such as Python, in which a dynamically typed language acquires static type checking after the fact. And within "static typing," a new oppositional construct "nominal v.s. structural" has emerged.
![image](https://gyazo.com/e0eb641c58a9fa6f52db6e11fcbdecb1/thumb/1000)
- (It's not that there were no structural type languages as of 2014, there was OCaml and Scala. But people using OCaml were naturally familiar with the type system of ML languages and did not confuse it with Java; people using Scala were dissatisfied with Java's type system and dared to choose Scala; people using OCaml were not dissatisfied with Java's type system and dared to choose Scala. It was not a situation like today, where a person in a "let's implement a web front-end" situation was faced with Dart and TypeScript and had to choose between the two. It is confusing to equate the type systems of these two languages by calling them "statically typed". The need has arisen to have a vocabulary to talk about them separately).

### Difference between nomenclatural and structural type systems
.

When can type B be used in a context where type A is required?

For example, when can an object of type B be assigned to a variable x of type A?
:

```
A x;
B y = new B();
x = y;  // OK? NG?
```


- (It may be better to limit yourself to user-defined types, since the pre-prepared types in the language may have special rules added, such as implicit type conversion. For example, `double z = 1;` was OK after Dart 2.1, but not before. These differences in behavior are not the main issue here)

In nominal type system languages, types have names. Even if they have exactly the same structure, they are different types if they have different names. In the following code, T1 and T2 have exactly the same structure, but an error occurs when assigning them.

Dart

```
class T1 {
  num x;
}

class T2 {
  num x;
}

void main() {
  T1 a;
  T2 b = new T2();
  a = b;  // ERROR: A value of type 'T2' can't be assigned to a variable of type 'T1'.
}
```


In this type system, by explicitly declaring that type T2 is a subtype of type T1, it is possible to use T2 in contexts where T1 is required. In the code below, extends is the declaration of the subtype.
Dart

```
class T1 {
  num x;
}

class T2 extends T1{ // explicitly declared "T2 is a subtype of T1
  num x;
}

void main() {
  T1 a;
  T2 b = new T2();
  a = b; // now OK
}

```


On the other hand, in languages with a structural type system, types are judged by the structure they have. Types do not necessarily have names, and even if they have different names, they are treated as compatible if they have the same structure.

TypeScript

```
type T1 = {
    x : number
}

type T2 = {
    x : number
}

let a:T1;
let b:T2 = {x: 1};
a = b; // OK
```


The `{x: 1}` part of `let b:T2 = {x: 1}` in this code is an unnamed object type.
This has the same form as both T1 and T2, so it can be substituted without error.

C++, born in 1985, and Java, born in 1995, used a nominal type system. These two languages became so major that many people are familiar with declaring partial type relationships with `extends` and `implements`. On the other hand, structural type systems were more mainstream in type theory research. As a result, when designing statically typed languages to generate JavaScript, there was a mix of languages that adopted the nominal type system with reference to Java and other languages that adopted the structural type system with reference to type theory.

- (The nominal type system had the advantage of a light process for determining whether a type was a subtype or not. However, 25 years have passed since the birth of Java, and the performance of computers has greatly advanced, so this may not be a reason for choosing the nominal type system. Rather, it is probably due to the historical background that there are many people who are familiar with Java).
    - (This area is not very definitive, so we may as well cut it down.)

- (Java adopted the generic (generic type) feature in 2004. (Java adopted generic types in 2004. This is the direction in which Java, which used to be a nametype type, is now moving toward a hybrid with structural types, but whether or not to devote a page to explaining this is a matter for discussion).


- [[Difference between a nomenclature-type system and a structural-type system.]]
---
This page is auto-translated from [/nishio/「名前的型システムと構造的型システムの違い」加筆案](https://scrapbox.io/nishio/「名前的型システムと構造的型システムの違い」加筆案) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.