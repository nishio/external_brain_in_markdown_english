---
title: "prime factor three"
---

![image](https://gyazo.com/f8fc916a62dfd0b10c6278774c52f865/thumb/1000)
![image](https://gyazo.com/aac9cc6742493f26a54b02e877b82c86/thumb/1000)
![image](https://gyazo.com/80f8a06e8e7fa3e7585e9bb59c395be0/thumb/1000)

log
> [nishio](https://twitter.com/nishio/status/1404460190951346179): Zanzan (movie)
- ![image](https://gyazo.com/f0ce28295bfe56faa8bfa63a5014e5a6/thumb/1000)
- > [nishio](https://twitter.com/nishio/status/1404462089637298186): The title is "Zanzan" but the original purpose of this is that there is no calculation nordon for the remainder. The remainder calculation itself is a "subtract as much as you can" mechanism. The interesting point is to use multiplication to store a specific value in the counter in one frame, and to do the store in the next frame after the reset with a one frame delay "from NOT+0".
- > [nishio](https://twitter.com/nishio/status/1404463611737559040): If you put NOT and "when changed from 0" on a signal line where 1 comes in only one frame, you have a signal line with a one frame delay. If you reset the counter with the former and multiply the latter by the signal line with a large value flowing and put it in the counter addition, you can store that large value in the counter.
- Postscript, other patterns appear below.

> [nishio](https://twitter.com/nishio/status/1404472472703934466): I've come up with a topic for the Hajime Pro competition, but it's probably a D problem out of the blue.
- > [nishio](https://twitter.com/nishio/status/1404476048566226948): "Find all prime numbers with three or fewer digits. Seek all means that a single number display block should show all prime numbers for at least one frame and no non-prime numbers."
- > Three digits raises the bar because we can't use nodons that are proportional to the definitional range.
- > [nishio](https://twitter.com/nishio/status/1404477102439550976): If it were "less than two digits", it would be possible to line up 100 Nordons in a row and Eratosthenes would be able to do it, making the problem easier.
- >  The only problem is that with everything under 3 digits, it seems that with a little effort, you won't be able to fit it into the 30 seconds that can be recorded on the Switch.

> [nishio](https://twitter.com/nishio/status/1404602812193931264): I was able to create a circuit that only displays when the input is an odd prime number, but I realized that I had to loosen the regulation "Do not display non-prime numbers" to "Do not display non-prime numbers and 0s". Otherwise, I realized that the difficulty would increase in a place unrelated to the prime number calculation.

> [nishio](https://twitter.com/nishio/status/1404610795988676608): Sosu (movie)
- > [nishio](https://twitter.com/nishio/status/1404611202714537985): can only give prime numbers above 11 (premature optimization is the root of all evil)

> [nishio](https://twitter.com/nishio/status/1404669347751100417): Hizelofiruta (movie)
- > [nishio](https://twitter.com/nishio/status/1404669812249268224): photo

> [nishio](https://twitter.com/nishio/status/1404672485207932928): Sosu 2 (movie)
- > [nishio](https://twitter.com/nishio/status/1404672705362685952): just barely got to 100 in 30 seconds (I'm starting at 11).

> [nishio](https://twitter.com/nishio/status/1404683377660227588): i saw your tweet about no variables, but you have a counter, you hit the reset of the counter with a 1 frame pulse T1, and you have a 1 frame delay T If you multiply T2 and X by the increment of the counter, you can save the value of X. I'll make a sample later.

> [nishio](https://twitter.com/nishio/status/1404734949094133762): note that there is a 1 frame delay between the input and output of the counter (NOT, for example), so there may be a way to make it work.
- > [uchan_nos](https://twitter.com/uchan_nos/status/1404735313193226252): if there is a delay, is it possible to shift the numbers in sequence like a shift register?
- > [nishio](https://twitter.com/nishio/status/1404739962940006400): you can do something close to that, but you need to be creative because there is no set of values, only addition and subtraction.
- > [nishio](https://twitter.com/nishio/status/1404742526385332225): so far so good. (MOVIE)
- > [nishio](https://twitter.com/nishio/status/1404743122815311879): should I just do b+=a-b...(strange world where the time cost of subtraction is 0)
- > [nishio](https://twitter.com/nishio/status/1404745482509815809): Ringu Baffa (movie)
    - > [nishio](https://twitter.com/nishio/status/1404745785036754948): done! > I'll shift the numbers in order like a shift register.
- > [nishio](https://twitter.com/nishio/status/1404747029687930881): if we take advantage of the zero subtraction cost, this circuit that uses two frames for "reset and add" can be done in one frame > [nishio](https://twitter.com/nishio/status/1404669347751100417): Hizelofiruta

> [nishio](https://twitter.com/nishio/status/1404747673807122438): ah, this is smart. I should just subtract my own output:.
- > [OffGao6502](https://twitter.com/OffGao6502/status/1404746483686002692): for those who lament the lack of "variables", if it helps.
- > You can create a mechanism to assign a value at any timing with 3 nods: "counter", "keisan (x)", and 0.00/1.00 binary signal. [https://twitter.com/i/status/1404746483686002692](https://twitter.com/i/status/1404746483686002692)
- > [OffGao6502](https://twitter.com/OffGao6502/status/1404748070504386562): sorry, I have to block the input as well, so 4 node.
- > 1.00 the moment the signal came in.
- >  ・Decrease" the value of the counter by the value of the counter
- >  (Reset)
- >  ・"Increase" the value of the counter by the value you want to assign.
- >  (Real substitution)
- >  simultaneously to achieve variable assignment.
- > [nishio](https://twitter.com/nishio/status/1404763552599089162): Ringu Baffa 2 (movie)
    - > [nishio](https://twitter.com/nishio/status/1404764122965708805): I tried to realize the ring buffer without using the minus, but that didn't turn out too pretty because it requires multiplication and clock line connection instead! Nah...

> [nishio](https://twitter.com/nishio/status/1404782935627026433): Sosu 3 (movie)
- > [nishio](https://twitter.com/nishio/status/1404783113427832839): didn't fit in 30 seconds? Let's reshoot the first half.
- > [nishio](https://twitter.com/nishio/status/1404784359698173955): Prime Numbers 3, first half (movie)
- > [nishio](https://twitter.com/nishio/status/1404785440515788807): doubled the clock frequency to get it down to 30 seconds! (movie)

---
This page is auto-translated from [/nishio/そすう3](https://scrapbox.io/nishio/そすう3) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.