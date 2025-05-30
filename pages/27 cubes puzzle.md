---
title: "27 cubes puzzle"
---

Physics [[puzzle]].
![image](https://gyazo.com/ea26a368afa7c5c19df7448006231a57/thumb/1000)
- Made of wood with holes and a rubber strap through the holes.
- It is not difficult if you read it calmly because there are only four branches at most and most of them are two or less.
- The manufacturer is Flidolin, but I believe there are others out there.

- 3-3-3-3 - 2-2-2 - 3-3 - 2-2 - 3-2-3-2 - 2-3

- The first two 3's don't lose their generality if they are X, Y
- There are two ways to get the next 3, X and Z.
    - If X, the next 3 will collide with Y, so Z is fixed.
    - ![image](https://gyazo.com/9881ecfbbc71f6f59372be099edc1107/thumb/1000)
    - The next 2 can be either X or Y, and there are two ways to do each of those as well.
        - When Z in Y
            - If you go to the center in the next 2, the next 3 will not fit, so run to the outer perimeter and fix to 3,3
            - ![image](https://gyazo.com/acfb275e85656ab52f5a04b8c1e5e0c0/thumb/1000)
            - But the end of the blank space in the 1F section would be 2.
            - This does not allow for the final 3 to be included in the NG.
        - When X in Y
            - NG because the next 3 will not be in either direction, no matter which way you turn the next 2.
        - Therefore, the next is fixed to X. If the next is Y, the "end of 2" recurs in the 2F part and is NG, so the next is fixed to Z.
    - Thus X-Z, the next 2 can only fit in the X direction, and there is only one way for 3-3 to fit in the space
        - ![image](https://gyazo.com/8f48cf84d3891883487ea1a2aadcaf3a/thumb/1000)
    - If the next 2 is Y, another "terminal is 2" occurs on 1F, so Z is the only way to go (the picture is already Z).
    - If the next 2 is X, then the next 3 cannot go in, so Y is the only possible choice, and then the next 3-2-3 can only be Z-X-Z.
        - This is an important point. For those who think logically, they can smoothly go through it, saying, "This is the only way it can be," but for those who just physically move the blocks around without thinking, it is difficult to proceed due to the physical difficulty of "inserting the blocks into the U-shape.
    - Once you get past this step, the rest is easy.
        - ![image](https://gyazo.com/733ba66303d6b727ded16d16408bbc43/thumb/1000)
        - The remaining 2-2-3 can only be Y-X-Y. Termination.
- If the third 3 is Z, the next 3 can be either X or Y (X-Y-Z)
    - Well, I don't want to delay this confirmation, so I've already explored the case where the third 3 is X and got the answer first, but just in case it's luck which one you choose, let's assume you chose this one and read on.
    - For X, the next 2 could be Z and Y (X-Y-Z-X)
        - In the case of Z, if the next 2 is Y, the "end is 2", so X is fixed.
            - Then the next 2 comes to the center with one choice, and the next 3 does not enter, ng.
        - If Y, then the next 2 is X or Z
            - In the case of X
                - If the next 2 is a Z, then "come to the center and 3 won't fit."
                - Even Y does not enter because it hits the first 3, NG
            - therefore Z
            - In this case, there are three options for the next 2, but the next 3 can only go in the Y minus direction
            - Then the next 3 is also determined, but the next 3 does not enter, NG
            - ![image](https://gyazo.com/c4455fb4f707ab77471ab4473ecfe18c/thumb/1000)
        - Therefore, X-Y-Z-X is NG
    - If X-Y-Z-Y, then the next 2 is X or Z
        - In the case of Z, if the next 2 is Y, "it comes to the center and 3 does not fit", so X
            - If the next 2 is Y, "it comes to the center and 3 does not fit", so Z
            - 3-3 is determined to be Y-Z.
            - ![image](https://gyazo.com/6ed0718ac6c548442af4ccc535b67d0e/thumb/1000)
            - When the next 2 is Y, the next 2 after that is Z, which "comes to the center and 3 does not fit", so X
                - However, if 3 is inserted, the two squares connected to the center of the space are separated by a fixed number, so NG
        - For X,
            - (No matter how you place the 3-2-3, it's NG because of the spatial separation that occurs, but well, I'll explain without leaps and bounds.)
            - If the next 2 is Y, there will be two ends, so it is NG.
            - If Z, then the following 3-2-3 putting is fixed in one way, but the result
            - ![image](https://gyazo.com/0ac5628ff9eccf5d18cf3d209fa19b3a/thumb/1000)
            - NG because it separates the remaining blocks from the space to be filled.
        - Therefore, X-Y-Z-Y is also NG
    - Therefore, X-Y-Z is NG.

It is not a very large search space if you divide it into cases and think about them in order. If you move around randomly, you may end up going round and round with no solution, or you may be lucky and start in a small space with a solution.

---
This page is auto-translated from [/nishio/27立方体パズル](https://scrapbox.io/nishio/27立方体パズル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.