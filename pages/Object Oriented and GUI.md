---
title: "Object Oriented and GUI"
---

> [kis](https://twitter.com/kis/status/1391394299057774593): it's like object oriented to put data and processing together, but it's usually better to keep the data and processing separate!

> [nishio](https://twitter.com/nishio/status/1391395404705452033): early on in GUI programming, you were trying to put together data (such as button labels) and processing (code to be executed when the button is pressed). wasn't it useful (at least in Java, where functions were not first class)? Do something like extends JFrame implements MouseListener.

> [kis](https://twitter.com/kis/status/1391395696658370562): object oriented is useful only for GUI

> [nishio](https://twitter.com/nishio/status/1391395900908392457): But for JavaScript and other languages where functions are first class, I thought, "Why register an event listener when you don't have to do it as a method? I think it's a good thing that functions are now first class, so that the "code to execute when pushed" is "code to execute when pushed". I guess that's why functions are now first class, and the "code to execute when pressed" has changed from "processing" to "data".

> [kis](https://twitter.com/kis/status/1391398531739492353): I think in the case of JS, the DOM takes the role of the object, and there is no need to handle objects on the JS side anymore!

> [nishio](https://twitter.com/nishio/status/1391399294377201668): ah, I see. The tree of objects is given from outside the language (in HTML, the object tree description language), and you just describe operations on it, so you didn't need object orientation.

> [kis](https://twitter.com/kis/status/1391400592312967169): I feel that objects are necessary for component assembly, but not for application processing. Even in JavaFX, you can just annotate the methods and there is no need for objects or lambdas.

I was going to title it "Object-oriented is (at least) useful for defining GUI components," but React and others are moving away from class components, which in essence means that GUI components do not need to have "state updates" themselves, and it is better not to have them. In the end, I think that one aspect of object-oriented programming, which is to combine data and processes that destructively update that data, is considered old-fashioned in the modern world.

---
This page is auto-translated from [/nishio/オブジェクト指向とGUI](https://scrapbox.io/nishio/オブジェクト指向とGUI) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.