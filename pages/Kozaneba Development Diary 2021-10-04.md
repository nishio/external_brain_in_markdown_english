---
title: "Kozaneba Development Diary 2021-10-04"
---

prev  [[Kozaneba Development Diary 2021-10-01]]
![image](https://gyazo.com/112315562acdd784a4fb2715e28089f3/thumb/1000)


-----
Used to explore other people's writing, useful
- Arrows are very useful
    - No longer limited to "relationships expressed through proximity."

- I want regular or double lines, not just arrows.
    - It's neither transitional nor confrontational.
    - A case in which there was originally a kozane called A, and then a group was formed to explain the contents of A in detail.
    - The most intuitive way to connect them is with equals.
    - The functionality provided now would give the group the title A.
    - ![image](https://gyazo.com/72b05907e6c63bfc2c1030b979e489ed/thumb/1000)
        - The statement "this and that are the same" is forcing a proximity representation at stage 3.
        - Close it because it's too bulky when left open.
        - But if you close it, you have to open it to see it.
        - If they're not in close proximity, but connected by a line, they can be placed apart.

- When an arrow is drawn against a group, the ends are wrong.
    - In some cases, they're far apart, in other cases, they're wedged in.
    - Bounding box for groups?
    - If you write an arrow on a child element and then close it?

- The additional arrow UI is still a little difficult to work with at times.
    - Do we need an arrow mode only for drawing one arrow?

- Ability to inherit the maximum size when the group is closed
    - As I mentioned before, still necessary.

- It could be made smaller than the normal size.
    - When I was using it for personal use, I deleted anything that wasn't important when I created Kozane in the first place.
    - In correcting other people's writing, I left out particles, conjunctions, etc.
    - Then I had to enlarge everything else because those are 1x size.
- sentence in both ways.
    - ![image](https://gyazo.com/efa0595dc7e8d9185c4ed23ea1670805/thumb/1000)
        - [Twitter](https://twitter.com/nishio/status/1444699350085423106)
            - I noticed something interesting when I used Kozaneba to correct other people's writing.
            - When I personally make a kozane, I make it as shown on the left, even if the input is the same sentence. However, when I was correcting other people's sentences, I unconsciously made them the way I did on the right.
    - ![image](https://gyazo.com/a647b14f4a9e0ad3387657471dc5bd5e/thumb/1000)
        - From the right state in the previous figure, we can expand important function words without changing particles, etc., and pick up only the expanded kozane as a result, resulting in the left state in the previous figure.
    - ![image](https://gyazo.com/0becd01a242df92dc5f1f838448bdc28/thumb/1000)
        - When I work alone, the left shape is created from the beginning, and then the spatial arrangement is started from there. This may seem like skipping a line to the rest of the world.
        - I had been holding off on a prototype algorithm that would produce a kozane like the one on the left when a sentence is entered, because it was not completed to my satisfaction, but in fact, it may be more satisfactory for users to simply chop it into words and produce a kozane like the one on the right.
        - Unlike when I created that, now I can group even multiple words into one lump.

Funny when closing a group containing arrows
- Binomial would be OK, NaN when there are more than that.
- Fixed.

`@firebase/firestore: Firestore (8.8.0): You are overriding the original host. If you did not intend to override your settings, use {merge: true}.`
- Fixed.

![image](https://gyazo.com/ede48304d187644ad953ec443438106d/thumb/1000)
???
The "group position" was the center of gravity, not the center, so if the contents were skewed, the endpoints of the arrows would change, but the width would be half of the total width.
- Fixed.

---

- Ability to inherit the maximum size when the group is closed
- Ordinary line
- double line

- ![image](https://gyazo.com/90a6ed3be3687f6434f564f88742658c/thumb/1000)
    - Hmmm... it's going to happen.
- ![image](https://gyazo.com/4d463f6028898c9760c14429eed4e87f/thumb/1000)
    - Shorten it a bit, but not at all.
- ![image](https://gyazo.com/eb2de04e8499f8f7e80ebf4dad96eb9b/thumb/1000)
    - If you work hard at math, you can get good at intersections, but don't work hard and try to fool them.
- ![image](https://gyazo.com/a74551e2fd66e7f65ba493e78caf8f3d/thumb/1000)
    - hmm
        - ![image](https://gyazo.com/6aed61e2e21465e5b5f16b402b0b25f0/thumb/1000)

I worked hard on my math.
- ![image](https://gyazo.com/112315562acdd784a4fb2715e28089f3/thumb/1000)
- Conclusion: ${1\over\sin\theta} + {1\over\tan\theta}$

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-10-04](https://scrapbox.io/nishio/Kozaneba開発日記2021-10-04) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.