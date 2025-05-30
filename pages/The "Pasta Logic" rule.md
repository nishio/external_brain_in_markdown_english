---
title: 'The "Pasta Logic" rule'
---

- [[The "Spaghetti Code" rule]] was significantly changed as a result of the [[20190930 Rule Amendment]].

---- full text
Number of players 2 / Play time

What's in it
- 16 command cards
- 10 flag chips x 2 colors: The colors of the flag chips correspond 1:1 to the players.
- 1 cursor (arrow frame)
- Increment chip 2 pcs.
- Decrement chip 2 pcs.
- Life counter (dice) 2 pcs.

Game Objectives
- Create a program for each other, rewrite it while executing it, and render the other's program inoperable.
- way of defeating
    - Reduces the opponent's life to 0 or less (equivalent to running out of energy)
    - Set the flag of the opponent's color to 0 (equivalent to the program being deleted).

rule explanation

■Outline
- The "Pasta Logic" game consists of three phases: "Command Preparation Phase," "Flag Placement Phase," and "Program Execution Phase.
- In the "Command Preparation Phase," command cards are lined up on the field to determine the initial state of the game by determining the first and second moves.
- During the "flag placement phase," each player places a flag chip on a command card. This represents program making.
- In the "program execution phase," commands are executed according to the state of the flags as the cursor is moved. This phase continues until the game ends.

- ■■ Command preparation phase
    - Shuffle 3 BASIC cards and 5 randomly selected cards
    - Lay the cards face down on the card table and place a cursor chip on the first card placed.
    - Deal 5 flag chips to each player.
    - The initial value of the life counter is 5.
    - Decide on the first and second moves.

- ■■Flag placement phase
    - The first player chooses one command card and places his flag chip on it.
    - Next, the back hand chooses one command card and places a flag chip on it.
    - Repeat this process to place all the flag chips you have on hand on the command card.
    - Placing a flag chip on a card is called "flagging".
    - Do not place more than two flags of your own on the same command during the flag placement phase.
    - Flags are arranged in columns in the order they are placed on the command card.
        - This means that "the flag set first has a higher priority.
    - The commands you flag will have a significant impact on the outcome of the game, but if this is your first time playing the game, you may not know where to flag commands to gain an advantage. In that case, it is a good idea to place the flags appropriately and proceed to the program execution phase to experience how the program is executed.

- ■■ Program execution phase
    - If the command card the cursor is pointing to is flagged, the player with the first flag has the right to choose whether or not to execute the command. It is also possible to choose not to execute the command.
    - After the command has been issued, if there are other flags in the row, the player with the next flag is given the right to execute it.
    - Repeat this until the end of the row, and when all flags on the card have been processed, move the cursor to the next command card.
    - If the command card the cursor is pointing to is not flagged, the cursor moves to the next command card.
    - When the cursor finishes with the last command card, it returns to the first command card again. This is repeated until the game is over.

- The "no more than one flag per command card" restriction only applies to the initial placement of flags.
    - There is no problem to have multiple flags on one command card by executing AddFlag or MoveFlag commands.

- ■Exit Game
    - You win by removing all of your opponent's flag chips or reducing your opponent's life to 0 or less.


List of command cards
- flag system
    - AddFlag: BASIC: Add a flag to the end of any {1} piece of command other than this command.
    - MoveFlag: BASIC: Move {1} flags other than this command to the end of another command
    - RemoveFlag: Remove {1} flags from one command other than this command.
    - Reorder: arbitrarily reorder the flags of {1} other than this command
    - Rotate: move the trailing flag of all commands except this card to the beginning
    - FastPass: Reduce life by {1} and add a flag to the beginning of {1} commands other than this command.

- life-system
    - Bug: BASIC: Reduce opponent's life by {1}.
    - ForkBomb: Reduce opponent's life by {2}. Remove activation flag.
    - Debug: Remove the activation flag and increase your life by {3}.
    - TradeOff: Reduce your life by {1} and your opponent's life by {2}.

- card-oriented
    - RemoveCommand: Remove any command from the game by its standing flags. RemoveStartingFlag
    - Reverse: Reduce your life by {1} and reverse the cursor's direction.
    - SwapCommand: Swap this command with any command. The flags on the command and the cursor move together.
    - ■ Subroutine: One of the {1} commands before or after this command, other than this one, is selected and the cursor is temporarily moved.

- parameter system
    - Increment: Increase any parameter by {1}.
    - Decrement: Decrement any parameter by {1}.

Supplemental explanation of command cards

- Increment and Decrement can affect the strength of other commands (numbers enclosed in curly brackets, parameters).
    - Parameters cannot be set negative in Decrement.
    - The fact that an Increment/Decrement is hanging on a parameter is expressed by placing an Increment/Decrement chip on the command card.
    - When an Incremented parameter is Decremented, the first Increment chip is removed instead of placing both chips. The reverse is also true.
    - The Increment/Decrement chip is removed when the cursor leaves the card.


History and Acknowledgements
The inspiration for the game's "flags over commands" came from Tom Jolly's Programmer's Nightmare (2000). Since this game was hard to obtain, Nishio cloned it, and through test play and discussion with Nakayama Tokoroten, made changes to eliminate the randomness in the execution phase (2009). (Acknowledgements for this project are given here.)
---
This page is auto-translated from [/nishio/「パスタロジック」ルール](https://scrapbox.io/nishio/「パスタロジック」ルール) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.