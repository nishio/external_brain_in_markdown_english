---
title: "Cave inside and outside unknown"
---

I first learned about it at [Summer Puzzle Competition 2020](https://jppuzzles.com/summerpuzzle2020/).
Similar [[slither link (popular Japanese number puzzle)]] is my favorite [[puzzle]].
We do it by thinking about how to solve it.

![image](https://gyazo.com/164de17f6821012a87c2d8ed26c39d69/thumb/1000)
1 is surrounded by walls except around the perimeter
Lines must be connected.
thus it follows that ...
- Notation: Absence of a line is represented by a crossing line
- ![image](https://gyazo.com/0fdc81b44244e7f56ae088f5e6253fbd/thumb/1000)

If you look at the perimeter of the 7, there are places where you say, "If there were a wall here, we wouldn't be able to accomplish the 7."
- ![image](https://gyazo.com/2eb23a2d84bcae9cbb7ae70b7c2fa277/thumb/1000)

Look around 4.
- 4 can't be accomplished with just right and bottom, so there's no wall on the top or left.
- Even if there were no walls on either side, that alone would make it 4.
- Therefore, to the right and below is a wall
- Only one of the walls is either up or left.
    - Notation: 1 on a corner means that one of the sides flanking it is a wall.
    - When one corner is 1, the opposite corner is also 1
- ![image](https://gyazo.com/12c99ace7e1797fda1ece2e053942a56/thumb/1000)

Note the 3 below.
- If the right side is empty, that alone makes 3, so the top and left must be closed.
- So the upper right corner is 1
- The lower left corner of the opposite 4 is also 1, so the left side is vacant.
- The top is the wall.
- The edge line extends 4 squares.
- ![image](https://gyazo.com/db58fca4183877c6fc8155ccc8648bc0/thumb/1000)

Notation: Paint the outside of the enclosure in blue and the inside in yellow
- When I use a single-color pen, I distinguish the diagonal lines by their orientation, but this time I decided to add color as well.
    - The color scheme is based on the image of the sea and islands
- Squares between walls are different colors, adjacent squares without walls are the same color.
- The wall to the left of 7 is determined to be empty.
- ![image](https://gyazo.com/6e22d8bfeb1c361cbf5b146f99df1765/thumb/1000)

If the right side of 2 is vacant, it will be 3, so this is the wall.
- 2 must extend one square to the left or down, so the lower left corner is 1
A's wall is now in place and B's vacancy is confirmed.
- I didn't realize it until it was too late.
![image](https://gyazo.com/82981e1f943bb3ae9645c3a4db646c48/thumb/1000)

Suppose the left side of 2 is empty.
- Left is blue
- The upper left corner will be blue because yellow should not be a flyover (the circle will no longer be one).
- There are no walls between squares of the same color, so they would be two to three squares in a row.
- Not this one.
- ![image](https://gyazo.com/2fcc01239dab228e825e324788f67e29/thumb/1000)
- Therefore, the left of 2 is a wall
- ![image](https://gyazo.com/989c2c4d33a9b1d058d7ee44baefa302/thumb/1000)

If 3 above is blue, yellow is the flyover, therefore 3 is yellow
If the upper left corner is blue,
- The lower left corner must be yellow for 7 to be 7
- The bottom row is yellow because yellow is not a flyover.
- The bottom 3 becomes 5, no.
Therefore, the upper left corner is yellow and the lower left corner is blue
If the bottom 3 are blue, it will be 4, which is confirmed to be yellow.
![image](https://gyazo.com/cd0a78d27e319d06d56af6e182a8312d/thumb/1000)

consideration
- Slitherlink is a major solution that puts information on the edges
    - I like [[put information on the corner]] too, but I haven't seen many people use it.
        - I think we need a way to express, "We haven't narrowed it down to the presence or absence of a wall, but we do have the information."
    - The other known theorem is "For any given cut of the grid, there are an even number of lines crossing it.
- In the case of this problem, the "absence of a wall" extends horizontally and vertically with clues
    - It's hard to utilize this information when you're focused on the wheel.
    - At the end of the day, he used the "blue or yellow" decision more than I expected.
        - The "yellow is not a flyover" rule comes in handy.
    - I was mistaken in looking similar to Slitherlink, but this puzzle would probably be easier to use as information if it were painted inside and out.

Okay, now we're going to solve the main story, but there's no 1, no square larger than one side of the map, so there's no starting point.
Think about it as you create new theorems.
- The opposite side of a corner with "2 or 1" (hereafter 21) is "0 or 1" (hereafter 01), and vice versa.
- The corner of square 2 is 21
    - 0, because it's over 2.
    - So, the face to face is 01.
- If the corner with 3 is 01, the diagonal is 21
    - Because if an angle is zero, then the diagonal must be two.
- ![image](https://gyazo.com/609f9ceace327f5a5eeac02e53a33fca/thumb/1000)
- What more can we do without the ghetto?
- I proceeded to do two choice Guesses in the upper right corner at 2. It's pretty deep...

The 2 in the upper left corner has a wall on either side, left or bottom.
- Assumption 1: There is a wall below.
    - If there is a wall in A, there is no wall because 3 is more than 4.
    - If there's no wall in B, there's a wall because 2 is more than 3.
    - The right side of 2 is definitely empty, so a wall is placed around it (green line below).
    - The circle does not close, so it becomes more and more definite, and 3 becomes 4 or more NG.
    - ![image](https://gyazo.com/520a6bbb33f2b28cb432cd6ec00995ba/thumb/1000)

- Therefore, there is no wall below.
    - Supplementary, the unattainability of 3 was confirmed when the wall was built around 2, but it was too late to notice. It might be good to have a notation to make it easier to notice.

Wall to the left of A.
- Theorem When a line touches the corner of a square in square 2, there is a line on the edge across the opposite corner.
    - When the lines touch, that corner is 1
    - So either wall will open.
    - NG if any other wall opens, since that alone would be more than 2.
- Wall on A makes 3 unattainable.
- Wall at B makes 3 unattainable.
- Ensure that the loop does not close.
- The upper right corner of 7 is 20
    - If 0, then the diagonal must be 2, but the contradiction
- therefore
    - Thanks to the diagonal propagation of the corner labels, the decision was quickly and easily made.
- ![image](https://gyazo.com/5afef077cdff084ba0eb24f7f84c88b2/thumb/1000)

broaden one's horizons
- If the corner of 7 is 1, it is determined to be 0 because it involves a smaller clue and is unattainable.
- The possibility of 1 disappears from the opposite corner of 3, so it is confirmed to be 2.
    - I thought the diagonals would also be fixed at zero, but I was wrong.
- There is a definite absence of a wall on the side of 6 to prevent the square of 7 from involving 2 and making it unattainable.
- If the lower left corner of 2 is 1, then the upper right corner is 2, since either 2 or 3 is unattainable
- The diagonal is fixed at 1 and the lower right corner of 3 is also 1
- So 3 can be stretched horizontally or vertically.
- If it were to grow horizontally, the walls would become more and more defined to achieve 7 and 2, and the walls would become a circle.
    - ![image](https://gyazo.com/c89f286ca2a905941b8a646b715b6197/thumb/1000)
- Therefore, 3 extends vertically.
- ![image](https://gyazo.com/6eae57fa455c33bab468c3fd2fb1b3ec/thumb/1000)
- The bottom two are.
    - If a line touches a corner, the diagonal is 2
    - Extending to the left makes 3.
- extending upwards because of
- ![image](https://gyazo.com/34e5c2b0329491884d44178a283f63f2/thumb/1000)

paint
- ![image](https://gyazo.com/af21a06d070a33279ef9e1e7828017f2/thumb/1000)
- Note the 4 on the upper side.
    - When blue, either vertical 4 or 112. 112 means 2 is NG, so vertical 4, yellow stops.
    - When yellow, if you try to pull out yellow, the bottom 4 stops as a horizontal 4.
- Therefore, no yellow can be drawn from this side, and the yellows on the right side must be connected.

Note the right side.
- ![image](https://gyazo.com/eb5b85250de022db8265e2cc74da60c8/thumb/1000)

- The problem is to paint these 6 squares in such a way that they satisfy the constraints of 4 while connecting the yellows.
- If the top 4 are blue
    - It is not a horizontal 4 because it is interrupted,
    - If it is 2 horizontally, the bottom 4 will be 5 vertically, so it is not a good idea,
    - With a vertical 4, the bottom 4 can only be 3.
- Therefore, the top 4 are confirmed yellow.
- If the bottom 4 are blue
    - If horizontal 4, it is NG because it is interrupted.
    - If 31, the top 4 are determined to be vertical 4 and interrupted, so NG
- Therefore, the bottom 4 are confirmed yellow.
- The square above it is confirmed blue.
- The bottom 4 are fixed to 31 horizontally, so the top 4 are fixed to 4 vertically.
- ![image](https://gyazo.com/2255fd37f7338f0ceccc9a6aae2ad4b1/thumb/1000)

- 4 is confirmed blue.
    - I overlooked this when I drew the diagram above.
    - If the way the numbers come in is fixed, one dead end is the opposite color."
    - Vertical 4 is determined by the condition that yellow must not be interrupted.
- The 6 turns yellow and is determined to be a vertical 6.
    - 2 does not lead right.
- The bottom of the 6 turns blue.
    - If the way the numbers come in is fixed, one dead end is the opposite color."
- If 4 is yellow, then that blue is in the way and won't fit in, so 4 is decided to be blue
- ![image](https://gyazo.com/07df3146a116a0dc1b0ffbb8008f9f53/thumb/1000)
- 4 is another square blue.
- 2 is blue and is determined below.
    - The two lower ones are decidedly yellow.
    - 5 must be yellow to fit, confirmed to be horizontal 5, but not yet determined if it will fit to the corners.

![image](https://gyazo.com/623c5dcb04df9468e03ac9512ae84b23/thumb/1000)
- It's time to use 10.
- If 10 is blue, then everything is blue except for one square on the lower side; no matter which way 5 goes in, the yellow is broken here.
- Therefore, 10 is yellow.
- If 10 right is blue, then 10 is not feasible, hence yellow
- Similarly, the left and bottom of 10 are yellow
- If 3 is blue, then right is yellow, not enough vertical, so left is definitively blue.
- If 3 is yellow, the blue enclave must not be created, so yellow above it too, but 3 becomes 4, NG
- Therefore, 3 is blue.
- The left of the 3 is decided to be blue, which determines how the 10 comes in.
![image](https://gyazo.com/b41a01aff4769cd233980ad14ddcef0e/thumb/1000)

4 is blue or yellow.
- ![image](https://gyazo.com/7fb28ae28ac233eb465fef9181507a70/thumb/1000)
- If yellow.
    - Right is blue
    - 3 confirmed vertically, blue on the left
    - 4 confirmed vertically
- If it's blue.
    - If you try your best to keep the yellow uninterrupted, the 2 on the left are unattainable.
- Therefore, yellow.

If 2 is blue, then 6 is horizontal and 2 is yellow because yellow is interrupted
- ![image](https://gyazo.com/40a96fa68fde08d488370f03963907e7/thumb/1000)
- This is NG.

The 2 on the lower side is broken by blue and yellow.
It is not possible to connect yellow through the center 2.
Therefore, yellow must pass through 6.
![image](https://gyazo.com/83143f4b0f2d0f1622177460096b5c03/thumb/1000)
The fact that 6 is now yellow creates a wall between it and the blue on the right and determines that there is no wall to the left of 2, which determines how to enter.
If there is a wall to the left of the 6, the vertical 6 interferes with the yellow above and is not feasible, hence no wall.
![image](https://gyazo.com/2b75b3b0324b1e3e2eee28c5520ae2a2/thumb/1000)

Continue when you are not sleepy.

---
This page is auto-translated from [/nishio/内外不明のCave](https://scrapbox.io/nishio/内外不明のCave) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.