# Five in a Row

## Story

Do you remember Tic-tac-toe from the beginning of your programming career?
Its big brother is here: Five-in-a-row or [Gomoku](https://en.wikipedia.org/wiki/Gomoku).
Now this is not a children's game; this is a serious sport with championships
(where Eastern European countries actually shine) and a field of cutting edge AI
research. It is a matter of national pride to create the best machine players
for AI competitions and human training. Your country needs ☛you☚!

## What are you going to learn?

- Break down the game logic into parts and reassemble them into a solid game workflow.
- Deal with the board as 2D arrays.
- Write parametrized methods (flexible board size and win condition).
- Move around the board programmatically in any directions.
- Handle edge cases (and literally the edge of the board).
- Think about a simple AI algorithm.

## Tasks

1. Implement the `Game` constructor to initialize empty `n`-by-`m` board, that is, an array filled with zeros. The inner arrays are rows.
    - An array of integer arrays (representing an array of rows) is created as the board, and stored as a private member of the `Game` instance.
    - Every cell of the board is initialized with `0`.
    - Getter `getBoard()` and setter `setBoard()` are connected to the stored board.
    - The rows of the board are independent (that is, changing one row does not affect the others).

2. Implement `getMove()` that asks for user input and returns the coordinates of a valid move on board.
    - Coordinates are specified as a letter and a number, for example, `A2` is the first row of the second column, and `C1` is the third row of the first column.
    - The function returns an array of integers containing the row and column number corresponding to the input.
    - The returned coordinates start from 0.
    - The integers indicate a valid (empty) position on the board.
    - If the user provides coordinates that are outside of board, keep asking.
    - If the user provides coordinates for a place that is taken, keep asking.
    - If the user provides input that does not follow the format of coordinates, keep asking.

3. Implement `mark()` that writes the value of `player` (a `1` or `2`) into the `row` & `col` element of the board.
    - If the cell at `row` and `col` is empty, it is marked with `player`.
    - It does not do anything if the coordinates are out of bounds.
    - It does not do anything if the cell is already marked.

4. Implement `hasWon()` that returns `true` if `player` (of value `1` or `2`) has `howMany` marks in a row on the board.
    - If `player` has `howMany` marks in a row on the board, `true` is returned.
    - If `player` does not have `howMany` marks in a row on the board, `false` is returned.

5. Implement `isFull()` that returns `true` if the board is full.
    - If there are no empty fields on the board, `true` is returned.
    - If there are empty fields on the board, `false` is returned.

6. Implement `printBoard()` that prints the board to the screen.
    - Players 1 and 2 are indicated with `X` and `O`, and empty fields are indicated with dots (`.`).
    - There are coordinates displayed around the board.
    - A 3-by-8 board is displayed in the following format.
```
   1  2  3  4  5  6  7  8
A  .  .  .  .  .  .  .  .
B  .  .  .  .  .  .  .  .
C  .  .  .  .  .  .  .  .
```

7. Implement `printResult()` that displays the result of the game.
    - If player 1 wins, print "X won!"
    - If player 2 wins, print "O won!"
    - If nobody wins, print "It's a tie!"

8. Use the implemented methods to write a `play()` method that runs a whole two-player game. Parameter `howMany` sets the win condition of the game.
    - Player 1 starts the game.
    - Players alternate their moves (1, 2, 1, 2...).
    - The game uses `howMany` to set the win condition.
    - The board is displayed before each move and also at the end of game.
    - The game ends when someone wins or if the board is full.
    - The game handles bad input (wrong coordinates) without crashing.

9. Allow players to quit the game anytime by typing `quit`.
    - When the player types `quit` instead of coordinates, the program exits.

10. [OPTIONAL] Implement player-against-AI mode.
    - The game is fully playable against the computer, and the AI can play any of the players. This means that when `enableAi()` is set for a player number, it calls `getAiMove()` instead of `getMove()` for that player.
    - Method `getAiMove()` returns a valid move (if possible) without asking for any input.
    - Method `getAiMove()` returns `null` if the board is full.
    - Gameplay is easy to follow, as there is a one second delay before each AI move, implemented in method `play()`.

11. [OPTIONAL] The AI is capable of recognizing the easiest opportunities to win the game in one move.
    - Method `getAiMove()` picks the winning move if there is one on the board.

12. [OPTIONAL] The AI is capable of recognizing if its enemy could win the game with the next move, and (supposing there is no direct winning move) moves against it.
    - Method `getAiMove()` (when there is no winning move in one step) picks a move which prevents a certain winning move for its enemy.
    - When there is a direct winning move, function `getAiMove()` still picks that.
    - When there are multiple one-step winning options for the enemy, `getAiMove()` tries to prevent one of them.

13. [OPTIONAL] The AI tries to look ahead more than one move. Be aware that a serious AI follows more complicated strategies.
    - If there are no direct winning or losing options, the AI picks an option that potentially creates a direct winning option for the next round.
    - As an addition to the above, if possible, the AI picks an option that potentially creates _more than one_ direct winning options for the next round (thus ensuring victory).
    - When none of the above options are possible, the AI picks a cell neighboring an already marked cell.

## General requirements

None

## Hints

- Try to come up with a general "pattern matching" feature that checks for
  sequences, such as `X X X .` or `. X X .` in any directions. Such an ability is
  most likely needed for an AI.
- Focus on the most basic aspects of AI for this game. Contrary to the introduction
  story, creating a really good AI is way above the scope of this project.
- Search the internet for strategy descriptions if you wish; you don't have to
  come up with an AI strategy by yourself. But, for your own good, do not use
  external code. Implement written instructions instead.

## Background materials

- <i class="far fa-exclamation"></i> [Arrays](project/curriculum/materials/competencies/java-basics/java-arrays.md.html)
- [Exceptions in Java](https://www.dummies.com/programming/java/what-you-need-to-know-about-exceptions-in-java/)

