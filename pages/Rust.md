---
title: "Rust"
---

2015 Rust 1.0 released
Rust itself was released in 2010
Good to see what happened to C++ at the same time.
- C++11 in 2011
    - std::unique_ptr
        - If the pointer pointing to the allocated memory area can be guaranteed to be unique, it can be released when exiting the scope

C++ emphasizes maintaining compatibility with source code written in the past
- So even if you think "it would be better to unify with unique_ptr", you cannot do so
- That's where Rust was born.
    - A kind of [Nonfree methods will be favored.


- [[Proposed Technical Additions to Support Coding]]

- Before GC, reference count, mark & sweep, write from around?
    - Reference count and shared_ptr
    - The concept of [[lifetime]]?
- RAII, reference and borrowing checker?
    - I'm getting the feeling it's hard to do without RAII to talk about.
    - [https://ja.wikipedia.org/wiki/RAII](https://ja.wikipedia.org/wiki/RAII)
- C++11 move semantics
    - I guess I'm going too far for most readers when it comes to right side value references.

- If you view it as C++ memory management, people in other languages lose interest.
    - on "close it when you open it" type restrictions.
    - Turn off the lights when you turn them on."
        - But if people are still using it, don't turn it off."


[https://doc.rust-jp.rs/book-ja/ch04-00-understanding-ownership.html](https://doc.rust-jp.rs/book-ja/ch04-00-understanding-ownership.html)
> Understanding Ownership
> Ownership is the most unique feature of Rust, because it allows us to do safety assurance without a garbage collector. Therefore, it is important to understand how ownership works in Rust. In addition to ownership, this chapter will discuss several other related features: borrowing, slicing, and how the compiler places data in memory.

(Memo: delete superfluous scopes later)
rust

```
fn main() {
    {
        let x = 1;
        let y = x;
        println!("x: {}", x);
        println!("y: {}", y);
    }
}
```

output

```
x: 1
y: 1
```

rust

```
fn main() {
    {
        let x = String::from("hello");
        let y = x;
        println!("x: {}", x);  // NG
        println!("y: {}", y);
    }
}
```

error

```
error[E0382]: borrow of moved value: `x`
 --> src/main.rs:5:27
  |
3 |         let x = String::from("hello");
  |             - move occurs because `x` has type `String`, which does not implement the `Copy` trait
4 |         let y = x;
  |                 - value moved here
5 |         println!("x: {}", x);
  |                           ^ value borrowed here after move
  |
  = note: this error originates in the macro `$crate::format_args_nl` which comes from the expansion of the macro `println` (in Nightly builds, run with -Z macro-backtrace for more info)
help: consider cloning the value if the performance cost is acceptable
  |
4 |         let y = x.clone();
  |                  ++++++++
```


C++.
cpp

```cpp
#include <iostream>
#include <string> 

int main () {
    std::string x("abc");
    std::string y;
    y = x;  // (*) copy
    std::cout << x << std::endl;  // OK
    std::cout << y << std::endl;
}
```


cpp

```cpp
#include <iostream>
#include <string> 
#include <memory> 

int main () {
    std::unique_ptr<std::string> x = std::make_unique<std::string>(std::string("abc"));
    std::unique_ptr<std::string> y;
    std::cout << *x << std::endl;
}
```

`no member named 'make_unique' in namespace 'std'`
`make_unique is an upcoming C++14 feature `
- effect
    - `$ clang++ -std=c++14 t.cpp && ./a.out`

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




> If you have heard the terms "shallow copy" and "deep copy" while working with other languages, the concept of copying pointers, length, and allowances without copying data may seem like a shallow copy. However, since the compiler also invalidates the first variable, it is known as a move instead of a shallow copy.
> Rust will never automatically "deep copy" data.

You need to be aware of whether the value is on the stack or the heap.
- Not too difficult for those who know what they're doing.
- So for those who weren't aware of it before, there's something new to be aware of.

rust

```
fn main() {
    {
        let x = String::from("hello");
        foo(x);
        println!("x: {}", x);  // NG
    }
}
fn foo(x: String){
    println!("x: {}", x);
}
```

error

```
error[E0382]: borrow of moved value: `x`
 --> src/main.rs:5:27
  |
3 |         let x = String::from("hello");
  |             - move occurs because `x` has type `String`, which does not implement the `Copy` trait
4 |         foo(x);
  |             - value moved here
5 |         println!("x: {}", x);  // NG
  |                           ^ value borrowed here after move
  |
note: consider changing this parameter type in function `foo` to borrow instead if owning the value isn't necessary
 --> src/main.rs:8:11
  |
8 | fn foo(x: String){
  |    ---    ^^^^^^ this parameter takes ownership of the value
  |    |
  |    in this function
  = note: this error originates in the macro `$crate::format_args_nl` which comes from the expansion of the macro `println` (in Nightly builds, run with -Z macro-backtrace for more info)
help: consider cloning the value if the performance cost is acceptable
  |
4 |         foo(x.clone());
  |              ++++++++
```


> It would be a bit of a hassle if I had to take ownership and then return that ownership to every function. How should I make a function use the value but not take ownership of it?

rust

```
fn main() {
    {
        let x = String::from("hello");
        foo(&x);
        println!("x: {}", x);  // OK
    }
}
fn foo(x: &String){
    println!("x: {}", x);
}
```


You can create a reference that refers to a value in >s1, but you do not own it. Not owning it means that the value it points to will not be dropped when the reference leaves scope.

`cannot borrow `s` as mutable more than once at a time`
> This is a wall for new Rustaceans. This is a barrier for new Rustaceans, because in many languages you can change it whenever you want... The advantage of having this constraint is that the compiler can prevent data races at compile time. A data race is analogous to a race condition and occurs when these three behaviors occur:.
>  Two or more pointers access the same data simultaneously.
>  At least one pointer is writing to data.
>  No mechanism is used to synchronize access to data.
>  Data races cause undefined behavior and are difficult to identify and resolve when trying to track them down at runtime. However, Rust does not even compile the code that causes data races, so it prevents this problem from occurring.

`cannot borrow `s` as mutable because it is also borrowed as immutable`

rust

```
fn main() {
    {
        foo();
    }
}
fn foo() -> &String{
    let x = String::from("hello");
    &x
}
```

error

```
error[E0106]: missing lifetime specifier
 --> src/main.rs:6:13
  |
6 | fn foo() -> &String{
  |             ^ expected named lifetime parameter
  |
  = help: this function's return type contains a borrowed value, but there is no value for it to be borrowed from
help: consider using the `'static` lifetime
  |
6 | fn foo() -> &'static String{
  |              +++++++
```


---
This page is auto-translated from [/nishio/Rust](https://scrapbox.io/nishio/Rust) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.