---
title: "Technology Supporting Coding English Checking"
---


- Translator Feedback
- Chaper12
- A2, A3: You are right about the possible page changes, so I will number the sections as well. In that case, the phrase "mentioned in section "6.3.2 Introduction to CLU" would be used.
- A4 "a bit of a mouthful" -> "a bit complex" Let's rewrite this policy
- A5 >S is a subset of T.
    - After rereading it, it looks good without.
- A6: The current translation is fine.
- A7 I don't understand your comment.
- A8 Ibid.
- A9 class itself is fine. it will provide it might be better to say it will provide the answer?
- A10
- > - The “UseInheritance” class inherits from the “Hello” class and has the “hello” method available (❷) which is executed in ❸.
- Let's break this up into sentences.
- > + The “UseInheritance” class inherits from the “Hello” class. So it has the “hello” method as its own method (❷). The mthod is executed in ❸.

- > - On the other hand, the “UseDelegate” method doesn’t inherit from the “Hello” class (❹).
- > + On the other hand, the “UseDelegate” class doesn’t inherit from the “Hello” class (❹).

- > - Instead, it creates an object from the “Hello” class and “delegates” the execution of the “hello” method to the object in ❻.
- > + Instead, it creates an object of the “Hello” class (❺) and “delegates” the execution of the “hello” method to the object in ❻.

A11 overriding is correct.
A16 This is also referred to in section "12.2.2 Multiple Inheritance: Useful for Code Reuse" instead of the page.
A18
- The original text was too casual to translate, sorry. What I wanted to convey here is as follows:.
    - The standard Python library mixes the UDPServer class with the ForkingMixIn class to create a new class before creating an instance.
    - It is clear from the name "MixIn" that ForkingMixIn should not be instantiated by itself.
    - However, it is not clear from the name whether UDPServer is a class that can be instantiated by itself.
    - ForkingMixIn provides a process_request method to UDPServer; does UDPServer need to have process_requests provided by other classes to work as expected, or can it be used on its own?
    - Python has no way to programmatically state what combinations are acceptable to use. So it is possible to create instances of classes that are not combined correctly.
    - Scala traitees have a way to declare "what methods are needed".

chap12 done

