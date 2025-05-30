---
title: "OOPL and Subtyping"
---

> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382325195994660867): kmizu is right, if you look at the current major OOPLs, the only essential difference between them and non-OOPLs is "the existence of subtyping", and in mainstream In mainstream languages, subtyping and implementation inheritance are closely intertwined, and it is generally said that implementation inheritance should not be used because it easily destroys encapsulation. I'd love to read an article that successfully discusses this point in defense of OOPL.

It is not a feature of OOPL that "it is convenient that data structures and procedures can be defined together."
- > [megascus](https://twitter.com/megascus/status/1382325803451523085): it would be useful to be able to define data structures and procedures together! I think it's just about the best way to do it.
- > [gakuzzzz](https://twitter.com/gakuzzzz/status/1382326369061801985): you can do that with non-OOPL ......
- > [kmizu](https://twitter.com/kmizu/status/1382698355902533643): struct + procedure all together is already named abstract data type (so it's a concept that comes up even in the non-OOP world).
- > [kmizu](https://twitter.com/kmizu/status/1382698986205765635): The concept of abstract data types predates the term OOP by a long time, and in fact, SML has a syntax for defining them called abstype. So it can be done in non-OOPL, right? (If not, is it easier to write chains in mainstream OOPL?) (If not, is it easier to write a chain in mainstream OOPL?
- > [gakuzzzz](https://twitter.com/gakuzzzz/status/1382740941195206663): Ah, I see, SML's abstype can limit the visible range of data constructors without using the module mechanism or anything. I didn't know about this feature, thanks!
- > [kmizu](https://twitter.com/kmizu/status/1382896708644794368): The concept of abstract data types has a longer history than OOP (a term I am not familiar with), and according to the English Wikipedia, Liskov proposed it in 1974 According to the English Wikipedia, the concept of abstract data type was proposed by Liskov in 1974. [Abstract data type - Wikipedia](https://en.wikipedia.org/wiki/Abstract_data_type)

Difference from abstract data type is inheritance and subtyping
- > [nagise](https://twitter.com/nagise/status/1382828660068024321): the part "structure + procedure together is already named abstract data type (so it's a concept that comes up even in the non-OOP world)" If that is the abstract data type, what is the "increased part" in OOP? So I'm reconsidering.
- > [kmizu](https://twitter.com/kmizu/status/1382898009655050243): As for history, if abstract data types = OOP, you wouldn't need a new word, and in fact, abstract data types have no inheritance or subtyping.

Stroustrup also says that unlike abstract data types, OOP is unique in its ability to distinguish between general and special attributes (subtyping) and to use it for new purposes without having to rewrite its definition (e.g., by inheriting and adding methods)
- > [zehnpaard](https://twitter.com/zehnpaard/status/1383177329254531072): Incidentally, Stroustrup's The C++ Programming Language (1986) seems to contrast Abstract Data Type and contrasts it with Object Oriented Programming.
- > [zehnpaard](https://twitter.com/zehnpaard/status/1383177654166228994): I am drawing from Stroustrup's "History of C++: 1979-1991".
- > "An abstract data type defines a sort of black box. Once it has been defined, it does not really interact with the rest of the program. There is no way of adapting it to new uses except by modifying its definition. ...
- > [zehnpaard](https://twitter.com/zehnpaard/status/1383177730448056321): "The problem is that there is no distinction between the general properties of any shape (a shape has a color, it can be drawn, and so forth) and the properties of a specific shape (a circle is a shape that has a radius, is drawn by a circle-drawing function, and so forth). ...
- > [zehnpaard](https://twitter.com/zehnpaard/status/1383177807317065729): "Expressing this distinction and taking advantage of it defines object-orientedprogramming. A language with constructs that allows this distinction to be expressed and used supports object-oriented programming. Other languages don't."


Unorganized---

> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382321740685078530): The concept of instantiation is indeed confusing to the uninitiated. I remember myself being confused because I couldn't distinguish between when the class definition is interpreted and when the main process is executed. I wonder if it would be easier to understand if it were a data constructor in a non-OOP language. Would it cause similar confusion?
> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382322533039415299): In the case of Java, the classification of compile time and run time is (not exactly) easy to organize your thoughts, but in Ruby In Ruby, it's easy to get confused because class definitions are interpreted at runtime, and you can mess around with metaprocessing. ......
> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382322945075257347): I knew OOP was an easy paradigm to shoot yourself in the foot with today: ......?


> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382328498329505792): OOPL has the advantage that it is easier to realize open recursion than non-OOPL, but I'm not sure if you've written a lot of code that utilizes such open recursion in real life. However, in reality, it's not so easy to write code that utilizes such open recursion a lot, is it?
> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382333367484514304): If the OOP paradigm is inherently of little merit, why bother teaching a concept that is difficult for beginning students to understand? A feeling like this comes to mind: ......
> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382333944658497538): can someone give me some statistics on whether the class-instance concept or the ADT concept is easier for a beginning student to understand? ......?


> [zehnpaard](https://twitter.com/zehnpaard/status/1382330112008392705): this statement from OCaml's discuss sums it up well
> 「Basically, when you use the inheritance relation you’re invoking two orthogonal things at once, the inheritance of implementation (aka subclassing) and the refinement of type/interface (aka subtyping).」
> [What is the "right" way to add constraints on a type, to handle recursive structures with variants and to combine fragments of types? - Learning - OCaml](https://discuss.ocaml.org/t/what-is-the-right-way-to-add-constraints-on-a-type-to-handle-recursive-structures-with-variants-and-to-combine-fragments-of-types/2810/29)


> [todesking](https://twitter.com/todesking/status/1382329768016629761): After doing Rust, I've come up with a theory that if you have typeclasses and ADT, you don't need subtyping.
>  Well, there are a few situations where you want to dynamically dispatch, so you have to have dyn, but the usage is pretty limited. ......
> [todesking](https://twitter.com/todesking/status/1382342306804600836): Rust's impl T{} is simply namespace separation, but I have a feeling that this is most of the joy I feel in OOP. I think this is what makes me happy in OOP. I like the user-centric approach when I can associate processing with data and complementation is good. ......
> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382344103782879236): I can see the benefits like affinity in the IDE in this area.
>  but if the IDE can use a pipe operator to find candidate completions from the type, or something like that, we'll get a substantially similar experience?
> [todesking](https://twitter.com/todesking/status/1382345302326222849): I think this "it's more intuitive to start writing with nouns" is just my OOP brain, and I may feel differently when I am proficient in FP. No, but don't you think of the object of the operation first?
> [gakuzzzz](https://twitter.com/gakuzzzz/status/1382346402487934985): we want to start writing from nouns and the order of processing from left to right, so let's put pipe operators in all languages!


> [kmizu](https://twitter.com/kmizu/status/1382991587068682240): By the way, this is actually the first time I've read "Programming with abstract data types" in its entirety (?). I've read "Programming with abstract data types" for the first time, and I see that there is a reference to SIMULA'67, which is chronologically ahead of SIMULA. But SIMULA doesn't have the data hiding feature, and that's the difference.
- ![image](https://gyazo.com/2974a5e9dd44dc4c6018b7974c92fd99/thumb/1000)
- [Programming with abstract data types | ACM SIGPLAN Notices](https://dl.acm.org/doi/10.1145/942572.807045) Barbara Liskov, Stephen Zilles, 1974

> [TakashiSasaki](https://twitter.com/TakashiSasaki/status/1382902897290059777): I wonder if we can sort this out in terms of polymorphism: OOPL is polymorphic requiring subtyping polymorphism. How to deal with parametric and ad hoc polymorphism is mixed.

> [cedretaber](https://twitter.com/cedretaber/status/1382331764241178624): I think the advantage of non-OOPL is that you have to have a good design theory to put the data structures and procedures together, whereas with OOPL you can just follow the standard way of writing the language. I think the advantage of OOPL is that you just follow the standard way of writing the language and you can keep it all together. ......
> [cedretaber](https://twitter.com/cedretaber/status/1382332115421863943): people who have become too comfortable with the idea of abstract data types do it without being told, so they think "OOPL is unnecessary"! I think there are many people in the world who don't, though I analogize (and there are sections where I feel that way, too).





---
This page is auto-translated from [/nishio/OOPLとサブタイピング](https://scrapbox.io/nishio/OOPLとサブタイピング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.