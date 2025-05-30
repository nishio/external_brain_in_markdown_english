---
title: 'The "Spaghetti Code" rule'
---

Spaghetti Code" rules (2 to 5 players / 10 minutes play time)
- (The gameplay is very different, so you may want to focus on two players. The playing time depends on the amount of long thinking. A chess timer is a good idea.)

What's in it
- 10 command cards (+ 5 extended command cards + 3 blank cards)
- 10 flag chips x 5 colors: The colors of the flag chips correspond one-to-one with the players.
- Cursor 1 pc.
- Increment chip 5 pcs.
- Decrement chip 5 pcs.
- Life counter 5 pcs x 5 colors

Game Objectives
- Defeat all players except yourself.
- way of defeating
    - Reduce the opponent's life to 0 or less.
    - Zero flags of the opponent's color.

rule explanation
- The rules of "Spaghetti Code" are difficult to understand in their entirety at once, so it is recommended that you start with level 1 for two players, and only after you are familiar with the game should you attempt level 2 and level 3 rules.

■Outline
- The "Spaghetti Code" game consists of three phases: the command preparation phase, the flag placement phase, and the program execution phase.
- In the "Command Preparation Phase," command cards are lined up on the field to determine the initial state of the game by determining the first and second moves.
- During the "flag placement phase," each player places a flag chip on a command card. This represents the program.
- In the "program execution phase," commands are executed according to the state of the flags as the cursor is moved. This phase continues until the game ends.

