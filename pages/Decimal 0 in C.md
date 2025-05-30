---
title: "Decimal 0 in C"
---

> [uchan_nos](https://twitter.com/uchan_nos/status/1366890931912249348): How do you write a decimal 0 in C?

I see, the C standard clearly defines 0 as octal, so there's no way to write 0 in decimal. w

![image](https://gyazo.com/3eddd2da2ac2e8a7280835dd5fad3cdd/thumb/1000)
[Final version of the C99 standard with corrigenda TC1, TC2, and TC3 included, formatted as a draft](http://www.open-std.org/jtc1/sc22/WG14/www/docs/n1256.pdf)

I was told "in C" but not when, so I guess I could find a "C compiler from before 0 was defined as octal" somewhere and write "0"...

PS [as of 1988](https://web.archive.org/web/20161223125339/http://flash-gordon.me.uk/ansi.c.txt), 0 was similarly defined as octal.
---

In Python, not only was 0 a decimal literal, but so were 0_0 and 0_0_0. w [doc](https://docs.python.org/ja/3/reference/lexical_analysis.html#integer-literals)
![image](https://gyazo.com/c83b125447526f4d9f9b3c157961167b/thumb/1000)

---

- bday1u2t:
    - > The 0 in the literal "0" is defined only as a prefix, and it reads as if Semantics does not describe what kind of number this literal should be interpreted as (there is no body to be interpreted as a number).
    - > That is, "The meaning of the literal "0" is undefined in the C language"?
    - ![image](https://gyazo.com/af6d32db38dbfd42c1431e0aee9d6510/thumb/1000)
- uchan_nos:
    - > The value of the octal constant is calculated using 8 as the radix. 0 is interpreted as an octal number and has the value 0. (If the value of 0 were undefined, almost every program in the world would depend on undefined behavior.)
- bday1u2t:
    - > No, the description says that the leading 0 of an octal literal is a prefix.
    - >  Just as 0x in hexadecimal is not to be interpreted as part of a number, should we not read 0 in octal as part of a number?
    - >  (Of course, there is no disagreement that any implementation should interpret the literal "0" as 0)
- nishio:
    - >  Interesting point. It is true that the 0x of a hexadecimal literal, which is similarly called a prefix, is removed and the remainder is interpreted as hexadecimal, so an octal literal should be removed as well and then interpreted, and then the behavior of "if an empty string is interpreted as octal notation, it shall be set to 0" is not clearly defined. Right.
- kaityo256:
    - > Sorry for the sideways comment, but the description says "octal is 0 start, optionally followed by 0-7", so it reads as if the lone "0" is defined to be octal.
- nishio:
    - > I don't disagree that the lone "0" is an octal literal, but I don't think it is explicitly stated that it corresponds to an integer 0. Because that, the first "0" is called a prefix, and in the case of a hexadecimal literal, the portion with the prefix removed is the integer in hexadecimal notation, and it does not say that it is not removed when it is octal.
- kaityo256:
    - > Hmmm, the syntax defines a single "0" to be "octal-constant", and the literal interpretation of "optionally" in the Description reads to me as if the single "0" is interpreted as an "octal constant" without a hyphen, and then interpreted as an "octal 0" by the semantics. It reads to me as if the semantics interpret it as "octal 0". ......
- nishio:
    - > I think the single character "0" is interpreted as meaning that only the prefix 0 exists and the optional "non-prefix part" is the empty string, since optionally is grammatically subject to FOLLOWED.
- kaityo256:
    - > I have no doubt that a single "0" is interpreted as an "octal constant" with "prefix 0" only, but in that sense, I don't think I can find a definition that says "remove the prefix (even in hexadecimal) and interpret the rest" in the first place. I wonder if there is a strict definition of "what a prefix is?"
- nishio:
    - >  and I was talking about this kind of English interpretation, and I thought what if the English sentence had changed with a newer standard, and I came up with a newer one, and I got the feeling that 0 is arguably changing to a definition that is 0.
        - (PS: The one I'm showing here is for C++, not C language)
    - ![image](https://gyazo.com/254b1e2d2c2c12be496aa3414dc3a90e/thumb/1000)
        - [Working Draft, Standard for Programming Language C++](http://open-std.org/JTC1/SC22/WG21/docs/papers/2020/n4878.pdf) Date: 2020-12-15 p.21
    - > This seems like a neat solution, since it specifies "remove prefix" and the word prefix only appears in the syntax definition (so the octal literal 0 is not a prefix).
        - ![image](https://gyazo.com/994e1681a2f0fee34a0e830a94023d26/thumb/1000)


- kaityo256:
    - > Oh, you have a good (though Note) definition for prefixes as well. I wonder if someone complained about it.
    - > On the contrary, the fact that it has been updated in this way must mean that there was a problem with the previous description of the specifications.


---
This page is auto-translated from [/nishio/C言語で10進数の0](https://scrapbox.io/nishio/C言語で10進数の0) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.