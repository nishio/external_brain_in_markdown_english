---
title: "simple irreducible fraction"
---

> [potetoichiro](https://twitter.com/potetoichiro/status/1383404029397508108): about the end of the world
- ![image](https://gyazo.com/11d10ff87e903baa96b7c276ede6e35c/thumb/1000)
There was some talk about how they came up with the idea, so I'm going to write an explanation.
- Let N be the number of digits in a.
- $\frac{10a+b}{10^Nc+a} =\frac{b}{c}$ so pay the denominator [$ (10a+b)c=(10^Nc+a)b
- Sorting for a, $bc(10^N-1)+a(b-10c) = 0$
    - For simplicity, we write $d+ae = 0$.
- Divide by a prime p large enough so that the equality holds even if the remainder is taken as an arbitrary number.
    - $d+ae\equiv 0 \pmod{P}$
- In this case, a is $a \equiv -de^{-1} \pmod{P}$.
    - $e^{-1} \equiv e^{P-2} \pmod{P}$ in [[Fermat's minor theorem]]
- Therefore, if $b,c,N$ is determined, $a$ is determined
- Check that it is obtained correctly (most of the time N does not match the length of a obtained).
- If you have multiple P's, you can also use [[Chinese remainder theorem]] to get a large a

Tweet Summary
> [nishio](https://twitter.com/nishio/status/1383426860114014210): I was wondering how you came up with the equation (10a+b)/(c×10^len(a)+a)=b/c, so (10a+b)c=(c×10^len(a)+a)b. len(a)+a)b, and since they are all integers, the equality holds even if you take the remainder with an arbitrary number, so the following is an abbreviation (It's too hard to draw formulas on a smartphone.
> [nishio](https://twitter.com/nishio/status/1383431158592012311): if b,c are prime to each other, then we know that a is a multiple of bc like this, the rest is the last equation, but since a and bc are not prime, what happens to the inverse element And...
- ![image](https://gyazo.com/cca80e7ace0ea2b3aeaff657165a6978/thumb/1000)
> [nishio](https://twitter.com/nishio/status/1383433767411347456): make sure the above equality holds for the original large fraction while I work out the rest!
- 712158808933002481389578163771 mod 7 * 41
    - ![image](https://gyazo.com/d8c779d5ec929797f9cb17a8bb7969bd/thumb/1000)

> [nishio](https://twitter.com/nishio/status/1383437077706985475): I wonder if there are any other conditions.
> [nishio](https://twitter.com/nishio/status/1383439224137912339): white flag once I lost track

-----

> [nishio](https://twitter.com/nishio/status/1383463045976903681): 12_307692 / 307692_3 = 4
> 41_302211 / 302211_3 = 41 / 3
> 57_301587 / 301587_3 = 19
> 71_301272984441 / 301272984441_3 = 71/3

> [nishio](https://twitter.com/nishio/status/1383466772611796995): Well [[Chinese remainder theorem]] (CRT)! I thought of that, and after I sorted out the equation for a, I took two prime numbers about 10^9 and made a CRT, but as it turns out, there were solutions smaller than 10^9, so it's not really a CRT, but a [[Fermat's minor theorem]] where you can find the inverse if you get a large enough prime number. That's right.
- ![image](https://gyazo.com/98dd3480a3bf250b63cdfb1fc04fe99a/thumb/1000)

> [nishio](https://twitter.com/nishio/status/1383467641721921541): I'm getting ready to remove these obvious ones and put up a list!
> 5050505050505050_5 / 50_5050505050505050 = 1/10

> [nishio](https://twitter.com/nishio/status/1383468653354520582): you have 297 except for the 10x ones with a range of 1 digit for b and max 2 digits for c. It took 0.2 seconds for this enumeration.
> [https://gist.github.com/nishio/488da0129efec7f9940bd4a521fb91b7](https://gist.github.com/nishio/488da0129efec7f9940bd4a521fb91b7)

> [nishio](https://twitter.com/nishio/status/1383470519895216128): oh, I forgot to mention that I set the number of digits in a to 2-17. As you can see from the output, if you don't limit the number of digits, there are innumerable.

source code: [https://gist.github.com/nishio/0a281988f2a9ddb37259e8a23fcf3316](https://gist.github.com/nishio/0a281988f2a9ddb37259e8a23fcf3316)

relevance
> [dorako220](https://twitter.com/dorako220/status/1383427993838649345): you can make it pretty easy using [[Repunit Number]]'s list of prime factorizations pic.twitter.com/EDWhnmmx 1l

- [[Programmatic search]]

---
This page is auto-translated from [/nishio/簡単約分](https://scrapbox.io/nishio/簡単約分) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.