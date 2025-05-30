---
title: "AGC022B"
---

![image](https://gyazo.com/13f3d39471baeb131d387b0805df3eab/thumb/1000)
[https://atcoder.jp/contests/agc022/tasks/agc022_b](https://atcoder.jp/contests/agc022/tasks/agc022_b)
Thoughts.
- 1: all gcd's are 1
- 2: One and the other sum, gcd is not 1
- 3: Element is less than 30000
- Hmmm, I can't image it, but from condition 2, 1 can't be a factor.
- If there is a 2, then one or more odd numbers exist. And any addition other than 2 is even.
- It is easy to show that there is no size 2 solution
- Consider the time of 3
    - If there are two, the other two are odd.
    - If there are 3, the rest is 3n+1
    - Odd, 3n+1, and a multiple of 5
        - 25.
    - Therefore, 2, 3, and 25 are solutions
- Think of a time when 4.
    - One even number in the remaining three.
    - If there are 3, then the sum of the remaining two is 3n+1
    - If there is a 5, then the remaining one is 5m.
    - Hmmm, that's going to be a lot of splitting up.
- 2+3+25=30=2x3x5.
    - 2 x 3 x 5 x 7 = 210 well distributed...how?
- You're thinking too hard about the constraints.
    - The condition that all gcd's are 1 holds for 2 x 3, 3 x 5, and 5 x 2
    - But in this instance, condition 2 is impossible.
- If condition 1 is not present
    - Easy, just make them all even numbers or something.
    - Put two odd numbers to satisfy condition 1.
        - Condition 2 holds for all but odd numbers.
    - For condition 2 to hold for this odd number?
        - Odd prime numbers, both sides must have something in common
        - Let a, b be two odd numbers and c be the sum of even numbers
        - Need common divisor for a+c and b, b+c and a
            - No, because if these two terms match, condition 1 is broken.
            - What if a=3n, b=5m?
            - I think I can find it with no problem, but I'd like to code it and check.
            - c cannot be a multiple of 3 or 5, but it can be an even number, so just adjust as appropriate
            - If c's remainder at 3 or 5 is determined, so are a's and b's.
                - [[Chinese remainder theorem]] guarantees that the number of conditions will be met by 30.

- Official Explanation
    - I overlooked the severity of the restrictions.
        - If you're choosing 2,000 pieces with less than 3,000 elements, you can't take the "mostly even" option.
    - I assumed that the sum is a multiple of 2, which led me to a method that consists of numbers up to about 4000.
        - The official explanation method is to assume that this is "the sum is a multiple of 2 and 3".
    - If the sum is a multiple of 2 and 3, and the components are multiples of 2 or 3, then "2: One and the sum of the others, gcd not 1" is satisfied
    - If 2 and 3 are in the components, then "1: all gcd's are 1" is also satisfied.

---
This page is auto-translated from [/nishio/AGC022B](https://scrapbox.io/nishio/AGC022B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.