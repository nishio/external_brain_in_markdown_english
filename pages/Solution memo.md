---
title: "Solution memo"
---

- There are 100 prisoners.
- He wears a white or black hat.


- consider from the outset
    - Think about the first one
        - The first one has to answer whether his hat is black or white without getting any clues.
        - No algorithm can guarantee him a correct answer.
    - That means that the remaining 99 must all answer correctly.
        - consider from the outset
            - The second person can tell the color of their hat by listening to the first person's statement and looking at the 98 hats in front of them.
            - How can this be achieved?
                - For example, if the first person answers the color of the second person's hat, we can make it happen.
                    - So what happens to the third person this way?
                        - The third person is to answer the color of his/her own hat with "the first person taught the second person the color of his/her hat, and the second person answered the color that was taught to him/her".
                            - I can't guarantee the correct answer because there are no hints.
                        - consideration
                            - The third person said, "The first and second person are just saying the same thing!"
                            - The first needs to give information not only for the second, but also for the third.
                            - The second person needs to answer the color of the hat he/she understands in order to answer correctly.
            - How can we make this happen? take2
                - For example.
                    - The first is said to be black when the second and third hats are the same color, and white when they are different colors.
                    - The second is (the color of the first said, the color of the third hat)
                        - (black, black), then answer black.
                        - (black, white), answer white.
                        - (white, black), answer "white".
                        - (white, white), then answer black.
                    - Now you can make it right.
                    - The third knows that the second statement is correct (the first said color, the second said color) because
                        - (black, black), then answer black.
                        - (black, white), answer white.
                        - (white, black), answer "white".
                        - (white, white), then answer black.
                    - Now you can make it right.
                - The algorithm could certainly save two people when there were three!
            - So how can we turn this into an algorithm that saves 99 out of 100 people?
                - Let's think outside the box.
                    - Think of ways to save 3 out of 4 people.
                        - >  The first person needs to be given information not only for the second person but also for the third person.
                        - We need to give them the fourth person's information as well.
                        - So the first answer needs to change depending on whether the fourth person is black or white.
                            - This one earlier was of the same nature.
                                - > The first is black when the second and third hats are the same color, and white when they are different colors.


It's an easier question to ask than "how many people can we save max?" And.
The question of "is it possible to save 99 people?" and "is it possible to save 99 people, but how would you do it?" are two dissimilar questions.
The reason is that the former requires information on whether or not it is possible, while the latter is a question of how to realize it given that information.


---
This page is auto-translated from [/nishio/解法メモ](https://scrapbox.io/nishio/解法メモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.