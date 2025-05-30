---
title: "Difference between a nomenclature-type system and a structural-type system."
---

from  [[Draft addition to "The Difference Between Named Type Systems and Structural Type Systems"]]
Difference between a nomenclature-type system and a structural-type system.

Dart: Currently, typedefs are restricted to function types. We expect this to change.

I was told at a TypeScript study group that "we study types in [[Technology Supporting Coding]]" and when I checked, there was still no explanation of the difference between structual and nominal. I would like to add it.

brainstorming
Type hint flow for dynamically typed languages
Later research on language rankings for 2014
- [https://www.immagic.com/eLibrary/ARCHIVES/GENERAL/TIOBE_NL/T140901I.pdf](https://www.immagic.com/eLibrary/ARCHIVES/GENERAL/TIOBE_NL/T140901I.pdf)
- Java 14% C++ 5% C# 4%
- Python 3% JavaScript 2% Ruby 1%
- Scala 0.4% Haskell 0.3%
scala story
- scala twitter
    - [Twitter hasn't abandoned Scala (at least not yet) - kmizu's Diary](http://kmizu.hatenablog.com/entry/2017/03/22/233335)
2019
- Java 15% C++ 9% C# 4%
- Python 8% JavaScript 3% Ruby 1%
- Scala 0.4% TypeScript 0.2% Haskell 0.2%

TypeScript was released in 2012
2019


The dictionary eliminates the need to clarify in advance what attributes are available.
Hackers and painters
- Pencil for drawing
But the undefined trap
- "" + 1
    - Static Typing Language "Error
    - Python runtime error TypeError: cannot concatenate 'str' and 'int' objects
    - JavaScript "1"
- `{}["x"]`
    - Python: KeyError
    - JavaScript: undefined
    - This is not the difference between static typing and dynamic typing, just that JavaScript is particularly bad among dynamically typed (dynamic checking) languages.
The point of discovery is far away from the problem area.
Implementation in js rapidly expanded by the needs of society
Execution occurs on the client side
Strong need to be aware of problems in advance
- Two approaches
    - Closure Compiler
        - Static checking while following JavaScript syntax
        - Assign type annotations in JavaDoc format
        - case
            - 2012
                - [How to make JavaScript fully compatible with Closure Compiler's ADVANCED mode! - Cybozu Inside Out | Cybozu Engineer's Blog](https://blog.cybozu.io/entry/502)
                - Cybozu kintone had 100,000 lines of JavaScript code as of 2012.
            - 2015
                - [https://www.slideshare.net/ama-ch/google-closure-toolsreact](https://www.slideshare.net/ama-ch/google-closure-toolsreact) about introducing React to a large service built with Google Closure Tools.
                - Cybozu KINTONE had 300,000 lines of JavaScript code as of 2015.
    - AltJS
        - Develop in another language and convert to JavaScript
        - [http://smurfpandey.github.io/altjs/](http://smurfpandey.github.io/altjs/)
        - Many languages were born.
        - TypeScript is one of these
        - As of 2015, TypeScript is already the only one
            - [https://www.buildinsider.net/hub/survey/201504-techtrend-en#altjs](https://www.buildinsider.net/hub/survey/201504-techtrend-en#altjs)
        - ![image](https://gyazo.com/d057a2390e793eefeb1211c3196e8bf8/thumb/1000)
            - It's reversed around February 2015.
        - Incidentally, there is also a [JSX](http://jsx.github.io/) created by a Japanese person, but as of 2019 it has been overshadowed by JSX as an abbreviation for JavaScript XML, making it difficult to search
            - The copyright notice on the project page stops at 2013.
                - > Copyright © 2012, 2013 DeNA Co., Ltd. et al.

Python Type hints
- [PEP 484 -- Type Hints | Python.org](https://www.python.org/dev/peps/pep-0484/)
- [PEP 483 -- The Theory of Type Hints | Python.org](https://www.python.org/dev/peps/pep-0483/)
- Provided as a library in Version 3.5
    - Released in 2015

Liskov's replacement principle
- Subtypes may be used in place of supertypes."
- Subtyping is not subclassing, thesis
    - Cook, W.R.; Hill, W.L.; Canning, P.S. (January 1990). "Inheritance is not subtyping". Proceedings of the Seventeenth Annual ACM Symposium on Principles of Programming Languages. San Francisco, California: 125–135.
- Java was released in 1995, so this paper was out

    - In [[Introduction to Type Systems]], "19.3 Named Type Systems and Structural Type Systems".
    - Structual was more mainstream as a type study, the system is simple.
    - nominal is a type always accompanied by a name
    - class Cat extends Animal { ... }
        - They are making a "named mold" called Cat.
        - Easy to verify if it is a subtype
    - Maybe Nominal was adopted in Java, etc. because of performance issues.
        - The rumor that "Scala is slow."
        - Later research has created a method for fast identification even with Structual.
            - Create a hash of type
        - Did these areas directly contribute to the increase or not?
        - It's been 15 years since Scala was born in 2004, so the machines are probably more powerful now.
            - (Would the SSD conversion be greater than the CPU performance?)
            - Did improved compile times contribute to the popularity of the Structural Typing language?

- Talking about Go's interface, there was no place to write it.

- [https://stackshare.io/stackups/dart-vs-typescript](https://stackshare.io/stackups/dart-vs-typescript)
    - TypeScript appears to be popular.
    - In TIOBE, though, it was Dart 0.5%, TypeScript 0.2%.
    - I guess it's a situation where there are too few of either and the small and large are reversed in the slightest situation.

- > the more important idea is the separation of concept: data and behavior are two distinct concepts in Go, not conflated into a single notion of “class”.
    - [https://twitter.com/rob_pike/status/942528032887029760](https://twitter.com/rob_pike/status/942528032887029760)
    - Author of Go.

- [https://en.wikipedia.org/wiki/Structural_type_systemに](https://en.wikipedia.org/wiki/Structural_type_systemに)
- >  C++ template functions exhibit structural typing on type arguments.
- but what exactly does this mean in terms of behavior?
    - > ([moriyoshit](https://twitter.com/moriyoshit/status/1122136706679881729))Operations on members of a type given in a type parameter will pass the compile if the structure matches whatever the type is, so either to that effect and
    - This is what you mean?
cpp

```cpp
struct A{
  int i;
  int j;
};

struct B{
  int i;
  int k;
};

template<class T>
int get_i(T& x){
  return x.i;
};

int main(){
  A a;
  B b;
  get_i<A>(a);
  get_i<B>(b);
}
```

        - Is this Structural Typing? It's just that two implementations of get_i have been created that are specialized with the given type parameters, and each one is compiled normally.
            - In a normal compilation, the code "x.i" succeeds whether x is A or B. Why not call it "Structural"?
        - Only the `get_i<T>` part is of interest: whether a type can enter T is "determined by the structure, not the name" of "the type that has member i."
cpp

```cpp
struct A{
  int i;
  int j;
};

struct B{
  int i;
  int k;
};

struct C{
  int j;
  int k;
};

template<class T>
int get_i(){
  T x;
  return x.i;
};

int main(){
  get_i<A>();
  get_i<B>();
  //get_i<C>();  // error: no member named 'i' in 'C'
}
```


- Generics (generic type) was introduced in Java in 5.0, 2004.
    - > Nominal languages have such "generic" features... Some of them have extensions of the "generic" function. But those with such extensions are no longer purely nominal type systems, but rather a somewhat complex hybrid of the two approaches. Designers of languages with evolving type functions tend to opt for the structural approach.
            - [[Introduction to Type Systems]]  P.198
    - When were templates introduced to C++?
    - I think that the nominal mechanism is no longer purely nominal, and that the Stractural mechanism is gradually being mixed in with the Nominal mechanism around that time.

- Constraints and concepts (since C++20) - cppreference.com
    - [https://en.cppreference.com/w/cpp/language/constraints](https://en.cppreference.com/w/cpp/language/constraints)
        - A predicate can be defined for a type, which is inspected at compile time.

- (Java adopted the generic (generic type) feature in 2004. (Java adopted generic types in 2004. This is the direction in which Java, which used to be a nametype type, is now moving toward a hybrid with structural types, but whether or not to devote a page to explaining this is a matter for discussion).
    - In short, in Java, if a type had a different name or was not in an inheritance relationship, it was a different type altogether, especially for containers, where different types T1 and T2 shared the "can be placed in that container" condition.
        - If it had certain characteristics, it was good to containerize it.
        - I guess you could say that once I started to understand this area, I realized that there are a lot of problems with pure Nominal.
- STL in 1993.
    - [https://en.wikipedia.org/wiki/Standard_Template_Library](https://en.wikipedia.org/wiki/Standard_Template_Library)
- function templates, class templates and, since C++14, variable templates. Since C++11
    - [https://en.wikipedia.org/wiki/Template_(C%2B%2B)](https://en.wikipedia.org/wiki/Template_(C%2B%2B))
        - Huh? That means the early STL was realized without using templates?
        - I wonder if templates are commonly used in the 1996 STL commentary.
            - [http://www.cmapx.polytechnique.fr/~benaych/stl-tutorial-Weidl.pdf](http://www.cmapx.polytechnique.fr/~benaych/stl-tutorial-Weidl.pdf)
        - So you are saying that it was only late in getting into the specification, but individual compilers were implementing it?
        - 1990
            - [https://en.cppreference.com/w/cpp/language/history](https://en.cppreference.com/w/cpp/language/history)
            - 1990: The Annotated C++ Reference Manual
                - This book described the language as designed, including some features that were not yet implemented. It served as the de-facto standard until the ISO.
                    - New features: namespaces, exception handling, nested classes, templates
            - So it was de facto in 1990, he said.
        - It was the variable length templates that came in with C++11, the fixed length ones have been around for a while!
            - [https://en.wikipedia.org/wiki/Variadic_template](https://en.wikipedia.org/wiki/Variadic_template)


---
This page is auto-translated from [/nishio/「名前的型システムと構造的型システムの違い」加筆案メモ](https://scrapbox.io/nishio/「名前的型システムと構造的型システムの違い」加筆案メモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.