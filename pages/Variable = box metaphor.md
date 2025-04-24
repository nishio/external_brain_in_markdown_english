---
title: "Variable = box metaphor"
---

> The Nishio Family Today
>  "You often compare the concept of [[variable]] in programming to a box, don't you?"
>  Wife: "Yes."
>  I said, "But with that analogy, if you assign the contents of box a to box b, wouldn't it be natural that box a would be empty at that point?"
>  Wife: "I put the whole box in there."
>  I "I see!"
[Facebook](https://www.facebook.com/nishiohirokazu/posts/10216859350412588)

To reproduce the natural behavior in [[C++]], such as "If the contents of box a are assigned to box b, box a will be empty at that point," use [[move semantics]]. [[unique_ptr]] provides exactly that functionality.
[https://wandbox.org/permlink/1Uk7XaISQatJniNt](https://wandbox.org/permlink/1Uk7XaISQatJniNt)
cpp

```cpp
#include <iostream>

struct hoge {
};

int main(){
  std::unique_ptr<hoge> a;
  std::cout << a << std::endl; // a is empty                                                                                               
  a.reset(new hoge());
  std::cout << a << std::endl; // a is not empty                                                                                           
  std::unique_ptr<hoge> b;
  std::cout << b << std::endl; // b is empty                                                                                               
  b = std::move(a);
  // b = a; won't work.
  // error: object of type ... cannot be assigned because its copy assignment operator is implicitly deleted
  // note: copy assignment operator is implicitly deleted because ... has a user-declared move constructor
  std::cout << a << std::endl; // a is empty                                                                                               
  std::cout << b << std::endl; // b is not empty                                                                                           
}
```


- [[even if]]

---
This page is auto-translated from [/nishio/変数=箱のたとえ](https://scrapbox.io/nishio/変数=箱のたとえ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.