- Level 1
![image](https://gyazo.com/37a0e980e0eb8e750d11b3a6bc309534/thumb/1000)

- ■What to use
    - At level 1, only flags and commands that affect the player's life can be used.
    - Select 5 cards marked Level 1 AddFlag, MoveFlag, RemoveFlag, Bug, and ForkBomb from the command cards.
    - It also uses 1 cursor chip, 10 flag chips of each color, and 5 life counters of each color.

Level 1 Command Cards: 5
AddFlag: Add a flag to the end of any command card except this command card.
MoveFlag: Move any {1} flag to the end of another command card.
RemoveFlag: Remove any {1} flags from the game
Bug: Reduce {1} life of any {1} player
ForkBomb: Reduce any one player's life by {2} and remove the flag that triggered this command from the game

- ■Command preparation phase
    - Shuffle the five command cards, place them face down on the desk, and place a cursor chip on the first card placed.
    - Each player is dealt 5 life counters and 4 flag chips.
    - The remaining 6 flag chips of each color that have not been distributed are placed in the "Unused Flag Chip Placement".
    - Decide on the first and second moves.
        - Since the first player has the advantage at level 1, the unfamiliar player is placed first.
        - If equal, decide by rock-paper-scissors-scissors, or the last person to lose moves first.
        - For a more rigorous method of deciding, see "Fair First Move Decision Algorithm" in the Appendix.

- ■Flag placement phase
    - The first player chooses a command card and places his flag chip on it. Next, the player chooses a command card and places a flag chip on it. This is repeated until all four flags are placed on the command card. Placing a flag chip is called "flagging".
    - During the flag placement phase, no more than two of your flags may be placed on the same command card.
        - If this is possible, it is because if the first card is a Bug, ForkBomb, or RemoveFlag, the first player can win by continuing to place on that card.
    - Flags are arranged in columns in the order they are placed on the command card.
        - This means that "the flag set first has a higher priority.
    - The commands you flag have a significant impact on the outcome of the game, but when playing for the first time, you may not know where to flag the commands to gain an advantage. In that case, it is a good idea to place the flags appropriately and proceed to the program execution phase to experience the program through once.

- ■ Program execution phase
    - If the command card the cursor is pointing to is not flagged, the cursor moves to the next command card.
    - If flagged, the player with the first flag has the right to execute the command. It is also possible to choose not to execute the command.
    - After the command has been issued, if there are other flags in the row, the player with the next flag is given the right to execute it.
    - Repeat this until the end of the row, and when all flags have been processed, the cursor moves to the next command card.
    - When the cursor finishes with the last command card, it returns to the first command card again. This is repeated until the game is over.

- The "no more than one flag per command card" restriction only applies to the initial placement of flags.
    - There is no problem to have multiple flags on one command card by executing AddFlag or MoveFlag commands.
- Flags removed by RemoveFlag are removed from the game. They will not revert to "unused flag chips". If you have used up all 6 unused flag chips, you cannot add flags with AddFlag (Add Flag).

- ■Exit Game
    - You win by removing all flag chips of all players except yourself or reducing the life of all players except yourself to 0 or less.

- Level 2
    - ■What to use
        - Level 2 command cards MoveCommand, RemoveCommand, and Reverse are added to the Level 1 tools. On level 2 islands, you can use commands that have effects on the direction the cursor moves or on the command itself.

Level 2 command cards: 3
■ MoveCommand: move {1} command card x to any position in the program.
- Flag standing at x moves with x
RemoveCommand: Remove any command card x from the game by its standing flags.
- If the cursor points to x, the cursor moves to the next command.
Reverse: Reverses the direction in which the cursor licks the command card.

- ■Flag placement phase
    - Place 5 flags, one more than on Level 1. The remaining 5 flags are placed in the "Unused Flag Chip Placement Area".
- ■ Program execution phase
    - RemoveCommand, added at level 2, is a very powerful card that removes command cards by their flags. The seemingly poor Reverse and MoveCommand also create powerful combos when combined with other cards.

    - Example
    - `(AddFlag A)(MoveCommand A)(ForkBomb A)`
    - In this state, the following winning combo is generated: "AddFlag adds a flag to FormBomb, MoveCommand moves MoveCommand with the cursor in front of AddFlag, AddFlag again adds a flag to FormBomb, and FormBomb is executed 3 times for 6 damage to the opponent. This is a combo to determine victory. In other words, Player B must place a flag on MoveCommand (or AddFlag and then MoveCommand when triggered) during the flag placement phase in order not to lose.
    - In the flag placement phase, you take turns placing flags while "conceiving and implementing a program that will help you win" and "understanding the intent of the program your opponent is writing and interfering with it". This is the core concept of the game.

    - ■Exit Game
        - In level 2, in addition to the winning strategy in level 1, there is another possible strategy in which the RemoveCommand removes the last enemy flag; if the RemoveCommand removes all enemy flags, the player with the first flag wins.

Level 3
- ■What to use
    - Add level 3 command cards Increment, Decrement and Increment/Decrement chip to level 2 tools. Level 3 commands can affect the strength (parameters) of other commands.
Level 3 Command Cards: 2
    - Increment: Increase any parameter (number enclosed in curly brackets) by {1}.
    - Decrement: Decrement {1} of any parameter (number enclosed in curly brackets).
        - However, the value cannot be negative.

■Flag placement phase
- Place 6 flags, one more than on Level 2.
■ Program execution phase
- The Increment and Decrement commands allow you to select any command and change its parameters (the numbers in square brackets). For example, Incrementing "Remove any {1} flags from the game" in RemoveFlag will increase the number by 1 and change it to "Remove any {2} flags from the game. On the other hand, Decrementing "Remove any {0} flags from the game" will change it to "Remove any {0} flags from the game," a command (NOP) that has no effect.
- The effect of Decrement cannot make the value negative. If a command has multiple parameters, choose one of them to change.
- The fact that an Increment/Decrement is hanging on a parameter is expressed by placing an Increment/Decrement chip on the command card.
- When an Incremented parameter is Decremented, the first Increment chip is removed instead of placing both chips. The reverse is also true.
- It is rare, but if you have used up your 5 increment/decrement chips each, you cannot increment/decrement any more.

Stalemate Resolution Algorithm
In rare cases, a situation occurs in which the situation does not change at all when both players choose the action they want to take, like a thousand-day move in Shogi. Once the board situation occurs, it occurs again, and the game ends as soon as one of the players declares "this is a stalemate". At this time,
- The one with more lives wins.
- In case of life tie, the player with more flag chips on the command card wins.
- In case of a tie, the one with more "flags at the head of the queue" wins.
- If there is a tie, the player with the first flag on the card with the current cursor wins.
will be. You are free to declare or not. The board status includes the number of unused chips.

Level 1 Command Cards: 5
AddFlag: Add a flag to the end of any command card except this command card.
MoveFlag: Move any {1} flag to the end of another command card.
RemoveFlag: Remove any {1} flags from the game
Bug: Reduce {1} life of any {1} player
ForkBomb: Reduce any one player's life by {2} and remove the flag that triggered this command from the game

Level 2 command cards: 3
■ MoveCommand: move {1} command card x to any position in the program.
- Flag standing at x moves with x
RemoveCommand: Remove any command card x from the game by its standing flags.
- If the cursor points to x, the cursor moves to the next command.
Reverse: Reverses the direction in which the cursor licks the command card.

Level 3 Command Cards: 2
Increment: Increase any parameter (number enclosed in curly brackets) by {1}.
Decrement: Decrement {1} of any parameter (number enclosed in curly brackets).
- However, the value cannot be negative.

Extra: 2 extra cards (+3 Blank cards)
ReversePriority: Reverse the priority of flags standing on all command cards except this command card.
Memory: Execute the command that the cursor was pointing to immediately before and after this command card.
- You can only choose to activate both or not activate both.
Blank: Here you can write new commands and change this game!

Instant: Immediate Command Cards: 3
■ MoveCommand: move {1} command card x to any position in the program.
- Flag standing at x moves with x
MoveFlag: Move any {1} flag to the end of another command card.
Bug: Reduce {1} life of any {1} player

Strategy Tip.
- ■There are commands for which it is advantageous to flag first, and commands for which it is not. For example, MoveCommand and Reverse favor the later, since the latter can cancel the former's operation by performing the reverse operation later. On the other hand, RemoveFlag and MoveFlag favor the earlier flag because the earlier flag can remove or move the later flag.
- ■If the rules allow only one flag of each color per command in the flag placement phase, it is advantageous not to immediately place a flag on a command card that was flagged first by the enemy. This is because each move in the flag placement phase narrows the opponent's options, but does not deprive him of the option to place a flag on that command.
- A card disabled by Decrement (NOP) is a very convenient place to move a flag, such as MoveFlag. However, there is a possibility that the card may be Incremented.
- You will want to flag many of your own flags on Incremented cards, but they may be removed all together by RemoveCommand.
- FormBomb first reduces the opponent's life, then flags are removed. The last flag may cost you your life, and you may win the game just in time.
- ■ At level 1, RemoveFlag removes 1 of the opponent's 4 flags and also reduces the opponent's number of moves, so as a percentage of damage it is over 25%. Bug, which reduces 1 of your opponent's 5 life, is weak because it does 20% damage, and ForkBomb, which reduces 1 of your flags and 2 of your opponent's life, is even weaker at 40% - 25%. However, this strength-weakness relationship is affected when flags are added by AddFlag cards or when the number of flags increases with level.
- The rule that the target flag of RemoveFlag is removed from the game prevents a loop in which one player increases flags with AddFlag and another player decreases flags with RemoveFlag from becoming an infinite loop. The loop will eventually run out of unused flags that can be added with AddFlag. The loop is not considered a stalemate due to the "board status includes the number of unused chips" clause in the "Stalemate Resolution Algorithm".
- Reverse only changes the order in which the cursor licks commands, but does not change the fact that the first flag in a command is executed first. The reversal of the order is introduced by the extra card ReversePriority. However, no major problems have been found with the Reverse rule that also reverses the order of flag execution, so it can be played as a variant rule if agreed upon by players in advance.
- If all flags are removed by RemoveCommand, the player with the first flag wins. It is important that this rule is clearly defined in advance, and the decision as to whether the first or the last player wins can be made either way. So it can be changed and played.

Tips for teaching people the rules
- Let's do it gradually from level 1.
- The first move has the advantage, so let's give the opponent the first move.
- If your opponent is having trouble figuring out what to do in the flag placement phase, place them alternately, starting with the first island.
- You start at a disadvantage, and you may feel tempted to think long and hard to turn the tables. However, if you do that, your opponent will have to wait a long time and lose, which is no fun at all. Prioritize raising your opponent in the game over winning now.

extension rule
- For those who are used to the Level 3 rules and find them insufficient, there are extended rules.

Introduction of Extension Rule::ReversePriority
- Use the ReversePriority extra card. This command reverses the flag order of other commands.
- Under the rule without ReversePriority, if there were multiple flags for the same command, all were given permission to execute in turn. When the ReversePriority card is inserted, this rule is changed. Each time the cursor is visited, only the first flag is given permission to execute. The first flag is moved to the end of the column if the command is executed. If the command is not executed, it remains at the top.
- This rule increases the value of the "do not execute command" option. This is because it has the effect of taking away the chance of activation from the flag behind the row.
- Also, the cursor moves faster, making it easier to create combos.

Introduction of Extension Rule::Memory
- Use the extra card Memory. The cursor remembers the commands of the immediately preceding and previous visited command cards, and the Memory command allows you to recall and invoke them.
- At this time, it behaves as if Memory's card had the default description of the immediately preceding and previously visited command card. It does not matter if it is Increment/Decremented in play or if the opponent's bits are on the island. Also, you can only choose whether to invoke both commands or none of them. The two previous commands are executed first, followed by the immediately preceding command.

Extended Rules::Introduction of Immediate Command Cards
- The rules of "Spaghetti Code" are like Shogi or Go, with no hidden information and no element of luck. For those who don't like it, the instant command card expansion introduces hidden information and an element of luck. This expansion increases the unpredictability of the opponent's actions.
- It is used to add an immediate command card to level 3 tools.
- After the command cards are lined up and before placing the flag, the immediate command cards are shuffled face down by the first player, the second player chooses one card, and the first player chooses one card. The one card not chosen remains face down until the end of the game. This adds unobservable information to the game and increases the difficulty of guessing the program's intent.
- During the program execution phase, when your flag executes a command, you can execute the command on the immediate command card instead of the command card on which the flag was placed. The immediate command card is removed from the game when executed.
- Immediate command cards can be kept face down until they are used. It is usually preferable to keep it face down to avoid giving information to the opponent. However, "Immediate Command Cards" are included in "Optional Command Cards".

Extended Rules::Multiplayer Interrupt
- Theoretically, the game can be played by any number of players as long as they have different colored flag frames. However, because of the strong interaction between players in this game, it is possible for one person to drop out early due to concentrated attacks.
- The eliminated players are bored with nothing to do until the end of the game. Therefore, we came up with an extension rule called "Interrupt".
- The dropout gets one bit each time the cursor returns to the first command card. At any given time, you can shout "Interrupt" to generate an interrupt and add a flag to the end of any island. (This additional rule has not been tested and played much. It may make the game harder to converge and play longer.)

Extension Rule::Sequential Open
- This is a variant rule that changes the way the Flag Placement Phase is played. When all cards are open in the flag placement phase, players tend to think long and hard. Therefore, the flag placement phase can be lightened by limiting the information given during the decision making phase, so that the weight is placed on trying to do something during the program execution phase.
- First, the command cards are lined up face down.
- First, the first card is opened and the first player decides whether to place the flag or pass. Then the second player decides whether to place the flag or pass. If both players pass, the next island is opened, since one cannot place more than one flag of one's own on an island.
    - First move, second move, first move pass, second move pass" ●○ Next island, ● is the first move
    - First move, second move pass, first move pass" ● Next island, ○ is the first move
    - First pass, second place, first pass, second place" ○ Next island, ● is first
    - First pass, second place, first place, second place, first pass, first place" ○● Next island, ○ is the first move
    - First move passes, second move passes, and the next island is the first.
- The rest will be played normally.

Appendix: Fair First Move Decision Algorithm for Two-Player
- For those who wish to remove the element of luck to the extreme, this section explains how to make a fair first move.
- First, one player A deals cards. The cards may be arranged in any order, or shuffled and arranged in any order.
- If shuffled, player A can look at the cards dealt and then redeal them if he thinks "this lineup favors the first or second player.
- Player B, the player not dealt the cards, can then choose whether to play first or second. Player B can choose whichever side he thinks has the advantage, and Player A can choose whichever side he thinks has the disadvantage, so there should be no complaints.

History and Acknowledgements
The inspiration for the game's "flags over commands" came from Tom Jolly's Programmer's Nightmare (2000). Since this game was hard to obtain, Nishio cloned it, and through test play and discussion with Nakayama Tokoroten, made changes to eliminate the randomness in the execution phase (2009). This is called the Simplified version of Programmer's Nightmare. I then created a fantasy-style version of "Battle of the Spaghetti Monsters," and after a long period of inactivity, I published the rulebook on the Internet in 2017. This "Spaghetti Code" was re-imported in 2019 in a programming-style flavor.

Card Image
[https://www.dropbox.com/s/sjek3kq9hj1gb1n/spagetti.pdf?dl=0](https://www.dropbox.com/s/sjek3kq9hj1gb1n/spagetti.pdf?dl=0)

Rulebook (abridged version)
[https://docs.google.com/document/d/1fzJHFD_aUUwC4biHQLKbZ5Wb5Fks4IDbG24dABXh-dQ/edit?usp=sharing](https://docs.google.com/document/d/1fzJHFD_aUUwC4biHQLKbZ5Wb5Fks4IDbG24dABXh-dQ/edit?usp=sharing)

---
This page is auto-translated from [/nishio/「スパゲッティコード」ルール](https://scrapbox.io/nishio/「スパゲッティコード」ルール) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.