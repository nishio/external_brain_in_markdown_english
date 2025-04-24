---
title: "Herumi BLS grant"
---

[https://blog.ethereum.org/2019/11/08/eth2-quick-update-no-3](https://blog.ethereum.org/2019/11/08/eth2-quick-update-no-3)
> Herumi BLS grant
>  We've given out a grant to Shigeo Mitsunari, the maintainer of the super-fast Herumi pairing library and BLS signature library. This grant is to bring the libraries up to spec with the new BLS standard (new hash-to-G2, constant-time signing, etc) as well as to help accomplish some more practical items for eth2 usability (Rust integration, fuzzing work, etc).
>  In addition to the feature component of the grant, there is also a performance component. The Herumi library is already 2-3x faster than the next best BLS option, but because signature verification is one of the main bottlenecks in eth2, any additional gains here would be excellent, enabling eth2 to run under even higher load and in more adverse scenarios. Shigeo will spend some additional time and effort further optimizing the library to ensure it runs as fast as possible 🚀.
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
### Explanation (for beginners)
- In [[Ethereum 2.0]], the verification of "[[BLS signatures]]" (a type of [[digital signature]]) produced by a large number of validators is very important. The ability to verify these signatures in large numbers and quickly has a significant impact on the overall performance of the network.

### What is the Herumi library?
- This is a library by [[Shiseo Mitsunari]] ([[Shigeo Mitsunari]]), a developer, that can process [[BLS signatures]] at high speed.
- It is estimated to be two to three times faster than other BLS implementations.
- The [[Ethereum Foundation]] has provided a grant to enable this library to meet new BLS standards (new algorithm specifications and security enhancements).
- We also help with tasks to improve usability and safety, such as integration into Rust and fuzzing tests (a method of bug detection).

In other words, ### Herumi's fast BLS implementation is essential for Ethereum 2.0 to efficiently handle large amounts of signature verification
, and performance and security enhancements are being made through support for developers.


[[eth2]]
- [[Shiseo Mitsunari]]  / [[herumi]]

---
This page is auto-translated from [/nishio/Herumi BLS grant](https://scrapbox.io/nishio/Herumi BLS grant) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.