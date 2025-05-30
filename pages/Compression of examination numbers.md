---
title: "Compression of examination numbers"
---

Q: What is
- Out of 1,000 candidates, 100 will be selected and those selected will be announced. Assume that the only characters available for publication are 0-9 and a space character. What method requires the fewest number of characters?

Current Champion
- 135 characters: Integer in full minimum hash and then in 11th decimal notation
    - The combination of choosing 100 out of 1000 is a mere 6.4e+139
    - So, if all patterns are numbered in dictionary order, they can be represented by a single 140-digit decimal number
    - If you display this in eleven decimal places, it shrinks even more.
        - log(6.4e+139) / log(11) == 134.24924331280693

loser
- 300 characters:
    - The examination number should be 0-999, and any number less than three digits should be padded with blanks.
    - Examination numbers are fixed-length, eliminating the need for a delimiter, and can be expressed with only three characters per person.

- 302 characters → 301 characters:.
    - Passed or not, consider an array of 1000 0/1's to be a 1000-digit binary number.
    - This is expressed in decimal notation
    - log(2) * 1000 / log(10) == 301.02999566398114 so just short of 301 digits
        - If you throw out one bit of the person with exam number 0, you can easily tell whether that person passed or failed based on the difference in the number of bits that are still standing.
            - log(2) * 999 / log(10) == 300.7289656683172
            - This will cut down on one character.
            - This is reduced with a bit of "exactly 100 standing bits" information
            - I used the above complete minimum hash in earnest.

- 302 characters
    - Distribute and place 2^n exam numbers and post the sum [src](https://twitter.com/n_a_s_o_a_n/status/1105617118966378496)
    - The expression is different, but in essence, it is the same as 1000-digit binary number, so it comes down to the above.

- Around 340 characters
    - Post the composite number of the examination number as a prime number.
        - ![image](https://gyazo.com/528322fc5433c8ed4a2df3c316f4160a/thumb/1000)

- Around 390 characters
    - Post examination numbers with blank separators only.
    - Short numbers, such as exam number 1, can be displayed in a small space.

- Less than 400 characters
    - Use blank padding for the examination number and also use blanks for the delimiter.
    - So-called normal form of acceptance announcement

- Less than 500 characters
    - Cases where one more digit is needed because the examination number was set to 1-1000 instead of 0-999.
---
This page is auto-translated from [/nishio/受験番号の圧縮](https://scrapbox.io/nishio/受験番号の圧縮) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.