Chapter11
- A2 Bjarne Stroustrup's homepage seems to have changed from [http://www2.research.att.com/~bs/homepage.html](http://www2.research.att.com/~bs/homepage.html) to [http://www.stroustrup.com/.](http://www.stroustrup.com/.)
    - The URL for the paper itself is [http://www.stroustrup.com/whatis.pdf.](http://www.stroustrup.com/whatis.pdf.)
- A3 Since we do not know if the number of pages in the Japanese book is the same as the number of pages in the original book, no page numbers are required.
- A7 "a bit of a mouthful" -> "a bit complex" Let's rewrite this policy
- A8 FORTRAN 66 is correct.
- A9
    - Hmmm, I feel a muddled discomfort when I see it in English. I will fix the original.
    - > - The idea here is that a first-class value is not quite limited in terms of how it can be used, just as a “first-class citizen” can receive fair treatment.
    - The expression "first-class" was used to distinguish between "first-class citizens," who are citizens with ordinary rights, and "second-class citizens," who receive inferior treatment, such as not having the right to vote.
    - > + The expression "first-class" was used to distinguish between "first-class citizen" with ordinary right and "second-class citizen" receiving inferior treatment such as not having voting rights.
    - memo
        - [https://en.wiktionary.org/wiki/first-class_citizen](https://en.wiktionary.org/wiki/first-class_citizen)
            - > A member of a class of individuals that receive fair treatment.
            - >  (programming, languages) Synonym of first-class object
        - [https://en.wikipedia.org/wiki/First-class_citizen](https://en.wikipedia.org/wiki/First-class_citizen)
        - The term "first class" could be misinterpreted today as "preferential treatment" because it is thought of like first class on an airplane.
        - On the other hand, the terms "first-class citizen" and "second-class citizen" are not so well recognized today.
            - > Prebs were recognized as second-class citizens in Roman society and were not allowed to be involved in religious ceremonies and government until around the time of the transition to the Republic.
            - [Plebs - Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%97%E3%83%AC%E3%83%96%E3%82%B9)
- A10, A11
    - > While Perl creates a package to implement the counter, JavaScript uses a hash for the same purpose.
    - > Another difference you may notice by looking at the code is the use of “this” as a keyword, which is a reserved word in JavaScript. When a function “my_method” is called in conjunction with an object “obj” (“obj.my_method()”), “this” is used to refer to “obj” within “my_method” itself.
    - > In Perl, we say “my $values = shift” to explicitly extract a parameter, whereas JavaScript obtains the value implicitly with a variable “this”. In the above example, since “this” is used within the function “push” when it’s called with “counter.push()”, “this” refers to “counter”. Therefore, we can replace “this” with “counter” and the program will still work.
    - Looks fine on the refers.
- A12
    - > This way, we can achieve the following:
    - > ...
    - > These aims can be achieved as in Perl’s packages.
    - The logic is not wrong, but the intent of the explanation is to say "the Perl version had these three features, and the code below achieves all of them", which seems twisted.
- A15
    - > We call this association of a value with a name a “(named) binding”. By combining the open function “push” with the scope of “makeCounter”, the program no longer has to look for variable definitions outside of the scope because the function “push” is now a completed whole. We use the term “closed” to describe this state of completeness.
    - It's not wrong in terms of logic, but it's hard to communicate.
    - We will add a figure for this here.

Chaper10
- A7
    - > Another approach is to mark a process that shouldn’t be interrupted during its execution.
    - > For example, we can decide that we mustn’t interrupt a thread that has the value of 0 in its memory.
    - This makes it look like EACH THREAD has a mark, but in fact the THREADS SHARE the MARK. The "share" part of "share a mark" in the original text has disappeared.
    - Also, the value "must not be interrupted" when it is "non-zero". The way it is written now, it would mean the opposite.
    - >  Each thread checks the memory value of a process before its execution;
    - >  the process thread can be executed if the value is 0; if it’s the value is not 0, it the thread has to wait for it the value to become 0 again.
- A9
    - > The point is to temporarily create a new version of the process in which some modifications are made and, once these modifications have been made, the new version will reflect the changes to the data outside of the temporary space.
    - "create a new version of the process" This was hard to understand in the original.
        - Creating a new version" is, so to speak, "create a local copy of the shared values.
        - Instead of rewriting the shared X and Y directly, a local copy is temporarily created on hand and rewritten, and the changes on hand are reflected in the shared X and Y after the processing of one group is completed.
        - If someone else had rewritten the data before you did, you discard the revision at hand and start over with the new data. (This area is discussed on p. 182.)
Chapter9
- A1
    - > What is great about a linked list is that
    - Maybe it would be better to simply say "The advantages of using the linked list are
- A2, A3
    - Instead of simply deleting it, "In Japan, the term "scattering function" was used in the 80s. I think this is a translation that well expresses the purpose of the function. But now the term hash function is more common in Japan." I think it would be better to use a footnote rounded to something like
- A6
    - > British people use the Roman alphabet, to which additional letters, such as ç, are added in the French writing system.
    - The important part of the preceding and following sentences is that the word "Characters" is associated with different things in different cultures. If we talk about the writing system, it would be a country-by-country definition, which would not match the example of gal (gal characters in Japan are not defined in the orthography). (Because gyaru characters are not defined as orthography in Japan.)
- A9 What you read as "alphabet" in the original text here is A-Z.
- A11 Translation is not required.
- A16 "a" is fine.
- A17 As noted.
- A19 I don't want to capitalize the decode at the beginning of the sentence because it is part of the case sensitive code, can't I just add The or something?
chapter9 done

Chapter8
- A1 It is true that the lights that are on are black and the lights that are off are white, which may seem to be the opposite of the idea that the lights that are on are brighter, but the books have a white background, so the "lights off = same as background" are white. This is important when we get to the 7-segment story two pages ahead, where the 7-segment LCD has a light background and black text, while the 7-segment LED has a dark background and light text. Which is brighter is not essential; 0 is the same as the background and 1 is different from the background.
- A3
    - > - Black circles and white circles represent each represent 1 and 0
    - > + Black circles represent "on" and white circles represent "off"
- A4
    - I see, I would add this.
    - > Base-2 system is commonly called "binary number system", where "bi-" means 2.
- A9
    - > - When the language processing wants to get the value, it has to read the bit stream on the memory as PyObject
    - > + When the Python implementation in C get the value from the memory, it consider the bit stream on the memory as PyObject
- A11 Let's apply a tentative translation and use the original title as a footnote

Chapter7
- A4
    - > - global variables are worthless
    - > + global variables are harmful
    - memo [https://dl.acm.org/citation.cfm?id=953355](https://dl.acm.org/citation.cfm?id=953355)
- memo
    - The "correspondence table" is translated as "scope," but "symbol table" might be more appropriate.
- A6
    - > To address this problem, the writers of Python decided to modify this behavior, and in 2001, Python 2.1 was released to implement the expected behavior for a nested scope described in Fig 7.9
    - Let's keep it simple.
    - > To address this problem, Python 2.1 was released in 2001 to implement the expected behavior for a nested scope described in Fig 7.9
- A8
    - > - However, we can avoid the problem of name collision because class names are hierarchical, and we have to import a class for it to be used at all
    - > + However, we can avoid the problem of name collision because class names are hierarchical, and we have to explicitly import classes which we want to access.

Chapter6
- A1: As pointed out, the analogy to "To Err is Human" is subtle. It is also subtle to assume that non-native readers are familiar with the saying, so "Program may fail" or something like that would be fine.
- A3 Let's tentatively translate
- A4
    - > In PL/I we first register the processes to be run for errors and then write potentially erroneous code, whereas languages that are popular today, such as Java, implement potentially erroneous code first, followed by the code that handles errors.
    - (try{......} ) is missing from the translation, as you pointed out, but I thought this sentence was too long to begin with.
    - What I want to say here is as follows
        - For PL/I, write the error handling code first, then write the potentially erroneous code.
        - In today's popular Java and other languages, write the potentially erroneous code first, and then write the error handling code.
        - In C++, potentially erroneous code is enclosed in `try{...} `...}.
        - How and when did this syntax come about?
- A5
    - It seems that native speakers misinterpreted the Japanese translation as a direct quote, which means that it is not a good idea to have the expression in a way that could be misinterpreted as a direct quote in the first place, so I thought it would be better to remove the quotation marks.
    - status quo
        - > Programmers can make mistakes in a variety of ways.
        - > He might forget about the possibility that a statement can throws an exception,
        - > or he may implement exception handling in wrong places or with wrong types.
        - >  In order to make sure that those things become less likely to happen and that a compiler can give us warnings about the mistakes made by programmers, we need 2 things.
        - > Firstly, we need to clearly declare what types of exceptions a statement could raise.
        - >  Secondly, we need to create a syntax that wraps around a potentially erroneous process.”
    - proposal
        - > He thought that there were two problems
        - >   * Programmers may forget about the possibility that a statement can throws an exception
        - >   * Programmers may implement exception handling in wrong places or with wrong types
        - >  To reduce this problem, and also, in order for the compiler to warn you about this problem, programming language should have following feature
        - >  * Firstly, we need to clearly declare what types of exceptions a statement could raise.
        - >  * Secondly, we need to create a syntax that wraps around a potentially erroneous code.
        - I feel like I should fix it a bit more, but I'll give you feedback anyway.
- A7 A8
    - > With SEH, you can ensure that resources such as memory blocks and files are correctly if execution unexpectedly terminates. You can also handle specific problems—for example, insufficient memory—by using concise structured code that does not rely on goto statements or elaborate testing of return codes.
    - Indeed, the original English of the MSDN is not correct.
    - Change "are correctly if" to "are correctly released if" and specify in a footnote that "the original was not released, but the author has corrected it so that it makes sense"!
- A10
    - I think it's too confusing as suggested, but how about "paired processes", "pairing processes", "encoupled processes", etc.?
- A11
    - Looks good as is.

Chapter5
- A4
    - > The answer lies in its ability to facilitate the processing of certain types of code. Indeed, recursion allows us to write clear code when it comes to processing a nested data structure where a process is being applied to a certain parameter and, within this process, the same process is also being applied to another parameter. When dealing with a nested data structure, it’s common to write code with some nested structures init.
    - The Japanese was muddled, as was the intent.
        - Recursive calls are easy when writing nested processes
        - Nested processing is a process in which one process is being performed while another is being performed on the same object.
        - This type of processing is often necessary, especially when dealing with nested data structures
    - That is to say.
- A5
    - I was wondering if you could simply shave it off, or just use something like It's complete.

Chapter4
- A3 modules are not required

Chapter3
- A3 Please confirm the following comments I made in my August 8 e-mail regarding this matter
    - > As for chapter 2, p20, the order of the sequence "2 3 * 1 +" and the
    - >  Since the sentence explains that the order of Japanese is the same: "Multiply 2 and 3, then subtract 1".
    - >  Simply replacing "Japanese" with "English" will not make sense.
    - >  Leave the text in "Japanese" and use footnotes.
    - >  "In Japanese, we say 'multiply 2 and 3 and add 1'.
    - >  I thought it would be a good idea to supplement with
- A6
    - > The same syntax tree for both FORTH and LISP
    - How about "syntax tree of FORTH and LISP are the same"?
- A7
    - This is indeed an oversimplification.
- A8
    - > - Don’t know what you want to create?
    - >  + Are you undecided about what you want to create?
    - In addition, I think it would be a good idea to fix the following
    - > - Why don’t you start by creating something simple?
    - > + You have to start by creating something simple.

Chapter2
- A1 I think deletion is fine.
- A2, A3 As indicated.

Chapter1
- A1
    - > Learning several languages will help you understand an important fact, which is that each language has specific rules upon which it operates.
    - No, what I mean here is simpler: Rules differ among languages.
- A2 Tentative translation, please.
- A4 You should put it in.




Task memo for non-translators
- Liskov Substitution Principle
    - Change "6.3.2 Introduction to CLU" to a link since "on page 67" is not kept in reflow
- p.224 footnote Since the original error message is in Java, should I check the error message in the English version of Java, strictly speaking? (Low priority)
- Errata p.226 "Fig. 12.3" is an error for "Fig. 12.12" (Erratum confirmed in the second printing of the Japanese edition)
- p.229 footnote 14 "Design and Evolution of C++" from the Japanese book, so check the wording in the original book.
    - The same applies to p. 186. Page numbers also need to be checked.
    - Also p. 208.
    - Also p. 72.
- Make p.230 "12.2.2 Multiple Inheritance: Useful for Code Reuse" a link
- Errata p.186 Bjarne Stroustrup's homepage seems to have changed from [http://www2.research.att.com/~bs/homepage.html](http://www2.research.att.com/~bs/homepage.html) to [http://www.stroustrup.com/.](http://www.stroustrup.com/.)
- Check the original notation on p.192 footnote 6 Programming in Modula-2 (should be in PDF)
- Errata p.199 The term "first-class" was used to distinguish between "first-class citizens," who are citizens with ordinary rights, and "second-class citizens," who receive inferior treatment, such as not having the right to vote.
- p.207 Added illustration of explanation because it is hard to convey ![image](https://gyazo.com/a7444659a9dae55cfa51e29b56757bc3/thumb/1000)
- Make references to p. 66 from p. 77 to p. 66 a chapter number instead of a page number

---

---
This page is auto-translated from [/nishio/コーディングを支える技術 英文チェック](https://scrapbox.io/nishio/コーディングを支える技術 英文チェック) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.