---
title: "Changes in programming languages over the past decade"
---

2023-01-12
> [@nishio](https://twitter.com/nishio/status/1613434779009167360?s=20&t=70HdGFTrSHooPvcvaQQ_rg): What are the major changes in programming language specifications in the last 10 years? What are the major changes in programming language specifications in the last 10 years?
- It's better not to cut them off exactly.
    - > [@nishio](https://twitter.com/nishio/status/1613440166617837570?s=20&t=70HdGFTrSHooPvcvaQQ_rg): Oh, well, there have been cases that have been around for 10 years, but have expanded in power over the past 10 years. I guess I shouldn't be too hard on them (TypeScript came out in 2012, Rust in 2010).
    - > [@umezawa_takeshi](https://twitter.com/umezawa_takeshi/status/1613437597011030019?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): I was dizzy when I realized that C++11 is more than 10 years old now! I was dizzy when I realized it was over 10 years ago. [https://t.co/rG7WVblUVX](https://t.co/rG7WVblUVX)
- It doesn't have to be limited to changes in language specifications.
    - There's also a "changes in the programming environment" kind of post, which is interesting too.

## async
- > nishio ES2017 async await
    - 2017 [async function - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- > Black tea pot (Dimbula) async/await syntax has entered various languages
    - 2015 [Python Release Python 3.5.0 | Python.org](https://www.python.org/downloads/release/python-350/)
- > [@tanakahisateru](https://twitter.com/tanakahisateru/status/1613509605547704320?s=20&t=L68AEmRVwi29iEpEi2eDdg): I added Fiber to the responses mentioning PHP because it hadn't been mentioned yet. I added Fiber because it wasn't mentioned yet... It's been a decade of single-threaded languages adopting the async keyword in a big way, not just PHP.
- > [@haxe](https://twitter.com/haxe/status/1613519039548260352?s=20&t=f9MbMUsiK6htbzaxyEFhvw): ... Async / await is also more than 10 years old in C# 5.0, but it too has spread to other languages. (Though there was an F# implementation before C#) [Async/await - Wikipedia](https://t.co/HSD5TCCXus).
- > nishio That, Python 3.5 (2015) async is earlier than ES2017 async, surprising!
    - > shibukawa
    - > [https://github.com/koush/node/commit/4ba9d5bf4b48d1d74214aa445fabd67c28a302bd](https://github.com/koush/node/commit/4ba9d5bf4b48d1d74214aa445fabd67c28a302bd)
    - > It was added to Node.js in 2013, apparently.
    - > [https://bugs.chromium.org/p/v8/issues/detail?id=4483](https://bugs.chromium.org/p/v8/issues/detail?id=4483)
    - I wonder if the proposal to >v8 is 2015.
    - > nishio Ah, I see, there is a lag before entering the standard
- Runtime supports multi-core in OCaml 5.0.
    - 2022-12-16: OCaml 5.0
    - > [@wat_aro](https://twitter.com/wat_aro/status/1613734633191149568?s=20&t=Q2e46V8DlyTjFZTEyv9dRQ): I think the Effect handlers in OCaml5 are huge!
        - > [@zehnpaard](https://twitter.com/zehnpaard/status/1614799265003606023?s=46&t=L1ZAIUOV6AdRftAAgxMcFw): Attempting to explain from the side, what is an Effect handler?
        - > Functionally, it extends the exception mechanism so that processing can be resumed from the point where the exception occurred.
        - > Various uses include Async/Await and other concurrency processes, State and IO states, etc.
        - > / Expression is similar to Monad, but Effect is easier to combine and has less impact on the surrounding code.
        - > [@zehnpaard](https://twitter.com/zehnpaard/status/1614800185485557761?s=20&t=MwSG-yIIW2rqslrECBBMlQ): - These properties make functional programming, not only OCaml have been studied quite a bit in the language theory community
        - >  Added in OCaml 5.0 for implementation of concurrency-like green threads as the runtime supports multi-core
        - > / It is known that the type system is incomplete for implementation in OCaml, and future research is awaited.
        - > [@zehnpaard](https://twitter.com/zehnpaard/status/1614807406004895746?s=20&t=MwSG-yIIW2rqslrECBBMlQ): the syntax and usage of effects handler in OCaml The official reference has a lot of information about this, but I personally learned the most from the ocaml effects tutorial.
            - [OCaml - Language extensions](https://v2.ocaml.org/manual/effects.html#s%3Aeffect-handlers)
            - [GitHub - ocamllabs/ocaml-effects-tutorial: Concurrent Programming with Effect Handlers (CUFP'17)](https://github.com/ocamllabs/ocaml-effects-tutorial)


## de-object oriented
.
- Programming style that avoids destructive updating of objects.
    - > [@nakayoshix](https://twitter.com/nakayoshix/status/1613441056737202176?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): both Java (Java SE 14) and C# (C# 9) have record type have been added.
        - > The separation of data structure (record) and algorithm (class) was taken for granted, and the trend from "changing objects with state (in the past) through methods" to "transforming immutable data through functions" became the norm.
        - > [@nakayoshix](https://twitter.com/nakayoshix/status/1613443746812809223?s=20&t=TfunlWNYTIcPGCJ4ztrzDw): @nishio OCaml (or ML if you trace it back further) derived F# I think it is an important change that Scala has a data type (data structure) similar to record type in the form of case class, and Python has a data type (data structure) similar to record type in the form of dataclass. Of course, there are more advanced algebraic data types in functional languages such as F#.
        - > [@roshian](https://twitter.com/roshian/status/1624704480796360704?s=20&t=ZRyOuSozdWzQR1jAuJaKbg): I think there was Scala's case class (and Kotlin's data class) before C#/Java's Record. I think Python got dataclass in 3.7(2018), so I guess it's this one in that vein. / "Programming Change Study Group - Scrapbox by NISHIO Hirokazu" [https://t.co/89sBjJ4zZI](https://t.co/89sBjJ4zZI)

- inherited away
    - > [@yoshiori](https://twitter.com/yoshiori/status/1613483890337021952?s=20&t=L68AEmRVwi29iEpEi2eDdg): @nishio New languages have lost the concept of inheritance. I'm talking about Rust and others.
        - > [@yoshiori](https://twitter.com/yoshiori/status/1613521505429909504?s=20&t=L68AEmRVwi29iEpEi2eDdg): @nishio Go has no classes to begin with (though you can use structs to create modifications), and if inheritance is eliminated, the role of classes will be to hold instance variables and function namespaces. The role of classes is to hold instance variables and function namespaces when there is no inheritance, so the role of classes is limited to holding state, and most of the time it's an immutable object and function approach.
- GUI development moves away from OOP.
    - nishio: Moving from class components to function components in React
        - The "class-based approach" that had been common in the past for creating GUI components was abandoned in favor of "functions" that have no state.
        - > Hooks are a new feature added in React 16.8 that allows you to use React features such as state without writing classes. [doc](https://ja.reactjs.org/docs/hooks-intro.html)
            - 2019: React 16.8 release
    - > shibukawa I feel the programming paradigm is changing, from object-oriented to functional-oriented, and I think it's practical to separate data and program, and to maintain the state, and to send the result edited in the editor to the browser and change the appearance in real time, like a hot module replacement. I feel that this is a paradigm shift in programming.
        - > I'm sure it's probably triggered by some of the troops at Meta, but I'm sensing a growing love of functional types via the web front end.
    - > Tefu, there is also Elm, and I feel that GUI development has moved from OOP to FP.

## Reactive programming style
.
- > [@ooharak](https://twitter.com/ooharak/status/1613450669121495040?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio Stream processing and ReactiveX have been around for a long time. I wonder if stream processing and ReactiveX have been around for a long time, or if it's only been in the last 10 years for Java or something like that.
    - > [@nishio](https://twitter.com/nishio/status/1613457582865395713?s=20&t=ajtYaLfTQBVa0cg_X273GA): @ooharak If you look at it in a broader sense as "patterns in how programs are structured". I think it is one of the interesting events!
- > [@haxe](https://twitter.com/haxe/status/1613519039548260352?s=20&t=f9MbMUsiK6htbzaxyEFhvw): @nishio ReactiveX is 11 years old in C#, but it spread to other languages in the I would say in the last 10 years. [ReactiveX - Wikipedia](https://t.co/4VLgEBP4jR)
- > taichi I think it's been about 10 years since the stream-oriented programming style has become accepted outside of embedded systems.
    - >  Rx, Node's gulp, Java's StreamAPI, that kind of thing. With this, the need for objects that cannot change state, such as record type, was recognized by everyone.

## Generics of Go
.
- > [@koizuka](https://twitter.com/koizuka/status/1613438708463828992?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio I guess we're talking like generics in Go
- > [@ymotongpoo](https://twitter.com/ymotongpoo/status/1613438840324362242?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio Go and the generics are in!
    - > [@ymotongpoo](https://twitter.com/ymotongpoo/status/1613440143276531713?s=20&t=dzWymjJAcWwDgb_7E-ulyQ): @nishio Go itself hasn't been published for 14 years. so there may be a lot of major changes in the language spec in that sense!
    - > [Release History - The Go Programming Language](https://t.co/SSg3AZB9C8)

## I still want the mold.
- > [@ajiyoshi](https://twitter.com/ajiyoshi/status/1613441206805200896?s=20&t=ZMR6oHWfQrjzAEZZ3sqbrQ): since PHP7 series (2015-) you can write types in various places. I heard that it was possible to write types in various places since PHP7 series (from 2015).
    - > The type system itself is of course a common feature, but the fact that even languages like PHP now support type constraints seems to be a trend.
    - > [@ajiyoshi](https://twitter.com/ajiyoshi/status/1613441738374516738?s=20&t=ZMR6oHWfQrjzAEZZ3sqbrQ): In the 00's (especially in the web industry), there was an upsurge of "languages that have types for values instead of variables. I feel that in the 10's, people are saying "I want to have types after all".
    - > [@ajiyoshi](https://twitter.com/ajiyoshi/status/1613444041299091457?s=20&t=ZMR6oHWfQrjzAEZZ3sqbrQ): Personally, I think "PHP with type annotations in PHP" is much bigger difference than "go with generics".
    - > [@nishio](https://twitter.com/nishio/status/1613444321222750210?s=20&t=ZMR6oHWfQrjzAEZZ3sqbrQ): @ajiyoshi I knew that the creation and spread of "typed AltJS I think it may have been significant that "typed AltJS" was created and popularized against JavaScript, thank you very much!
- > [@methane](https://twitter.com/methane/status/1613519520618119170?s=20&t=L68AEmRVwi29iEpEi2eDdg): @nishio @zetamatta I want the type, where I think you need TypeScript.
- Gradual typing.
    - > shibukawa Gradual molding boom
    - > [@cubbit2](https://twitter.com/cubbit2/status/1613499662383865856?s=20&t=L68AEmRVwi29iEpEi2eDdg): Ruby, Python, PHP and other dynamic languages are all Type Hinting, Gradual Typing, etc.

## half-precision floating-point number
.
- > [@cpp_akira](https://twitter.com/cpp_akira/status/1613441963487039490?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio Very recently, in C++23, float16_t and bfloat16_t in C++23 (GCC extension _Float16 and others have been around for a while).
- > I'm sure other languages will be supported in the future, so I'm sure the scope of impact will be quite large.
    - > [@nishio](https://twitter.com/nishio/status/1613444002333835266?s=20&t=9-JyPbceqqeORtEZsRQ2SA): @cpp_akira I see, the need for semi-precision has increased in relation to machine learning, etc. I guess that means. It is indeed an interesting change! Thank you!

## people have come to accept type postfix notation
.
> [@ryushi](https://twitter.com/ryushi/status/1613441936744124416?s=20&t=YoXj-vNxY868u2v_oDxLDg): @nishio Postfixing types has become mainstream. hoge = "aaa"; even in Java.
- > [@ryushi](https://twitter.com/ryushi/status/1613447513377509376?s=20&t=YoXj-vNxY868u2v_oDxLDg): @nishio I don't find it hard for people to read anymore, even with type postfixed, It's easier to build compilers.
- > [@nishio](https://twitter.com/nishio/status/1613447781947150337?s=20&t=YoXj-vNxY868u2v_oDxLDg): @ryushi That means it's easier to handle complex types that take type arguments. Is that right?
- > [@ryushi](https://twitter.com/ryushi/status/1613448525949603840?s=20&t=YoXj-vNxY868u2v_oDxLDg): @nishio Yes, it is. It is now relatively easy to implement compilers that infer complex types.

## Language Server Protocol (+ GitHub Copilot)
- > [@yoshiori](https://twitter.com/yoshiori/status/1613444701071495168?s=20&t=EFnfA4Z792NYNFmLZW4FGw): @nishio It's not a specification, but the act of programming I think LSP is a very big thing for the act of programming. （I think LSP is a big thing for the act of programming, not a specification.)
    - > [@nishio](https://twitter.com/nishio/status/1613445770480607232?s=20&t=EFnfA4Z792NYNFmLZW4FGw): @yoshiori I think the evolution of IDEs is a major trend that cannot be ignored
- > [@shoma](https://twitter.com/shoma/status/1613460702496428032?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): voted for Language Server Protocol (2016)
- > shibukawa Language Server will be available within 10 years.
- 2016 [Language Server Protocol - Wikipedia](https://en.wikipedia.org/wiki/Language_Server_Protocol)
    - > LSP was originally developed for Microsoft Visual Studio Code and is now an open standard. On 2016 June 27, Microsoft announced a collaboration with Red Hat and Codenvy to standardize the protocol's specification.
- 2021 [GitHub Copilot - Wikipedia](https://en.wikipedia.org/wiki/GitHub_Copilot)
    - > Shiro I don't remember any mention of GitHub copilot. I'm thinking that I might stop writing programming languages in the first place.

## pattern match
.
- > [@_ko1](https://twitter.com/_ko1/status/1613444561598296064?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio Python or Ruby with pattern matching? (Not that the idea is new...)
- > [@joker1007](https://twitter.com/joker1007/status/1613447783037689857?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio In Ruby, it's still JIT compilation. I think the introduction of pattern matching is another modern language feature.
- > [@imunolion](https://twitter.com/imunolion/status/1613628529614426112?s=20&t=Q2e46V8DlyTjFZTEyv9dRQ): @nishio By structural pattern match, are you talking about ninja pattern match or dragon pattern match? It has become so popular that it is now a dead word.

## null handling
.
- > [@masaichi](https://twitter.com/masaichi/status/1613459225765875714?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio What about null safety in dart, objective How about nullability in -c?
    - > [@kagilinn](https://twitter.com/kagilinn/status/1613461206182039553?s=46&t=UjgC92p_O2OHr0dUuXvDew): @masaichi @nishio C# is also #nullable C# also allows null safety (as a warning, in effect, since C# allows certain types of warnings to be errors), and various languages are adding ways to make nullability explicit.
- > [@Fushihara](https://twitter.com/Fushihara/status/1613440386399375360?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): C# is now null safe. typescript and I think it's rare that the main body supports it instead of an alt language like kotlin.
- > shibukawa: Dart is 2011 / null safety is one boom?
- [[Nullable]]

## package system
.
- <img src='https://scrapbox.io/api/pages/nishio-en/tokoroten/icon' alt='tokoroten.icon' height="19.5"/>I feel that the language and packaging systems are much more compatible than they used to be.
    - Library management systems like npm and pypi are now more closely tied to the language.
- > taichi I wonder if there is a sense that management of dependent libraries has become a standard offering in the last decade.

## formatter
- > taichi I think in the last 10 years Lint and formatters have also become language standard offerings.
- > ymotongpoo I think the impact that gofmt has had.

## visual language
.
- > shibukawa Kismet, I have the impression that the number of people using visual languages has increased a lot with BluePrint (in game development).
    - > I remember Unity saying something about officially releasing it, but I wonder what happened to that?
    - > Well, Godot will lose its visual language with 4, so it's not that major.
- > tokoroten Visual pipeline programming like blueprint in UE / houdini

# Interactive Execution Sharing
.
> tokoroten Was jupyter, r studio, and other interactive consoles a major thing in 2013? I'm under the impression they were a bit further back.
- > Not the traditional interactive type, but one that brings it to the web and allows data to be stored properly.
    - > >Project Jupyter, separated from IPython by FernandoPérez in 2014, supports execution environments for dozens of languages.
- > swallowThe market share is not that big, but Wolfram's notebook with Mathematica has been around for a long time (2.0 released in 1991).
    - >  As Python spread into areas covered by Fortran and Mathematica, various environments were developed.
- > 2015, GitHub and the Jupyter project announced native rendering of the Jupyter notebook file format (.ipynb files) on the GitHub platform
    - > In 2015, about 200,000 Jupyter notebooks were available on GitHub. By 2018, about 2.5 million were available. In January 2021, nearly 10 million were available, including notebooks about the first observation of gravitational waves and about the 2019 discovery of a supermassive black hole.
    - > Major cloud computing providers have adopted the Jupyter Notebook or derivative tools as a frontend interface for cloud users. Examples include Amazon SageMaker Notebooks, Google's Colaboratory, and Microsoft's Azure Notebook.
        - [Project Jupyter - Wikipedia](https://en.wikipedia.org/wiki/Project_Jupyter)
        - 2017: Google Colaboratory
            - [Google just released its internal tool to collaborate on AI](https://qz.com/1113999/nerds-rejoice-google-just-released-its-internal-tool-to-collaborate-on-ai/amp)
        - > nishio interactive execution changed from "an act done by an individual" to "an executable document" or "code written in literary programming".


Java lambda expressions, type inference
- > [@kis](https://twitter.com/kis/status/1613445568793042944?s=20&t=p18R18pGcXYAFNWM99KpAQ): @nishio In Java, it's lambda expressions, type inference...
- > Java8 is 2013.
    - > [@kis](https://twitter.com/kis/status/1613445989003841539?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): still, considering the impact in the world and the lambda expression in Java in 2013. I'm not sure.
    - > I think it was a surprise to people who don't use Java.
    - digression
        - > [@nishio](https://twitter.com/nishio/status/1613446188187127809?s=20&t=p18R18pGcXYAFNWM99KpAQ): @kis By the way, I was thinking that Kishida-san is trying to abolish object-orientation as PM these days. By the way, I thought you are trying to abolish object oriented as PM, but was there any event that triggered it?
        - > [@kis](https://twitter.com/kis/status/1613447062758264833?s=20&t=p18R18pGcXYAFNWM99KpAQ): @nishio The reason for this was the aging of the population and the fact that when I was asked to write an article for Software Design on object oriented design, I thought that object oriented design was rather detrimental. I was asked to write an article about object-oriented design, and when I thought about it, I realized that object-oriented design is rather harmful. I was going to write "I don't need object oriented" even though it was a part of a feature article about relearning object oriented.
        - > [https://t.co/0YcyqC5P52](https://t.co/0YcyqC5P52)


>  I think ymotongpoo Playground has become more common
>  [https://go.dev/play/](https://go.dev/play/)
>  [https://play.rust-lang.org/](https://play.rust-lang.org/)
>  [https://play.kotlinlang.org/](https://play.kotlinlang.org/)


> shibukawa Native desktop GUI has been going downhill, and Electron and browser-wrapped apps have been increasing........................for the last 10 years or so?
- 2013: [Electron (software framework) - Wikipedia](https://en.wikipedia.org/wiki/Electron_(software_framework))

> tokoroten what about google docs GAS or something like that?
> nishio The range of people who write programs has expanded a lot.
> tokoroten  [https://ja.m.wikipedia.org/wiki/Google_Apps_Script](https://ja.m.wikipedia.org/wiki/Google_Apps_Script)
>  It was quite a long time ago, but I get the impression that it's only in the last few years that it started to catch fire.
>  I guess it's largely because of the popularity of chat, and the fact that I now have a place to post!
>  My impression is that GAS was ignited by the spread of chat in remote work.
- > shibukawa GAS may not have changed the world that much if you think of it as a VBA flow


> kumagi This time 10 years ago was when smartphones were finally coming out and games for i-mode were still in a phase where the more you put out, the more they sold.
- = Java
- >  Nowadays, we live in a world where we don't want to write ObjC or Kotlin individually, so we build one framework and it can be used on all platforms, or we just need a webview because we're going to focus on the web.
- 2007 [iPhone - Wikipedia](https://ja.wikipedia.org/wiki/IPhone)
- 2013 iPhone 5S

> golden_lucky I feel like declarative writing has become common in many languages in the last decade.


> [@haxe](https://twitter.com/haxe/status/1613447767598436352?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio I guess constexpr and lambda expressions for C++. I feel like compile-time computation has been generalized from black magic.

> [@mike_neck](https://twitter.com/mike_neck/status/1613455737765892098?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): It's not a spec, but Java now has a 6-month release cycle is a big deal.

> [@haxe](https://twitter.com/haxe/status/1613459109143277571?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): @nishio C# changed a lot, big and small, in C# 5.0 -> C# 11. The compiler was also revamped as an afterthought, and the runtime is now multi-platform and both are OSS. I'm amazed they put so much effort into it. [History of C# - C# Guide | Microsoft Learn](https://t.co/8mSZKjlnno)

> [@takiuchi](https://twitter.com/takiuchi/status/1613460275428200448?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): I wonder if it's the widespread use of transpilers

> [@tako_and_kitune](https://twitter.com/tako_and_kitune/status/1613442491809955840?s=20&t=GOGMRmO2xd9wHM-8fLVlUw): postgres, is the material view functionality?

> [@aokomoriuta](https://twitter.com/aokomoriuta/status/1613581316540485632?s=20&t=K0SCtEHu9eSmm0gsEI24-A): the heyday of domain-specific languages (DSL). Especially TVM, etc. Maybe a little different from the spec change.

> [@yutkat](https://twitter.com/yutkat/status/1613531545733853185?s=20&t=K0SCtEHu9eSmm0gsEI24-A): @nishio It's not a language specification, but personally, LSP, Linter, I think the biggest thing is that the development tool chain is now available for most languages, such as LSP, Linter, formatter, build runner, etc., and the development experience has been greatly improved.
> Container technology has made testing easier.

> kumagi The programming environment in the browser has improved a hoot thanks to Chrome and v8.
> shibukawa I can tell you about the old days when there were no developer tools until IE8 and you had to install firebug to debug.
>  shibukawa Well, it was Safari that changed the world by being the first to include built-in developer tools!
>  I don't know how they do it these days with hot reloads and such.

> kumagi In terms of the last 10 years in programming, I think the rise of LLVM is also in the last 10 years.
- > Although nothing qualitative has changed since the time of gcc, LLVM, which has a loose license and relatively modern code, has been improved by GAFA, which even created a dedicated department to improve it, resulting in considerable power savings on a global scale.

> tokoroten WebAssembly

> tokoroten In the last decade, quantum computers (quantum annealers) have become available for rent.
- > With AWS braket and such, quantum computers can now be rented by the hour.
- >  [https://aws.amazon.com/jp/braket/](https://aws.amazon.com/jp/braket/)
- > When you write an equation for a conventional constraint problem, PyQUBO and others have come up that convert it to an Ising model.
    - > ![image](https://gyazo.com/a117f52d254532e63ab28630c55d699b/thumb/1000)


> I'm kinda hoping for a crazy machine like tokoroten Cerebras.
>  [https://cn.teldevice.co.jp/product/cerebras_cs-2/](https://cn.teldevice.co.jp/product/cerebras_cs-2/)
>  [https://www.cerebras.net/](https://www.cerebras.net/)


> tokoroten SSDs have become more common, m.2 SSDs have become more common, and I think IO speeds have increased, but I wondered if this has changed anything, but I don't think it has changed the programming paradigm...
- > nishio I think that the speeding up of IO has gradually reduced the need for "designing properly with RDBMS" and led to the NoSQL boom (miscellaneous).
    - > Random access is much slower than sequential access" was a limitation derived from the physical structure of the hardware.
- > takabow IO speed-up gradually made it possible to manage large data even with RDBMS, NoSQL boom was over, and RDBMS made a comeback / If anything, this is the image of RDBMS.
    - > Around 2010, I think it was the beginning of the NoSQL boom (actually, it was around 2008), and at that time, especially in overseas and global businesses, RDBMS was not enough in terms of performance, and the burden of sharding operation was small, so they started to use NoSQL I think that they started to use NoSQL for scalability "out of necessity".
        - > I wanted scalability, so I used NoSQL, even if I had to give up other things.
    - > Around 2010-12, there was a story that RDBMS can be used for performance if they are replaced with SSD or Fusion IO, although it costs a lot of money to strengthen the infrastructure.
- > tokoroten Until then, we used to do vertical or horizontal distribution / If we do vertical or horizontal distribution, we can't get locks or use transactions, so why not use NoSQL?
- > nishio Ah, I see. Originally, the transactional nature of RDBMSs was their strength, but as the number of accesses from the Internet increased, the capacity of a single server exceeded the capacity of RDBMSs, and they began to be distributed across multiple servers, so the benefits of transactions began to wane. But then the benefits of transactional data started to wane, and they said, "Well, let's just throw it out and go with NoSQL.
- > takabow A RDBMS on a single physical machine with TB of memory and TB of disk space is becoming a realistic option, and I'm starting to think that this is the way to go without the hassle of sharding.
    - > Aurora's 96 core machine is fine.


Network thickness
- > kumagi When Hadoop was gaining popularity, 1GbE networks were the mainstream for a long time, and the speed was only about the speed of sequential reads on a HDD. MapReduce was the way to do it.
- [Evolving Jupiter: Google Data A look back at the evolution of the Center's network | Official Google Cloud Blog](https://cloud.google.com/blog/ja/topics/systems/the-evolution-of-googles-jupiter-data-center-network?hl=ja)
- ![image](https://storage.googleapis.com/gweb-cloudblog-publish/images/1_Jupiter.1000062220000793.max-2000x2000.jpg)
- > How many 100GbE NICs can you point to via proprietary chips that are not available out there, like 25GbE? It's a world like that.
- > tokoroten Computing services have changed, but has the impact even been felt in "programming languages"?
- > kumagi There's about as much difference as MapReduce becoming SQL, but the language talk is definitely a bit off.

> shibukawa And then there's the time travel debug.

> kumagi In terms of ML programming paradigm change, supercomputer-like supercomputing has fallen into the direction of using strong BLAS via numpy instead of writing craftsman's work in FORTRUN.

> [@mattn_jp](https://twitter.com/mattn_jp/status/1613822684311465984?s=20&t=Q2e46V8DlyTjFZTEyv9dRQ): Vim has implemented vim9script, a processing system 10 times faster than Vim script which is 10 times faster than Vim script. (sad no one is interested)

> [@nakayoshix](https://twitter.com/nakayoshix/status/1613794219088572418?s=20&t=Q2e46V8DlyTjFZTEyv9dRQ): It is important to note that F# is talked about continuously with async/await and record type. I think it's important to note that F# is mentioned in succession in async/await and record types.
> The async syntax is now commonplace in C#, JavaScript, Python, and other languages, but F#'s greatest feature is that it is built on a more generalized framework of computation expressions (async expressions).

> [@igrep](https://twitter.com/igrep/status/1613723086725210112?s=20&t=Q2e46V8DlyTjFZTEyv9dRQ): @nishio It's a minor and relatively recent modification, so I'm not sure how widespread it is. But GHC's RecordDotSyntax [https://t.co/MlPQxlouZT](https://t.co/MlPQxlouZT) and LinearTypes [https://t.co/6k32GGUul5](https://t.co/6k32GGUul5) are pretty big changes around here.
- > [@nishio](https://twitter.com/nishio/status/1613761154186383361?s=20&t=kOZtOzEqBBq-L04NVi9-bg): @igrep The former would make users of other languages say "couldn't you?" but the latter is great. This one seems too far ahead to be understood...

nishio
- ES2015 Arrow functions (changes in the treatment of this due to)
- Python, with some details.
    - asyncio
    - matrix multiplication operator
        - <img src='https://scrapbox.io/api/pages/nishio-en/tokoroten/icon' alt='tokoroten.icon' height="19.5"/>
            - In terms of making the language easier to use and develop, operator overrides
            - Override numpy matrix operations for convenience
    - walrus operator
        - > [@usopyon](https://twitter.com/usopyon/status/1613510676928172033?s=20&t=L68AEmRVwi29iEpEi2eDdg): @nishio Python's walrus operator is a language spec. Maybe not so much, but I think it was a rather big event, even the development structure changed because of this discussion: [https://t.co/YJiCwzLcSM](https://t.co/YJiCwzLcSM)
    - async generator
    - Structural Pattern Matching
    - Or is it?

~~~

> _3F_2 VSCode appeared

> hajimehoshi 2013 is the time of Go 1.1 or something?

> tokibito TypeScript is also about 2013
- > hajimehoshi TypeScript didn't exist in 2012 / just barely


> tokibito Python is growing tremendously, but...
- 2013 [C Language Moves to #1 in Popularity - April Programming Language Popularity | TECH+](https://news.mynavi.jp/techplus/article/20130412-a162/)
- > ![image](https://gyazo.com/e28b630f956ef9a9f2d0fc39a1ff59a5/thumb/1000)
- 2023 [TIOBE Programming Languages Ranking, C++ will make the most progress in 2022 | TECH+ (TECH+)](https://news.mynavi.jp/techplus/article/20230110-2558740/)
- > ![image](https://gyazo.com/dca9bdb97590a85752bb37330b7c733c/thumb/1000)


> shibukawa 2013, I guess it was the time when the competition for js engine development was raising the performance among scripting languages.
- > On the other hand, flash is gone, silverlight is gone, java applet is gone..,
- > Galaga is gone too.

> tokibito Docker came out about 10 years ago?
- > shibukawa exactly 2013 [https://docker-docs.netlify.app/release-notes/docker-engine/](https://docker-docs.netlify.app/release-notes/docker-engine/)

>  hajimehoshi When did Wasm come out?
- > shibukawa wasm's predecessor asm.JS seems to be 2013

>  tokibito If it's linguistic, there seems to be a lot more examples of Rust being used.
- > Rust has quite a history?

> shibukawa Also, Spectre/Meltdown is a change to the language runtime, or a change to the language runtime.

> tokibito Ten years ago there was a lot of excitement about language features, but lately it's more about code generation and tools.

> shibukawa I wonder if it is a significant trend that JavaScript specification is now under community jurisdiction.

> tokibito The development environment for embedded devices could be richer, like MicroPython.

> hajimehoshi There is a modest change in C# where the variable captured in foreach is now a different variable for each loop instead of using the same reference around, and Go is following suit [https://github.com/golang/go/discussions/](https://github.com/golang/go/discussions/) 56010

> Bonsai Craftsman I guess it's only been in the last 10 years that it's pretty much established to write code down to the infrastructure.
- > tokoroten IaC~
- [Infrastructure as Code - Wikipedia](https://ja.wikipedia.org/wiki/Infrastructure_as_Code)
    - 2006 [Amazon Elastic Compute Cloud - Wikipedia](https://en.wikipedia.org/wiki/Amazon_Elastic_Compute_Cloud)

> tokoroten Democratization of machine learning, I guess...
> scikit-learn has lowered the cost of learning dramatically by aligning its APIs
> Until then, each algorithm had its own API and the learning cost was too high.

<img src='https://scrapbox.io/api/pages/nishio-en/tokoroten/icon' alt='tokoroten.icon' height="19.5"/>
- Serverless like aws lambda
    - I want to do calculations with a specific program, not have a server.
    - There were many use cases where the server had no state or files, and only communication and computation were used.
> shibukawa I think that Google App Engine, Lambda, Cloud Run, serverless, and FaaS have become much more popular. Well, if I say that the programming mindset is equivalent to CGI, that's true.


<img src='https://scrapbox.io/api/pages/nishio-en/tokoroten/icon' alt='tokoroten.icon' height="19.5"/>
- Whether or not smart contracts are considered a language.
- The first Raspberry pi came out in 2013
    - Personally, I am aware that the diversity between the top and bottom of what is called "PC" has increased.
- Generalization of GPGPUs. Especially tensorflow and nvidia sets.
- Reduce release costs with cloud and IaC → DevOps

[https://b.hatena.ne.jp/entry/s/scrapbox.io/nishio/この10年のプログラミング言語の変化](https://b.hatena.ne.jp/entry/s/scrapbox.io/nishio/この10年のプログラミング言語の変化)
- > otoan52 The ones that don't seem to be out much are GC-less modern languages like Rust, practical use of columnar DBs, Linux in Windows, around privacy issues, and visual programming like scratch being introduced to education.
- > n314 Type checking and functionalization seem loosely related, but I'm not sure. The process of changing the state of an object is now divided into detailed functions, which makes it even more difficult without the type.
- > roshi I'm sure that Rust's ownership and lifetime will be adopted by other languages in the future (though I hope it will be a bit simpler). Also, I'm personally interested in Nix, although I don't think it will become a major player (sorry).
- > xlc Non-blocking IO is the biggest change for me, since async/await is the only way to have non-blocking IO. I don't care about strictness, so it is easier to write without types.
- > topiyama As an embedded developer, I think the advent of Rust and the spread of gcc -O3. I feel that GUI programming can now be made in textile when I see C# code that is written with async task functions for everything.
- > nunulk I was personally interested in de-object oriented (or rather de-unitary paradigm), like Clojure's protocol or Rust's trait is currently considered to be a good idea.
- > oinume Interesting. I guess schema-driven development has become mainstream in the web world.
- > havanap I think there is something dataflow oriented (stream, immutable, visual, tensor, ETL)

---
This page is auto-translated from [/nishio/この10年のプログラミング言語の変化](https://scrapbox.io/nishio/この10年のプログラミング言語の変化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.