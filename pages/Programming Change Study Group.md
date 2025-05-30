---
title: "Programming Change Study Group"
---

2023-02-10
- I tweeted on "[[Changes in programming languages over the past decade]]" while waiting for an eye exam the other day, and the response was more than I expected.
    - The above page, summarized in bullet points, has been viewed over 10,000 PV.
- I put this together in [Kozaneba digital stationery to organize your thoughts
        - [[Kozaneba:Changes in programming languages in the last decade]]
    - (This is also a test of the easy line-drawing function I added to Kozaneba last week.)
- Today I'll explain it in a nutshell, then explain the important points with code.

## First, the big picture
.
- ![image](https://gyazo.com/69c8676477b96050ae696d51b7206796/thumb/1000)
    - This is the real big picture
- ![image](https://gyazo.com/b4784d52c52797355c8566cf07125941/thumb/1000)
    - Zoom a little
    - We started out with the question, "What are the major changes in programming language specifications that have occurred in the last 10 years?
    - However, looking at the opinions gathered, there are some that do not fit within the framework of "programming language specifications.
        - Biggest: Browser
        - Other machine learning and container technologies have had a major impact on the activity of programming in the last decade.
    - Before we get into the programming language specifications, let's take a quick look at this first

## Browser
- ![image](https://gyazo.com/93b2e5ee8df55544778ed45a0f64b700/thumb/1000)
- The iPhone 5S came out 10 years ago in 2013.
    - In the decade that followed, smartphones became widespread.
    - More work to create smartphone apps.
    - On the other hand, making separate versions for iOS and Android is expensive
    - A movement to do it with WebView (browser component) is born.
- At the same time, something similar was happening in the desktop environment.
    - Electron appeared in 2013
    - It is expensive to create separate GUI applications for Windows, Mac, and Linux.
    - A movement to realize this with the Chromium rendering engine and Node.js is born.
    - That this is a realistic option was really demonstrated in Microsoft's IDE Visual Studio Code (2015), which is built on Electron
    - If something as complex as an IDE can run with decent performance, then why not this?
- What has happened in the last decade
    - Technological Advances in Browsers
    - This is not the narrow scope of "providing web services".
    - It affected a wide range of "GUI offerings."
- Q&A
    - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Has the relative importance of the OS decreased?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The browser has taken away a lot of the "operation" of the OS as a "system that performs operations.
        - I recently bought an electronic instrument called InstaChord, and when I did a firmware update for it, it no longer requires a native app, but instead allows serial communication directly from the browser to USB-connected peripherals.
        - > Web Serial API provides a way for websites to receive data from and send data to serial devices. The target can be a device connected via a serial port, or a USB or Bluetooth device acting as a serial port. [MDN](https://developer.mozilla.org/ja/docs/Web/API/Web_Serial_API)
        - Ten years ago, you would have been told to "run this exe file in Windows", but now you can do things that have nothing to do with the OS.

return one's gaze
- ![image](https://gyazo.com/2b3acb8b22ae82979a0687e63a677081/thumb/1000)

    - There are three big topics.
        - I want to be able to do what I want.
        - async/await
        - Avoid destructive renewal
    - There are many more factors involved with regard to programming styles that avoid destructive updates.
        - I haven't fully organized it at this stage of preparing this lecture material, but let's take a quick look at it.
        - (Note: Although "de-object-oriented" is prominently displayed in the figure, we chose to avoid this because it is a vague phrase that people have different images of what they imagine by the term "object-oriented.)

GUI development and moves to avoid destructive updates
- The story of programming styles that avoid destructive updates is quite related to the GUI story.
- ![image](https://gyazo.com/770ae9733b7c4e687a5bdd3a71a8d588/thumb/1000)
- GUI used to be an important application area for object-oriented
    - Individual buttons are instances of the Button class, individual labels are instances of the Label class, ...
    - GUI was an easy application domain to understand the benefits of object orientation in a straightforward manner.
    - But as of a decade ago, there were signs of change in its use.
        - > There is a movement around Java to avoid "inheritance for the purpose of implementation reuse. For example, the Abstract Window Toolkit (AWT) released in 1995 had a rule of "inheritance and overriding various methods. However, the Standard Widget Toolkit (SWT) used by Eclipse and others now has a "do not inherit" rule.
        - >  What developed instead was the concept of "delegation."
            - ( [[Technology Supporting Coding]]  p.222)
            - (Side note: I made the mistake of writing "now" in the text, readers today in 2023 may not understand Eclipse...)
    - 2019, React "Hooks API"
        - Programmers do not use classes when defining stateful GUI components
        - Use a function without state instead.
        - The Hooks API is the mechanism that allows this function component to do the same things as the class component.
        - We will consider the function component to be the standard usage.

Hooks API and Function Components
- GUI components with state
    - Consider, for example, a switch that turns on and off when clicked.
    - This is an "on/off" state
- When defining a component in a class, naively, the state of the component is held as a member variable
- In the function component, the React side has the state
    - Get the current value of the state and setter by a mechanism called the Hooks API
    - ![image](https://gyazo.com/a16e89398f997015f385a40f8fed22ef/thumb/1000)
    - When updating the state, call its setter
    - By letting React handle state changes, the component no longer has state, so functions are better.
- What makes me happy about this?
    - React's side can know "that the state has been updated".
        - Implementation style where classes rewrite member variables makes it difficult for the framework to detect changes
        - Especially with past object-oriented thinking, it tends to be "let's make the members private so they can't be seen from the outside".
    - React also knows "components that refer to that state".
        - Only components that have read that state will behave in a way that depends on that state.
        - Only this component requires redrawing
        - ![image](https://gyazo.com/34daca8ccd87549b9ce7fa42076fabbd/thumb/1000)
        - React calls the target function component and redraws with the result
        - Q: Describe only the method of state transitions, without taking responsibility for managing the state?
        - A: Well, yes. If each object manages its own state, it would be chaotic. That's why we're talking about putting it all in one place in React.
    - Function components can be designed as stateless functions that get their latest state from the Hooks API and return a rendering result (virtual DOM)
        - If the programmer writes it properly, it will be a function with no side effects.
        - That is, you don't have to call it the same number of times as the number of state updates.
        - It doesn't even have to be synchronous with state updates.
        - For example, if you write code that toggles on and off 101 times when a button is pressed, the rendering will only be performed once, and so on.
        - This is important for performance, so let's all use the function component to be able to do this, and then it will be faster.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q: It is also common to create web apps without state, but with state in the database.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A: Hmmm, that seems to be a different thing you are referring to by the word "state".
        - There are "persistent states" and "non-persistent states" in the state.
        - State" in GUI includes which text box has the focus.
        - It is not practical to send all state on the browser to the database
        - There must also exist a state that is only on the browser
    - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>I can say that even in the React model, there are local variables in the function component and the detailed state is held there.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A local variable of a function is not accessible after exiting the function, so you don't really think of it as a state, do you?
        - There could be a component that is not shown on the screen that watches for updates with respect to some of the React state and writes to the database when there is an update.
        - When a state is updated, it is the programmer's choice as to which of them are stored in the database and which are not.
        - Since all the state is gathered in React, the design that when the "state you want to persist" is updated, it goes to write it to the database will be easier to implement than if the components have their own state in pieces.
    - Add specific examples
        - In Kozaneba, moving elements by drag-drop is all saved to the database at the time of drop.
        - In Kozaneba, clicking on an element opens a context menu
        - This "which menu is open where" is also a "state" that React manages and affects the rendering of the GUI
        - If saved, it can be restored at the next startup in exchange for the cost of writing the database.
        - I don't think this should be stored in a database. I don't see any benefit to the cost.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q2: Is it preferable to have no state not because of reuse but because of the wider application?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A: I want to make it loosely coupled.
        - Redrawing is necessary if the state changes
        - But that's where synchronous calls are too tightly coupled.
        - Do we actually need that tight coupling?
        - The time resolution of the human eye is low, so a slight display refresh delay on the browser is not a problem.
        - Some updates can be made asynchronous so that they are no longer needed.
        - So I wanted to separate "state rewriting" from "redraw triggered by state rewriting".
        - I suspect this was the biggest motivation for the inclusion of the Hooks API.

Reactive Programming System Flow
- ![image](https://gyazo.com/fa53b2b0babf79eda645d5b80af0f684/thumb/1000)
    - Varying names, shaky concepts.
    - I realize I don't know enough about it to explain it, so I'll just take a quick look at the facts this time.
- 2007 C# LINQ(Language INtegrated Query)
c#

```
// Specify the data source.
int[] scores = { 97, 92, 81, 60 };

// Define the query expression.
IEnumerable<int> scoreQuery =
    from score in scores
    where score > 80
    select score;

// Execute the query.
foreach (int i in scoreQuery)
{
    Console.Write(i + " ");
}

// Output: 97 92 81
```

    - [Language-Integrated Query (LINQ) (C#) | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/)
    - Write SQL-like query language for arrays and other collections
- 2009~2011 C# Rx(ReactiveExtensions)
    - LINQ thinking applied to asynchronous processing
    - As an extension of the trend to treat databases and arrays as "similar" in a unified manner, the concept of streams was used to describe asynchronous processing
    - [reactive Reactive Framework - Scaling Asynchronous Client/Server Links with Reactive Extensions | Microsoft Learn](https://learn.microsoft.com/ja-jp/archive/msdn-magazine/2016/june/reactive-framework-scale-asynchronous-client-server-links-with-)
- 2014 Java Stream API
java

```
 int sum = widgets.stream()
           .filter(w -> w.getColor() == RED)
           .mapToInt(w -> w.getWeight())
           .sum();
```

    - [Stream (Java Platform SE 8)](https://docs.oracle.com/javase/jp/8/docs/api/java/util/stream/Stream.html)
    - Of course, each method call does not create a large temporary object
- 2020 Java / C#: Record type
    - [Records - C# reference | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/record)
c#

```
public record Person(string FirstName, string LastName);
```

    - [record-class](https://docs.oracle.com/javase/jp/15/language/records.html)
java

```
record Rectangle(double length, double width) { }
```

        - > The record class declares a set of fields, and the appropriate accessors, constructors, equals, hashCode and toString methods are automatically created. The fields are FINAL because this class is intended to function as a simple "data carrier".
        - > This concise declaration is equivalent to the following standard classes
java

```
public final class Rectangle {
    private final double length;
    private final double width;

    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    double length() { return this.length; }
    double width()  { return this.width; }

    // Implementation of equals() and hashCode(), which specify
    // that two record objects are equal if they
    // are of the same type and contain equal field values.
    public boolean equals...
    public int hashCode...

    // An implementation of toString() that returns a string
    // representation of all the record class's fields,
    // including their names.
    public String toString() {...}
}
```

    - Q: Very simple struct?
    - A: The major difference between STRUCT and STRUCT is that destructive renewal is prohibited.
    - Q: Can't I just assign first? object that simply transfers data?
    - A: Yes. Until now, the means to create such objects could not be realized without writing a lot of code.
        - In the course of development in 2009 or so, Java and C# changed because "it's not right that the object conveyed here is destructible" and "we need a way to easily apply an indestructible object".
    - Q2: Do you mean const data?
        - A2: I would say so.
- Q3: I think only mutexes will have the desire to have variable
    - A: I haven't followed anything around Mutex, I don't know.

- The same way the function component returned a virtual DOM in React that I mentioned earlier.
    - Avoid human-disruptive updates to the browser's raw DOM
    - Return virtual DOM = create and return a new object
    - The work of destructive updating to reflect it in the raw DOM is done by React, not humans.
- Brief summary
    - Describes things as a series of functions that take an immutable, final "data carrier" object and return a new object
    - Instead of destructively rewriting objects, a trend was born to use such methods
    - A way to describe it effortlessly went into the language side.

[[Promise]] and [[async/await]]
- This is significant as it relates to asynchronous processing
- ![image](https://gyazo.com/aeda341c5e9ddd54bb6bffe639b64f32/thumb/1000)
- async function returns Promise, await blocks until Promise is resolved
- Promise (or future) is an old idea.
        - [[History of Promise]]
- The 1997 E language was implemented as it is used today.
- C#, Python, ECMAScript, Rust, etc. have successively adopted this approach over the past decade
- What is Promise?
    - The value is returned immediately without blocking when asynchronous processing is performed, which is Promise
    - The promise, "I'll provide the value later."
- If you'd rather see definitions than metaphors, this is for you.
    - [Promises/A+](https://promisesaplus.com/)
    - > An open standard for sound, interoperable JavaScript promises—by implementers, for implementers.
- Promise has three states
    - ![image](https://gyazo.com/607ca5a38fb90ddbb4ef57eae202abb8/thumb/1000)
- then method
js

```javascript
promise2 = promise1.then(onFulfilled, onRejected);
```

- ![image](https://gyazo.com/8834e1646f07cd1ee5ce56e1196a27cb/thumb/1000)
- Other ways of expressing asynchronous processing were passing callbacks or registering event handlers
js

```javascript
// callback style
do_something(params, on_success, on_error);
```

js

```javascript
r = new Request(params);
r.on_success = on_success;
r.on_error = on_error;
r.send()
```

    - In the past, JavaScript used `XMLHttpRequest` to hit APIs of other services, which was a style of using event handlers
        - [Using XMLHttpRequest - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)
        - This was troublesome, so third-party libraries tried, and the style of using Promise became the de facto standard.
        - After that, a Promise-using style API was standardized.
            - [Fetch API - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
    - What was the trouble? Many things:.
        - Writing what you want to do after asynchronous processing first in the source code is confusing the flow of thought.
        - Error handling when asynchronous process 1 is performed, followed by asynchronous process 2 using the result of asynchronous process 1, and so on.
            - It is defined this way at [Promises/A+](https://promisesaplus.com/) so it can be written in one place
                - > If `onRejected` is not a function and `promise1` is rejected, `promise2` must be rejected with the same reason as `promise1`.
            - In the style of callbacks and event handlers, you would make it a named function and specify it in `on_error` here and there

- [[incremental typing]]
- ![image](https://gyazo.com/6ca93fa1196d2124f7c7ecc0a484c065/thumb/1000)
- A dynamically typed language said "I still want types" and introduced [[incremental typing]] (Gradual Typing)
- Example
python

```
def foo(x: int):
    y: str = x  # NG
```

    - `error: Incompatible types in assignment (expression has type "int", variable has type "str")  [assignment]`
- I don't want to write type declarations for everything.
    - So what is the one that doesn't have a type declaration written on it?
    - implicit any type
- Is the any type like Java's `java.lang.Object` type?
    - No, sir.
python

```
def foo(x: int):
    y: object = x  # OK
```

python

```
def foo(x: object):
    y: str = x  # NG
```

    - `error: Incompatible types in assignment (expression has type "object", variable has type "str")  [assignment]`
    - Attempting to assign a value of type Object to a value of type String (implicit downcasting) is not allowed.
        - This is normal type behavior.
        - That ANY is a special type that can implicitly perform both upcasting and downcasting.
        - ![image](https://gyazo.com/8e18254db69518ccc099cf724fdb1f86/thumb/1000)![image](https://gyazo.com/802836aae4333668c25a40bf1f6b5120/thumb/1000)
    - In TypeScript, the types corresponding to these two behaviors are unknown and any
ts

```typescript
const take_number = (x: number): void => {};
{
  let x: any;
  take_number(x);  // OK
}
{
  let x: unknown;
  take_number(x);  // NG
}
```

        - `Argument of type 'unknown' is not assignable to parameter of type 'number'.`
- Current Python (mypy) does not guess the return type.
python

```
def foo(x: int):
    return x

print(typing.reveal_type(foo))
```

    - `note: Revealed type is "def (x: builtins.int) -> Any"`
    - This is a different behavior from TypeScript
        - ![image](https://gyazo.com/485b1234b2e40fa0839bf9379e8ddce3/thumb/1000)
    - It is expected that humans will explicitly state this
python

```
def foo(x: int) -> int:
    return x

print(typing.reveal_type(foo))
```

        - `note: Revealed type is "def (x: builtins.int) -> builtins.int"`

Nomenclatural and structural typing
- ![image](https://gyazo.com/dbb2e686e58f68db832dcc6ab1d0ad05/thumb/1000)
- from [[Draft addition to "The Difference Between Named Type Systems and Structural Type Systems"]]
    - ![image](https://gyazo.com/df9ab60204aa68fff5318dccb0c6a6da/thumb/1000)
    - Just having a row of 0s and 1s in memory does not tell you whether it is an integer or a floating point number.
    - Static typing is used to attach information such as "this is an integer" to a variable by declaring it as `int n;` or something like that.
    - Dynamic typing attaches the information "this value is an integer" to the value.
- There are two approaches to this "meta-information on variables"
    - Schools that use structure to make decisions
    - School of judging by name
    - ![image](https://gyazo.com/d5e7ab2fc66dd5cecc55a95e5667d199/thumb/1000)

- C++, born in 1985, and Java, born in 1995, used a nominal type system.
    - Different names are not interchangeable.
        - Declare subtype relationships with `extends` and `implements`.
    - Since these two languages have become so major, many people are probably familiar with this approach.
- On the other hand, structural type systems were more dominant in type theory research.
    - As a result, when designing statically typed languages to generate JavaScript, we ended up with a mixture of languages that adopt a naming type system with reference to Java and other languages (such as Dart) and languages that adopt a structural type system with reference to type theory (such as TypeScript).
- Example in TypeScript
TypeScript

```
type T1 = {
    x : number
}

type T2 = {
    x : number
}

let a: T1;
let b: T2 = {x: 1};
a = b; // OK
```

    - The `{x: 1}` part of `let b:T2 = {x: 1}` in this code is an unnamed object type.
    - This has the same form as both T1 and T2, so it can be substituted without error.
- An example of giving different names to the same type of structure and expecting it to be distinguished.
        - [[True story due to misunderstanding of nomenclatural and structural types]]

Rust: Ownership/Lifetime
- Rust was released in 2010.
    - Rust 1.0 was released in 2015
    - Rust remained #1 in "Developers' Most Loved Programming Languages" by Stack Overflow from 2016-2020
- Rust is said to be characterized by the concepts of ownership and lifetime, but ownership is not a concept unique to Rust
    - std::unique_ptr` is adopted in C++11
    - This means "the only pointer pointing to the allocated memory."
    - When this pointer exits the scope, there will be no way to reference that memory, so it can be freed.
- C++ is bound to be compatible with past code: simple notation for conventional behavior, new notation for new behavior.
    - Rust escapes this compatibility bind by becoming a different language.
rust

```
let x = String::from("hello");
let y = x;
println!("x: {}", x);  // NG
println!("y: {}", y);
```

    - `error: borrow of moved value: x`
    - x and y are unique_ptr in C++, and the move is done with `y = x`.
    - C++ usually tries to copy references.
        - Use `std::move` to express "we intend to move, not copy".
        - The "right side value/left side value" distinction was added in C++11 to achieve this without breaking existing code
            - If a value is a right-hand side value, then it is not used in the future and should be moved, not copied.
            - Thus, a move constructor that accepts right-hand side value references is added
        - std::move casts to a right-hand side value reference so that the move is performed
- In C++, it is not the compiler's job to "take care not to dereference a pointer that is not valid".
    - Human care or check with static analysis tools.
    - In Rust, the compiler checks it.
    - I tried to do the same thing as the above Rust code in C++ and got a Segmentation fault.
cpp

```cpp
#include <iostream>
#include <string> 
#include <memory> 

int main () {
    std::unique_ptr<std::string> x = std::make_unique<std::string>(std::string("abc"));
    std::unique_ptr<std::string> y;
    y = std::move(x);
    std::cout << *y << std::endl;
    std::cout << *x << std::endl;  // here
}
```

output

```
abc
Segmentation fault
```

    - In this code, x is null so that it cannot be read or released by mistake
- 'Isn't it the same as RAII to be released when you get out of scope?' What's unusual about that?" I thought.
    - I think the important thing is more the change in the default behavior of "move when writing simple".
    - Example
rust

```
let x = String::from("hello");
foo(x);  // move
println!("x: {}", x);  // NG
```

        - In this example, x moves at the function call, so it can't be used after that.
        - The compiler will follow the move by assignment or function call and release at "the point where it exits the scope without moving".

Concept of Lifetime
- Scope for which the reference is valid
- Since many people now associate the word scope with a block on the source code (since they have come to interpret it as lexical scope), calling it scope causes confusion.
    - The feature that references made in the caller are also valid in the destination is similar to dynamic scopes in Perl and other languages.
rust

```
let x;
let y;
// println!("x: {}", x);  // NG
// error[E0381]: used binding `x` is possibly-uninitialized
x = String::from("hello");
println!("x: {}", x);  // OK
y = x;
// println!("x: {}", x);  // NG
// error[E0382]: borrow of moved value: `x`
```

    - The use of x before initialization and after move is shown to be a compile error
- lifetime designator
    - Notation to tell when the compiler cannot guess the lifetime.
    - Many people seem to be confused by the unique notation.
        - This is the act of assigning metadata to a variable, so in a broad sense "type"
        - The lifetime specifier "must be named" and is conventionally named `'a`, the same as naming a type variable `T` in generics.
        - The name itself does not have meaning, but the same name is used in multiple places to express the relationship between the elements.
    - Example 1
        - Multiple references with the same name lifetime specifier make their common subset lifetime
rust

```
fn longest(x: &str, y: &str) -> &str {  // NG
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

error

```
error[E0106]: missing lifetime specifier
  --> src/main.rs:14:33
   |
14 | fn longest(x: &str, y: &str) -> &str {
   |               ----     ----     ^ expected named lifetime parameter
   |
   = help: this function's return type contains a borrowed value, but the signature does not say whether it is borrowed from `x` or `y`
help: consider introducing a named lifetime parameter
   |
14 | fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
   |           ++++     ++          ++          ++
```

    - Example 2
        - static lifetime
            - Lifetime specifiers named in advance by the system
            - It represents "lifetime across the entire program."
rust

```
fn dangle() -> &String {
    let s = String::from("hello");
    &s
}
```

error

```
error[E0106]: missing lifetime specifier
  --> src/main.rs:22:16
   |
22 | fn dangle() -> &String {
   |                ^ expected named lifetime parameter
   |
   = help: this function's return type contains a borrowed value, but there is no value for it to be borrowed from
help: consider using the `'static` lifetime
   |
22 | fn dangle() -> &'static String {
   |                 +++++++
```

        - This is inherently no good.
            - Because s is released when exiting the function.
            - But the compiler decides, "Well, if I change it to a constant, I can make the whole program lifetime.
                - The result is an error message that's two steps ahead of the rest of us.
        - If you make it so that the compiler doesn't know if it can be made into a constant, you'll get a straightforward error message.
rust

```
fn dangle(x: &String) -> &String {
    let s = x.clone();
    &s
}
```

error

```
error[E0515]: cannot return reference to local variable `s`
  --> src/main.rs:31:5
   |
31 |     &s
   |     ^^ returns a reference to data owned by the current function
```


---
This page is auto-translated from [/nishio/プログラミングの変化勉強会](https://scrapbox.io/nishio/プログラミングの変化勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.